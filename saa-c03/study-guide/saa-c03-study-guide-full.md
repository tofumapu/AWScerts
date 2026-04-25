# AWS Certified Solutions Architect – Associate (SAA-C03)

## Từ Khoá

| Từ khoá                               | Phản xạ đúng                                |
| ------------------------------------- | ------------------------------------------- |
| `least operational overhead`          | Managed service, native feature, serverless |
| `most cost-effective`                 | Rẻ nhất + giữ đủ constraint                 |
| `on-premises`                         | VPN / DX / Storage Gateway / DataSync / DMS |
| `highly available`                    | Multi-AZ / ASG / Route 53 failover          |
| `low latency global HTTP/HTTPS`       | CloudFront                                  |
| `low latency global TCP/UDP`          | Global Accelerator + NLB                    |
| `strict ordering / deduplication`     | SQS FIFO                                    |
| `fanout / broadcast`                  | SNS                                         |
| `private access S3/DynamoDB`          | Gateway VPC Endpoint                        |
| `rotate credentials / DB password`    | Secrets Manager                             |
| `WORM / legal hold / compliance mode` | S3 Object Lock Compliance Mode              |
| `PII in S3`                           | Macie                                       |
| `threat detection / compromise`       | GuardDuty                                   |
| `web attack / SQLi / XSS`             | WAF                                         |
| `DDoS`                                | Shield                                      |
| `audit API calls`                     | CloudTrail                                  |
| `config compliance / drift`           | AWS Config                                  |
| `multi-account governance`            | Organizations + SCP                         |
| `no SSH / no bastion / no open port`  | SSM Session Manager                         |
| `single pane glass security`          | Security Hub                                |

## Phân Bổ Domain Chính Thức

| Domain | % | Trọng tâm |
|---|---|---|
| Domain 1 – Secure Architectures | 30% | IAM, encryption, network security, compliance |
| Domain 2 – Resilient Architectures | 26% | HA, DR, decoupling, backup |
| Domain 3 – High-Performing Architectures | 24% | Storage, compute, DB, caching, analytics |
| Domain 4 – Cost-Optimized Architectures | 20% | Pricing models, tiering, right-sizing |

---

# DOMAIN 1 — Design Secure Architectures (30%)

## 1.1 IAM — Identity & Access Management

### Nguyên Tắc Cốt Lõi

- **Không bao giờ hardcode credentials** vào code, AMI, container image, file.
- **IAM Role** = đáp án đúng cho mọi workload AWS cần gọi service khác.
- **Least privilege** là lý do nhiều đáp án sai dù "cũng chạy được".

### Mapping: Actor → Solution

| Actor | Solution |
|---|---|
| EC2 → AWS service (S3, KMS, DDB, SSM) | IAM Role (Instance Profile) |
| Lambda → AWS service | Lambda Execution Role |
| ECS Task → AWS service | Task Role (`taskRoleArn`) |
| EKS Pod → AWS service (least-privilege) | **IRSA** (IAM Roles for Service Accounts) — không dùng Node Profile |
| Cross-account access | AssumeRole qua STS — không chia sẻ access key |
| Vendor/SaaS cần quyền vào account bạn | Tạo Role ở account bạn, trust vendor account |
| Centralized SSO nhiều account | IAM Identity Center |
| Guardrail nhiều account | SCP (Organizations) |
| Landing zone chuẩn | AWS Control Tower |

### SCP vs IAM Policy vs Permission Boundary

| | SCP | IAM Policy | Permission Boundary |
|---|---|---|---|
| Áp ở đâu | Org/OU level | Principal (user/role) | Specific IAM entity |
| Cấp quyền? | ❌ Chỉ giới hạn trần | ✅ | ❌ Chỉ giới hạn trần của entity |
| Use case | Guardrail toàn org | Grant permissions | Delegate role creation safely |

**Rule:**
- "Ngăn tất cả account trong OU xóa CloudTrail" → **SCP**.
- "Developer chỉ được tạo role không vượt qua boundary" → **Permission Boundary**.
- "Cấp quyền cho team dev đọc S3" → **IAM Policy**.

### Resource Access Manager (RAM)

- Chia sẻ tài nguyên cross-account **trong cùng Organization** mà không cần copy.
- Resources thường dùng với RAM: VPC Subnet, Transit Gateway, Route 53 Resolver Rules, Glue Data Catalog.
- Pattern: "Nhiều account cần dùng chung subnet/TGW" → **RAM**.

---

## 1.2 Secrets Manager vs Parameter Store

| Tiêu chí | Secrets Manager | Parameter Store |
|---|---|---|
| Auto rotation native (DB creds) | ✅ Tích hợp RDS/Aurora | ❌ Phải tự dựng Lambda |
| Cost | $0.40/secret/tháng | Free (Standard) |
| Secure String | ✅ | ✅ (KMS encrypted) |
| Best for | DB credentials, API keys cần rotate | Config, feature flags, non-rotating |
| `rotation + least ops` | **Secrets Manager thắng** | Distractor |

**Rule chốt:** `rotate` + `database credentials` + `least ops` → **Secrets Manager luôn thắng**.

---

## 1.3 KMS và Mã Hóa

### 3 Loại Key

| Key type | Khi nào | Lưu ý |
|---|---|---|
| AWS managed key | Default encryption, ít ops | Không tùy chỉnh policy sâu |
| Customer managed key (CMK) | Key policy chi tiết, cross-account, audit | Phải manage lifecycle |
| CloudHSM | Dedicated HSM, compliance cực nghiêm | **Chỉ chọn khi đề thật sự buộc dedicated HSM** |

> ⚠️ "External Key Store" trong KMS ≠ Amazon EKS (Elastic Kubernetes Service).

### Use Cases Lặp Nhiều

- Share encrypted EBS snapshot cross-account → thêm account đích vào **key policy** của CMK, rồi share snapshot.
- S3/EBS/RDS/EFS/DynamoDB encryption at rest → gắn KMS.
- Lambda decrypt SQS message encrypted → thêm `kms:Decrypt` vào Lambda execution role.
- Encryption in transit RDS → tải AWS root CA cert, cấu hình SSL connection.

### ACM (AWS Certificate Manager)

- **Miễn phí** TLS cert cho public domains, tự động renew.
- Deploy tới: **ALB, NLB, CloudFront, API Gateway, Elastic Beanstalk**.
- **Không** deploy trực tiếp lên EC2 — phải import cert hoặc dùng Certbot/Let's Encrypt.
- **CloudFront chỉ nhận cert từ us-east-1** — quan trọng, hay ra đề.
- Validate qua DNS (CNAME record) hoặc email.

---

## 1.4 S3 Security và Compliance

### 4 Tính Năng Phân Biệt Rõ

| Tính năng                 | Mục đích                                               | KHÔNG phải              |
| ------------------------- | ------------------------------------------------------ | ----------------------- |
| **Versioning**            | Giữ version cũ, recover overwrite/delete               | Compliance immutability |
| **Lifecycle**             | Auto transition/expire → tối ưu cost                   | Protection chống xóa    |
| **Object Lock**           | WORM (Write Once Read Many), kể cả root không xóa được | Chỉ cost tiering        |
| **Replication (CRR/SRR)** | Copy cross-Region/cross-account                        | Thay thế Object Lock    |

### Object Lock — Chi Tiết Quan Trọng

- **Governance mode:** user có permission đặc biệt có thể override.
- **Compliance mode:** **không ai xóa được, kể cả root** — regulatory compliance thật sự.
- Phải bật **Versioning trước** khi enable Object Lock.
- Retention period + Legal hold là hai cơ chế riêng biệt.
- Pattern: "hồ sơ tài chính giữ 7 năm, kể cả admin không xóa được" → **Object Lock Compliance Mode**.

### S3 Replication — Chi Tiết Quan Trọng

| | CRR (Cross-Region Replication) | SRR (Same-Region Replication) |
|---|---|---|
| Scope | Cross-Region | Same Region |
| Use case | DR, latency reduction, compliance | Log aggregation, test/prod sync |
| Yêu cầu | Versioning bật ở cả source và destination | Versioning bật ở cả hai |
| Object cũ | **Không tự replicate** — cần S3 Batch Replication | Same |
| Delete markers | Không replicate by default (phải enable) | Same |

- **S3 Replication Time Control (RTC):** đảm bảo 99.99% objects replicate trong 15 phút — dùng khi cần SLA replication.

### S3 Pre-signed URL

- Cấp quyền truy cập **tạm thời** (có expiry) vào object cụ thể, không cần làm bucket public.
- Lambda generate pre-signed URL → client tải trực tiếp từ S3, không tốn bandwidth qua app server.

### S3 Transfer Acceleration vs CloudFront

- **Transfer Acceleration:** tăng tốc **upload** lên S3 qua CloudFront edge locations.
- **CloudFront:** cache và phân phối **download** nhanh hơn.

### S3 CORS

- Phải cấu hình CORS khi browser JS ở domain A cần gọi S3 API ở domain B.
- Pattern: "web app bị lỗi khi gọi S3 từ browser" → cần **CORS policy trên S3 bucket**.

---

## 1.5 VPC Security

### Security Group vs NACL

| Tiêu chí | Security Group | NACL |
|---|---|---|
| Áp dụng ở đâu | ENI/Instance | Subnet |
| Stateful | ✅ (return traffic tự động allow) | ❌ (phải tạo rule cả in lẫn out) |
| Allow/Deny | Chỉ Allow | Allow **và Deny** |
| Rule đánh giá | Tất cả rules | Theo thứ tự số, dừng khi khớp |
| **Khi nào thắng** | Mở cổng cho instance | **Chặn IP/CIDR cụ thể**, subnet guardrail |

**Rule:** Deny một IP cụ thể → **NACL**. Allow EC2 nhận port 443 → **Security Group**.

### VPC Endpoints

| Loại | Service | Đặc điểm |
|---|---|---|
| **Gateway Endpoint** | S3 và DynamoDB | Miễn phí, dùng route table, không có ENI |
| **Interface Endpoint** (PrivateLink) | Hầu hết AWS services | Có ENI trong subnet, có phí hourly + data |

- Gateway Endpoint: không route qua hybrid link (DX/VPN) — on-prem cần **Interface Endpoint**.
- Interface Endpoint: cho SSM, KMS, EC2 API, API Gateway, Secrets Manager...

### VPC Peering vs Transit Gateway

| | VPC Peering | Transit Gateway |
|---|---|---|
| Model | 1-1 connection | Hub-and-spoke (1 TGW kết nối nhiều VPC) |
| Transitive routing | ❌ **Non-transitive** — A↔B, B↔C, A không đến C qua B | ✅ Transitive |
| Cross-Region | ✅ | ✅ (TGW Peering cross-Region) |
| Scale | Khó scale (N² connections) | Scale tốt |
| Cost | Rẻ hơn | Đắt hơn, có thêm attachment fee |
| **Khi nào** | 2-3 VPC cần connect đơn giản | Nhiều VPC, hub-and-spoke, on-prem kết hợp |

**Bẫy quan trọng:** VPC Peering **không transitive** — đây là lý do cần Transit Gateway khi nhiều VPC.

### PrivateLink

- Expose service từ một VPC/account cho VPC/account khác **mà không peer toàn mạng**.
- Pattern: "công ty A có service, muốn cho B dùng mà không expose toàn VPC" → **PrivateLink**.

### Egress-Only Internet Gateway

- Chỉ dành cho **IPv6** — cho phép instance trong private subnet gửi traffic IPv6 ra internet nhưng không nhận traffic inbound.
- Tương đương NAT Gateway nhưng cho IPv6.

### VPC Flow Logs

- Log metadata traffic qua ENI, subnet, VPC — gửi tới CloudWatch Logs hoặc S3.
- Pattern: "cần biết traffic nào bị reject ở mức network" → **VPC Flow Logs**.

---

## 1.6 Security Services Chi Tiết

### So Sánh 7 Security Services

| Service | Bài toán đúng | Không phải |
|---|---|---|
| **WAF** | Layer 7: SQLi, XSS, rate limit, geo-block, HTTP flood | DDoS volumetric |
| **Shield Standard** | DDoS cơ bản (miễn phí, mặc định) | — |
| **Shield Advanced** | DDoS phức tạp, cost protection, 24/7 DRT | Thay WAF |
| **GuardDuty** | Threat detection từ CloudTrail/VPC Flow Logs/DNS/EKS logs | Chặn traffic, scan vuln |
| **Macie** | Phát hiện PII/sensitive data trong **S3** | Threat detection |
| **Inspector** | Vulnerability assessment: EC2, ECR images, Lambda | Threat detection, PII |
| **Network Firewall** | Deep packet inspection ở VPC level, stateful/stateless filtering | WAF (Layer 7 web), NACL (basic) |

### AWS Network Firewall

- Stateful và stateless packet inspection ở **VPC perimeter** level.
- Hỗ trợ: domain filtering, IDS/IPS rules (Suricata), protocol detection.
- Pattern: "cần deep packet inspection ở mức VPC, không chỉ port/CIDR" → **Network Firewall**.
- Khác WAF: WAF cho web apps (HTTP); Network Firewall cho tất cả traffic ở VPC level.

### Security Hub

- **Aggregate security findings** từ nhiều service: GuardDuty, Inspector, Macie, Config, IAM Access Analyzer.
- Cross-account, cross-region với delegated administrator.
- Pattern: "cần single pane of glass cho security posture toàn bộ AWS accounts" → **Security Hub**.

### Amazon Detective

- **Root cause analysis** cho security incidents — phân tích và visualize relationships.
- Data sources: GuardDuty findings, CloudTrail, VPC Flow Logs.
- Pattern: "GuardDuty phát hiện threat, cần investigate origin và scope" → **Detective**.

### CloudTrail vs CloudWatch vs AWS Config

| Service | Câu hỏi nào |
|---|---|
| **CloudTrail** | "Ai đã gọi API gì, lúc nào, từ đâu?" — audit, forensic |
| **CloudWatch** | "Metric CPU bao nhiêu? Alarm khi latency > X? Log application?" |
| **AWS Config** | "Resource có config đúng policy? Khi nào thay đổi? SG có mở 0.0.0.0/0?" |

**Bẫy:**
- "Ai xóa security group" → **CloudTrail**.
- "EBS không encrypted theo policy" → **AWS Config** (managed rule: `ebs-encryption-enabled`).
- "Alarm khi CPU > 80%" → **CloudWatch**.

### CloudWatch Chi Tiết

- **Metric Filters:** extract metric từ log pattern.
- **CloudWatch Logs Insights:** ad-hoc log query — không cần cluster.
- **Container Insights:** metrics chi tiết cho ECS/EKS ở level pod/service.
- **Composite Alarms:** combine nhiều alarm với AND/OR logic.
- **Synthetics Canaries:** monitor endpoint/API availability từ bên ngoài.

### AWS Config Chi Tiết

- **Managed Rules:** built-in rules (>150 rules), ví dụ: `ec2-instance-no-public-ip`, `s3-bucket-public-read-prohibited`.
- **Custom Rules:** Lambda-backed custom logic.
- **Conformance Packs:** bundle nhiều rules + remediation vào một pack (ví dụ: CIS Benchmark).
- **Aggregator:** view compliance across nhiều accounts/regions.
- **Remediation:** auto-remediation qua SSM Automation document.

---

## 1.7 Systems Manager (SSM)

> **Topic cực quan trọng thường bị bỏ qua trong guide ôn thi!**

### SSM Session Manager — Exam Pattern Phổ Biến Nhất

- **Kết nối EC2 instance mà không cần SSH key, không cần public IP, không mở port 22**.
- Hoạt động qua SSM Agent + IAM role — không cần bastion host.
- **Pattern hay ra đề:** "Cần truy cập EC2 trong private subnet mà không mở port, không cần bastion" → **SSM Session Manager**.
- Tất cả session được log vào CloudWatch Logs hoặc S3 (audit trail).

### SSM Parameter Store

- Lưu configuration và secrets (integration với KMS cho SecureString).
- Free (Standard tier), có Advanced tier với extra features.
- Tham khảo section 1.2 cho so sánh với Secrets Manager.

### SSM Patch Manager

- Auto patch EC2 (OS updates), theo lịch, có patch baseline.
- Pattern: "auto patch fleet EC2 với ít ops nhất" → **SSM Patch Manager**.

### SSM Automation

- Thực thi automation documents (runbooks) cho infra tasks.
- Dùng cho: restart instance, rotate creds, backup, remediation.
- AWS Config có thể trigger SSM Automation cho auto-remediation.

---

## 1.8 Multi-Account Governance

| Nhu cầu                                  | Đáp án              |
| ---------------------------------------- | ------------------- |
| Quản trị nhiều account tập trung         | AWS Organizations   |
| Guardrail không cho account con làm X    | SCP                 |
| SSO tập trung nhiều account              | IAM Identity Center |
| Landing zone chuẩn, automated governance | AWS Control Tower   |
| Chia sẻ resource cross-account           | RAM                 |

**SCP không cấp quyền** — chỉ giới hạn trần quyền. Root của member account cũng bị giới hạn.

---

## 1.9 Networking Hybrid

### Site-to-Site VPN vs Direct Connect

| Tiêu chí | Site-to-Site VPN | Direct Connect (DX) |
|---|---|---|
| Setup time | Nhanh (phút-giờ) | Lâu (tuần-tháng) |
| Throughput | Giới hạn bởi internet | 1/10/100 Gbps dedicated |
| Latency | Không ổn định | Predictable, consistent |
| Encrypted | ✅ IPsec mặc định | ❌ Phải thêm VPN over DX nếu muốn encrypt |
| Cost | Rẻ hơn | Đắt hơn |
| **Khi nào** | Nhanh, backup cho DX, budget thấp | Throughput lớn, latency ổn định, lâu dài |

### Direct Connect Gateway

- Kết nối **1 Direct Connect connection với nhiều VPC ở nhiều Region**.
- Không cần nhiều DX connection riêng cho từng Region.
- Pattern: "công ty có 1 DX connection nhưng cần kết nối VPC ở us-east-1, eu-west-1, ap-southeast-1" → **Direct Connect Gateway**.

### Transit Gateway — Chi Tiết

- Hub-and-spoke: 1 TGW kết nối hàng trăm VPC + on-prem.
- **Cross-Region TGW Peering:** kết nối TGW ở các Region khác nhau.
- Attach với: VPC, VPN, DX (Transit VIF), TGW Peering.
- **Route tables per TGW:** kiểm soát routing granular giữa các attachment.
- Pattern: "on-prem + 50 VPCs cần kết nối nhau qua hub" → **Transit Gateway**.

---

## 1.10 Cognito

| | User Pools | Identity Pools |
|---|---|---|
| Mục đích | Authentication — user directory, login | Authorization — AWS credentials tạm thời |
| Output | JWT tokens | AWS STS credentials |
| Dùng khi | Login/signup web/mobile | App cần gọi AWS service (S3, DynamoDB) |

**Pattern:** "Mobile app authenticate user rồi cho upload S3" → **User Pool + Identity Pool + IAM Role**.

---

## 1.11 Well-Architected Framework — 6 Pillars

| Pillar | Nội dung |
|---|---|
| **Operational Excellence** | Run and monitor systems, automate operations, improve processes |
| **Security** | Protect data, systems, assets — IAM, encryption, detection |
| **Reliability** | Recover from failures, scale, manage change — HA, DR, backup |
| **Performance Efficiency** | Use computing resources efficiently — right service, right size |
| **Cost Optimization** | Avoid unnecessary costs — right pricing model, eliminate waste |
| **Sustainability** | Minimize environmental impact — efficient resource usage |

**AWS Well-Architected Tool:** review workload theo 6 pillars, nhận recommendations.

---

## 1.12 CloudFormation

- **IaC (Infrastructure as Code)** — AWS native.
- **Stacks:** deploy/update/delete infrastructure từ template YAML/JSON.
- **StackSets:** deploy cùng stack **across nhiều accounts và regions** → pattern cho multi-account governance.
- **Change Sets:** preview changes trước khi apply — quan trọng cho production.
- **Nested Stacks:** chia template lớn thành nhiều template nhỏ tái dùng.
- **DeletionPolicy:** Retain, Snapshot, Delete — quyết định gì xảy ra với resource khi stack bị xóa.
- Pattern: "deploy cùng infrastructure ra 10 account dev theo chuẩn" → **CloudFormation StackSets**.

---

## 1.13 Decision Tree — Domain 1

```
Quyền truy cập?
  EC2/Lambda/ECS/EKS cần gọi AWS service → IAM Role (IRSA cho EKS pod)
  Cross-account → AssumeRole (STS)
  Multi-account SSO → IAM Identity Center
  Multi-account guardrail → SCP
  Landing zone → Control Tower
  Share resource cross-account → RAM

Secrets/credentials?
  Rotation + DB credentials → Secrets Manager
  Config/flag, không rotation → Parameter Store
  TLS certificate → ACM (us-east-1 cho CloudFront)

Mã hóa?
  Key policy chi tiết / cross-account → Customer Managed KMS Key
  Default encryption, ít ops → AWS Managed Key
  Dedicated HSM (compliance buộc) → CloudHSM

S3 compliance?
  WORM, kể cả root không xóa → Object Lock Compliance Mode
  Version history → Versioning
  Cost tiering tự động → Lifecycle

Network security?
  Deny IP cụ thể → NACL
  Open port cho instance → Security Group
  SQLi/XSS/HTTP flood → WAF
  Deep packet inspection VPC → Network Firewall
  DDoS → Shield
  PII in S3 → Macie
  Threat detection → GuardDuty
  Vulnerability EC2/ECR → Inspector
  API audit → CloudTrail
  Config compliance → AWS Config
  Single pane security → Security Hub
  Incident investigation → Detective

EC2 access không SSH/bastion?
  → SSM Session Manager

Multi-account infra deployment?
  → CloudFormation StackSets
```

---

# DOMAIN 2 — Design Resilient Architectures (26%)

## Core Theory

4 khái niệm phải tách biệt:
- **HA:** vẫn phục vụ khi 1 thành phần / AZ lỗi.
- **Durability:** dữ liệu không mất (S3: 11 nines).
- **Fault Tolerance:** tiếp tục chạy gần như không gián đoạn.
- **DR:** phục hồi sau sự cố lớn (Region/account scope).

---

## 2.1 SQS Chi Tiết

### SQS Standard vs FIFO

| | Standard | FIFO |
|---|---|---|
| Ordering | Không đảm bảo (best-effort) | **Đảm bảo exactly-once, ordered** |
| Throughput | Không giới hạn | 300 msg/s (3,000/s với batching) |
| Deduplication | Không | ✅ (deduplication ID) |
| **Khi nào** | High throughput, order không quan trọng | Order/dedup là bắt buộc |

**FIFO keyword:** `strict order`, `sequence`, `exactly once`, `deduplication`, `no duplicate` → **SQS FIFO**.

### Visibility Timeout

- Khi consumer lấy message, message bị **ẩn** trong thời gian `visibility timeout`.
- Nếu consumer không xóa message trước khi timeout → message **xuất hiện lại** → có thể bị xử lý lần 2.
- Pattern: "message bị xử lý 2 lần" → **tăng visibility timeout** hoặc consumer cần xóa message sau khi xử lý xong.
- Default: 30 giây. Max: 12 giờ.

### Long Polling vs Short Polling

- **Short polling:** query SQS ngay, trả về ngay dù queue trống → nhiều empty responses, tốn tiền.
- **Long polling:** SQS đợi tới khi có message hoặc đến timeout → ít API calls, rẻ hơn.
- Pattern: "giảm số lượng API calls đến SQS, giảm cost" → **Long Polling** (`ReceiveMessageWaitTimeSeconds > 0`).

### Dead Letter Queue (DLQ)

- Cô lập **poison message** (xử lý lỗi nhiều lần) → giữ luồng chính không bị block.
- DLQ **không** giải quyết throughput hay scaling.
- Cả SQS và SNS đều hỗ trợ DLQ.

### SQS Extended Client Library

- SQS có giới hạn message size **256 KB**.
- Nếu payload > 256 KB → dùng **S3 làm body store**, message SQS chỉ chứa pointer → **SQS Extended Client Library**.

### Lambda Destinations vs DLQ

| | DLQ | Lambda Destinations |
|---|---|---|
| Áp dụng khi | Message xử lý fail (tất cả invocation types) | Async invocation success **hoặc** failure |
| Route | 1 destination (SQS/SNS) | Riêng cho success và failure |
| Metadata | Message body + error | Execution result + context |
| **Khi nào** | Cần catch failed messages đơn giản | Cần route async invocation kết quả linh hoạt |

---

## 2.2 SNS vs EventBridge vs SQS

| Tiêu chí         | SQS                             | SNS                        | EventBridge                         |
| ---------------- | ------------------------------- | -------------------------- | ----------------------------------- |
| Mô hình          | Queue (pull)                    | Pub/Sub (push fanout)      | Event bus (routing by rule)         |
| Consumer         | Competing consumers             | Nhiều subscriber song song | Nhiều target theo rule              |
| Ordering         | FIFO queue: có; Standard: không | Không                      | Không                               |
| Retention        | 4 ngày (max 14)                 | Push ngay                  | Push ngay                           |
| Replay           | ❌                               | ❌                          | ❌ (Archive feature: có thể replay)  |
| SaaS integration | ❌                               | ❌                          | ✅ (Salesforce, Datadog, Zendesk...) |
| Schedule         | ❌                               | ❌                          | ✅ (EventBridge Scheduler)           |
| **Trigger đúng** | Decouple, buffer, retry, DLQ    | Fanout 1→nhiều             | Routing theo rule, SaaS, schedule   |

### EventBridge Chi Tiết

- **Default event bus:** nhận events từ AWS services.
- **Custom event bus:** nhận events từ custom apps.
- **Partner event bus:** nhận events từ SaaS partners.
- **EventBridge Scheduler:** standalone service để schedule tasks (cron/rate), riêng biệt với EventBridge Rules.
- Pattern: "trigger Lambda mỗi ngày lúc 8 giờ sáng" → **EventBridge Scheduler** (hoặc EventBridge Rule với schedule expression).

---

## 2.3 Auto Scaling và HA Compute

### ASG Scaling Policies

- **Target Tracking:** đơn giản nhất, giữ metric ở target (CPU 60%, request count 1000/instance).
- **Step Scaling:** scale từng bước theo mức metric.
- **Scheduled Scaling:** biết trước pattern tải (tăng capacity trước 8h sáng).
- **Predictive Scaling:** ML predict pattern tải, scale proactively.

### ALB vs NLB vs GWLB

| Tiêu chí | ALB | NLB | Gateway LB (GWLB) |
|---|---|---|---|
| Layer | 7 (HTTP/HTTPS) | 4 (TCP/UDP/TLS) | 3 (IP) |
| Routing | Path, host, header, query param | IP + Port | — |
| Static IP | ❌ | ✅ (Elastic IP per AZ) | — |
| WebSocket | ✅ | ✅ | — |
| Cross-zone LB | ✅ Default | ❌ Default (có thể bật) | — |
| Sticky sessions | ✅ | ✅ | — |
| Use case | Web apps, microservices | Gaming, IoT, VoIP, static IP | **Transparent routing qua security appliances** |

**GWLB:** route traffic qua fleet firewall/IDS/IPS transparently — app không biết traffic đã qua appliance.

### Connection Draining / Deregistration Delay

- Trước khi remove instance khỏi target group, LB cho phép inflight requests hoàn thành (mặc định 300s).
- Pattern: "instance bị terminate nhưng vẫn cần xử lý xong requests đang chờ" → **Deregistration Delay**.

### ASG Lifecycle Hooks

- Tạm dừng launch/terminate để chạy script trước khi ASG tiếp tục.
- Launch hook: install software, register to service discovery trước khi serve traffic.
- Terminate hook: drain connections, backup state, deregister từ service discovery.

---

## 2.4 Database Resilience

### Multi-AZ vs Read Replica vs Aurora Replica

| | Multi-AZ | Read Replica | Aurora Replica |
|---|---|---|---|
| Mục đích | **HA/failover tự động** | **Scale đọc** | Scale đọc + failover nhanh |
| Traffic đọc | ❌ (standby chỉ failover) | ✅ | ✅ |
| Failover | Tự động ~1-2 phút | Manual promote | Tự động ~30s |
| Cross-Region | ❌ | ✅ | ✅ |
| **Khi nào** | Production HA | Reporting, read-heavy | Aurora HA + scale đọc |

**Bẫy số 1 toàn domain 2:** Read Replica cho HA → sai. Multi-AZ cho scale đọc → sai.

### RDS Multi-AZ DB Cluster (Mới)

- 1 writer + **2 reader instances** trong 3 AZs khác nhau.
- Failover nhanh hơn Multi-AZ thông thường (không cần promote standby từ binary log).
- Khác RDS Multi-AZ (2 AZs): Multi-AZ DB Cluster có 3 AZs và reader có thể serve read traffic.

### Aurora Global Database

- **1 primary Region** + tối đa 5 **secondary Regions** (read-only).
- Replication lag **< 1 giây** (thường ~100ms).
- **RPO = seconds, RTO = minutes** cho cross-Region failover.
- Dùng cho: global app cần local read latency, DR cross-Region với RPO/RTO rất thấp.
- Pattern: "app global cần đọc với latency thấp ở nhiều Region, và DR RPO < 1 phút" → **Aurora Global Database**.

### RDS Proxy

- Connection pooler managed: gom kết nối từ Lambda/ECS thành ít kết nối thực tới DB.
- Giải quyết **connection storm** khi Lambda/ECS scale mạnh.
- Tích hợp với Secrets Manager để auto rotation credentials.

### RDS Automated Backups vs Manual Snapshots

| | Automated Backup | Manual Snapshot |
|---|---|---|
| Retention | 0-35 ngày | Vô thời hạn |
| Point-in-time recovery | ✅ | ❌ |
| Xóa khi xóa DB | ✅ | ❌ (giữ lại) |
| **Dùng khi** | PITR, rolling window | Long-term, migrate |

---

## 2.5 Disaster Recovery

### 4 DR Strategies

| Strategy | RTO | RPO | Cost | Mô tả |
|---|---|---|---|---|
| **Backup & Restore** | Giờ | Giờ | Thấp | Backup only; restore từ snapshot |
| **Pilot Light** | 10-30 phút | Phút | Thấp-TB | Core services minimal; scale up khi cần |
| **Warm Standby** | Phút | Giây-Phút | TB | Full stack ở scale nhỏ; scale up khi failover |
| **Active-Active** | Giây | Gần 0 | Cao | Cả 2 Region phục vụ traffic song song |

**Rule chọn:**
- Đề không gắn RPO/RTO cụ thể → Pilot Light hoặc Warm Standby thường đủ, rẻ hơn Active-Active.
- RPO thấp (phút/giây) → replication gần real-time.
- RTO thấp (phút) → warm standby hoặc active-active.

---

## 2.6 Route 53 — Routing Policies Chi Tiết

| Policy | Khi nào | Ghi chú |
|---|---|---|
| **Simple** | 1 resource, không health check | Không failover |
| **Weighted** | A/B testing, blue-green, phân tải % | Weight 0 = tắt |
| **Latency-based** | Route đến Region latency thấp nhất | Thực đo latency, không phải geography |
| **Failover** | Active-passive DR | Bắt buộc health check |
| **Geolocation** | Serve content theo **quốc gia/continent** | Compliance, local content |
| **Geoproximity** | Route theo geography + **bias** kéo traffic | Traffic Flow required |
| **Multivalue Answer** | Return nhiều IP, health check từng record | Không thay load balancer |
| **IP-based** | Route dựa trên CIDR của client IP | ISP-based routing |

### CNAME vs Alias Record

| | CNAME | Alias |
|---|---|---|
| Trỏ tới | Hostname bất kỳ | AWS resource (ELB, CloudFront, S3, API GW...) |
| Apex domain (`example.com`) | ❌ Không được | ✅ Được |
| Cost | Charge per query | Free cho AWS resource |
| Health check | ❌ | ✅ |
| TTL | Có thể set | Managed by Route 53 |

**Rule cứng:** Apex domain → **Alias record**. Không bao giờ CNAME ở apex domain.

---

## 2.7 Step Functions

- Orchestrate workflow nhiều bước với retry, timeout, error handling rõ ràng.
- **Standard Workflow:** long-running (tới 1 năm), exactly-once, đầy đủ audit.
- **Express Workflow:** high-throughput, at-least-once, rẻ hơn cho event processing.
- Pattern: "workflow 5 bước, mỗi bước có retry riêng, timeout riêng" → **Step Functions**.
- Tốt hơn chuỗi Lambda gọi nhau: visibility, audit trail, built-in retry logic.

---

## 2.8 AWS Backup

- Backup tập trung cho: RDS, DynamoDB, EFS, EBS, FSx, S3, Aurora, EC2.
- Tạo backup plan: schedule, retention, cross-Region/cross-account copy.
- **Thắng** khi: nhiều service, compliance, retention rõ ràng, central policy, ít ops.

---

## 2.9 Elastic Load Balancing — Chi Tiết

### Sticky Sessions (Session Affinity)

- ALB và NLB đều hỗ trợ.
- Đảm bảo user luôn được route đến cùng target.
- Dùng khi app có session state trên instance (không stateless).

### Cross-Zone Load Balancing

- **ALB:** bật mặc định — distribute đều qua tất cả instance dù ở AZ nào.
- **NLB:** tắt mặc định — chỉ route trong AZ của nó.
- Bật cross-zone NLB: giúp distribute đều hơn khi số instance không đều giữa AZs.

### Health Checks

- ALB: HTTP/HTTPS health check.
- NLB: TCP/HTTP/HTTPS health check.
- Health check response: 200 OK → healthy; timeout → unhealthy.

---

## 2.10 Decision Tree — Domain 2

```
Decouple producer-consumer? → SQS
Ordering / deduplication? → SQS FIFO
Message bị xử lý 2 lần? → Tăng SQS Visibility Timeout
Payload SQS > 256 KB? → SQS + S3 Extended Client Library
Fanout 1 event nhiều hệ? → SNS
Event routing theo rule / SaaS / schedule? → EventBridge
Workflow nhiều bước, retry, timeout? → Step Functions

HA relational DB? → Multi-AZ
Scale đọc relational DB? → Read Replica / Aurora Replica
HA + read scale Aurora? → Aurora với Multi-AZ replicas
Connection burst Lambda vào DB? → RDS Proxy
Global relational < 1s RPO? → Aurora Global Database
Global NoSQL? → DynamoDB Global Tables

DR cross-Region?
  RPO/RTO vài giờ → Pilot Light / Backup-only
  RPO phút, RTO phút → Warm Standby
  RPO giây, RTO giây → Active-Active / Aurora Global

Backup tập trung nhiều service? → AWS Backup
Traffic failover DNS? → Route 53 Failover + Health Check
```

---

# DOMAIN 3 — Design High-Performing Architectures (24%)

## 3.1 Storage — Phân Biệt Toàn Bộ

| Service | Model | Khi nào | Không nên khi |
|---|---|---|---|
| **S3** | Object | Static content, archive, data lake, backup | POSIX/SMB app trực tiếp |
| **EBS** | Block | OS disk, DB disk, 1 EC2 trong 1 AZ | Share nhiều instance/AZ |
| **EFS** | Shared POSIX NFS | Nhiều EC2 nhiều AZ, Linux | Windows SMB chuyên biệt |
| **FSx for Windows** | SMB/NTFS | Windows file share, AD integration | Linux POSIX |
| **FSx for Lustre** | HPC | HPC/ML throughput cao, gắn S3 | Windows workloads |
| **FSx for NetApp ONTAP** | NFS + SMB | Cần cả NFS và SMB trên cùng volume | — |
| **FSx for OpenZFS** | NFS | Linux workload cần ZFS features | — |
| **Instance Store** | Ephemeral block | Scratch, buffer, rất nhanh | Dữ liệu cần persistent |

### EBS Volume Types

| Type | IOPS Max | Throughput | Khi nào |
|---|---|---|---|
| **gp3** | 16,000 (provision độc lập) | 1,000 MB/s | General purpose, cost-effective |
| **gp2** | 16,000 (phụ thuộc size) | — | Legacy, gp3 tốt hơn |
| **io2 Block Express** | 256,000 IOPS | — | DB mission-critical, IOPS cứng |
| **io1** | 64,000 IOPS | — | DB hiệu năng cao |
| **st1** | HDD | 500 MB/s | Sequential large (log, Hadoop) |
| **sc1** | HDD | 250 MB/s | Cold data, rẻ nhất |

**gp3:** Provision IOPS và throughput **độc lập với dung lượng** — hay ra đề: "cần 10,000 IOPS trên volume 100 GB" → gp3.

---

## 3.2 Compute — Phân Biệt

| Service | Thắng khi | Không nên khi |
|---|---|---|
| **Lambda** | Event-driven, bursty, stateless, ≤15 phút | Job dài, stateful, connection storm DB |
| **EC2** | Full OS control, legacy app, job dài | Đề nhấn ít ops/serverless |
| **ECS/Fargate** | Container managed, không quản host | Cần deep host control |
| **ECS on EC2** | Container + control host/cost riêng | — |
| **EKS** | Kubernetes ecosystem, Helm, operator | Đề không nhắc K8s |
| **AWS Batch** | Batch CPU-intensive, queue-based | Job ngắn event-driven |
| **App Runner** | Container đơn giản, fully managed, web app | VPC phức tạp, complex networking |
| **Elastic Beanstalk** | PaaS, web app với ít code change, Tomcat/Node/PHP | Cần control sâu infra |

### Elastic Beanstalk Chi Tiết

- **PaaS:** auto provision EC2, ASG, ALB, deploy code.
- Hỗ trợ: Java/Tomcat, Node.js, PHP, Python, Ruby, .NET, Docker.
- **Web server environment:** phục vụ HTTP requests.
- **Worker environment:** xử lý background tasks từ SQS queue.
- Pattern: "migrate web app Java/Tomcat lên AWS với ít thay đổi nhất, ít ops nhất" → **Elastic Beanstalk**.

### EC2 Instance Types — Phân Biệt

| Family | Tối ưu cho | Ví dụ |
|---|---|---|
| **M (General Purpose)** | Cân bằng CPU/RAM | M7i, M6g |
| **C (Compute Optimized)** | CPU-intensive (HPC, batch, ML inference) | C7i, C6g |
| **R/X (Memory Optimized)** | In-memory DB, big data, SAP | R7i, X2idn |
| **I/D (Storage Optimized)** | High IOPS, NoSQL, data warehousing | I4i, D3 |
| **P/G/Inf (Accelerated)** | ML training, GPU rendering | P5, G5, Inf2 |
| **T (Burstable)** | Low baseline CPU, burst khi cần | T3, T3a |

Pattern: "cần nhiều RAM cho in-memory database" → **R class**. "Cần cao CPU cho ML training" → **C hoặc P class**.

### Lambda — Giới Hạn Quan Trọng

- Timeout tối đa: **15 phút**.
- Memory: 128 MB – 10,240 MB.
- Ephemeral storage (/tmp): tới **10 GB**.
- Concurrent executions: default 1,000/Region (có thể tăng).
- **Provisioned Concurrency:** giữ environments warm → loại bỏ cold start.
- **Reserved Concurrency:** giới hạn tối đa concurrent executions của 1 function.
- **Function URLs:** HTTPS endpoint trực tiếp cho Lambda, không cần API Gateway.
- **Layers:** chia sẻ code/thư viện giữa nhiều functions.
- **Container image:** support tới 10 GB image từ ECR.

### EC2 Placement Groups

| Type | Mô tả | Khi nào |
|---|---|---|
| **Cluster** | Cùng AZ, cùng rack | HPC, low-latency (<10 Gbps inter-node) |
| **Spread** | Phần cứng riêng biệt, max 7/AZ | Giảm correlated failure risk |
| **Partition** | Partition riêng, rack riêng | Distributed: HDFS, Cassandra, Kafka |

### EC2 Instance Metadata Service (IMDS v2)

- IMDS v2 (session-oriented) bảo mật hơn v1 (không cần token).
- Dùng IMDSv2 để lấy instance metadata (IAM role credentials, instance ID, AZ...) từ bên trong EC2.
- Pattern: "tăng cường bảo mật cho EC2, ngăn SSRF attacks vào metadata" → **Enforce IMDSv2**.

---

## 3.3 Database — Phân Biệt Toàn Bộ

### RDS vs Aurora vs DynamoDB

| | RDS | Aurora | DynamoDB |
|---|---|---|---|
| Model | Relational SQL | Relational (MySQL/PgSQL compat) | NoSQL key-value/document |
| Failover | Multi-AZ ~1-2 phút | ~30s, up to 15 replicas | Serverless, built-in |
| Read scale | Read replica | Aurora Replica (lag thấp hơn) | — |
| Global | Cross-Region read replica | **Aurora Global Database** | **Global Tables** |
| Latency | ms | ms | **Single-digit ms** |
| **Chọn khi** | Relational chuẩn | Relational + scale tốt hơn | Access pattern rõ, scale lớn |

### ElastiCache Redis vs Memcached

| | Redis | Memcached |
|---|---|---|
| Data structures | Rich (strings, hashes, lists, sets, sorted sets, bitmaps) | Simple key-value |
| Persistence | ✅ (RDB, AOF) | ❌ |
| Replication | ✅ (replica sets) | ❌ |
| Multi-AZ | ✅ | ❌ |
| Cluster mode | ✅ (horizontal sharding) | ✅ (multi-node sharding) |
| **Khi nào** | Session store, leaderboard, pub/sub, persistence | Simple caching, multi-threaded perf |

**Rule:** Nếu đề không chỉ định → **Redis** (tổng quát hơn, nhiều tính năng hơn).

### DynamoDB — Chi Tiết

**Capacity Modes:**
- **Provisioned:** chỉ định RCU/WCU, dự đoán được, dùng Reserved để tiết kiệm.
- **On-Demand:** pay-per-request, không cần dự báo, traffic không đều. Đắt hơn provisioned ở high load.
- **Auto Scaling:** provisioned + tự scale RCU/WCU.

**Các tính năng quan trọng:**
- **TTL:** tự xóa item sau expire (không tốn WCU).
- **Streams:** capture changes real-time → Lambda trigger.
- **Global Tables:** multi-Region, multi-active, sub-second replication.
- **DAX:** microsecond read cache, chỉ cho DynamoDB.
- **Transactions:** ACID transactions across items/tables trong same Region.

### Amazon MSK vs Kinesis Data Streams

| | Amazon MSK | Kinesis Data Streams |
|---|---|---|
| Protocol | **Apache Kafka** | AWS proprietary |
| Migration | Lift-and-shift Kafka workloads | Từ đầu trên AWS |
| Consumer | Kafka consumers (Kafka API) | Kinesis API, Lambda, Firehose |
| Managed | Managed Kafka + Zookeeper | Fully managed, serverless option |
| **Khi nào** | Existing Kafka workloads, Kafka ecosystem | New streaming trên AWS, ít ops |

**MSK Serverless:** không cần provision shards/brokers — auto scale.

---

## 3.4 API Gateway — Chi Tiết

### REST API vs HTTP API vs WebSocket API

| | REST API | HTTP API | WebSocket API |
|---|---|---|---|
| Cost | $3.50/1M requests | **$1.00/1M requests** | $1.00/1M messages |
| Features | Đầy đủ (usage plans, API keys, caching, request validation) | Simplified, JWT auth, CORS | Bidirectional real-time |
| Latency | TB | **Thấp hơn REST** | — |
| Private integration | ✅ (VPC Link) | ✅ | ❌ |
| **Khi nào** | Cần full features, API keys, usage plans | Serverless, ít ops, cost thấp | Chat, gaming, real-time |

**Rule:** Đề không yêu cầu features đặc biệt → **HTTP API** (rẻ hơn, ít ops hơn REST API).

### API Gateway Throttling

- **Default limits:** 10,000 req/s burst, 5,000 req/s steady-state per account per Region.
- **Usage Plans:** rate limit và quota cho từng API key/client.
- Pattern: "cần rate limit từng customer" → **Usage Plans + API Keys**.

### API Gateway Caching

- Cache responses tại API Gateway (0.5 GB – 237 GB).
- Giảm số calls đến backend.
- Cache key: query parameters, headers.

### API Gateway VPC Link

- Kết nối API Gateway private với NLB/ALB trong VPC.
- Pattern: "API Gateway public nhưng backend ECS ở private subnet" → **API Gateway + VPC Link + NLB**.

---

## 3.5 CloudFront — Chi Tiết

### Lambda@Edge vs CloudFront Functions

| | Lambda@Edge | CloudFront Functions |
|---|---|---|
| Runtime | Node.js, Python | JavaScript (limited) |
| Execution location | Regional Edge Cache | **Edge Locations** (gần user hơn) |
| Latency | Thấp | **Cực thấp** |
| Max duration | 30s (viewer), 30s (origin) | < 1ms |
| Access to network | ✅ | ❌ |
| Use case | Complex logic, dynamic content, A/B testing | **Simple header manipulation, URL rewrite, redirects** |
| Cost | Đắt hơn | Rẻ hơn |

**Rule:** Cần logic đơn giản ở edge → **CloudFront Functions**. Cần logic phức tạp, network calls → **Lambda@Edge**.

### Origin Groups

- Cấu hình **primary + secondary origin** cho CloudFront.
- Nếu primary origin fail (status 4xx/5xx) → CloudFront tự động failover sang secondary.
- Pattern: "CloudFront cần HA origin failover" → **Origin Groups**.

### CloudFront Key Tính Năng

- **OAC (Origin Access Control):** recommended cách CloudFront truy cập S3 private. OAI (cũ) → dùng OAC.
- **Signed URL:** 1 file cụ thể, time-limited.
- **Signed Cookie:** nhiều files (thư mục), time-limited.
- **WAF WebACL:** gắn vào CloudFront để chặn SQLi/XSS ở edge.
- **Geo restriction:** whitelist/blacklist quốc gia.
- **Field-Level Encryption:** encrypt specific fields (credit card) tại edge.

---

## 3.6 Analytics Pipeline

### Kinesis Family

| Service | Mô tả | Khi nào |
|---|---|---|
| **Kinesis Data Streams** | Custom consumers, real-time, replay | Custom processing, nhiều consumer, replay |
| **Kinesis Data Firehose** | Managed delivery → S3/Redshift/OpenSearch | Delivery managed, ít ops |
| **Kinesis Data Analytics (MSF)** | Real-time SQL/Flink trên stream | Real-time analytics trên stream |
| **Kinesis Video Streams** | Video ingest và process | IoT cameras, ML video |

**Shard calculation (Kinesis):** 1 shard = 1 MB/s in, 2 MB/s out, 1,000 records/s. Scale bằng cách tăng shards.

### Athena vs Redshift vs EMR vs Glue

| | Athena | Redshift | EMR | Glue |
|---|---|---|---|---|
| Model | Serverless SQL on S3 | Data warehouse | Managed Hadoop/Spark | Serverless ETL |
| Cost | Pay per scan (TB) | Pay per cluster-hour | Pay per cluster-hour | Pay per DPU-hour |
| Ops | Zero | Thấp | Cao | Zero |
| **Khi nào** | Ad-hoc query on S3 | BI/reporting lặp lại | Complex Spark/ML | ETL, Data Catalog |

### Amazon OpenSearch Service

- Full-text search, log analytics, real-time monitoring.
- Pattern: "search trong product catalog" hoặc "log dashboard phức tạp hơn CloudWatch" → **OpenSearch**.

---

## 3.7 Networking Performance

### Direct Connect vs VPN (nhắc lại)

**Direct Connect Gateway:** 1 DX → nhiều VPC nhiều Region — không cần nhiều DX connections riêng.

### Global Infrastructure: Region / AZ / Edge / Local Zones / Wavelength

| | Mô tả | Khi nào |
|---|---|---|
| **Region** | Tập hợp AZs, isolated | Workload chính |
| **AZ** | Isolated data center trong Region | HA, Multi-AZ |
| **Edge Locations** | CloudFront/Route 53 PoPs | CDN, DNS |
| **Local Zones** | AWS infrastructure gần thành phố lớn | Latency-sensitive workloads gần user cuối |
| **Wavelength Zones** | AWS trong 5G network của telecom | Ultra-low latency cho mobile 5G |

---

## 3.8 SES — Simple Email Service

- Managed email sending service.
- Send: transactional, marketing, bulk emails.
- Pattern: "app cần gửi email xác nhận đơn hàng, notification" → **SES**.
- Khác SNS: SNS là pub/sub messaging; SES chuyên cho email.

---

## 3.9 AWS IoT Core

- Connect và manage IoT devices tại scale.
- **Protocol:** MQTT, WebSocket, HTTP.
- **Rules Engine:** route IoT messages đến AWS services (S3, DynamoDB, Kinesis, Lambda, SQS...).
- Pattern: "hàng triệu cảm biến IoT gửi data, cần route đến S3 và DynamoDB" → **IoT Core + Rules Engine**.

---

## 3.10 AI/ML Services

| Service | Dùng cho |
|---|---|
| **Rekognition** | Image/video: detect object, face, text, content moderation |
| **Textract** | Extract text, forms, tables từ document (PDF, image) |
| **Comprehend** | NLP: sentiment, entity extraction, topic modeling |
| **Translate** | Machine translation |
| **Transcribe** | Speech-to-text |
| **Polly** | Text-to-speech |
| **Lex** | Conversational chatbot (Alexa tech) |
| **SageMaker** | Custom ML: build, train, deploy models |
| **Kendra** | Enterprise search với AI |
| **Personalize** | Personalized recommendations |

---

## 3.11 Decision Tree — Domain 3

```
Storage?
  Nhiều EC2, POSIX Linux → EFS
  Windows SMB + AD → FSx for Windows
  HPC + S3 integration → FSx for Lustre
  NFS + SMB cùng volume → FSx for NetApp ONTAP
  Block 1 EC2 → EBS (gp3 cho general; io2 cho IOPS cao)
  Object, data lake → S3
  Ephemeral → Instance Store

Compute?
  Event-driven ≤15 phút → Lambda
  Full OS control → EC2
  Container, ít ops → ECS/Fargate
  Kubernetes → EKS
  Batch CPU queue → AWS Batch
  Web app PaaS ít code change → Elastic Beanstalk

Database?
  Key-value/document, scale lớn → DynamoDB
  DynamoDB + microsecond → DAX
  Relational chuẩn → RDS
  Relational scale đọc + failover nhanh → Aurora
  Aurora global <1s replication → Aurora Global Database
  Cache general/session → ElastiCache Redis
  Analytics/BI → Redshift
  Ad-hoc query on S3 → Athena
  ETL managed → Glue
  Complex Spark/ML → EMR
  Full-text search → OpenSearch

API?
  Simple serverless API → HTTP API (API Gateway)
  Need usage plans/keys/caching → REST API (API Gateway)
  Real-time bidirectional → WebSocket API
  Backend trong private VPC → API Gateway + VPC Link

Network?
  Global HTTP cache → CloudFront
  Global TCP/UDP → Global Accelerator + NLB
  Private S3/DDB → Gateway Endpoint
  Private other AWS service → Interface Endpoint
  Many VPCs hub-spoke → Transit Gateway
  1 DX nhiều Region → Direct Connect Gateway
  Low-latency logic at edge → CloudFront Functions
  Complex logic at edge → Lambda@Edge

Streaming?
  New AWS streaming → Kinesis Data Streams
  Existing Kafka → MSK
  Managed delivery → Kinesis Firehose
  Real-time analytics on stream → Kinesis Data Analytics (MSF)
```

---

# DOMAIN 4 — Design Cost-Optimized Architectures (20%)

## 4.1 EC2 Pricing Models

| Model | Khi nào | Discount |
|---|---|---|
| **On-Demand** | Linh hoạt, không cam kết | 0% |
| **Reserved Instance (RI)** | Steady-state, cam kết 1-3 năm, instance type ổn định | Tới 72% |
| **Savings Plans** | Steady-state, linh hoạt instance family/region (Compute SP: cả Lambda/Fargate) | Tới 66% |
| **Spot** | Workload chịu interrupt (batch, ETL, CI/CD, render, stateless) | Tới 90% |
| **Dedicated Host** | Compliance, BYOL (Bring Your Own License) | Đắt nhất |
| **Dedicated Instance** | Physical isolation (không BYOL) | Đắt |

### Savings Plans Types

| | EC2 Instance Savings Plan | Compute Savings Plan |
|---|---|---|
| Scope | 1 instance family, 1 Region | Bất kỳ family, region, cả Lambda, Fargate |
| Discount | Cao hơn | Thấp hơn một chút |
| **Khi nào** | Instance type ổn định | Hay đổi instance type/region |

---

## 4.2 S3 Storage Classes

| Class | Retrieval | Min Duration | Khi nào |
|---|---|---|---|
| **Standard** | Ngay | — | Hot data, truy cập thường |
| **Standard-IA** | Ngay | 30 ngày | Ít truy cập, cần access nhanh |
| **One Zone-IA** | Ngay | 30 ngày | Re-creatable data, 1 AZ, rẻ hơn |
| **Intelligent-Tiering** | Varies | — | Access pattern không đoán được |
| **Glacier Instant Retrieval** | Ngay | 90 ngày | Archive + instant access |
| **Glacier Flexible Retrieval** | Phút-12 giờ | 90 ngày | Archive, đợi được vài giờ |
| **Glacier Deep Archive** | 12-48 giờ | 180 ngày | Long-term compliance, hiếm đọc |

**Rules:**
- Không biết pattern → **Intelligent-Tiering**.
- Archive cần ngay khi cần → **Glacier Instant Retrieval**.
- Archive compliance, hiếm đọc, đợi được → **Glacier Deep Archive**.
- Data có thể tái tạo, 1 AZ → **One Zone-IA** (rẻ nhất có instant retrieval).

---

## 4.3 Cost Optimization Patterns

### NAT Gateway vs VPC Endpoint

- NAT Gateway: tốn kém cho traffic S3/DynamoDB ($0.045/GB data processing).
- **Gateway VPC Endpoint** cho S3/DynamoDB: **miễn phí hoàn toàn**.
- Pattern cực hay ra đề: "Private subnet có bill NAT cao do access S3 thường xuyên" → **Gateway VPC Endpoint**.

### Serverless vs Always-On

- Lambda/Fargate: pay-per-use → thắng khi workload intermittent/bursty.
- EC2 always-on: thua về cost khi chỉ dùng vài giờ/ngày.

### Dev/Test Scheduling

- Start/stop EC2/RDS theo lịch → EventBridge + Lambda hoặc AWS Instance Scheduler.
- Tiết kiệm ~65-70% nếu chỉ dùng giờ hành chính.

### Right-Sizing

- **AWS Compute Optimizer:** phân tích utilization EC2, Lambda, EBS, ECS → recommend instance type phù hợp.
- **AWS Trusted Advisor:** checks tự động — cost, security, fault tolerance, performance, service limits.
  - Free tier: basic checks (S3 public, SG ports, MFA root).
  - Business/Enterprise: đầy đủ checks.
- **Cost Explorer:** visualize và analyze cost, forecast.

---

## 4.4 Data Transfer Cost Optimization

- **Cross-AZ data transfer:** có phí ($0.01/GB) → colocate services cùng AZ khi có thể.
- **Cross-Region transfer:** đắt hơn ($0.02/GB+) → cân nhắc replication cost vs benefit.
- **Internet egress:** tốn kém → dùng VPC Endpoint thay NAT cho S3/DynamoDB.
- **CloudFront:** giảm origin hits → giảm egress cost từ origin.

---

## 4.5 Storage Cost Optimization

- S3 Lifecycle: tự động transition từ Standard → IA → Glacier theo thời gian.
- S3 Intelligent-Tiering: auto-tier, phù hợp khi access pattern không đoán được.
- EBS: chọn gp3 thay gp2 (gp3 rẻ hơn ~20% và flexible IOPS).
- Delete unattached EBS volumes, old snapshots.

---

## 4.6 Snow Family

| Device | Capacity | Khi nào |
|---|---|---|
| **Snowcone** | 8-14 TB | Edge nhỏ, DataSync agent |
| **Snowball Edge Storage Optimized** | 80 TB usable | Data migration lớn |
| **Snowball Edge Compute Optimized** | 42 TB + GPU | Edge ML/compute + storage |
| **Snowmobile** | 100 PB | Exabyte-scale migration |

Pattern: "upload 50 TB qua internet quá chậm/tốn kém" → **Snowball Edge**.

---

## 4.7 Migration Strategies — 7 Rs

| Strategy | Mô tả | Khi nào |
|---|---|---|
| **Retire** | Tắt bỏ | App không cần |
| **Retain** | Giữ on-prem | Dependency, regulatory |
| **Rehost** | Lift-and-shift (EC2 thay physical server) | Nhanh, minimal change |
| **Replatform** | Lift-tinker-shift (RDS thay MySQL self-managed) | Cải tiến một phần |
| **Repurchase** | SaaS thay thế (Salesforce, WorkDay) | SaaS available |
| **Refactor/Re-architect** | Cloud-native redesign | Scale, serverless |
| **Relocate** | VMware Cloud on AWS | VMware workloads |

---

## 4.8 DataSync vs Storage Gateway vs Transfer Family

| Service | Khi nào |
|---|---|
| **DataSync** | **Migration**: file/object online từ on-prem/NFS/SMB → S3/EFS/FSx. Scheduled, incremental. |
| **Storage Gateway** | **Ongoing hybrid**: on-prem app cần file/block interface nhưng data ở AWS. |
| **Transfer Family** | **Managed SFTP/FTPS/FTP/AS2**: B2B file transfer → S3/EFS. |

### Storage Gateway Types

| Type | Protocol | Primary data location | Khi nào |
|---|---|---|---|
| **File Gateway (S3)** | NFS/SMB | S3 (với local cache) | On-prem app cần file interface, data ở S3 |
| **Volume Gateway – Cached** | iSCSI | S3 (cache hot on-prem) | Giảm on-prem storage, access hot data nhanh |
| **Volume Gateway – Stored** | iSCSI | On-prem (async backup S3) | Full data on-prem, DR backup lên S3 |
| **Tape Gateway** | iSCSI VTL | S3/Glacier | Thay physical tape backup |

---

## 4.9 Decision Tree — Domain 4

```
Compute cost?
  Steady workload dài hạn → Savings Plans / Reserved
  Hay đổi instance type → Compute Savings Plan
  Batch, chịu interrupt → Spot
  Intermittent/bursty → Lambda/Fargate
  Dev/test theo giờ → Schedule start/stop

Storage cost?
  Hot → Standard; ít truy cập → Standard-IA; archive → Glacier classes
  Không đoán được pattern → Intelligent-Tiering
  Transition tự động → Lifecycle policy

Network cost?
  Private subnet → S3/DynamoDB nhiều → Gateway Endpoint (miễn phí)
  Cross-AZ traffic → colocate hoặc endpoint

Analytics cost?
  Ad-hoc thỉnh thoảng → Athena (pay per scan)
  Reporting lặp lại → Redshift (nhưng cân nhắc pause khi idle)

Migration cost?
  Bulk data transfer TB/PB → Snow Family
  Online incremental → DataSync
  DB migration + CDC → DMS
```

---

# MASTER COMPARISON TABLES

## Bảng 1: Messaging — SQS vs SNS vs EventBridge vs Kinesis vs MSK

| | SQS | SNS | EventBridge | Kinesis Streams | MSK |
|---|---|---|---|---|---|
| Model | Queue | Pub/Sub | Event bus | Stream | Kafka |
| Consumer | Competing | All subscribers | Rules-based | Multiple consumers | Kafka consumers |
| Ordering | FIFO only | ❌ | ❌ | Per shard | Per partition |
| Retention | 4d (14d max) | Push only | Push only | 24h-365d | Configurable |
| Replay | ❌ | ❌ | ❌ (Archive: limited) | ✅ | ✅ |
| **Trigger** | Decouple, buffer | Fanout | Routing, SaaS, schedule | Real-time stream | Kafka workload |

## Bảng 2: Storage

| | S3 | EBS | EFS | FSx Windows | FSx Lustre |
|---|---|---|---|---|---|
| Type | Object | Block | NFS | SMB | Lustre |
| Multi-AZ | ✅ | ❌ | ✅ | ✅ option | ❌ Scratch/✅ Persistent |
| Multi-instance | ✅ | ❌ | ✅ | ✅ | ✅ |
| OS | Any | Linux/Win | Linux | Windows | Linux |
| **Khi nào** | Object, archive | Single EC2 disk | Shared Linux | Windows + AD | HPC/ML |

## Bảng 3: CloudFront vs Global Accelerator

| | CloudFront | Global Accelerator |
|---|---|---|
| Layer | 7 HTTP/HTTPS | 3/4 TCP/UDP |
| Caching | ✅ | ❌ |
| Static IP | ❌ | ✅ (2 anycast IPs) |
| Protocol | HTTP/HTTPS/WebSocket | TCP/UDP |
| Use case | Web/CDN | Gaming, VoIP, TCP non-HTTP |

## Bảng 4: VPC Connectivity

| Scenario | Solution |
|---|---|
| 2-3 VPC connect đơn giản | VPC Peering |
| Nhiều VPC hub-and-spoke | Transit Gateway |
| Expose service cho VPC/account khác | PrivateLink |
| Private S3/DynamoDB | Gateway Endpoint |
| Private AWS service khác | Interface Endpoint |
| On-prem → AWS nhanh | Site-to-Site VPN |
| On-prem → AWS dedicated | Direct Connect |
| 1 DX → nhiều VPC nhiều Region | Direct Connect Gateway |
| On-prem cần private S3 qua DX | Interface Endpoint (không phải Gateway) |

## Bảng 5: Database Selection

| Nhu cầu | Service |
|---|---|
| Relational SQL, chuẩn | RDS |
| Relational + scale đọc tốt, failover nhanh | Aurora |
| Relational serverless, workload không đều | Aurora Serverless v2 |
| Relational + global low latency, RPO giây | Aurora Global Database |
| Key-value/document, scale lớn | DynamoDB |
| DynamoDB + microsecond read | DAX |
| DynamoDB multi-Region active-active | DynamoDB Global Tables |
| Session cache, general cache | ElastiCache Redis |
| Analytics warehouse | Redshift |
| Ad-hoc query on S3 | Athena |
| Full-text search | OpenSearch |
| Time-series data | Timestream |

## Bảng 6: Security Services

| Threat | Service |
|---|---|
| SQLi, XSS, HTTP flood, bot | WAF |
| DDoS volumetric | Shield |
| Deep packet inspection VPC | Network Firewall |
| Threat detection (compromise, C2) | GuardDuty |
| PII/sensitive data in S3 | Macie |
| Vulnerability EC2/ECR/Lambda | Inspector |
| Security findings aggregation | Security Hub |
| Security incident investigation | Detective |
| API audit trail | CloudTrail |
| Config compliance/drift | AWS Config |
| Metrics/alarms/logs | CloudWatch |

## Bảng 7: IAM & Access Control

| Nhu cầu | Solution |
|---|---|
| Workload AWS gọi service khác | IAM Role |
| EKS pod, least-privilege | IRSA |
| Cross-account | AssumeRole (STS) |
| Multi-account SSO | IAM Identity Center |
| Multi-account guardrail | Organizations + SCP |
| Landing zone | Control Tower |
| Share resource cross-account | RAM |
| Limit permissions của entity | Permission Boundary |
| Web/mobile user authenticate | Cognito User Pool |
| AWS creds cho app user | Cognito Identity Pool |
| EC2 access không SSH/bastion | SSM Session Manager |

## Bảng 8: Hybrid Connectivity & Data Transfer

| Nhu cầu | Service |
|---|---|
| Hybrid link nhanh | Site-to-Site VPN |
| Hybrid link dedicated, stable | Direct Connect |
| 1 DX nhiều VPC nhiều Region | Direct Connect Gateway |
| Many VPCs + on-prem hub-spoke | Transit Gateway |
| Hybrid file access (NFS/SMB interface) | Storage Gateway File Gateway |
| Block storage on-prem → S3 backup | Storage Gateway Volume Gateway |
| Online data migration | DataSync |
| Database migration + CDC | DMS |
| Managed SFTP/FTPS/AS2 | Transfer Family |
| Bulk data TB/PB | Snow Family |

## Bảng 9: EC2 Pricing

| Workload | Model |
|---|---|
| Steady, dài hạn, instance type ổn định | Reserved Instance |
| Steady, dài hạn, hay đổi type/region | Compute Savings Plan |
| Batch, tolerant interruption | Spot |
| Short-term, unpredictable | On-Demand |
| Compliance, BYOL | Dedicated Host |

## Bảng 10: S3 Storage Classes

| Class | Retrieval | Min | Best for |
|---|---|---|---|
| Standard | Ngay | — | Hot data |
| Standard-IA | Ngay | 30d | Backup ít truy cập |
| One Zone-IA | Ngay | 30d | Non-critical, re-creatable |
| Intelligent-Tiering | Varies | — | Unknown pattern |
| Glacier Instant | Ngay | 90d | Archive + instant access |
| Glacier Flexible | Phút-giờ | 90d | Archive + vài giờ OK |
| Glacier Deep Archive | 12-48h | 180d | Long-term compliance |

## Bảng 11: API Gateway Types

| | REST API | HTTP API | WebSocket API |
|---|---|---|---|
| Cost | $3.50/1M | $1.00/1M | $1.00/1M |
| Features | Full | Simplified | Bidirectional |
| VPC Link | ✅ | ✅ | ❌ |
| **Khi nào** | Full features needed | Simple serverless | Real-time chat/gaming |

## Bảng 12: Compute Comparison

| Service | Khi nào thắng |
|---|---|
| Lambda | Event-driven ≤15 phút, bursty, stateless |
| EC2 | Full OS control, legacy, job dài |
| ECS/Fargate | Container, ít ops, serverless container |
| EKS | Kubernetes ecosystem |
| Batch | Batch CPU-intensive, queue |
| Elastic Beanstalk | PaaS, web app, ít code change |
| App Runner | Container đơn giản, no VPC |

---

# TRAP CATALOG — 35 Bẫy Thường Xuyên

1. **Read Replica cho HA production** → sai; phải Multi-AZ.
2. **Multi-AZ cho scale đọc** → sai; phải Read Replica / Aurora Replica.
3. **Parameter Store khi cần auto rotation DB credentials** → sai; Secrets Manager.
4. **NAT Gateway cho private subnet → S3/DynamoDB** → sai; Gateway Endpoint (miễn phí).
5. **CloudFront cho UDP/TCP** → sai; Global Accelerator.
6. **EBS cho shared storage nhiều instance/AZ** → sai; EFS.
7. **S3 làm POSIX file system trực tiếp cho app legacy** → sai; Storage Gateway hoặc EFS.
8. **EKS pod dùng Node Instance Profile thay IRSA** → sai; IRSA là least-privilege.
9. **Tự viết Lambda cron để rotate secret** → sai; Secrets Manager native rotation.
10. **Security Group để deny một IP cụ thể** → sai; NACL có deny rule.
11. **CloudWatch khi đề hỏi audit API call** → sai; CloudTrail.
12. **CloudTrail khi đề hỏi metric/alarm CPU** → sai; CloudWatch.
13. **AWS Config khi đề hỏi ai gọi API** → sai; CloudTrail; Config là cho resource state.
14. **GuardDuty khi đề hỏi PII trong S3** → sai; Macie.
15. **Macie khi đề hỏi threat detection** → sai; GuardDuty.
16. **WAF để chặn DDoS volumetric** → sai; Shield.
17. **Shield để chặn SQLi/XSS** → sai; WAF.
18. **VPN khi đề nhấn dedicated, predictable, throughput lớn** → sai; Direct Connect.
19. **Direct Connect khi đề nhấn triển khai nhanh** → sai; VPN.
20. **DynamoDB cho workload SQL joins phức tạp** → sai; RDS/Aurora.
21. **RDS cho key-value scale cực lớn, single-digit ms** → sai; DynamoDB.
22. **DAX như cache chung cho mọi backend** → sai; DAX chỉ cho DynamoDB.
23. **CloudFront cho non-HTTP traffic** → sai; Global Accelerator.
24. **Snapshot/backup cho failover nhanh** → sai; Multi-AZ hoặc warm standby.
25. **Active-active đắt tiền khi đề chỉ cần active-passive DR** → overbuild.
26. **CNAME tại apex domain** → sai; phải Alias record.
27. **ACM cert deploy trực tiếp lên EC2** → sai; ACM chỉ cho ALB, CloudFront, API GW.
28. **CloudFront cert ở region khác us-east-1** → sai; phải request ở us-east-1.
29. **OAI thay OAC cho S3 private origin** → OAI là cách cũ; OAC là recommended.
30. **Gateway Endpoint cho on-prem truy cập S3 qua DX** → sai; cần Interface Endpoint.
31. **VPC Peering khi cần transitive routing** → sai; VPC Peering non-transitive; cần Transit Gateway.
32. **Visibility timeout ngắn khi xử lý lâu** → message xuất hiện lại → duplicate processing.
33. **Bastion host khi đề yêu cầu không mở port, không SSH** → sai; SSM Session Manager.
34. **Kinesis Streams khi chỉ cần delivery managed vào S3** → overkill; dùng Firehose.
35. **SNS khi đề cần queue semantics, retry, back-pressure** → sai; SQS.

---

# LAST-MINUTE RULES — 50 Rules

## Security (Rules 1-20)

1. `Rotate + DB credentials + least ops` → **Secrets Manager**.
2. `Config/feature flag, không rotation` → **Parameter Store**.
3. `Cross-account encryption` → **Customer Managed KMS Key** + key policy.
4. `WORM, kể cả root không xóa` → **S3 Object Lock Compliance Mode**.
5. `PII in S3` → **Macie**.
6. `Threat detection, account compromise, C2` → **GuardDuty**.
7. `SQLi/XSS/HTTP flood/rate limit` → **WAF**.
8. `DDoS` → **Shield** (Advanced nếu đề nhấn advanced protection).
9. `Deep packet inspection VPC` → **Network Firewall**.
10. `Ai gọi API gì, lúc nào` → **CloudTrail**.
11. `Config compliance, drift, resource state` → **AWS Config**.
12. `Metric, alarm, log, dashboard` → **CloudWatch**.
13. `Single pane of glass security` → **Security Hub**.
14. `Investigate security incident root cause` → **Amazon Detective**.
15. `Block specific IP` → **NACL** (không phải Security Group).
16. `Guardrail mọi account trong OU` → **SCP**.
17. `Centralized SSO nhiều account` → **IAM Identity Center**.
18. `EKS pod least-privilege` → **IRSA**.
19. `ACM cert cho CloudFront` → **Request ở us-east-1**.
20. `EC2 access không SSH, không open port, không bastion` → **SSM Session Manager**.

## Resilience (Rules 21-35)

21. `Apex domain Route 53` → **Alias record** (không phải CNAME).
22. `HA relational DB` → **Multi-AZ**.
23. `Scale đọc relational DB` → **Read Replica / Aurora Replica**.
24. `Aurora global, RPO giây` → **Aurora Global Database**.
25. `Connection burst Lambda/ECS → DB` → **RDS Proxy**.
26. `Message bị xử lý 2 lần` → **Tăng SQS Visibility Timeout**.
27. `Ordering + dedup` → **SQS FIFO**.
28. `SQS payload > 256 KB` → **S3 + SQS Extended Client Library**.
29. `Fanout 1 event nhiều hệ` → **SNS**.
30. `Event routing theo rule, SaaS, schedule` → **EventBridge**.
31. `Workflow nhiều bước, retry, timeout` → **Step Functions**.
32. `Backup tập trung nhiều service + compliance` → **AWS Backup**.
33. `DR cross-Region → RPO/RTO → chọn strategy`.
34. `Failover DNS` → **Route 53 Failover Routing + Health Check**.
35. `Nhiều VPC cần hub-and-spoke` → **Transit Gateway**.

## Performance (Rules 36-45)

36. `Global HTTP cache, CDN` → **CloudFront**.
37. `Global TCP/UDP, anycast static IP` → **Global Accelerator + NLB**.
38. `Simple logic ở edge` → **CloudFront Functions**.
39. `Complex logic ở edge` → **Lambda@Edge**.
40. `Shared POSIX storage nhiều EC2` → **EFS**.
41. `Windows SMB + AD` → **FSx for Windows**.
42. `HPC throughput cao + S3` → **FSx for Lustre**.
43. `DynamoDB microsecond read` → **DAX**.
44. `Session cache / general cache` → **ElastiCache Redis**.
45. `Ad-hoc query on S3` → **Athena**.

## Cost (Rules 46-50)

46. `Private subnet → S3/DynamoDB → bill NAT cao` → **Gateway VPC Endpoint** (miễn phí).
47. `Workload intermittent/bursty` → **Lambda/Fargate** rẻ hơn EC2 always-on.
48. `Workload steady dài hạn` → **Savings Plans / Reserved**.
49. `Batch, chịu interrupt` → **Spot** (tới 90% discount).
50. `Right-sizing EC2/Lambda` → **AWS Compute Optimizer**.

---
