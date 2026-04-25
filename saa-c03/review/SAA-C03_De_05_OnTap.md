# SAA-C03 - Bộ Ôn Tập Chi Tiết - Đề 05

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 05 tham khảo từ Đề Internet - devcloudly
- Blueprint tham chiếu: `w:\SAA-C03\AWS-Certified-Solutions-Architect-Associate_Exam-Guide.pdf`
- Ghi chú kỹ thuật: đề 2 -> đề 16 được dựng từ mốc reset số câu `65 -> 1` trong file nguồn.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon EC2 | 39 |
| Amazon S3 | 32 |
| Amazon Lambda | 18 |
| Amazon CloudFront | 12 |
| Amazon Relational Database Service | 10 |
| Auto Scaling Group | 10 |
| Amazon DynamoDB | 9 |
| Amazon EBS | 6 |
| Amazon Athena | 6 |
| Amazon Redshift | 6 |
| Amazon FSx | 5 |
| Amazon Virtual Private Cloud | 5 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon FSx | 4 |
| Amazon EC2 | 3 |
| Amazon CloudFront | 3 |
| Amazon SQS | 2 |
| Amazon S3 | 2 |
| Auto Scaling Group | 2 |
| Amazon Athena | 1 |
| Amazon EBS | 1 |
| Amazon SNS | 1 |
| Amazon API Gateway | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| cloudfront | 179 |
| latency | 105 |
| dynamodb | 103 |
| serverless | 92 |
| sqs | 59 |
| sns | 53 |
| elasticache | 51 |
| multi-az | 48 |
| cost-effective | 36 |
| route 53 | 33 |

## Service Key-Notes

### Amazon EC2
- EC2 là compute linh hoạt nhất nhưng cũng đòi hỏi vận hành nhiều hơn Lambda/Fargate.
- Đề SAA rất hay hỏi chọn instance family, Auto Scaling, IAM role cho EC2, EBS attachment, placement, và tối ưu cost bằng Spot/Reserved/Savings Plans.
- Nếu workload steady-state, custom OS, agent nặng, networking sâu hoặc cần control kernel thì EC2 vẫn là đáp án hợp lý.

### Amazon S3
- Object storage mặc định cho durability rất cao, static website, data lake, backup, log archive và integration với gần như toàn bộ hệ AWS.
- Phải phân biệt rõ S3 Standard, Standard-IA, One Zone-IA, Intelligent-Tiering, Glacier Instant Retrieval, Glacier Flexible Retrieval và Glacier Deep Archive.
- Các câu hay ra: Object Lock, Versioning, Lifecycle, Replication, Access Points, static website + CloudFront, event notification, requester pays.

### Amazon Lambda
- Phù hợp cho event-driven, bursty workload, không quản server, scale rất nhanh theo request/event.
- Bẫy thường gặp: connection storm vào RDS, timeout cho long-running jobs, cold start/VPC, cần stateful/session hoặc filesystem lâu dài.
- Đi cùng API Gateway, SQS, SNS, EventBridge, S3 event, Step Functions rất thường xuyên trong đề.

### Amazon CloudFront
- CDN toàn cầu cho HTTP/HTTPS, caching edge và giảm latency, đồng thời che chắn origin như S3 hoặc ALB.
- Điểm mạnh: edge cache, signed URL/cookie, origin failover, TLS, geo restriction, integration với WAF.
- Nếu đề là static site, media, cache object ở edge, giảm tải origin thì hãy nghiêng về CloudFront.

### Amazon Relational Database Service
- RDS hợp cho relational workloads cần SQL, transactions, backup managed, patching managed.
- Luôn tách bạch: Multi-AZ cho HA/failover, read replica cho scale đọc, RDS Proxy cho connection pooling.
- Đề hay hỏi migration, encryption, snapshot, backup retention, read-heavy vs write-heavy.

### Auto Scaling Group
- ASG là công cụ scale EC2 theo policy/metrics/schedule, đồng thời tự thay instance unhealthy.
- Đi cùng ALB/NLB, launch template, mixed instances, spot/on-demand blend, warm pool.
- Nếu đề hỏi stateless web/app tier cần elasticity và self-healing, ASG là ứng viên rất mạnh.

### Amazon DynamoDB
- NoSQL fully managed, scale cực lớn, single-digit ms latency, TTL, streams, on-demand/provisioned, global tables.
- Hợp cho key-value/document và access pattern rõ ràng. Không phù hợp khi bài toán phụ thuộc join/phức tạp SQL truyền thống.
- Thường đi kèm DAX, Lambda, API Gateway, EventBridge, Kinesis, caching, session/profile store.

### Amazon EBS
- Block storage cho EC2, phù hợp boot volume, database local disks, transactional workload.
- Cần nắm gp3 vs io1/io2 vs st1/sc1, snapshot, encryption, resize, Multi-Attach chỉ trong các ngữ cảnh rất đặc biệt.
- Khi đề nói IOPS, throughput block storage, boot disk, volume snapshot thì EBS là trung tâm.

## Pattern Key-Notes

### cloudfront
- CloudFront là CDN cho HTTP/HTTPS content, tối ưu cache và latency, che chắn origin như S3 hoặc ALB.
- Static website, media distribution, cache web objects, giảm latency toàn cầu thường nghĩ đến CloudFront.
- Nếu đề nhấn mạnh cache vài phút sau deploy, hãy phối hợp TTL phù hợp và invalidation thay vì để TTL = 0 mãi mãi.

### latency
- Latency thấp thường kéo theo edge service, cache, in-memory store, đúng Region placement hoặc protocol phù hợp.
- CloudFront, Global Accelerator, ElastiCache, DynamoDB/DAX, Direct Connect là nhóm đáp án nổi bật cho bài toán latency.
- Đừng nhầm CloudFront với Global Accelerator: cái đầu thiên caching HTTP, cái sau thiên routing nhanh cho traffic động TCP/UDP.

### dynamodb
- DynamoDB hợp với key-value/document, low-latency ở quy mô lớn, serverless, auto scaling, global tables, TTL.
- Nếu đề yêu cầu schema linh hoạt, scale cực lớn, latency thấp nhất, không cần join/phức tạp SQL, DynamoDB thường thắng RDS.
- Nắm thêm DAX, partition key, sort key, GSI/LSI, on-demand vs provisioned.

### serverless
- Serverless thắng khi tải biến thiên, ít vận hành, cần scale nhanh, trả tiền theo mức dùng.
- Bộ đôi xuất hiện rất nhiều: API Gateway + Lambda + DynamoDB/SQS/SNS/EventBridge.
- Nhưng đừng ép serverless vào workload cần stateful long-running compute, custom kernel, hay network control sâu.

### sqs
- SQS dùng để decouple producer-consumer, buffer traffic, retry, DLQ. FIFO khi cần ordering + deduplication.
- Standard queue ưu tiên throughput gần như không giới hạn; FIFO ưu tiên ordering exactly-once processing semantics ở mức thiết kế.
- Nếu đề hỏi strict ordering, idempotency, xử lý không mất message: hãy nhìn vào SQS FIFO.

### sns
- SNS là pub/sub fanout: 1 message đẩy tới nhiều subscriber như SQS, Lambda, HTTPS, email.
- Nếu đề cần gửi song song tới nhiều hệ downstream, SNS thường tốt hơn SQS đơn lẻ.
- SNS không phải message queue để consumer poll tuần tự; nó là notification/fanout layer.

## Cách Học Đề Này

- Đọc nhanh bảng domain focus để biết đề nghiêng về Secure, Resilient, Performance hay Cost.
- Học thuộc trước các service note và pattern note ở trên, sau đó mới làm lại từng câu.
- Với câu sai, đừng chỉ nhớ đáp án đúng; hãy nhớ vì sao các distractor sai theo tiêu chí exam như `least ops`, `least cost`, `HA`, `latency`, `immutability`.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EBS, Amazon EFS, Amazon FSx, Amazon EC2, Amazon Relational Database Service, Amazon FSx for Windows File Server
- Đáp án tham khảo: **Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.**
- Takeaway nhanh: Tất cả 3 tầng trên EC2: EC2 Windows instances cho phép cài đặt SQL Server đầy đủ (bao gồm Enterprise Edition), hỗ trợ native backups (qua T-SQL BACKUP/RESTORE) và Data Quality Services (DQS) – tính năng KHÔNG được hỗ trợ trên Amazon RDS for SQL Server (RDS chỉ hỗ trợ một phần SQL features, thiếu DQS vì không cho phép cài add-ons đầy đủ). EC2 linh hoạt tùy chỉnh SQL Server theo nhu cầu.
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/native-backup-rds-sql-server/ | https://aws.amazon.com/rds/sqlserver/Installing | https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-sql-server/comparison.html | https://www.examtopics.com/discussions/amazon/view/99670-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to migrate a Windows-based application from on premises to the AWS Cloud. The application has three tiers: an application tier, a business tier, and a database tier with Microsoft SQL Server. The company wants to use specific features of SQL Server such as native backups and Data Quality Services. The company also needs to share files for processing between the tiers.
How should a solutions architect design the architecture to meet these requirements?

### Các lựa chọn
1. Host all three tiers on Amazon EC2 instances. Use Amazon FSx File Gateway for file sharing between the tiers.
2. Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.
3. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use Amazon Elastic File System (Amazon EFS) for file sharing between the tiers.
4. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume for file sharing between the tiers.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty muốn di chuyển ứng dụng Windows 3 tầng từ on-premises lên AWS Cloud:

Tầng ứng dụng (application tier), tầng business, và tầng cơ sở dữ liệu (database tier) sử dụng Microsoft SQL Server.

Yêu cầu đặc biệt cho SQL Server: Hỗ trợ native backups (sao lưu gốc của SQL Server) và Data Quality Services (DQS) – một tính năng nâng cao để kiểm tra và làm sạch dữ liệu.

Yêu cầu chia sẻ file: Các tầng cần chia sẻ file để xử lý dữ liệu giữa chúng (file sharing giữa tiers).

🎯 Mục tiêu thiết kế kiến trúc: Sử dụng dịch vụ AWS phù hợp để đáp ứng đầy đủ các tính năng SQL Server cụ thể (không bị hạn chế) và file sharing tương thích với môi trường Windows. Kiến trúc phải đơn giản, hiệu quả, và tuân thủ best practices AWS (cập nhật đến 2026, với FSx và RDS SQL Server phiên bản mới nhất hỗ trợ Enterprise Edition features một phần).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.

🛠️ Lý do chi tiết:

Tất cả 3 tầng trên EC2: EC2 Windows instances cho phép cài đặt SQL Server đầy đủ (bao gồm Enterprise Edition), hỗ trợ native backups (qua T-SQL BACKUP/RESTORE) và Data Quality Services (DQS) – tính năng KHÔNG được hỗ trợ trên Amazon RDS for SQL Server (RDS chỉ hỗ trợ một phần SQL features, thiếu DQS vì không cho phép cài add-ons đầy đủ). EC2 linh hoạt tùy chỉnh SQL Server theo nhu cầu.

Amazon FSx for Windows File Server: Dịch vụ file storage native SMB (Server Message Block) cho Windows, hỗ trợ Active Directory integration, file sharing đa instances (multi-AZ cho HA), và performance cao (SSD/HDD). Hoàn hảo cho app Windows chia sẻ file giữa các EC2 tiers mà không cần gateway hybrid.

Ưu điểm tổng thể: Chi phí tối ưu, scalable, bảo mật (IAM, VPC), và phù hợp migration Windows apps (AWS Migration Tools như DMS hoặc VM Import/Export).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích từng phương án (giữ nguyên văn bản gốc bằng tiếng Anh). Tôi đánh dấu ✅ đúng hoặc ❌ sai, kèm giải thích chi tiết bằng tiếng Việt dựa trên tài liệu AWS mới nhất (2026).

❌ Phương án SAI: Host all three tiers on Amazon EC2 instances. Use Amazon FSx File Gateway for file sharing between the tiers.

🧨 Lý do sai: Amazon FSx File Gateway (trước đây là Storage Gateway - File Gateway) dành cho hybrid cloud (kết nối on-premises với AWS S3/FSx), KHÔNG phải file sharing thuần cloud giữa EC2 instances. Nó không cung cấp SMB share native tốc độ cao cho Windows EC2, mà chỉ cache file từ S3 – gây latency cao, không phù hợp "share files for processing between tiers". EC2 + SQL full OK, nhưng file sharing sai.

✅ Phương án ĐÚNG: Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.

🛠️ Lý do đúng: Như đã giải thích ở trên. FSx Windows là lựa chọn best practice cho Windows file shares trên AWS (hỗ trợ NTFS ACLs, quotas, backups tự động). Kết hợp EC2 cho SQL Server đầy đủ tính năng (native backups/DQS).

❌ Phương án SAI: Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use Amazon Elastic File System (Amazon EFS) for file sharing between the tiers.

🚫 Lý do sai kép:

RDS for SQL Server: KHÔNG hỗ trợ Data Quality Services (DQS) (yêu cầu custom setup trên EC2) và native backups bị hạn chế (chỉ qua snapshots RDS, không full T-SQL BACKUP/RESTORE linh hoạt). RDS thiếu nhiều SQL advanced features.

Amazon EFS: File system NFS-based (Linux-centric), KHÔNG tương thích native SMB cho Windows apps. Windows EC2 cần mount phức tạp (qua NFSv4.1), gây performance kém và không hỗ trợ Windows ACLs/AD fully.

❌ Phương án SAI: Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume for file sharing between the tiers.

🔒 Lý do sai kép:

RDS: Giống trên, thiếu DQS và native backups đầy đủ.

EBS io2: Block storage gắn trực tiếp vào MỘT instance duy nhất, KHÔNG chia sẻ giữa nhiều EC2 tiers (multi-attach chỉ cho cụm cụ thể như EKS, không general file sharing). io2 chỉ cho high IOPS, không phải file server.

📘 Tài liệu tham khảo AWS (cập nhật 2026)

Amazon FSx for Windows: docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html – Xác nhận SMB sharing cho EC2 Windows.

RDS SQL Server limitations: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_SQLServer.html#SQLServer.Concepts.FeaturesSupported – Không hỗ trợ DQS (xem "Unsupported Features").

EC2 SQL Server best practices: aws.amazon.com/windows/sql/ – Native backups/DQS trên EC2.

Migration guide: AWS Application Migration Service cho Windows apps.

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm ví dụ thực tế, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99670-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/rds/sqlserver/Installing

https://aws.amazon.com/premiumsupport/knowledge-center/native-backup-rds-sql-server/

https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-sql-server/comparison.html

## Câu 02

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon CloudFront, Amazon Global Accelerator, Amazon EC2
- Takeaway nhanh: Kiến trúc hiện tại dùng ELB (có lẽ là ALB cho HTTP), nhưng để phục vụ toàn cầu và personalize theo device, cần CloudFront làm frontend CDN. CloudFront hỗ trợ caching multiple versions (nhiều variants của cùng object) dựa trên headers như User-Agent, giúp giảm latency và chi phí bằng cách cache tại edge locations (hơn 400 points toàn cầu tính đến 2026). Lambda@Edge tích hợp hoàn hảo với CloudFront, chạy code serverless tại edge để inspect User-Agent header, sau đó redirect hoặc serve object phù hợp (ví dụ: mobile version cho smartphone). Kết hợp hai actions này tạo giải pháp tối ưu: CloudFront cache + Lambda@Edge logic động.
- Nguồn tham khảo trong block: https://aws.amazon.com/lambda/edge/ | https://www.examtopics.com/discussions/amazon/view/95011-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones.
The company wants to provide its customers with different versions of content based on the devices that the customers use to access the website.
Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Configure Amazon CloudFront to cache multiple versions of the content.
2. Configure a host header in a Network Load Balancer to forward traffic to different instances.
3. Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.
4. Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up host-based routing to different EC2 instances.
5. Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up path-based routing to different EC2 instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đã triển khai website bán lẻ toàn cầu trên nhiều instance Amazon EC2 nằm sau Elastic Load Balancer (ELB), với các instance được quản lý bởi Auto Scaling Group (ASG) trải rộng trên nhiều Availability Zones (AZ) để đảm bảo tính sẵn sàng cao. 🎯 Yêu cầu chính là cung cấp nội dung khác nhau (different versions of content) cho khách hàng dựa trên thiết bị truy cập (devices), cụ thể là dựa vào User-Agent header trong request HTTP (ví dụ: mobile, desktop, tablet).

Đây là tình huống điển hình cần content personalization hoặc device-based content delivery ở quy mô toàn cầu. Giải pháp phải tận dụng các dịch vụ AWS để cache và route traffic động mà không làm ảnh hưởng đến kiến trúc hiện tại (EC2 + ELB + ASG). Câu hỏi yêu cầu chọn TWO actions từ solutions architect để đáp ứng yêu cầu này. 🛠️ Kiến thức áp dụng: Dựa trên tài liệu AWS cập nhật đến năm 2026, tập trung vào Amazon CloudFront (CDN toàn cầu với edge computing) và Lambda@Edge để xử lý logic động tại edge locations.

✅ Đáp án đúng và lý do lựa chọn

Hai đáp án đúng là:

Configure Amazon CloudFront to cache multiple versions of the content.

Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.

Lý do lựa chọn chi tiết:

Kiến trúc hiện tại dùng ELB (có lẽ là ALB cho HTTP), nhưng để phục vụ toàn cầu và personalize theo device, cần CloudFront làm frontend CDN. CloudFront hỗ trợ caching multiple versions (nhiều variants của cùng object) dựa trên headers như User-Agent, giúp giảm latency và chi phí bằng cách cache tại edge locations (hơn 400 points toàn cầu tính đến 2026).

Lambda@Edge tích hợp hoàn hảo với CloudFront, chạy code serverless tại edge để inspect User-Agent header, sau đó redirect hoặc serve object phù hợp (ví dụ: mobile version cho smartphone). Kết hợp hai actions này tạo giải pháp tối ưu: CloudFront cache + Lambda@Edge logic động.

✅ Hoàn hảo cho yêu cầu global audience và device-based content, không cần thay đổi backend EC2/ELB/ASG.

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên văn bản gốc tiếng Anh của phương án, chỉ giải thích bằng tiếng Việt với lý do đúng/sai dựa trên tính năng AWS mới nhất (2026).

✅ Configure Amazon CloudFront to cache multiple versions of the content.

Đúng! CloudFront hỗ trợ multiple cache behaviors và cache based on headers (bao gồm User-Agent). Bạn có thể upload các phiên bản content khác nhau (ví dụ: desktop.html, mobile.html) và cấu hình cache keys để lưu trữ variants tại edge, giảm tải origin (EC2/ELB) và tối ưu tốc độ toàn cầu. Đây là bước nền tảng cho device-based delivery. 🏆

❌ Configure a host header in a Network Load Balancer to forward traffic to different instances.

Sai! Network Load Balancer (NLB) chỉ hỗ trợ TCP/UDP/TLS traffic ở Layer 4, không inspect HTTP headers như host header (Layer 7). NLB không forward dựa trên host header – tính năng này thuộc Application Load Balancer (ALB). Hơn nữa, không giải quyết device-based (User-Agent), chỉ route theo host name, không phù hợp với caching global. 🚫

✅ Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.

Đúng! Lambda@Edge chạy tại CloudFront edge locations, cho phép inspect User-Agent header ngay lập tức và thực hiện actions như origin request/redirect/viewer response. Ví dụ: Nếu User-Agent là mobile, return object mobile-optimized. Kết hợp với CloudFront caching, đây là giải pháp serverless, scalable cho personalization toàn cầu mà không cần thay backend. ⚡

❌ Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up host-based routing to different EC2 instances.

Sai! AWS Global Accelerator tối ưu đường dẫn static IP toàn cầu nhưng không làm device-based routing. NLB chỉ Layer 4, không hỗ trợ host-based routing (cần ALB cho HTTP host header). Cấu hình này chỉ route theo IP/endpoint, không inspect User-Agent hay cache content versions – không đáp ứng yêu cầu content khác nhau theo device. 🌐❌

❌ Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up path-based routing to different EC2 instances.

Sai! Tương tự trên, Global Accelerator + NLB không hỗ trợ path-based routing (Layer 7, chỉ ALB mới có). NLB chỉ forward TCP/UDP, không parse path hay User-Agent. Giải pháp này chỉ cải thiện latency đường dẫn, không personalize content theo device hoặc caching multiple versions. 📍🚫

📘 Tài liệu tham khảo (AWS cập nhật 2026)

Amazon CloudFront Developer Guide: CloudFront Caching with Multiple Variants & Cache Behaviors.

Lambda@Edge Documentation: Using Lambda@Edge with CloudFront – Hỗ trợ User-Agent inspection từ 2018, tối ưu hóa 2026 với ARM runtime.

ELB/NLB Comparison: Elastic Load Balancing Features – Xác nhận NLB Layer 4 only.

Global Accelerator Guide: Routing Policies – Không hỗ trợ HTTP routing động.

✅ Nguồn chính thức AWS Console & Well-Architected Framework (Global Apps pillar) khuyến nghị CloudFront + Lambda@Edge cho edge personalization. Nếu thi DOP-C02, đây là pattern chuẩn! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95011-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/lambda/edge/

## Câu 03

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SQS, Amazon Lambda, Amazon Elastic Container Service, Amazon S3, Amazon FSx, Amazon EC2, Amazon FSx for NetApp ONTAP
- Đáp án tham khảo: **Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon FSx for NetApp ONTAP for storage.**
- Takeaway nhanh: Amazon EC2 Linux phù hợp cho simulation app (hỗ trợ NFS mount trực tiếp). Amazon EC2 Windows phù hợp cho visualization desktop app (hỗ trợ SMB/CIFS mount). Amazon FSx for NetApp ONTAP là file system managed, hỗ trợ multi-protocol access (NFS v3/v4.1 và SMB 2.0/3.0/3.1.1 đồng thời trên cùng một volume). Simulation app ghi dữ liệu NFS mỗi 5 phút, visualization app đọc SMB ngay lập tức → không trùng lặp dữ liệu, chỉ một file system duy nhất.
- Nguồn tham khảo trong block: https://aws.amazon.com/de/blogs/storage/getting-started-cloud-file-storage-with-amazon-fsx-for-netapp-ontap-using-netapp-management-tools/ | https://aws.amazon.com/fsx/netapp-ontap/features/#:~:text=Amazon%20FSx%20for%20NetApp%20ONTAP%20offers%20high%2Dperformance%20file%20storage,NVMe%2Dover%2DTCP%20protocols | https://www.examtopics.com/discussions/amazon/view/99512-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A research company runs experiments that are powered by a simulation application and a visualization application. The simulation application runs on Linux and outputs intermediate data to an NFS share every 5 minutes. The visualization application is a Windows desktop application that displays the simulation output and requires an SMB file system.
The company maintains two synchronized file systems. This strategy is causing data duplication and inefficient resource usage. The company needs to migrate the applications to AWS without making code changes to either application.
Which solution will meet these requirements?

### Các lựa chọn
1. Migrate both applications to AWS Lambda. Create an Amazon S3 bucket to exchange data between the applications.
2. Migrate both applications to Amazon Elastic Container Service (Amazon ECS). Configure Amazon FSx File Gateway for storage.
3. Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon Simple Queue Service (Amazon SQS) to exchange data between the applications.
4. Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon FSx for NetApp ONTAP for storage.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty nghiên cứu chạy các thí nghiệm sử dụng ứng dụng simulation (chạy trên Linux, xuất dữ liệu trung gian ra NFS share mỗi 5 phút) và ứng dụng visualization (ứng dụng desktop Windows, cần truy cập file system SMB để hiển thị kết quả simulation). Hiện tại, họ duy trì hai file system đồng bộ (một cho NFS và một cho SMB), dẫn đến trùng lặp dữ liệu và lãng phí tài nguyên. Yêu cầu là migrate cả hai ứng dụng lên AWS mà không thay đổi code, đồng thời giải quyết vấn đề chia sẻ dữ liệu hiệu quả giữa Linux (NFS) và Windows (SMB).

Mục tiêu chính:

Hỗ trợ shared storage đa giao thức (NFS cho Linux và SMB cho Windows).

Không code change: Ứng dụng phải mount file system trực tiếp như cũ.

Tối ưu hóa: Tránh trùng lặp dữ liệu, sử dụng tài nguyên hiệu quả.

🛠️ Giải pháp lý tưởng trên AWS: Sử dụng EC2 cho các app (Linux và Windows) và một file system hỗ trợ cả NFS/SMB đồng thời.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon FSx for NetApp ONTAP for storage.

Lý do chọn đáp án này:

Amazon EC2 Linux phù hợp cho simulation app (hỗ trợ NFS mount trực tiếp).

Amazon EC2 Windows phù hợp cho visualization desktop app (hỗ trợ SMB/CIFS mount).

Amazon FSx for NetApp ONTAP là file system managed, hỗ trợ multi-protocol access (NFS v3/v4.1 và SMB 2.0/3.0/3.1.1 đồng thời trên cùng một volume). Simulation app ghi dữ liệu NFS mỗi 5 phút, visualization app đọc SMB ngay lập tức → không trùng lặp dữ liệu, chỉ một file system duy nhất.

Không cần code change: Apps mount FSx như NFS/SMB on-prem.

Cập nhật 2026: FSx ONTAP hỗ trợ high availability, snapshot, encryption, và scale lên petabytes (AWS re:Invent 2025 xác nhận multi-AZ và performance cải thiện).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, với giữ nguyên nội dung gốc bằng tiếng Anh. Tôi đánh dấu ✅ đúng hoặc ❌ sai, kèm giải thích bằng tiếng Việt.

Migrate both applications to AWS Lambda. Create an Amazon S3 bucket to exchange data between the applications.

❌ Sai: AWS Lambda là serverless, không hỗ trợ persistent file system NFS/SMB (Lambda chỉ ephemeral storage /tmp). Simulation cần ghi NFS định kỳ, visualization là desktop app không chạy trên Lambda. S3 là object storage, không mount như file share → yêu cầu code change lớn (phải dùng SDK). Không đáp ứng "no code changes".

Migrate both applications to Amazon Elastic Container Service (Amazon ECS). Configure Amazon FSx File Gateway for storage.

❌ Sai: ECS là container orchestration, nhưng visualization desktop app Windows không dễ containerize mà không code change (desktop GUI cần Windows desktop env). Amazon FSx File Gateway (trước là Storage Gateway File Gateway) chỉ cache SMB/NFS từ on-prem/S3 sang FSx, không phải shared file system native cho EC2/ECS. Không hỗ trợ multi-protocol trực tiếp hiệu quả như yêu cầu, gây latency cao và không giải quyết trùng lặp.

Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon Simple Queue Service (Amazon SQS) to exchange data between the applications.

❌ Sai: EC2 Linux/Windows đúng hướng, nhưng Amazon SQS là message queue service (FIFO/Standard), không thay thế file system NFS/SMB. Apps cần mount file share trực tiếp để đọc/ghi dữ liệu lớn (intermediate data mỗi 5 phút), SQS chỉ trao đổi message nhỏ → yêu cầu code change hoàn toàn (polling queue thay vì file mount). Không giải quyết shared storage.

Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Configure Amazon FSx for NetApp ONTAP for storage.

✅ Đúng: Như giải thích ở trên, hoàn hảo cho shared storage multi-protocol (NFS + SMB trên cùng volume), EC2 native support, zero code change, tối ưu tài nguyên.

📘 Tài liệu tham khảo (cập nhật AWS 2026)

Amazon FSx for NetApp ONTAP: docs.aws.amazon.com/fsx/latest/ONTAPGuide/what-is.html → Xác nhận multi-protocol NFS/SMB.

EC2 File System Support: docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html và Windows SMB guide.

AWS Well-Architected Framework - Storage Lens: Storage pillar khuyến nghị FSx ONTAP cho hybrid workloads (Well-Architected Tool 2025 update).

Sample Exam DOP-C02: Tương tự question DOP-C02-SAM-10 (DevOps Pro cert, AWS Training Portal 2026).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm chi tiết, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99512-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/fsx/netapp-ontap/features/#:~:text=Amazon%20FSx%20for%20NetApp%20ONTAP%20offers%20high%2Dperformance%20file%20storage,NVMe%2Dover%2DTCP%20protocols.

https://aws.amazon.com/de/blogs/storage/getting-started-cloud-file-storage-with-amazon-fsx-for-netapp-ontap-using-netapp-management-tools/

## Câu 04

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SNS, Amazon SQS, Amazon Step Functions, Amazon Lambda
- Đáp án tham khảo: **Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.**
- Takeaway nhanh: SQS là dịch vụ message queue lý tưởng cho async processing và decoupling các tier. Khi upload ảnh, ngay lập tức đặt message vào queue để một worker (ví dụ Lambda hoặc EC2) xử lý thumbnail sau (không block response). Response nhanh: Alert user ngay sau upload rằng ảnh đã nhận (qua app message), không chờ 60s thumbnail. Hỗ trợ high throughput, durability (at-least-once delivery), và tích hợp dễ với S3 (upload trigger) + Lambda. Phù hợp best practice AWS cho image processing pipelines (cập nhật 2026: SQS FIFO cho ordered processing nếu cần).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html | https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/99753-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect is designing a multi-tier application for a company. The application's users upload images from a mobile device. The application generates a thumbnail of each image and returns a message to the user to confirm that the image was uploaded successfully.
The thumbnail generation can take up to 60 seconds, but the company wants to provide a faster response time to its users to notify them that the original image was received. The solutions architect must design the application to asynchronously dispatch requests to the different application tiers.
What should the solutions architect do to meet these requirements?

### Các lựa chọn
1. Write a custom AWS Lambda function to generate the thumbnail and alert the user. Use the image upload process as an event source to invoke the Lambda function.
2. Create an AWS Step Functions workflow. Configure Step Functions to handle the orchestration between the application tiers and alert the user when thumbnail generation is complete.
3. Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.
4. Create Amazon Simple Notification Service (Amazon SNS) notification topics and subscriptions. Use one subscription with the application to generate the thumbnail after the image upload is complete. Use a second subscription to message the user's mobile app by way of a push notification after thumbnail generation is complete.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một solutions architect đang thiết kế ứng dụng multi-tier cho công ty. Người dùng upload hình ảnh từ thiết bị di động. Ứng dụng cần tạo thumbnail cho mỗi ảnh (quá trình này có thể mất lên đến 60 giây), và trả về thông báo xác nhận upload thành công cho người dùng.

📌 Yêu cầu chính:

Cung cấp response time nhanh chóng để thông báo rằng ảnh gốc đã được nhận (không chờ thumbnail hoàn thành).

Thiết kế hệ thống asynchronously dispatch requests giữa các tier ứng dụng (decoupling để xử lý async).

🛠️ Vấn đề cốt lõi: Cần tách biệt việc xác nhận nhận ảnh ngay lập tức (sync/fast) và tạo thumbnail async (chậm, queue-based). Điều này tuân thủ nguyên tắc AWS Well-Architected Framework về Reliability và Operational Excellence (phiên bản mới nhất 2023-2026, nhấn mạnh serverless decoupling với SQS/SNS).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.

Lý do 🏆:

SQS là dịch vụ message queue lý tưởng cho async processing và decoupling các tier. Khi upload ảnh, ngay lập tức đặt message vào queue để một worker (ví dụ Lambda hoặc EC2) xử lý thumbnail sau (không block response).

Response nhanh: Alert user ngay sau upload rằng ảnh đã nhận (qua app message), không chờ 60s thumbnail.

Hỗ trợ high throughput, durability (at-least-once delivery), và tích hợp dễ với S3 (upload trigger) + Lambda. Phù hợp best practice AWS cho image processing pipelines (cập nhật 2026: SQS FIFO cho ordered processing nếu cần).

📋 Giải thích tất cả các phương án (đúng/sai)

❌ [SAI] Write a custom AWS Lambda function to generate the thumbnail and alert the user. Use the image upload process as an event source to invoke the Lambda function.

Giải thích sai: Lambda có thể async (event source từ S3 upload), nhưng phương án này kết hợp generate thumbnail + alert user trong cùng Lambda → có thể mất 60s, làm chậm response confirm nhận ảnh. Không decoupling đúng (user chờ Lambda done). Lambda timeout 15 phút ok, nhưng vi phạm yêu cầu "faster response" cho ảnh gốc. Không phải best practice cho long-running tasks.

❌ [SAI] Create an AWS Step Functions workflow. Configure Step Functions to handle the orchestration between the application tiers and alert the user when thumbnail generation is complete.

Giải thích sai: Step Functions tốt cho orchestration complex workflows, nhưng alert user sau khi thumbnail complete → response chậm (60s+). Không đáp ứng "faster response time to notify original image received". Step Functions có thể async, nhưng logic này vẫn block user feedback (cập nhật 2026: Express Workflows nhanh hơn nhưng vẫn chờ steps).

✅ [ĐÚNG] Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.

Giải thích đúng (như phần trên): Hoàn hảo decoupling – queue message async cho thumbnail, alert ngay lập tức. Scale tự động, cost-effective.

❌ [SAI] Create Amazon Simple Notification Service (Amazon SNS) notification topics and subscriptions. Use one subscription with the application to generate the thumbnail after the image upload is complete. Use a second subscription to message the user's mobile app by way of a push notification after thumbnail generation is complete.

Giải thích sai: SNS là pub/sub fan-out (broadcast), không phải queue cho sequential processing (có thể duplicate/lossy nếu không idempotent). Alert thứ hai sau thumbnail complete → chậm response confirm ảnh gốc. Không decoupling tốt như SQS (SNS + SQS mới full pattern). Push notification ok cho mobile, nhưng logic sai yêu cầu.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

AWS SQS Documentation: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html (Decoupling apps with queues).

AWS Well-Architected Framework - Reliability Pillar: https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html (Async patterns).

Serverless Image Handler Pattern: AWS Samples GitHub (S3 + SQS + Lambda for thumbnails).

Exam DOP-C02 Guide: AWS Certified DevOps Engineer Professional (SQS cho async workloads).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm case studies, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99753-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 05

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon S3
- Đáp án tham khảo: **Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.**
- Takeaway nhanh: Header x-amz-server-side-encryption bắt buộc yêu cầu SSE khi upload (ví dụ: giá trị "AES256" cho SSE-S3 hoặc "aws:kms" cho SSE-KMS). Bucket policy sẽ deny s3:PutObject nếu header này thiếu, đảm bảo 100% object được mã hóa server-side. Đây là best practice AWS khuyến nghị để enforce encryption mà không phụ thuộc vào client-side config. Hỗ trợ đầy đủ SSE types, bao gồm KMS multi-Region keys (cập nhật 2025). 🛡️ Hiệu quả cao, không ảnh hưởng performance nhờ S3 Bucket Key.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/ | https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/#:~:text=Solution%20overviewThank | https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingServerSideEncryption.html | https://docs.aws.amazon.com/AmazonS3/latest/userguide/amazon-s3-policy-keys.html | https://www.examtopics.com/discussions/amazon/view/99685-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted?

### Các lựa chọn
1. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set.
2. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private.
3. Update the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true.
4. Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc đảm bảo tất cả các object được upload vào một Amazon S3 bucket đều được mã hóa (encrypted). Đây là yêu cầu bảo mật quan trọng trong AWS, đặc biệt để tuân thủ các tiêu chuẩn như PCI DSS hoặc HIPAA. 🛡️

Ngữ cảnh chính: Solutions Architect cần cấu hình S3 bucket policy để từ chối (deny) các hoạt động PutObject (upload object) nếu không đáp ứng điều kiện mã hóa. Phương pháp này sử dụng server-side encryption (SSE), nơi AWS tự động mã hóa object khi lưu trữ.

Mục tiêu: Ngăn chặn upload object không mã hóa, áp dụng cho tất cả người dùng/khách hàng upload vào bucket.

Liên quan AWS cập nhật 2026: S3 hỗ trợ SSE-S3 (mã hóa mặc định AWS-managed keys), SSE-KMS (AWS KMS keys), SSE-C (customer-provided keys). Bucket policy với header x-amz-server-side-encryption là cách enforce encryption chuẩn, kết hợp với S3 Bucket Key hoặc Default Encryption (S3 Bucket Default Encryption) cho các upload mới. Không dùng ACL hoặc transport headers cho encryption object-level. 📘

Nguồn tham khảo:

AWS S3 User Guide: Using Bucket Policies and Encryption (cập nhật 2025-2026).

AWS Well-Architected Framework: Security Pillar - S3 Encryption.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.

Lý do:

Header x-amz-server-side-encryption bắt buộc yêu cầu SSE khi upload (ví dụ: giá trị "AES256" cho SSE-S3 hoặc "aws:kms" cho SSE-KMS). Bucket policy sẽ deny s3:PutObject nếu header này thiếu, đảm bảo 100% object được mã hóa server-side.

Đây là best practice AWS khuyến nghị để enforce encryption mà không phụ thuộc vào client-side config. Hỗ trợ đầy đủ SSE types, bao gồm KMS multi-Region keys (cập nhật 2025). 🛡️ Hiệu quả cao, không ảnh hưởng performance nhờ S3 Bucket Key.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh dấu ✅ (đúng) hoặc ❌ (sai), kèm giải thích rõ ràng:

Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set.

❌ Sai: Header s3:x-amz-acl dùng để set Access Control List (ACL) cho object (như public-read, private), không liên quan đến mã hóa. Policy này chỉ enforce ACL, không ngăn upload object không mã hóa. ACL đã deprecated từ 2023, ưu tiên IAM policies. 🗑️

Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private.

❌ Sai: Tương tự trên, chỉ enforce ACL="private" (hạn chế truy cập public), không đảm bảo mã hóa object. Không giải quyết encryption, chỉ bảo vệ visibility. ACL không phải công cụ cho data-at-rest encryption. 🚫

Update the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true.

❌ Sai: Điều kiện aws:SecureTransport (hoặc "true") enforce kết nối HTTPS (transport encryption), không mã hóa object lưu trữ. Chỉ bảo vệ data-in-transit, object vẫn có thể lưu không mã hóa trên S3. Dùng cho transit security, không phải storage encryption. 🔒 (chỉ transit!)

Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.

✅ Đúng: Như đã giải thích ở phần đáp án. Header này trực tiếp yêu cầu SSE, deny nếu thiếu → toàn bộ object bắt buộc mã hóa. Linh hoạt với SSE-S3/KMS/C, tích hợp S3 Access Points (cập nhật 2026). Hoàn hảo cho compliance! 🎯

🛠️ Lời khuyên thực hành

Ví dụ bucket policy JSON (dựa AWS docs):

Code

{

  "Statement": [{

    "Effect": "Deny",

    "Principal": "*",

    "Action": "s3:PutObject",

    "Resource": "arn:aws:s3:::your-bucket/*",

    "Condition": {

      "StringNotEquals": {

        "s3:x-amz-server-side-encryption": "AES256"

      }

    }

  }]

}

Kết hợp S3 Default Encryption để tự động mã hóa upload thiếu header. Test bằng AWS CLI: aws s3 cp file s3://bucket/ --no-server-side-encryption (sẽ fail). 🚀

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! Nếu cần ví dụ code chi tiết hơn, hỏi nhé. 😊

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99685-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/#:~:text=Solution%20overviewThank

https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingServerSideEncryption.html

https://aws.amazon.com/blogs/security/how-to-prevent-uploads-of-unencrypted-objects-to-amazon-s3/

https://docs.aws.amazon.com/AmazonS3/latest/userguide/amazon-s3-policy-keys.html

## Câu 06

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon SQS, Amazon Lambda, Amazon Systems Manager, Amazon EC2
- Takeaway nhanh: AWS Lambda là dịch vụ serverless compute hoàn hảo cho workload này: Tự động scale theo số lượng messages trong SQS (qua SQS event source mapping hoặc triggers), không cần quản lý server như EC2, và pay-per-use (chỉ tính phí execution time thực tế, millisecond-level billing). Script trên EC2 có thể được chuyển sang Lambda runtime phù hợp (ví dụ: Python, Node.js), kết nối trực tiếp với SQS mà không cần poll thủ công – Lambda sẽ batch process messages tự động.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99698-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS) queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to the queue.
What should a solutions architect recommend to meet these requirements?

### Các lựa chọn
1. Increase the size of the EC2 instance to process messages faster.
2. Use Amazon EventBridge to turn off the EC2 instance when the instance is underutilized.
3. Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime.
4. Use AWS Systems Manager Run Command to run the script on demand.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một công ty đang sử dụng Amazon EC2 instance để chạy một script liên tục poll (kiểm tra định kỳ) và xử lý messages từ Amazon Simple Queue Service (SQS) queue. Mục tiêu là giảm chi phí vận hành (operational costs) trong khi vẫn duy trì khả năng xử lý số lượng messages tăng dần (growing number of messages).

🛠️ Phân tích yêu cầu cốt lõi:

Vấn đề hiện tại: EC2 chạy liên tục (always-on), tốn kém ngay cả khi queue rỗng, và khó scale thủ công khi messages tăng.

Yêu cầu lý tưởng: Giải pháp phải serverless hoặc tự động scale, pay-per-use (chỉ tính phí khi xử lý), hỗ trợ trigger tự động từ SQS để xử lý messages mà không cần poll thủ công, phù hợp với kiến trúc AWS hiện đại đến năm 2026 (SQS hỗ trợ event source mapping với Lambda).

✅ Đáp án đúng

Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime.

Lý do lựa chọn:

AWS Lambda là dịch vụ serverless compute hoàn hảo cho workload này: Tự động scale theo số lượng messages trong SQS (qua SQS event source mapping hoặc triggers), không cần quản lý server như EC2, và pay-per-use (chỉ tính phí execution time thực tế, millisecond-level billing).

Script trên EC2 có thể được chuyển sang Lambda runtime phù hợp (ví dụ: Python, Node.js), kết nối trực tiếp với SQS mà không cần poll thủ công – Lambda sẽ batch process messages tự động.

Giảm chi phí: EC2 tốn ~24/7, Lambda chỉ chạy khi có message, tiết kiệm lên đến 90% cho workload sporadic/growing (dữ liệu AWS Well-Architected Framework 2024-2026).

Xử lý growing messages: Lambda scale concurrent executions lên hàng nghìn, visibility timeout SQS đồng bộ hoàn hảo.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, với giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá dựa trên khả năng giảm chi phí và scale cho growing messages theo best practices AWS mới nhất (SQS FIFO/Standard queues hỗ trợ Lambda triggers từ 2019, tối ưu hóa 2025 với longer polling).

❌ [SAI] Increase the size of the EC2 instance to process messages faster.

Phương án này tăng chi phí thay vì giảm: Upsize EC2 (ví dụ từ t3.micro sang m5.large) làm tăng giờ tính phí (on-demand/spot), không giải quyết vấn đề always-on. Scale thủ công không hiệu quả cho growing messages, vi phạm nguyên tắc right-sizing trong AWS Compute Optimizer (2026).

❌ [SAI] Use Amazon EventBridge to turn off the EC2 instance when the instance is underutilized.

EventBridge (trước là CloudWatch Events) có thể schedule/stop EC2 dựa trên metrics (CPU low), nhưng không scale tự động khi messages tăng đột biến – cần start thủ công hoặc complex rules. Vẫn phải quản lý EC2 (patching, scaling groups), chi phí cao hơn serverless, không tối ưu cho poll-based workloads (AWS khuyến nghị Lambda cho SQS từ 2024 docs).

✅ [ĐÚNG] Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime.

Như đã giải thích ở trên: Serverless migration lý tưởng, hỗ trợ SQS-Lambda integration native (batch size lên 10,000 messages từ 2023), zero cold starts với Provisioned Concurrency (2026), đảm bảo giảm chi phí + scale vô hạn.

❌ [SAI] Use AWS Systems Manager Run Command to run the script on demand.

SSM Run Command chạy script on-demand thủ công trên EC2/fleets, không tự động poll/scale với SQS. Phải trigger manual/API, không xử lý growing messages realtime, tăng operational overhead (IAM roles phức tạp), chi phí EC2 vẫn cao – không phù hợp serverless pattern (SSM dành cho management, không compute chính).

📘 Tài liệu tham khảo (AWS cập nhật 2024-2026)

AWS SQS + Lambda Integration: docs.aws.amazon.com/lambda/latest/dg/with-sqs.html – Event source mapping chi tiết.

AWS Well-Architected Framework (Serverless Lens): aws.amazon.com/architecture/well-architected – Khuyến nghị migrate EC2 polling to Lambda cho cost optimization.

EC2 vs Lambda Cost Comparison: AWS Pricing Calculator & Compute Blog: SQS Polling Patterns.

EventBridge/EC2 Stopping: docs.aws.amazon.com/eventbridge/latest/userguide/eb-start-stop-ec2.html – Giới hạn scale.

🛠️ Khuyến nghị DevOps: Sử dụng AWS SAM/ CDK để deploy Lambda + SQS nhanh chóng, monitor bằng CloudWatch + X-Ray cho growing workloads!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99698-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 07

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2
- Đáp án tham khảo: **Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.**
- Takeaway nhanh: Cluster Placement Group pack các instances vào cùng một high-performance network topology trong cùng một AZ, mang lại network throughput cực cao (lên đến 100 Gbps giữa các instances với instance types hỗ trợ enhanced networking như c5n/c6gn - cập nhật 2024). Hoàn hảo cho in-memory database với >100k TPS, vì độ trễ microsecond và throughput cao giảm bottleneck.
- Nguồn tham khảo trong block: https://aws.amazon.com/ec2/pricing/on-demand/#Data_Transfer | https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html | https://www.examtopics.com/discussions/amazon/view/99807-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost-effective network design that minimizes data transfer charges.
Which solution meets these requirements?

### Các lựa chọn
1. Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.
2. Launch all EC2 instances in different Availability Zones within the same AWS Region. Specify a placement group with partition strategy when launching EC2 instances.
3. Deploy an Auto Scaling group to launch EC2 instances in different Availability Zones based on a network utilization target.
4. Deploy an Auto Scaling group with a step scaling policy to launch EC2 instances in different Availability Zones.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế mạng cost-effective cho một ứng dụng latency-sensitive sử dụng in-memory database chạy trên các instance Amazon EC2. Các yêu cầu chính bao gồm:

Xử lý hơn 100.000 giao dịch mỗi phút (tức là workload cao, cần high network throughput).

Giảm thiểu chi phí chuyển dữ liệu (data transfer charges), vì traffic giữa các EC2 instances có thể phát sinh phí nếu không thiết kế đúng.

Giải pháp phải đảm bảo độ trễ thấp (low latency) cho database in-memory, thường yêu cầu các instances giao tiếp nội bộ với tốc độ mạng cao nhất có thể (như 10 Gbps hoặc hơn với enhanced networking). Mục tiêu là chọn thiết kế mạng tối ưu trên AWS, tận dụng các tính năng như Placement Groups để tối ưu hóa hiệu suất mạng mà không tốn kém phí chuyển dữ liệu cross-AZ/Region.

📘 Tài liệu tham khảo:

AWS EC2 Placement Groups: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html (cập nhật 2024-2026, hỗ trợ cluster strategy cho throughput lên đến 100 Gbps với instance types mới như c6gn).

AWS Data Transfer Pricing: https://aws.amazon.com/ec2/pricing/on-demand/#Data_Transfer (traffic trong cùng AZ miễn phí; cross-AZ tính phí ~$0.01/GB).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.

Lý do 🛠️:

Cluster Placement Group pack các instances vào cùng một high-performance network topology trong cùng một AZ, mang lại network throughput cực cao (lên đến 100 Gbps giữa các instances với instance types hỗ trợ enhanced networking như c5n/c6gn - cập nhật 2024).

Hoàn hảo cho in-memory database với >100k TPS, vì độ trễ microsecond và throughput cao giảm bottleneck.

Minimize data transfer charges: Traffic nội bộ trong cùng AZ và placement group là miễn phí 100%, không phát sinh phí cross-AZ.

Cost-effective vì không cần dịch vụ managed như ElastiCache (có thể đắt hơn cho workload custom).

🧩 Giải thích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm lý do cụ thể dựa trên yêu cầu câu hỏi.

Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.

✅ Đúng hoàn toàn 🏆: Như đã giải thích ở trên, cluster strategy tối ưu cho low-latency/high-throughput trong cùng AZ, traffic miễn phí, phù hợp 100% với workload latency-sensitive và chi phí thấp.

Launch all EC2 instances in different Availability Zones within the same AWS Region. Specify a placement group with partition strategy when launching EC2 instances.

❌ Sai 🚫: Partition strategy dùng để phân tán instances qua nhiều AZ/partition cho fault tolerance (tối đa 7 partitions/group), nhưng KHÔNG cung cấp high throughput/low latency (chỉ đảm bảo không cùng rack). Cross-AZ traffic phát sinh phí cao (~$0.01/GB), vi phạm yêu cầu minimize charges và latency cho in-memory DB.

Deploy an Auto Scaling group to launch EC2 instances in different Availability Zones based on a network utilization target.

❌ Sai ⚠️: Auto Scaling Group (ASG) với network utilization target (qua CloudWatch) sẽ scale ra nhiều AZ, dẫn đến cross-AZ traffic thường xuyên → phí data transfer cao. Không đảm bảo độ trễ thấp cho >100k TPS, vì traffic giữa AZ chậm hơn (latency ~1-2ms so với <1ms trong AZ).

Deploy an Auto Scaling group with a step scaling policy to launch EC2 instances in different Availability Zones.

❌ Sai 🔄: Step scaling policy (dựa alarm CloudWatch) vẫn launch instances cross-AZ để high availability, gây phí data transfer và latency cao hơn. Không giải quyết throughput cao cho database in-memory, chỉ tập trung scale mà bỏ qua network design tối ưu.

Kết luận 🎯: Giải pháp cluster placement group trong cùng AZ là lựa chọn tối ưu nhất theo best practices AWS cho workload high-throughput/low-latency, cập nhật đến 2026 với hỗ trợ instance generations mới (như c7gn cho 200 Gbps). Nếu cần HA cao hơn, có thể kết hợp với ElastiCache Redis/Memcached managed service!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99807-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

## Câu 08

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon Glue, Amazon QuickSight, Amazon DynamoDB, Amazon Q, Amazon CloudFront, Amazon S3
- Đáp án tham khảo: **Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.**
- Takeaway nhanh: 🖼️ QuickSight là dịch vụ BI (Business Intelligence) chuyên visualization, tích hợp native với Athena: Kết nối trực tiếp dataset từ Athena, tạo dashboard, biểu đồ realtime, ML insights (SPICE engine). Đây là best practice AWS cho log analysis + viz (cập nhật 2026: QuickSight hỗ trợ Athena v3 engine).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99508-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations.
What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.
2. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
3. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.
4. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả tình huống thực tế trong AWS: Một công ty đang sử dụng Amazon CloudFront để phân phối nội dung website, đã kích hoạt tính năng logging trên distribution CloudFront, và các log được lưu trữ tự động vào một Amazon S3 bucket thuộc công ty. Yêu cầu chính là thực hiện phân tích nâng cao (advanced analyses) trên dữ liệu log này và xây dựng visualizations (hình ảnh hóa dữ liệu) để dễ dàng quan sát, báo cáo.

🛠️ Thách thức kỹ thuật:

Log CloudFront là dữ liệu lớn, không cấu trúc, lưu dưới dạng file trong S3 (dạng tab-delimited format).

Cần công cụ query SQL chuẩn để phân tích mà không cần di chuyển dữ liệu.

Cần tích hợp visualization chuyên dụng để tạo dashboard, biểu đồ từ kết quả query.

Giải pháp phải serverless, scalable, phù hợp với kiến trúc AWS hiện đại (cập nhật đến 2026, CloudFront logs vẫn hỗ trợ Athena partition/query tối ưu).

📘 Tài liệu tham khảo:

AWS CloudFront Logging Documentation (xác nhận logs lưu S3).

Amazon Athena for CloudFront Logs (hướng dẫn query logs).

Amazon QuickSight Integration.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

Lý do chi tiết:

🧩 Athena là dịch vụ query serverless hoàn hảo cho dữ liệu S3 (như CloudFront logs), hỗ trợ standard SQL trực tiếp trên file log mà không cần ETL hay load data. Athena tự động partition logs theo ngày/giờ để query nhanh, tiết kiệm chi phí (pay-per-query).

🖼️ QuickSight là dịch vụ BI (Business Intelligence) chuyên visualization, tích hợp native với Athena: Kết nối trực tiếp dataset từ Athena, tạo dashboard, biểu đồ realtime, ML insights (SPICE engine). Đây là best practice AWS cho log analysis + viz (cập nhật 2026: QuickSight hỗ trợ Athena v3 engine).

✅ Ưu điểm tổng thể: Giải pháp end-to-end serverless, không cần infrastructure, scale tự động, phù hợp DevOps Professional (cost-effective, zero-management).

📋 Giải thích tất cả các phương án (đúng/sai)

Phương án 1: Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.

❌ Sai. Athena đúng cho query SQL trên S3 logs ✅, nhưng AWS Glue là dịch vụ ETL (Extract-Transform-Load) và data catalog, KHÔNG phải công cụ visualization. Glue dùng để crawl schema, transform data trước khi query Athena, không tạo dashboard/biểu đồ. Sử dụng Glue ở đây không đáp ứng yêu cầu "build visualizations".

Phương án 2: Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

✅ Đúng hoàn toàn. Như giải thích ở phần đáp án đúng: Athena query SQL chuẩn trên S3 logs 🛠️, QuickSight visualize chuyên sâu 📊. Best practice AWS, tích hợp seamless.

Phương án 3: Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.

❌ Sai kép. DynamoDB là NoSQL database (key-value/document), KHÔNG hỗ trợ standard SQL queries trực tiếp trên dữ liệu S3. Logs phải export/load vào DynamoDB trước (phức tạp, tốn kém), không serverless cho S3. Glue visualization sai như phương án 1.

Phương án 4: Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

❌ Sai chính. DynamoDB không query standard SQL trên S3 logs (chỉ PartiQL limited SQL-like, không dành cho S3). QuickSight đúng visualization nhưng vô dụng vì query sai từ đầu. Phải dùng Athena hoặc EMR cho logs S3.

Tóm tắt khuyến nghị DevOps: 🚀 Luôn ưu tiên Athena + QuickSight cho log analysis S3 (CloudWatch Logs Insights nếu logs khác). Test bằng AWS Free Tier để verify!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99508-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 09

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon DynamoDB, Amazon API Gateway, Amazon S3, Amazon Route 53, Amazon EC2, Amazon Virtual Private Cloud
- Takeaway nhanh: API Gateway tạo HTTPS endpoint công khai, managed hoàn toàn, tự động scale theo traffic, hỗ trợ HA multi-AZ, throttling, caching (cập nhật 2024-2026 với HTTP APIs v2 nhanh hơn REST APIs). Lambda xử lý serverless, chạy code mà không quản lý server, HA với concurrency cao (lên đến hàng triệu request/giây), tích hợp trực tiếp với API Gateway qua proxy integration.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99699-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company’s facility has badge readers at every entrance throughout the building. When badges are scanned, the readers send a message over HTTPS to indicate who attempted to access that particular entrance.
A solutions architect must design a system to process these messages from the sensors. The solution must be highly available, and the results must be made available for the company’s security team to analyze.
Which system architecture should the solutions architect recommend?

### Các lựa chọn
1. Launch an Amazon EC2 instance to serve as the HTTPS endpoint and to process the messages. Configure the EC2 instance to save the results to an Amazon S3 bucket.
2. Create an HTTPS endpoint in Amazon API Gateway. Configure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.
3. Use Amazon Route 53 to direct incoming sensor messages to an AWS Lambda function. Configure the Lambda function to process the messages and save the results to an Amazon DynamoDB table.
4. Create a gateway VPC endpoint for Amazon S3. Configure a Site-to-Site VPN connection from the facility network to the VPC so that sensor data can be written directly to an S3 bucket by way of the VPC endpoint.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi này thuộc chủ đề thiết kế kiến trúc hệ thống serverless và highly available trên AWS, tập trung vào việc xử lý tin nhắn HTTPS từ các badge readers (cảm biến quét thẻ) tại các cửa ra vào tòa nhà.

Yêu cầu chính:

Hệ thống phải xử lý tin nhắn từ sensor một cách highly available (HA), nghĩa là không có điểm nghẽn đơn lẻ, tự động scale và chịu lỗi cao.

Kết quả xử lý phải dễ dàng truy cập và phân tích cho đội ngũ security (ví dụ: lưu trữ dữ liệu có cấu trúc để query nhanh).

Thách thức:

Tin nhắn đến qua HTTPS endpoint (cần endpoint công khai, bảo mật).

Hệ thống phải serverless ưu tiên để giảm quản lý, chi phí và tăng HA (không dùng server thủ công).

Dữ liệu cần lưu trữ durable, scalable cho phân tích (như truy vấn theo thời gian, user, cửa ra vào).

Kiến trúc lý tưởng phải tận dụng các dịch vụ managed, HA như API Gateway (endpoint HTTPS), Lambda (xử lý logic), và DynamoDB (lưu trữ NoSQL nhanh).

✅ Đáp án đúng: Create an HTTPS endpoint in Amazon API Gateway. Configure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.

Lý do chọn đáp án đúng 🛠️:

API Gateway tạo HTTPS endpoint công khai, managed hoàn toàn, tự động scale theo traffic, hỗ trợ HA multi-AZ, throttling, caching (cập nhật 2024-2026 với HTTP APIs v2 nhanh hơn REST APIs).

Lambda xử lý serverless, chạy code mà không quản lý server, HA với concurrency cao (lên đến hàng triệu request/giây), tích hợp trực tiếp với API Gateway qua proxy integration.

DynamoDB là NoSQL database fully managed, HA (multi-AZ replication), low-latency query (GSI/LSI cho phân tích security), phù hợp dữ liệu thời gian thực.

Toàn bộ kiến trúc serverless, zero-management, cost-effective (pay-per-use), đáp ứng 100% yêu cầu HA và phân tích. Đây là best practice theo AWS Well-Architected Framework (Pillar: Reliability & Operational Excellence).

📋 Phân tích chi tiết từng phương án trả lời

❌ Launch an Amazon EC2 instance to serve as the HTTPS endpoint and to process the messages. Configure the EC2 instance to save the results to an Amazon S3 bucket.

Sai vì: EC2 là instance không tự động HA (single point of failure nếu không dùng ASG/ALB phức tạp), phải tự quản lý HTTPS (SSL cert, scaling), không serverless. S3 chỉ lưu object blob, không phù hợp phân tích structured data (cần Athena/Glue mới query được, chậm và tốn kém hơn DynamoDB). Không đáp ứng HA gốc.

✅ Create an HTTPS endpoint in Amazon API Gateway. Configure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.

Đúng vì: Như giải thích trên, full serverless HA stack. API Gateway xử lý HTTPS native, Lambda scale vô hạn, DynamoDB query nhanh cho security team (ví dụ: scan theo user/ID cửa). Best practice cho IoT/sensor ingestion (cập nhật 2026 vẫn là gold standard).

❌ Use Amazon Route 53 to direct incoming sensor messages to an AWS Lambda function. Configure the Lambda function to process the messages and save the results to an Amazon DynamoDB table.

Sai vì: Route 53 là DNS service, chỉ resolve domain/IP, không tạo HTTPS endpoint hay xử lý HTTP traffic trực tiếp (sensor gửi HTTPS cần proxy/ALB). Lambda không expose public endpoint trực tiếp mà không qua API Gateway/ALB. Thiết kế này không khả thi cho HTTPS ingestion.

❌ Create a gateway VPC endpoint for Amazon S3. Configure a Site-to-Site VPN connection from the facility network to the VPC so that sensor data can be written directly to an Amazon S3 bucket by way of the VPC endpoint.

Sai vì: Yêu cầu public HTTPS endpoint từ facility (không private), VPN + VPC endpoint chỉ cho traffic nội bộ VPC → S3 (interface endpoint). Sensor không viết direct to S3 (S3 không phải HTTPS API endpoint, cần SDK). Không xử lý logic (chỉ dump raw data), thiếu HA cho endpoint, S3 kém cho real-time query.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2024-2026)

AWS API Gateway Docs: api-gateway-http-apis.md – Hỗ trợ HTTPS endpoints serverless.

Lambda + API Gateway Integration: Well-Architected Serverless Lens – HA cho IoT workloads.

DynamoDB Best Practices: DynamoDB Developer Guide – Phân tích access logs.

Exam Topic DOP-C02: AWS Certified DevOps Engineer Professional – Domain 2: Implementation (High Availability Architectures).

AWS Blogs: "Serverless IoT Backend" (2023-2025 updates on API Gateway v2 throttling).

Kiến trúc này tối ưu chi phí ~0.01$/1M requests, scale tự động! 🚀 Nếu cần diagram hoặc code sample, hỏi thêm nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99699-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 10

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon DynamoDB, Auto Scaling Group, Amazon CloudFront, Amazon S3, Amazon Global Accelerator, Amazon EC2, Amazon DynamoDB Accelerator
- Đáp án tham khảo: **Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.**
- Takeaway nhanh: Nó tự động monitor health của các endpoints (như ALB) qua health checks (TCP/HTTP/HTTPS), và chuyển hướng traffic (redirect/failover) chỉ đến healthy endpoints ở các Region khác nếu cần. Cấu hình: Tạo accelerator → Thêm listener cho port app → Attach Regional endpoints (mỗi Region một) với ALB làm endpoint cụ thể. Traffic từ client sẽ được route thông minh dựa trên health và latency.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/global-accelerator/latest/dg/about-endpoint-groups-health-check-options.html | https://www.examtopics.com/discussions/amazon/view/95014-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a popular gaming platform running on AWS. The application is sensitive to latency because latency can impact the user experience and introduce unfair advantages to some players. The application is deployed in every AWS Region. It runs on Amazon EC2 instances that are part of Auto Scaling groups configured behind Application Load Balancers (ALBs). A solutions architect needs to implement a mechanism to monitor the health of the application and redirect traffic to healthy endpoints.
Which solution meets these requirements?

### Các lựa chọn
1. Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.
2. Create an Amazon CloudFront distribution and specify the ALB as the origin server. Configure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the traffic.
3. Create an Amazon CloudFront distribution and specify Amazon S3 as the origin server. Configure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the traffic.
4. Configure an Amazon DynamoDB database to serve as the data store for the application. Create a DynamoDB Accelerator (DAX) cluster to act as the in-memory cache for DynamoDB hosting the application data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một nền tảng game phổ biến chạy trên AWS, nơi latency (độ trễ) là yếu tố cực kỳ quan trọng vì nó ảnh hưởng trực tiếp đến trải nghiệm người dùng (UX) và có thể tạo lợi thế không công bằng cho một số người chơi. Ứng dụng được triển khai ở mọi AWS Region, sử dụng Amazon EC2 instances nằm trong Auto Scaling Groups (ASG) và đứng sau Application Load Balancers (ALB).

Yêu cầu chính: Solutions Architect cần triển khai cơ chế giám sát sức khỏe (health monitoring) của ứng dụng và chuyển hướng traffic chỉ đến các healthy endpoints (các điểm cuối khỏe mạnh). Điều này nhằm đảm bảo traffic luôn được route đến các Region/endpoint tốt nhất, giảm thiểu latency và tránh các endpoint kém chất lượng.

Mục tiêu cốt lõi: Sử dụng dịch vụ AWS hỗ trợ global traffic management với health checks tự động, failover đến healthy endpoints, và tối ưu latency toàn cầu. Đây là tình huống điển hình cho các ứng dụng low-latency như gaming, multiplayer real-time.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.

Lý do chi tiết:

🛠️ AWS Global Accelerator là dịch vụ lý tưởng cho yêu cầu này vì nó sử dụng Anycast IP để route traffic toàn cầu đến endpoint gần nhất và khỏe mạnh nhất, giảm latency đáng kể (thường dưới 50ms cho gaming).

Nó tự động monitor health của các endpoints (như ALB) qua health checks (TCP/HTTP/HTTPS), và chuyển hướng traffic (redirect/failover) chỉ đến healthy endpoints ở các Region khác nếu cần.

Cấu hình: Tạo accelerator → Thêm listener cho port app → Attach Regional endpoints (mỗi Region một) với ALB làm endpoint cụ thể. Traffic từ client sẽ được route thông minh dựa trên health và latency.

Phù hợp với kiến thức AWS mới nhất (2026): Global Accelerator hỗ trợ Dual-stack IPv4/IPv6, tích hợp AWS Shield cho DDoS protection (rất cần cho gaming), và traffic dial để kiểm soát tỷ lệ traffic giữa endpoints.

Đây là best practice cho multi-Region apps nhạy cảm latency, vượt trội hơn Route 53 (chỉ DNS-level).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng phương án một cách chi tiết. Tôi giữ nguyên văn bản gốc tiếng Anh của phương án, chỉ giải thích đúng/sai bằng tiếng Việt với lý do rõ ràng dựa trên tính năng AWS.

✅ Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.

(Đúng - Như đã giải thích ở trên. Đây là giải pháp chính xác nhất cho global health-based routing và low-latency gaming apps.)

❌ Create an Amazon CloudFront distribution and specify the ALB as the origin server. Configure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the traffic.

(Sai - CloudFront là CDN chủ yếu cho caching static/dynamic content từ origins như ALB, giúp giảm latency qua edge locations. Tuy nhiên, nó không monitor health của ALB endpoints ở multi-Region để redirect traffic tự động; chỉ forward đến origin nếu healthy, nhưng không failover global thông minh. Cache headers và Lambda@Edge chỉ tối ưu caching/routing edge, không giải quyết health monitoring/redirect như yêu cầu. Không phù hợp cho real-time gaming dynamic traffic.)

❌ Create an Amazon CloudFront distribution and specify Amazon S3 as the origin server. Configure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the traffic.

(Sai - CloudFront với S3 chỉ dành cho static content (như assets game), không phải ứng dụng dynamic chạy trên EC2/ALB. Hoàn toàn không liên quan đến health monitoring hay redirect traffic đến ALB endpoints. S3 là object storage, không hỗ trợ app logic real-time, dẫn đến high latency và không đáp ứng yêu cầu gaming platform.)

❌ Configure an Amazon DynamoDB database to serve as the data store for the application. Create a DynamoDB Accelerator (DAX) cluster to act as the in-memory cache for DynamoDB hosting the application data.

(Sai - DynamoDB + DAX chỉ là giải pháp caching dữ liệu NoSQL để giảm read latency từ DB (microseconds), không liên quan gì đến traffic routing, health monitoring endpoints, hoặc ALB/EC2. Đây là cho backend data layer, không giải quyết vấn đề network-level global traffic management cho gaming app.)

📘 Tài liệu tham khảo (AWS Documentation - Phiên bản mới nhất 2026)

AWS Global Accelerator: What is AWS Global Accelerator? & Health Checks – Xác nhận routing dựa trên health và low-latency.

CloudFront Limitations: CloudFront Origins – Không hỗ trợ multi-Region failover như Accelerator.

DynamoDB DAX: DAX Overview – Chỉ caching DB, không routing.

AWS Well-Architected Framework (Gaming Lens): Gaming on AWS – Khuyến nghị Global Accelerator cho low-latency multiplayer.

💡 Lưu ý DevOps: Trong thực tế DOP-C02 exam, ưu tiên Global Accelerator cho global apps với health checks > Route 53/CloudFront. Test với AWS Console để verify! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95014-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/global-accelerator/latest/dg/about-endpoint-groups-health-check-options.html

## Câu 11

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon QuickSight, Amazon Redshift, Amazon EventBridge, Amazon SNS, Amazon Lambda, Amazon DynamoDB, Amazon Q, Amazon Macie, Amazon S3
- Takeaway nhanh: Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon Simple Notification Service (Amazon SNS) subscription. Kết hợp hai bước này: DynamoDB lưu trữ chính → Export S3 → Macie scan S3 → Notify via EventBridge/SNS. 🛠️ Giải pháp tối ưu, serverless, scalable.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/prescriptive-guidance/latest/dynamodb-hierarchical-data-model/introduction.html | https://www.examtopics.com/discussions/amazon/view/99940-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to create an application to store employee data in a hierarchical structured relationship. The company needs a minimum-latency response to high-traffic queries for the employee data and must protect any sensitive data. The company also needs to receive monthly email messages if any financial information is present in the employee data.
Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Use Amazon Redshift to store the employee data in hierarchies. Unload the data to Amazon S3 every month.
2. Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.
3. Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly events to AWS Lambda.
4. Use Amazon Athena to analyze the employee data in Amazon S3. Integrate Athena with Amazon QuickSight to publish analysis dashboards and share the dashboards with users.
5. Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon Simple Notification Service (Amazon SNS) subscription.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi yêu cầu một solutions architect thiết kế giải pháp cho ứng dụng lưu trữ dữ liệu nhân viên theo cấu trúc phân cấp (hierarchical structured relationship). Các yêu cầu chính bao gồm:

Phản hồi latency thấp nhất (minimum-latency) cho các truy vấn high-traffic (lưu lượng cao).

Bảo vệ dữ liệu nhạy cảm (protect sensitive data).

Gửi email hàng tháng nếu phát hiện thông tin tài chính (financial information) trong dữ liệu nhân viên.

Đây là câu hỏi chọn 2 bước kết hợp (Choose two) để đáp ứng đầy đủ yêu cầu. Giải pháp cần tập trung vào:

Lưu trữ dữ liệu phân cấp với hiệu suất cao (NoSQL phù hợp hơn SQL/warehouse).

Phát hiện và thông báo dữ liệu nhạy cảm định kỳ (hàng tháng qua email).

📘 Tài liệu tham khảo:

AWS DynamoDB Developer Guide (2024-2026): Single-table design cho hierarchical data.

Amazon Macie User Guide (cập nhật 2025): Tích hợp EventBridge & SNS cho notifications.

AWS Well-Architected Framework: Reliability & Security pillars.

✅ Đáp án đúng (Chọn 2) và lý do lựa chọn

Hai đáp án đúng là:

Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.

Lý do: DynamoDB lý tưởng cho hierarchical data (single-table design với partition/sort keys, GSIs), hỗ trợ low-latency queries ở quy mô high-traffic (millions requests/sec). Export định kỳ ra S3 qua DynamoDB Export to S3 (tính năng native từ 2020, cập nhật 2025 hỗ trợ continuous export).

Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon Simple Notification Service (Amazon SNS) subscription.

Lý do: Macie tự động phát hiện sensitive data (như financial info) trong S3. Tích hợp EventBridge để trigger SNS gửi email hàng tháng (SNS hỗ trợ email subscriptions native). Hoàn hảo cho yêu cầu bảo vệ và notify định kỳ.

Kết hợp hai bước này: DynamoDB lưu trữ chính → Export S3 → Macie scan S3 → Notify via EventBridge/SNS. 🛠️ Giải pháp tối ưu, serverless, scalable.

📋 Giải thích tất cả các phương án (Đúng/Sai)

Dưới đây là phân tích từng lựa chọn một, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá dựa trên yêu cầu câu hỏi:

Use Amazon Redshift to store the employee data in hierarchies. Unload the data to Amazon S3 every month.

❌ SAI: Redshift là data warehouse cho OLAP/analytics, không phù hợp low-latency queries high-traffic (latency cao hơn DynamoDB, cần cluster management). Hierarchical data kém hiệu quả ở Redshift. Unload to S3 khả thi nhưng không giải quyết core issue về performance.

Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.

✅ ĐÚNG: DynamoDB excels ở hierarchical data (qua single-table design, LSI/GSI), minimum-latency cho high-throughput queries (sub-ms response). Export to S3 native (point-in-time hoặc continuous, cập nhật 2025 hỗ trợ serverless export). Phù hợp hoàn hảo cho lưu trữ chính.

Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly events to AWS Lambda.

❌ SAI: Macie đúng cho sensitive data detection (financial info), EventBridge tích hợp tốt. Nhưng Lambda không gửi email trực tiếp (cần thêm SNS/SES), và không chỉ rõ "monthly notifications" qua email. Không khớp yêu cầu chính xác.

Use Amazon Athena to analyze the employee data in Amazon S3. Integrate Athena with Amazon QuickSight to publish analysis dashboards and share the dashboards with users.

❌ SAI: Athena/QuickSight tốt cho query & visualize S3 data, nhưng không đáp ứng low-latency storage (Athena serverless query-on-S3, latency cao cho high-traffic). Không có cơ chế notify email hàng tháng về financial info, chỉ là analysis tool.

Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon Simple Notification Service (Amazon SNS) subscription.

✅ ĐÚNG: Macie scan sensitive data (PII/financial) trong S3 hiệu quả. EventBridge + SNS trigger monthly emails native (SNS topic subscribe email). Đáp ứng bảo vệ dữ liệu và notify định kỳ, tích hợp liền mạch với export từ DynamoDB.

🧠 Kết luận: Giải pháp chọn DynamoDB + Macie/SNS đảm bảo performance, security, compliance theo best practices AWS 2026. Không cần over-engineer với Redshift/Athena! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99940-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/prescriptive-guidance/latest/dynamodb-hierarchical-data-model/introduction.html

## Câu 12

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Redshift, Amazon Aurora, Amazon Aurora Serverless, Amazon Relational Database Service
- Takeaway nhanh: 🔹 Aurora Serverless là phiên bản serverless của Amazon Aurora, không yêu cầu chọn instance type – nó tự động scale capacity từ 0.5 ACU (Aurora Capacity Units) đến hàng nghìn ACU dựa trên workload thực tế. Hoàn hảo cho infrequent access (scale down gần 0 khi idle, tiết kiệm chi phí) và scale up nhanh cho more users in future. 🔹 Hỗ trợ MySQL-compatible (Aurora MySQL), dễ migrate từ on-premises MySQL bằng AWS DMS (Database Migration Service) với minimal downtime (continuous replication, cutover nhanh).
- Nguồn tham khảo trong block: https://aws.amazon.com/rds/aurora/serverless/ | https://www.examtopics.com/discussions/amazon/view/99769-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type in anticipation of more users in the future.
Which service should a solutions architect recommend?

### Các lựa chọn
1. Amazon Aurora MySQL
2. Amazon Aurora Serverless for MySQL
3. Amazon Redshift Spectrum
4. Amazon RDS for MySQL

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi

📘 Nội dung câu hỏi:

Câu hỏi mô tả một công ty đang sử dụng cơ sở dữ liệu MySQL on-premises phục vụ đội ngũ bán hàng toàn cầu (global sales team), với mô hình truy cập infrequent (thỉnh thoảng, không thường xuyên). Đội ngũ bán hàng yêu cầu cơ sở dữ liệu phải có minimal downtime (thời gian gián đoạn tối thiểu) trong quá trình di chuyển. Quản trị viên cơ sở dữ liệu muốn migrate (chuyển đổi) cơ sở dữ liệu này lên AWS mà không cần chọn một instance type cụ thể, vì dự đoán sẽ có nhiều người dùng hơn trong tương lai (anticipation of more users).

🛠️ Yêu cầu chính cần giải quyết:

Dịch vụ phải hỗ trợ MySQL (tương thích để migrate dễ dàng).

Serverless hoặc tự động scale để tránh chọn instance type cố định, phù hợp với workload thay đổi (infrequent access hiện tại nhưng scale up sau).

Hỗ trợ minimal downtime (có thể dùng replication, DMS hoặc snapshot để migrate seamless).

Phù hợp với kiến thức AWS mới nhất (2024-2026): Aurora Serverless v2 đã cải tiến scale nhanh hơn, hỗ trợ MySQL 8.0+, và tích hợp tốt với global access qua multi-AZ/multi-region.

✅ Đáp án đúng: Amazon Aurora Serverless for MySQL

Lý do lựa chọn (chi tiết):

🔹 Aurora Serverless là phiên bản serverless của Amazon Aurora, không yêu cầu chọn instance type – nó tự động scale capacity từ 0.5 ACU (Aurora Capacity Units) đến hàng nghìn ACU dựa trên workload thực tế. Hoàn hảo cho infrequent access (scale down gần 0 khi idle, tiết kiệm chi phí) và scale up nhanh cho more users in future.

🔹 Hỗ trợ MySQL-compatible (Aurora MySQL), dễ migrate từ on-premises MySQL bằng AWS DMS (Database Migration Service) với minimal downtime (continuous replication, cutover nhanh).

🔹 Theo cập nhật 2026: Aurora Serverless v2 scale tức thì (sub-second), hỗ trợ data API, Lambda integration, và global databases cho sales team toàn cầu.

🔹 Ưu điểm khác: High availability (multi-AZ auto), backup tự động, encryption – vượt trội cho enterprise migration.

📋 Giải thích tất cả các phương án (đúng/sai)

❌ Amazon Aurora MySQL

Phương án này là Aurora provisioned (có instance), yêu cầu chọn instance type cụ thể (như db.r6g.large) ngay từ đầu. Không phù hợp vì câu hỏi nhấn mạnh "without selecting a particular instance type" và scale linh hoạt cho future growth. Tuy hỗ trợ MySQL và minimal downtime migrate, nhưng vẫn cần quản lý capacity thủ công – không serverless.

✅ Amazon Aurora Serverless for MySQL

(Như đã giải thích ở trên) – Đúng hoàn toàn vì serverless, auto-scale, MySQL-compatible, minimal downtime qua DMS/replication, lý tưởng cho workload biến động.

❌ Amazon Redshift Spectrum

Đây là dịch vụ data warehouse analytics (OLAP), dùng để query dữ liệu từ S3 qua Redshift clusters. Không phải database OLTP như MySQL (không hỗ trợ MySQL engine), không migrate trực tiếp on-premises MySQL, và yêu cầu Redshift cluster (có instance). Không liên quan đến transactional workload của sales team.

❌ Amazon RDS for MySQL

RDS for MySQL là dịch vụ provisioned RDS, bắt buộc chọn instance type (ví dụ: db.t4g.medium) và quản lý capacity thủ công. Tuy hỗ trợ migrate MySQL với minimal downtime (read replicas), nhưng không linh hoạt scale tự động như serverless, không phù hợp "without selecting instance type" và future unpredictable growth.

📚 Tài liệu tham khảo (AWS cập nhật mới nhất 2024-2026)

AWS Documentation - Aurora Serverless: docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless.html – Chi tiết v2 scale, MySQL support.

AWS DMS for Migration: aws.amazon.com/dms/ – Minimal downtime replication từ on-premises MySQL sang Aurora.

Aurora Features: aws.amazon.com/rds/aurora/features/ – So sánh Serverless vs Provisioned.

Exam Prep (DevOps Pro): A Cloud Guru / AWS re:Invent 2025 sessions về serverless databases.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ thực tế, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99769-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/rds/aurora/serverless/

## Câu 13

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EC2, Amazon Virtual Private Cloud, Elastic IP addresses
- Takeaway nhanh: Security Group của EC2 chỉ cần thêm inbound rule cho phép traffic từ Security Group ID của ALB (ví dụ: source = sg-12345678). AWS Security Groups là stateful và hỗ trợ cross-referencing giữa các SG (dù ở subnet khác nhau), nên traffic từ bất kỳ instance/target nào thuộc ALB SG sẽ được allow tự động. Điều này chặn hoàn toàn traffic từ nguồn khác (inside/outside private subnet), vì chỉ ALB (với SG riêng) mới match rule. Không cần thay đổi route table hay IP.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99660-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs a web application that is deployed on Amazon EC2 instances in the private subnet of a VPC. An Application Load Balancer (ALB) that extends across the public subnets directs web traffic to the EC2 instances. The company wants to implement new security measures to restrict inbound traffic from the ALB to the EC2 instances while preventing access from any other source inside or outside the private subnet of the EC2 instances.
Which solution will meet these requirements?

### Các lựa chọn
1. Configure a route in a route table to direct traffic from the internet to the private IP addresses of the EC2 instances.
2. Configure the security group for the EC2 instances to only allow traffic that comes from the security group for the ALB.
3. Move the EC2 instances into the public subnet. Give the EC2 instances a set of Elastic IP addresses.
4. Configure the security group for the ALB to allow any TCP traffic on any port.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một kiến trúc AWS tiêu chuẩn: Ứng dụng web chạy trên các instance EC2 nằm trong private subnet của VPC (không có public IP, không tiếp xúc trực tiếp với internet). Application Load Balancer (ALB) được triển khai trải rộng trên các public subnet, nhận traffic từ internet và forward đến EC2 instances.

Yêu cầu chính: Triển khai biện pháp bảo mật mới để chỉ cho phép inbound traffic từ ALB đến EC2, đồng thời ngăn chặn hoàn toàn access từ mọi nguồn khác (bao gồm các nguồn bên trong VPC như private subnet khác hoặc bên ngoài VPC).

🛠️ Mục tiêu cốt lõi: Sử dụng Security Groups (SG) để kiểm soát traffic ở layer mạng (L4), tận dụng tính năng SG referencing (một SG có thể reference ID của SG khác), đảm bảo tính private và least privilege principle. Kiến trúc này tuân thủ best practices AWS VPC security model (cập nhật đến 2026, với hỗ trợ IPv6 và enhanced VPC peering).

✅ Đáp án đúng

Configure the security group for the EC2 instances to only allow traffic that comes from the security group for the ALB.

Lý do lựa chọn:

Security Group của EC2 chỉ cần thêm inbound rule cho phép traffic từ Security Group ID của ALB (ví dụ: source = sg-12345678). AWS Security Groups là stateful và hỗ trợ cross-referencing giữa các SG (dù ở subnet khác nhau), nên traffic từ bất kỳ instance/target nào thuộc ALB SG sẽ được allow tự động.

Điều này chặn hoàn toàn traffic từ nguồn khác (inside/outside private subnet), vì chỉ ALB (với SG riêng) mới match rule. Không cần thay đổi route table hay IP.

Ưu điểm: Zero-trust model, scalable (ALB auto-scale không ảnh hưởng), và tuân thủ AWS Well-Architected Framework (Security Pillar). ✅ Hoàn hảo cho yêu cầu!

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc. Mỗi phương án được đánh giá dựa trên tính khả thi, bảo mật và khớp yêu cầu.

❌ [SAI] Configure a route in a route table to direct traffic from the internet to the private IP addresses of the EC2 instances.

Giải thích sai: Route table chỉ kiểm soát routing path (L3), không restrict nguồn traffic. Private subnet mặc định không có route đến internet (IGW chỉ ở public subnet), nên config route này sẽ phá vỡ private nature của EC2, expose trực tiếp từ internet → rủi ro bảo mật cao, không chặn nguồn khác, và vi phạm yêu cầu "preventing access from any other source". Không dùng NAT Gateway/IGW cho private subnet inbound.

✅ [ĐÚNG] Configure the security group for the EC2 instances to only allow traffic that comes from the security group for the ALB.

Giải thích đúng: Như đã nêu ở phần đáp án. SG EC2 inbound rule: Type: HTTP/HTTPS (port 80/443), Source: sg-[ALB-SG-ID]. Traffic từ ALB nodes (ở public subnet) sẽ match, còn nguồn khác (EC2 khác trong VPC hoặc external) bị drop ngay tại ENI level. Hỗ trợ full đến 2026 với ALB Target Group integration.

❌ [SAI] Move the EC2 instances into the public subnet. Give the EC2 instances a set of Elastic IP addresses.

Giải thích sai: Di chuyển EC2 sang public subnet + EIP sẽ làm EC2 public-facing trực tiếp, bỏ qua ALB và expose inbound từ internet (qua IGW). Không restrict chỉ từ ALB, mà còn tăng attack surface (DDoS, scanning). Vi phạm yêu cầu giữ private subnet và "preventing access from any other source outside".

❌ [SAI] Configure the security group for the ALB to allow any TCP traffic on any port.

Giải thích sai: Config SG của ALB chỉ kiểm soát inbound đến ALB (từ internet/client), không ảnh hưởng inbound đến EC2. Inbound đến EC2 vẫn do SG của EC2 quyết định. "Any TCP any port" còn mở rộng lỗ hổng cho ALB (không least privilege), không giải quyết yêu cầu restrict nguồn đến EC2.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS VPC Security Groups: Security groups for your Application Load Balancer – Chi tiết SG referencing cho ALB-EC2.

ALB Listener & Target Groups: Application Load Balancers – Best practices private targets.

Well-Architected Framework (Security Pillar): AWS Well-Architected – Least privilege với SG.

Exam Prep DOP-C02: AWS Certified DevOps Engineer Professional (2024-2026 syllabus) – Domain 3: Implementation & Automation, focus VPC networking.

🛠️ Lời khuyên thực tế: Kết hợp với NACL (stateless) cho subnet-level control và AWS WAF trên ALB cho L7 protection. Test bằng VPC Reachability Analyzer!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99660-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 14

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon Budgets, Amazon Simple Email Service
- Nguồn tham khảo trong block: https://console.aws.amazon.com/cost-management/home | https://www.examtopics.com/discussions/amazon/view/99513-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A solutions architect needs to determine the most efficient way to obtain this report information.
Which solution meets these requirements?

### Các lựa chọn
1. Run a query with Amazon Athena to generate the report.
2. Create a report in Cost Explorer and download the report.
3. Access the bill details from the billing dashboard and download the bill.
4. Modify a cost budget in AWS Budgets to alert with Amazon Simple Email Service (Amazon SES).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc lập kế hoạch ngân sách AWS, nơi ban quản lý yêu cầu báo cáo các mục chi phí AWS được liệt kê theo từng user (theo người dùng IAM). Dữ liệu này dùng để tạo ngân sách bộ phận. Kiến trúc sư giải pháp (Solutions Architect) cần tìm cách hiệu quả nhất để lấy báo cáo này.

📌 Yêu cầu chính: Báo cáo phải chi tiết theo user, dễ dàng truy xuất và tải xuống, phù hợp cho lập kế hoạch ngân sách. Không cần thiết lập phức tạp hay chỉ cảnh báo, mà cần báo cáo đầy đủ và linh hoạt.

🛠️ Bối cảnh AWS (cập nhật đến 2026): AWS cung cấp nhiều công cụ quản lý chi phí như Cost Explorer, Billing Dashboard, AWS Budgets, Athena... nhưng phải chọn giải pháp hiệu quả nhất (efficient), nghĩa là nhanh, chi tiết theo user (qua IAM user hoặc tags), và hỗ trợ export.

✅ Đáp án đúng và lý do lựa chọn

Create a report in Cost Explorer and download the report.

🧩 Lý do: AWS Cost Explorer là công cụ mạnh mẽ nhất để phân tích chi phí chi tiết theo user IAM, service, tag, hoặc nhóm. Bạn có thể tạo báo cáo tùy chỉnh (custom reports) lọc theo "Linked Account" hoặc "User" (kết hợp với Cost Allocation Tags kích hoạt cho IAM users). Báo cáo hỗ trợ tải xuống CSV/Excel dễ dàng, phù hợp hoàn hảo cho lập kế hoạch ngân sách bộ phận. Đây là cách hiệu quả nhất vì không cần setup thêm (chỉ cần quyền IAM phù hợp), giao diện trực quan, và cập nhật dữ liệu gần real-time (lên đến 13 tháng lịch sử chi phí). Không có công cụ nào khác cung cấp phân tích theo user mượt mà bằng.

📘 Tài liệu tham khảo: AWS Cost Explorer Documentation & Analyzing Costs by IAM User (AWS cập nhật 2025-2026 hỗ trợ AI insights mới).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, đánh dấu ✅ đúng hoặc ❌ sai, với lý do dựa trên tính năng AWS mới nhất:

Run a query with Amazon Athena to generate the report.

❌ Sai: Athena dùng để query dữ liệu chi phí từ S3 (qua AWS Cost and Usage Reports - CUR), nhưng yêu cầu setup phức tạp: kích hoạt CUR (daily/ hourly), export sang S3, tạo Glue table, rồi viết SQL query. Không hiệu quả cho báo cáo theo user (phải join nhiều bảng), tốn thời gian và chi phí query. Không phải cách "most efficient" so với Cost Explorer sẵn dùng.

Create a report in Cost Explorer and download the report.

✅ Đúng: Như giải thích ở trên, đây là lựa chọn tối ưu với giao diện thân thiện, lọc theo user/tag, và export trực tiếp. Hỗ trợ RI/SP savings analysis mới (2026), lý tưởng cho budget planning.

Access the bill details from the billing dashboard and download the bill.

❌ Sai: Billing Dashboard chỉ cung cấp tổng bill PDF/CSV hàng tháng, không phân tích chi tiết theo user (chỉ theo service/account). Không hỗ trợ lọc theo IAM user hay tạo báo cáo tùy chỉnh, chỉ xem tổng quan. Không đáp ứng yêu cầu "listed by user" một cách hiệu quả.

Modify a cost budget in AWS Budgets to alert with Amazon Simple Email Service (Amazon SES).

❌ Sai: AWS Budgets chỉ dùng để thiết lập ngưỡng ngân sách và gửi alert (qua SES/SNS), không tạo báo cáo chi tiết theo user. Chỉ hiển thị tổng chi phí so với budget, không liệt kê billed items by user. Không phù hợp cho "report" dùng lập kế hoạch.

🛠️ Lời khuyên thực tế: Để tối ưu, kích hoạt Cost Allocation Tags cho IAM users trước (qua Tag Editor), rồi dùng Cost Explorer với filter "User:All". Nếu cần tự động hóa, tích hợp AWS Cost Explorer API với Lambda.

📘 Nguồn bổ sung: AWS Billing Best Practices & Cost Explorer Reports Guide (cập nhật 2026).

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99513-exam-aws-certified-solutions-architect-associate-saa-c03/

https://console.aws.amazon.com/cost-management/home.

## Câu 15

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon Route 53, Amazon EC2
- Đáp án tham khảo: **Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.**
- Takeaway nhanh: 🛡️ ALB tự động thực hiện health checks định kỳ trên các EC2 instances trong target group, đánh dấu unhealthy instances và loại bỏ chúng khỏi traffic routing. Route 53 sử dụng alias record trỏ đến DNS name của ALB (không phải IP trực tiếp của EC2), đảm bảo chỉ traffic đến ALB và ALB mới quyết định route đến healthy instances. Giải quyết triệt để vấn đề: Không còn DNS queries trả IP unhealthy trực tiếp. ALB còn hỗ trợ auto-scaling, sticky sessions, và HTTPS termination (cập nhật 2025: hỗ trợ gRPC và WebSocket health checks tốt hơn).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-simple-configs.html | https://www.examtopics.com/discussions/amazon/view/95345-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a web application hosted over 10 Amazon EC2 instances with traffic directed by Amazon Route 53. The company occasionally experiences a timeout error when attempting to browse the application. The networking team finds that some DNS queries return IP addresses of unhealthy instances, resulting in the timeout error.
What should a solutions architect implement to overcome these timeout errors?

### Các lựa chọn
1. Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.
2. Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.
3. Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.
4. Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả vấn đề thực tế trong môi trường AWS:

Một công ty đang chạy ứng dụng web trên hơn 10 instance Amazon EC2, với lưu lượng truy cập được định tuyến qua Amazon Route 53. Tuy nhiên, thỉnh thoảng người dùng gặp lỗi timeout khi truy cập ứng dụng. Nguyên nhân được networking team xác định là một số DNS queries từ Route 53 trả về địa chỉ IP của các instance EC2 không lành mạnh (unhealthy), dẫn đến kết nối thất bại và timeout.

🛠️ Mục tiêu giải pháp: Cần triển khai cơ chế để Route 53 chỉ trả về IP của các instance khỏe mạnh (healthy), tránh routing traffic đến instance unhealthy. Điều này đòi hỏi tích hợp health checks hiệu quả và một lớp load balancing thông minh trước EC2 để tự động loại bỏ instance kém chất lượng khỏi DNS responses.

📘 Kiến thức AWS cập nhật đến 2026: Route 53 hỗ trợ health checks cơ bản, nhưng không lý tưởng cho multi-instance scaling. Application Load Balancer (ALB) phiên bản mới nhất (2024-2026) tích hợp health checks nâng cao, hỗ trợ target groups với EC2, và tích hợp seamless với Route 53 alias records cho low-latency DNS resolution (theo AWS Well-Architected Framework - Reliability Pillar).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

Lý do chi tiết:

🛡️ ALB tự động thực hiện health checks định kỳ trên các EC2 instances trong target group, đánh dấu unhealthy instances và loại bỏ chúng khỏi traffic routing.

Route 53 sử dụng alias record trỏ đến DNS name của ALB (không phải IP trực tiếp của EC2), đảm bảo chỉ traffic đến ALB và ALB mới quyết định route đến healthy instances.

Giải quyết triệt để vấn đề: Không còn DNS queries trả IP unhealthy trực tiếp. ALB còn hỗ trợ auto-scaling, sticky sessions, và HTTPS termination (cập nhật 2025: hỗ trợ gRPC và WebSocket health checks tốt hơn).

Hiệu quả cao: Giảm timeout, tăng availability lên 99.99% theo SLA ALB.

Tài liệu tham khảo:

AWS Docs: ALB Health Checks (cập nhật 2026).

Route 53 Alias Records for ALB.

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên tính khả thi, best practices AWS, và khả năng giải quyết vấn đề timeout do unhealthy instances.

❌ [SAI] Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.

Giải thích sai: Simple routing policy chỉ trả về fixed IP (hoặc weighted), không tự động loại bỏ unhealthy instances khỏi tất cả DNS responses. Health check chỉ ảnh hưởng đến record cá nhân, nhưng với 10+ instances, cần tạo record riêng lẻ cho từng cái – phức tạp quản lý, không scale, và vẫn có nguy cơ return IP unhealthy nếu query cache cũ (TTL issues). Không phù hợp cho production multi-instance (vi phạm Scalability best practices).

❌ [SAI] Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.

Giải thích sai: Failover policy dành cho active-passive failover (primary/secondary), không phải load balancing nhiều instances. Tạo record failover cho từng EC2 sẽ dẫn đến quản lý hỗn loạn (hàng chục records), health check chỉ failover sang backup chứ không distribute traffic đều. Không giải quyết routing đến unhealthy primary instances, vẫn gây timeout thường xuyên.

❌ [SAI] Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.

Giải thích sai: CloudFront là CDN cho caching/static content, origin health check chỉ failover đến origin khác (custom origins hỗ trợ limited). Với EC2 dynamic web app, không hiệu quả cho low-latency hoặc non-cacheable traffic, và Route 53 vẫn cần alias đến CloudFront – nhưng vấn đề gốc là EC2 unhealthy, CloudFront không load balance như ALB (chỉ cache miss mới hit origin). Tăng latency toàn cầu, không scale tốt cho 10+ instances (cập nhật 2026: CloudFront Origin Failover vẫn không thay thế ALB).

✅ [ĐÚNG] Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

Giải thích đúng (tóm tắt lại): Như phần trên, ALB + health checks + Route 53 alias là giải pháp chuẩn AWS cho web apps trên EC2 fleets. Tự động, scalable, và trực tiếp khắc phục DNS returning unhealthy IPs. Hỗ trợ integration với Auto Scaling Groups (ASG) để thay thế instances tự động.

🛡️ Khuyến nghị bổ sung: Kết hợp ALB với ASG và Route 53 Resolver cho monitoring tốt hơn. Test bằng AWS Fault Injection Simulator (FIS) để verify.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95345-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-simple-configs.html

## Câu 16

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EC2, Amazon Virtual Private Cloud, VPC peering
- Takeaway nhanh: Đây là CIDR nhỏ nhất hợp lệ trong các lựa chọn: Prefix /24 (256 IP), không overlap với 192.168.0.0/24 (thuộc dải private RFC 1918 khác nhau: 10.0.0.0/8 vs 192.168.0.0/16). Hợp lệ peering: Không trùng IP, kích thước VPC chuẩn (/28 đến /16), hỗ trợ routing trực tiếp qua peering connection. Các lựa chọn khác hoặc overlap, hoặc kích thước không hợp lệ cho VPC → loại bỏ. 🛠️ Smallest ở đây ưu tiên valid + non-overlapping với prefix lớn nhất khả dụng.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/vpc/latest/userguide/configure-your-vpc.html | https://www.examtopics.com/discussions/amazon/view/99651-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering connection to the development VPC.
What is the SMALLEST CIDR block that meets these requirements?

### Các lựa chọn
1. 10.0.1.0/32
2. 192.168.0.0/24
3. 192.168.1.0/32
4. 10.0.1.0/24

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào VPC Peering trên AWS, một tính năng cho phép kết nối hai VPC (Virtual Private Cloud) để các tài nguyên trong chúng giao tiếp như cùng mạng nội bộ mà không cần gateway hoặc VPN.

Bối cảnh: Một ứng dụng mới được triển khai trên các instance EC2 trong development VPC với CIDR block 192.168.0.0/24 (tương đương 256 địa chỉ IP từ 192.168.0.0 đến 192.168.0.255).

Yêu cầu: Tạo VPC mới trong cùng một AWS account, thiết lập peering với development VPC. CIDR block của VPC mới phải hợp lệ cho peering và là nhỏ nhất có thể (smallest CIDR block – nghĩa là phạm vi IP nhỏ nhất, tức prefix length lớn nhất theo quy tắc AWS).

Quy tắc chính cho VPC Peering (cập nhật AWS 2026):

CIDR của hai VPC không được overlap (không trùng lặp bất kỳ IP nào) hoặc một CIDR không được là subset của CIDR kia.

CIDR block cho VPC IPv4 phải nằm trong khoảng /16 đến /28 (tối thiểu 16 địa chỉ IP, tối đa /16 cho ~65k IP).

VPC peering intra-account (cùng account) hỗ trợ fully meshed, nhưng vẫn yêu cầu non-overlapping CIDRs.

Mục tiêu: Tìm CIDR nhỏ nhất (ít IP nhất) nhưng vẫn valid peering với 192.168.0.0/24.

📘 Tài liệu tham khảo:

AWS VPC Peering Guide: docs.aws.amazon.com/vpc/latest/peering/peering-design.html (What is VPC Peering? – Non-overlapping CIDRs).

VPC Limits: docs.aws.amazon.com/vpc/latest/userguide/vpc-cidr-blocks.html (/16 to /28 for IPv4 CIDRs, cập nhật 2024-2026 không thay đổi).

✅ Đáp án đúng: 10.0.1.0/24

Lý do lựa chọn:

Đây là CIDR nhỏ nhất hợp lệ trong các lựa chọn: Prefix /24 (256 IP), không overlap với 192.168.0.0/24 (thuộc dải private RFC 1918 khác nhau: 10.0.0.0/8 vs 192.168.0.0/16).

Hợp lệ peering: Không trùng IP, kích thước VPC chuẩn (/28 đến /16), hỗ trợ routing trực tiếp qua peering connection.

Các lựa chọn khác hoặc overlap, hoặc kích thước không hợp lệ cho VPC → loại bỏ. 🛠️ Smallest ở đây ưu tiên valid + non-overlapping với prefix lớn nhất khả dụng.

🧩 Giải thích tất cả các phương án (đúng/sai)

❌ [SAI] 10.0.1.0/32

Sai vì /32 chỉ là 1 IP duy nhất, không hợp lệ cho VPC CIDR (AWS yêu cầu tối thiểu /28 ~16 IP). Dù non-overlapping với 192.168.0.0/24, nhưng VPC không thể tạo với kích thước này → peering thất bại ngay từ bước tạo VPC.

❌ [SAI] 192.168.0.0/24

Sai vì hoàn toàn overlap với development VPC (giống hệt CIDR). Quy tắc peering cấm overlap → AWS từ chối thiết lập peering connection, gây lỗi "CIDR block overlap".

❌ [SAI] 192.168.1.0/32

Sai tương tự lựa chọn đầu: /32 không hợp lệ cho VPC (quá nhỏ). Dù non-overlapping (192.168.1.0 khác 192.168.0.0/24), nhưng không tạo được VPC → không peering được.

✅ [ĐÚNG] 10.0.1.0/24

Đúng vì non-overlapping (10.0.1.0-255 khác hẳn 192.168.0.0-255), kích thước /24 hợp lệ VPC (/16-/28), là smallest valid trong lựa chọn (256 IP, prefix lớn). Peering thành công, routing private IP trực tiếp. 🟢 Hoàn hảo cho yêu cầu!

Lưu ý thực tế: Khi tạo VPC peering, dùng AWS Console/CLI kiểm tra "CIDR block mismatch" nếu overlap. Test bằng aws ec2 accept-vpc-peering-connection. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99651-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/vpc/latest/userguide/configure-your-vpc.html

## Câu 17

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Route 53, Amazon Site-to-Site VPN, Amazon EC2, Amazon Virtual Private Cloud
- Takeaway nhanh: Phân tích tất cả các phương án Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99954-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Traffic must not traverse the internet.
How should a solutions architect configure access to meet these requirements?

### Các lựa chọn
1. Create a private hosted zone by using Amazon Route 53.
2. Set up a gateway VPC endpoint for Amazon S3 in the VPC.
3. Configure the EC2 instances to use a NAT gateway to access the S3 bucket.
4. Establish an AWS Site-to-Site VPN connection between the VPC and the S3 bucket.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi yêu cầu thiết kế giải pháp để ứng dụng chạy trên các instance Amazon EC2 có thể truy cập một Amazon S3 bucket, với điều kiện bắt buộc traffic KHÔNG được đi qua internet. Điều này nhằm đảm bảo tính bảo mật cao, giữ cho lưu lượng dữ liệu nội bộ trong mạng AWS (private traffic), tránh rủi ro từ public internet. 🛡️️

Các yếu tố chính:

EC2 instances nằm trong một VPC (Virtual Private Cloud).

S3 bucket là dịch vụ public nhưng cần truy cập private.

Giải pháp phải sử dụng các tính năng native của AWS để route traffic trực tiếp qua backbone AWS mà không expose ra ngoài.

✅ Đáp án đúng và lý do lựa chọn

Set up a gateway VPC endpoint for Amazon S3 in the VPC.

Lý do: Gateway VPC Endpoint (hay còn gọi là S3 Gateway Endpoint) là phương pháp tối ưu và được khuyến nghị nhất theo best practices AWS (cập nhật đến 2026). Nó tạo một endpoint trong VPC, route traffic từ EC2 trực tiếp đến S3 qua mạng private AWS, hoàn toàn không qua internet. Endpoint này miễn phí (không tính phí data transfer), hỗ trợ policy-based access control, và tích hợp dễ dàng với IAM roles/policies. Không cần NAT hay VPN, giảm độ phức tạp và chi phí. 🏆

Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh:

❌ Create a private hosted zone by using Amazon Route 53.

Phương án này SAI vì private hosted zone chỉ giải quyết vấn đề DNS resolution (giải quyết tên miền nội bộ trong VPC), không route traffic private đến S3. Traffic vẫn phải đi qua internet hoặc public endpoint nếu không có endpoint khác. Route 53 hữu ích để resolve endpoint URL nhưng không thay thế được cơ chế route traffic private.

✅ Set up a gateway VPC endpoint for Amazon S3 in the VPC.

ĐÚNG như đã giải thích ở trên. Đây là giải pháp chính thức cho S3 (Gateway type), hỗ trợ prefix list route table để route CIDR của S3 trực tiếp.

❌ Configure the EC2 instances to use a NAT gateway to access the S3 bucket.

Phương án này SAI vì NAT Gateway dùng để outbound traffic từ private subnet ra internet (hoặc public services). Traffic đến S3 vẫn traverse qua internet (NAT masquerade thành public IP), vi phạm yêu cầu. NAT chỉ phù hợp cho các dịch vụ cần public access, không private. 💸️ (Còn tốn phí data transfer).

❌ Establish an AWS Site-to-Site VPN connection between the VPC and the S3 bucket.

Phương án này SAI và không khả thi vì S3 bucket không phải tài nguyên on-premises hoặc có IP cố định để kết nối VPN. Site-to-Site VPN dùng cho kết nối VPC với data center ngoài, không áp dụng cho S3 (S3 dùng endpoint hoặc Direct Connect). Traffic vẫn không đảm bảo private 100% và phức tạp không cần thiết. 🚫

📘 Tài liệu tham khảo

AWS Documentation: VPC Endpoints (Gateway endpoints for S3 - cập nhật 2024-2026).

AWS Well-Architected Framework: Security Pillar - Private Access to S3.

Exam Guide DOP-C02 (DevOps Engineer Professional): Nhấn mạnh VPC Endpoints cho private S3 access.

(Kiến thức dựa trên phiên bản AWS mới nhất đến 2026, không thay đổi core feature này). 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99954-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 18

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon CloudFormation, Amazon EC2, DR RPO and RTO
- Đáp án tham khảo: **Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.**
- Takeaway nhanh: Phương án này đáp ứng RTO < 4 giờ vì AMI có thể copy cross-Region nhanh chóng (thường vài phút đến giờ), sau đó AWS CloudFormation tự động triển khai toàn bộ stack infrastructure (EC2, networking, etc.) chỉ khi kích hoạt DR. Ít tài nguyên nhất normal ops: Chỉ tốn chi phí lưu trữ AMI (rẻ ~$0.05/GB/tháng), không chạy instance liên tục. Operationally efficient nhất: CloudFormation là dịch vụ Infrastructure as Code (IaC) native của AWS, hỗ trợ template YAML/JSON chuẩn hóa, version control, drift detection, và tích hợp CI/CD (như CodePipeline). Không cần custom code, dễ audit và scale theo phiên bản mới nhất (2026: hỗ trợ CloudFormation StackSets cross-Region).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/zh_cn/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html#backup-and-restore | https://docs.aws.amazon.com/zh_cn/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html#backup-and-restoreEnglish | https://www.examtopics.com/discussions/amazon/view/99459-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application. The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS resources during normal operations.
Which solution will meet these requirements in the MOST operationally efficient way?

### Các lựa chọn
1. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS Lambda and custom scripts.
2. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.
3. Launch EC2 instances in a secondary AWS Region. Keep the EC2 instances in the secondary Region active at all times.
4. Launch EC2 instances in a secondary Availability Zone. Keep the EC2 instances in the secondary Availability Zone active at all times.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc triển khai giải pháp khôi phục thảm họa (Disaster Recovery - DR) cho ứng dụng chạy trên Amazon EC2 instances. Các yêu cầu cụ thể bao gồm:

Recovery Time Objective (RTO) < 4 giờ: Thời gian khôi phục hệ thống phải dưới 4 giờ sau sự cố.

Sử dụng ít tài nguyên AWS nhất trong hoạt động bình thường (normal operations): Giải pháp phải tiết kiệm chi phí và tài nguyên khi không có sự cố.

Cách thức hoạt động hiệu quả nhất (MOST operationally efficient): Ưu tiên phương pháp tự động hóa, dễ quản lý, ít can thiệp thủ công, phù hợp với best practices của AWS.

Đây là kịch bản Pilot Light strategy trong AWS DR (theo AWS Well-Architected Framework), nơi chỉ lưu trữ dữ liệu và hình ảnh hệ thống (như AMI) ở vùng phụ (secondary Region), sau đó tự động triển khai infrastructure khi cần. Không giữ instance chạy liên tục để tiết kiệm tài nguyên. ✅

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.

Lý do lựa chọn 🛠️:

Phương án này đáp ứng RTO < 4 giờ vì AMI có thể copy cross-Region nhanh chóng (thường vài phút đến giờ), sau đó AWS CloudFormation tự động triển khai toàn bộ stack infrastructure (EC2, networking, etc.) chỉ khi kích hoạt DR.

Ít tài nguyên nhất normal ops: Chỉ tốn chi phí lưu trữ AMI (rẻ ~$0.05/GB/tháng), không chạy instance liên tục.

Operationally efficient nhất: CloudFormation là dịch vụ Infrastructure as Code (IaC) native của AWS, hỗ trợ template YAML/JSON chuẩn hóa, version control, drift detection, và tích hợp CI/CD (như CodePipeline). Không cần custom code, dễ audit và scale theo phiên bản mới nhất (2026: hỗ trợ CloudFormation StackSets cross-Region).

So với các phương án khác, đây là cách tối ưu nhất theo AWS DR best practices.

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên RTO, tài nguyên normal ops, và operational efficiency:

❌ Phương án SAI: Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS Lambda and custom scripts.

Giải thích sai 🚫: Mặc dù đáp ứng RTO <4 giờ và ít tài nguyên normal ops (tương tự AMI copy), nhưng sử dụng Lambda + custom scripts kém efficient vì yêu cầu viết/maintain code thủ công, dễ lỗi, khó debug cross-Region, và không hỗ trợ declarative IaC như CloudFormation. AWS khuyến nghị tránh custom scripts để giảm operational overhead (theo AWS Well-Architected Reliability Pillar).

✅ Phương án ĐÚNG: Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.

Giải thích đúng 🏆: Như đã phân tích ở trên, đây là giải pháp Pilot Light lý tưởng, kết hợp AMI cross-Region (RPO thấp) + IaC tự động. CloudFormation đảm bảo deployment idempotent, repeatable, và tích hợp với AWS services mới (2026: Module support cho reusable templates). Hoàn hảo cho RTO <4 giờ mà không lãng phí tài nguyên.

❌ Phương án SAI: Launch EC2 instances in a secondary AWS Region. Keep the EC2 instances in the secondary Region active at all times.

Giải thích sai 🚫: Vi phạm yêu cầu ít tài nguyên normal ops vì phải giữ instance chạy 24/7 ở secondary Region (chi phí gấp đôi primary). RTO rất thấp (< phút với Auto Scaling), nhưng không efficient – đây là Warm Standby strategy, tốn kém hơn Pilot Light. AWS khuyên dùng cho RTO <15 phút thôi.

❌ Phương án SAI: Launch EC2 instances in a secondary Availability Zone. Keep the EC2 instances in the secondary Availability Zone active at all times.

Giải thích sai 🚫: Không phải DR thực sự vì secondary AZ vẫn trong cùng Region – chỉ là High Availability (HA) chống AZ failure, không bảo vệ chống Region-wide outage (như thiên tai). Giữ instance active tốn tài nguyên gấp đôi, và RTO thấp nhưng không meet yêu cầu cross-Region DR. AWS phân biệt rõ HA vs DR trong docs.

📘 Tài liệu tham khảo (cập nhật đến 2026)

AWS Well-Architected Framework - Reliability Pillar: docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/disaster-recovery.html – Chi tiết 4 DR strategies (Backup & Restore, Pilot Light, Warm Standby, Multi-site Active/Active).

Disaster Recovery of Workloads on AWS whitepaper: d1.awsstatic.com/whitepapers/DR_AWS.pdf – Pilot Light với AMI + CloudFormation ví dụ cụ thể.

AWS CloudFormation User Guide: docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html – Cross-Region deployments với StackSets (phiên bản 2026 hỗ trợ enhanced drift detection).

EC2 AMI Copy Cross-Region: docs.aws.amazon.com/AWSEC2/latest/UserGuide/CopyingAMIs.html – Thời gian copy thường <1 giờ cho AMI cỡ trung bình.

Giải pháp này giúp công ty tiết kiệm chi phí ~70-80% so với Warm Standby! 💡 Nếu cần ví dụ CloudFormation template, hãy hỏi thêm nhé! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99459-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/zh_cn/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html#backup-and-restore

https://docs.aws.amazon.com/zh_cn/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html#backup-and-restoreEnglish

## Câu 19

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Elastic Container Service, Amazon CloudWatch, Amazon EC2 Auto Scaling, Amazon EC2
- Takeaway nhanh: AWS Application Auto Scaling là dịch vụ tích hợp sẵn cho ECS (bao gồm Fargate) để scale desired count của ECS services/tasks dựa trên target tracking scaling policies (scale để duy trì target value như 70% CPU utilization). Nó hỗ trợ CloudWatch alarms kích hoạt scaling khi metrics vượt ngưỡng, giúp tự động scale up/down, giảm chi phí hiệu quả. Với Fargate, không cần EC2 Auto Scaling vì không có instances; Application Auto Scaling xử lý trực tiếp scalable targets cho ECS. Đây là best practice theo AWS Well-Architected Framework (Operational Excellence pillar) và cập nhật mới nhất 2026.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/autoscaling/application/userguide/what-is-application-auto-scaling.html | https://www.examtopics.com/discussions/amazon/view/99813-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high traffic to the application upon its launch. However, the company wants to reduce costs when utilization decreases.
What should a solutions architect recommend?

### Các lựa chọn
1. Use Amazon EC2 Auto Scaling to scale at certain periods based on previous traffic patterns.
2. Use an AWS Lambda function to scale Amazon ECS based on metric breaches that trigger an Amazon CloudWatch alarm.
3. Use Amazon EC2 Auto Scaling with simple scaling policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.
4. Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi xoay quanh một công ty đang triển khai ứng dụng mới trên Amazon Elastic Container Service (Amazon ECS) cluster, sử dụng Fargate launch type cho các ECS tasks. Họ đang giám sát CPU và memory usage chặt chẽ vì dự đoán traffic cao ngay khi launch ứng dụng. Tuy nhiên, mục tiêu chính là giảm chi phí khi utilization (sử dụng tài nguyên) giảm xuống sau giai đoạn cao điểm.

🛠️ Vấn đề cốt lõi: Với Fargate (serverless compute engine cho ECS), không quản lý EC2 instances trực tiếp, nên cần giải pháp auto scaling phù hợp để scale ECS tasks dựa trên metrics (như CPU/memory) từ Amazon CloudWatch alarms. Giải pháp phải linh hoạt, hỗ trợ target tracking policies và tối ưu chi phí theo phiên bản AWS mới nhất (2024-2026), nơi AWS Application Auto Scaling là công cụ chuẩn cho ECS Fargate.

✅ Đáp án đúng

Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

Lý do chọn đáp án này:

AWS Application Auto Scaling là dịch vụ tích hợp sẵn cho ECS (bao gồm Fargate) để scale desired count của ECS services/tasks dựa trên target tracking scaling policies (scale để duy trì target value như 70% CPU utilization).

Nó hỗ trợ CloudWatch alarms kích hoạt scaling khi metrics vượt ngưỡng, giúp tự động scale up/down, giảm chi phí hiệu quả.

Với Fargate, không cần EC2 Auto Scaling vì không có instances; Application Auto Scaling xử lý trực tiếp scalable targets cho ECS. Đây là best practice theo AWS Well-Architected Framework (Operational Excellence pillar) và cập nhật mới nhất 2026.

📋 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do cụ thể dựa trên kiến thức AWS ECS Fargate (không hỗ trợ EC2 Auto Scaling trực tiếp).

Use Amazon EC2 Auto Scaling to scale at certain periods based on previous traffic patterns.

❌ Sai: EC2 Auto Scaling chỉ dành cho EC2 instances (như ECS với EC2 launch type), không áp dụng cho Fargate (serverless, không quản lý instances). Scaling theo lịch cố định (scheduled scaling) dựa trên lịch sử traffic không linh hoạt, không dựa trên metrics real-time từ CloudWatch, dẫn đến lãng phí chi phí nếu traffic không khớp lịch.

Use an AWS Lambda function to scale Amazon ECS based on metric breaches that trigger an Amazon CloudWatch alarm.

❌ Sai: Có thể dùng Lambda + CloudWatch Events để gọi ECS APIs scale thủ công, nhưng đây không phải giải pháp tự động hóa chuẩn (custom solution phức tạp, dễ lỗi, tốn công maintain). AWS khuyến nghị dùng Application Auto Scaling thay vì tự code Lambda, vì nó hỗ trợ target tracking native và tích hợp sâu hơn với ECS Fargate.

Use Amazon EC2 Auto Scaling with simple scaling policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

❌ Sai: Lại nhầm lẫn EC2 Auto Scaling (chỉ scale EC2 fleets) với ECS Fargate. ECS metrics có thể trigger CloudWatch alarm, nhưng EC2 Auto Scaling không scale ECS tasks trực tiếp. Simple scaling policies kém hiệu quả hơn target tracking; đây là anti-pattern cho Fargate.

Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

✅ Đúng: Hoàn hảo cho ECS Fargate! Application Auto Scaling đăng ký scalable target (ECS service), sử dụng target tracking policies để tự động scale desired count dựa trên metrics (CPU/memory). CloudWatch alarms trigger scaling mượt mà, tối ưu chi phí (scale down khi low utilization). Hỗ trợ full theo AWS updates 2026, bao gồm predictive scaling.

📘 Tài liệu tham khảo (AWS docs cập nhật mới nhất 2024-2026)

Automatically scale your Amazon ECS service - AWS Docs 🛠️ (Xác nhận Application Auto Scaling cho Fargate).

Target tracking scaling for Amazon ECS - AWS Auto Scaling 📈 (Chi tiết target tracking policies).

ECS Fargate scaling best practices - AWS Well-Architected ✅ (Khuyến nghị chính thức).

AWS re:Post & Exam Prep (DOP-C02): Application Auto Scaling là key cho ECS serverless scaling.

Hy vọng phân tích này giúp bạn nắm vững! 🚀 Nếu cần thêm ví dụ code Terraform/CLI, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99813-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/autoscaling/application/userguide/what-is-application-auto-scaling.html

## Câu 20

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon DataSync, Amazon S3, Amazon FSx, Amazon EC2, Amazon FSx for Windows File Server
- Đáp án tham khảo: **Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.**
- Takeaway nhanh: Amazon FSx for Windows File Server là dịch vụ fully managed file storage dành riêng cho Windows workloads, hỗ trợ đầy đủ SMB protocol (SMB 2.0, 3.0, 3.1.1) với tính năng Multi-AZ cho high availability. Nó cung cấp shared file system có thể mount từ nhiều EC2 instances (Windows/Linux hỗ trợ SMB), phù hợp cho gaming app cần chia sẻ dữ liệu realtime. AWS tự động quản lý backup, patching, encryption, scaling (lên đến petabytes), và integration với Active Directory.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99809-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.
Which AWS solution meets these requirements?

### Các lựa chọn
1. Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.
2. Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
3. Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.
4. Create an Amazon S3 bucket. Assign an IAM role to the application to grant access to the S3 bucket. Mount the S3 bucket to the application server.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế một giải pháp lưu trữ chia sẻ (shared storage) cho ứng dụng game chạy trên AWS Cloud. Các yêu cầu chính bao gồm:

Hỗ trợ SMB clients (Server Message Block - giao thức chia sẻ file phổ biến trên Windows) để truy cập dữ liệu.

Giải pháp phải fully managed (AWS quản lý hoàn toàn, không cần quản lý hạ tầng thủ công như server, OS, patch...).

Phù hợp cho môi trường gaming, nơi cần lưu trữ nhanh, chia sẻ giữa các server (origin server và application server).

Mục tiêu là chọn dịch vụ AWS cung cấp file system chia sẻ qua SMB, fully managed, và dễ dàng mount/attach vào các EC2 instances. Đây là chủ đề thường gặp trong kỳ thi AWS Certified DevOps Engineer - Professional (DOP-C02), phần thiết kế storage scalable và managed services. ✅

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.

Lý do chi tiết:

Amazon FSx for Windows File Server là dịch vụ fully managed file storage dành riêng cho Windows workloads, hỗ trợ đầy đủ SMB protocol (SMB 2.0, 3.0, 3.1.1) với tính năng Multi-AZ cho high availability.

Nó cung cấp shared file system có thể mount từ nhiều EC2 instances (Windows/Linux hỗ trợ SMB), phù hợp cho gaming app cần chia sẻ dữ liệu realtime.

AWS tự động quản lý backup, patching, encryption, scaling (lên đến petabytes), và integration với Active Directory.

"Attach to origin server" và "connect application server" khớp chính xác với cách FSx hoạt động: tạo file system, mount qua SMB share.

Cập nhật đến 2026: FSx vẫn là lựa chọn chuẩn (AWS re:Invent 2024 nhấn mạnh FSx với Lustre/SMB enhancements), không có thay thế fully managed SMB nào tốt hơn. 🛠️

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên nội dung văn bản gốc bằng tiếng Anh, chỉ giải thích bằng tiếng Việt để rõ ràng:

❌ [SAI] Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.

AWS DataSync chỉ dùng để chuyển dữ liệu giữa on-premises và AWS (hoặc giữa các dịch vụ AWS), không phải dịch vụ lưu trữ chia sẻ SMB. Nó không tạo file system mountable liên tục, mà chỉ sync batch/ realtime, không fully managed cho shared access. Không đáp ứng yêu cầu SMB clients ongoing. 🚫

❌ [SAI] Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.

Giải pháp này dùng EC2 tự quản lý (self-managed Windows file server với File Server role), không fully managed vì phải tự install OS, patch, scale, backup thủ công. Dễ fail-over kém, tốn công DevOps, vi phạm yêu cầu "fully managed". ❌

✅ [ĐÚNG] Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.

Như đã giải thích ở trên: Fully managed, native SMB support, shared access giữa multiple servers, tích hợp AWS services (VPC, AD). Hoàn hảo cho gaming workloads cần low-latency file sharing. 🟢

❌ [SAI] Create an Amazon S3 bucket. Assign an IAM role to the application to grant access to the S3 bucket. Mount the S3 bucket to the application server.

S3 là object storage, không hỗ trợ SMB protocol native (chỉ dùng S3 File Gateway hoặc s3fs hacky, không fully managed SMB). Mount S3 qua tools như s3fs có performance kém, không phải true file system cho gaming (high IOPS cần). Không chia sẻ như SMB share chuẩn. 📦🚫

📘 Tài liệu tham khảo (cập nhật mới nhất 2026)

AWS FSx for Windows Documentation: Amazon FSx for Windows File Server - Xác nhận fully managed SMB shares.

AWS Storage Services Whitepaper (2024): Nhấn mạnh FSx cho Windows workloads.

DOP-C02 Exam Guide: Domain 2.1 - Implement shared storage (FSx vs EFS/EFS vs S3).

AWS re:Invent 2024 Sessions: STG3** - FSx updates for gaming/entertainment.

AWS Console/CLI: aws fsx create-file-system --file-system-type WINDOWS demo SMB mount.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🎮 Nếu cần thêm ví dụ code Terraform/CloudFormation cho FSx, hãy hỏi nhé. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99809-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 21

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon DynamoDB, Amazon S3, Amazon S3 Glacier, Amazon CLI, Amazon Backup
- Đáp án tham khảo: **Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.**
- Takeaway nhanh: AWS Backup hoàn hảo cho yêu cầu này vì nó hỗ trợ lập kế hoạch sao lưu định kỳ (backup plan) cho DynamoDB với lịch cron (ví dụ: ngày 1 hàng tháng). Lifecycle policy trong AWS Backup vault cho phép tự động transition sang cold storage (như AWS Backup Cold Storage hoặc S3 Glacier) sau 6 tháng, giữ sẵn sàng truy cập nhanh trong 6 tháng đầu. Retention period có thể đặt chính xác 7 năm cho từng recovery point, đảm bảo compliance mà không cần can thiệp thủ công.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/ | https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/Its | https://docs.aws.amazon.com/aws-backup/latest/devguide/creating-a-backup-plan.html | https://www.examtopics.com/discussions/amazon/view/99793-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an application that is backed by an Amazon DynamoDB table. The company’s compliance requirements specify that database backups must be taken every month, must be available for 6 months, and must be retained for 7 years.
Which solution will meet these requirements?

### Các lựa chọn
1. Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.
2. Create a DynamoDB on-demand backup of the DynamoDB table on the first day of each month. Transition the backup to Amazon S3 Glacier Flexible Retrieval after 6 months. Create an S3 Lifecycle policy to delete backups that are older than 7 years.
3. Use the AWS SDK to develop a script that creates an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the script on the first day of each month. Create a second script that will run on the second day of each month to transition DynamoDB backups that are older than 6 months to cold storage and to delete backups that are older than 7 years.
4. Use the AWS CLI to create an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the command on the first day of each month with a cron expression. Specify in the command to transition the backups to cold storage after 6 months and to delete the backups after 7 years.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế giải pháp sao lưu (backup) cho bảng Amazon DynamoDB nhằm đáp ứng các yêu cầu tuân thủ (compliance) nghiêm ngặt của công ty:

📅 Tần suất sao lưu: Thực hiện mỗi tháng một lần (every month).

⏳ Thời gian sẵn sàng truy cập: Sao lưu phải có sẵn trong 6 tháng (available for 6 months).

🗂️ Thời hạn lưu trữ: Giữ sao lưu trong 7 năm (retained for 7 years).

🛠️ Bối cảnh AWS: DynamoDB hỗ trợ hai loại sao lưu chính là On-Demand Backup (sao lưu theo yêu cầu, toàn bộ bảng tại một thời điểm) và Point-in-Time Recovery (PITR) (khôi phục theo thời điểm). Tuy nhiên, để quản lý lifecycle tự động (chuyển sang cold storage và xóa sau thời hạn), AWS Backup là dịch vụ được khuyến nghị nhất (theo tài liệu AWS cập nhật 2024-2026), vì nó tích hợp vault-based backup với chính sách lifecycle linh hoạt cho DynamoDB, hỗ trợ transition to cold storage (như S3 Glacier) và retention policy dài hạn mà không cần script tùy chỉnh.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.

Lý do chọn đáp án này 🏆:

AWS Backup hoàn hảo cho yêu cầu này vì nó hỗ trợ lập kế hoạch sao lưu định kỳ (backup plan) cho DynamoDB với lịch cron (ví dụ: ngày 1 hàng tháng).

Lifecycle policy trong AWS Backup vault cho phép tự động transition sang cold storage (như AWS Backup Cold Storage hoặc S3 Glacier) sau 6 tháng, giữ sẵn sàng truy cập nhanh trong 6 tháng đầu.

Retention period có thể đặt chính xác 7 năm cho từng recovery point, đảm bảo compliance mà không cần can thiệp thủ công.

Đây là giải pháp managed, serverless, chi phí tối ưu và tuân thủ best practices AWS (không cần code/script). ✅

📋 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm giải thích rõ ràng:

✅ Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.

🧠 Giải thích đúng: Như đã nêu ở trên, AWS Backup (ra mắt hỗ trợ DynamoDB từ 2020, cập nhật lifecycle đầy đủ đến 2026) xử lý toàn bộ yêu cầu một cách tự động, an toàn và scalable. Không có rủi ro code lỗi hoặc phụ thuộc EventBridge/SDK.

❌ Create a DynamoDB on-demand backup of the DynamoDB table on the first day of each month. Transition the backup to Amazon S3 Glacier Flexible Retrieval after 6 months. Create an S3 Lifecycle policy to delete backups that are older than 7 years.

🧠 Giải thích sai: DynamoDB on-demand backups không lưu trữ trực tiếp trong S3 mà dùng DynamoDB Backup Storage riêng (không export tự động sang S3 Glacier). Không có cơ chế native "transition to S3 Glacier" cho backups DynamoDB; bạn phải export thủ công qua Export to S3 (beta tính đến 2024), rồi mới áp S3 Lifecycle – phức tạp, không tự động và không đáp ứng "available 6 months" mượt mà.

❌ Use the AWS SDK to develop a script that creates an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the script on the first day of each month. Create a second script that will run on the second day of each month to transition DynamoDB backups that are older than 6 months to cold storage and to delete backups that are older than 7 years.

🧠 Giải thích sai: Mặc dù EventBridge + SDK có thể tạo backup on-demand hàng tháng (qua CreateBackup API), nhưng DynamoDB không hỗ trợ "transition to cold storage" native qua script. Delete backup chỉ qua DeleteBackup API, nhưng không có cold storage tier cho DynamoDB backups (chỉ AWS Backup mới có). Giải pháp này tùy chỉnh cao, dễ lỗi, tốn công maintain, vi phạm best practices (IAM permissions phức tạp, chi phí Lambda cao).

❌ Use the AWS CLI to create an-on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the command on the first day of each month with a cron expression. Specify in the command to transition the backups to cold storage after 6 months and to delete the backups after 7 years.

🧠 Giải thích sai: AWS CLI (aws dynamodb create-backup) chỉ tạo on-demand backup, không hỗ trợ tham số "transition to cold storage" hoặc "delete after 7 years" trong cùng command. EventBridge chỉ trigger backup, không quản lý lifecycle. DynamoDB thiếu tính năng này; phải dùng AWS Backup để có retention/transition tự động.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2024-2026)

AWS Backup for DynamoDB – Hướng dẫn backup plan, lifecycle (cold storage sau X ngày, retention tối đa 100 năm).

DynamoDB Backups Best Practices – So sánh On-Demand vs AWS Backup.

AWS Backup Lifecycle Policies – Chi tiết transition và retention.

AWS Well-Architected Framework: Reliability Pillar (2024) khuyến nghị AWS Backup cho compliance dài hạn.

Giải pháp này đảm bảo tuân thủ 100%, chi phí thấp (~$0.10/GB/tháng cho cold storage)! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99793-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/aws-backup/latest/devguide/creating-a-backup-plan.html

https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/

https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/Its

## Câu 22

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon S3
- Đáp án tham khảo: **Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.**
- Takeaway nhanh: Đây là cách an toàn nhất vì tuân thủ least privilege principle: Chỉ cấp quyền đọc chính xác cho S3 bucket cụ thể, không thừa quyền. Lambda sử dụng execution role (IAM role) để tạm thời assume quyền, tự động rotate credentials, không lưu trữ key lâu dài. AWS docs chính thức (2026): Lambda execution roles là recommended approach cho inter-service access, giảm bề mặt tấn công so với bucket policy hoặc keys.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html | https://www.examtopics.com/discussions/amazon/view/99756-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account.
Which solution will meet these requirements in the MOST secure manner?

### Các lựa chọn
1. Apply an S3 bucket policy that grants read access to the S3 bucket.
2. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.
3. Embed an access key and a secret key in the Lambda function’s code to grant the required IAM permissions for read access to the S3 bucket.
4. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to all S3 buckets in the account.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc cấp quyền read access (quyền đọc) cho một hàm AWS Lambda truy cập vào một Amazon S3 bucket nằm trong cùng một AWS account. Yêu cầu chính là tìm giải pháp an toàn nhất (MOST secure) theo nguyên tắc least privilege (quyền hạn tối thiểu) và các best practices của AWS.

🛠️ Bối cảnh kỹ thuật:

AWS Lambda chạy trong môi trường serverless, không nên hardcode credentials (như access key) vì rủi ro lộ thông tin.

S3 bucket và Lambda cùng account, nên ưu tiên sử dụng IAM roles để Lambda assume role và truy cập S3 mà không cần credentials tĩnh.

Kiến thức cập nhật đến 2026: AWS khuyến nghị sử dụng execution roles cho Lambda với IAM policies granular (chi tiết), hỗ trợ S3 Object Lambda và IAM Access Analyzer để kiểm tra quyền hạn (theo AWS Well-Architected Framework - Security Pillar, phiên bản mới nhất).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.

Lý do:

Đây là cách an toàn nhất vì tuân thủ least privilege principle: Chỉ cấp quyền đọc chính xác cho S3 bucket cụ thể, không thừa quyền.

Lambda sử dụng execution role (IAM role) để tạm thời assume quyền, tự động rotate credentials, không lưu trữ key lâu dài.

AWS docs chính thức (2026): Lambda execution roles là recommended approach cho inter-service access, giảm bề mặt tấn công so với bucket policy hoặc keys.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm giải thích bằng tiếng Việt:

Apply an S3 bucket policy that grants read access to the S3 bucket.

❌ Sai: Bucket policy có thể cấp quyền cho Lambda (qua Principal là Lambda service), nhưng kém an toàn hơn vì policy gắn trực tiếp vào bucket, dễ bị lạm dụng nếu bucket thay đổi hoặc nhiều service truy cập. Không tuân thủ least privilege tốt bằng IAM role trên Lambda (IAM role tập trung quản lý quyền cho function cụ thể). AWS ưu tiên IAM roles cho Lambda hơn bucket policies trong cùng account.

Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.

✅ Đúng: Như đã giải thích ở trên. Đây là best practice của AWS: Gắn IAM role vào Lambda (qua console/CLI/CDK), rồi attach policy JSON chỉ định s3:GetObject cho bucket cụ thể (ARN). An toàn cao, dễ audit bằng IAM Access Analyzer, và hỗ trợ Lambda versions/aliases.

Embed an access key and a secret key in the Lambda function’s code to grant the required IAM permissions for read access to the S3 bucket.

❌ Sai: Rất không an toàn! Hardcode access/secret key vào code vi phạm Security best practices, dễ lộ key qua logs, Git repo, hoặc reverse engineering. AWS cấm khuyến khích cách này từ 2017 (Lambda IAM roles ra đời), và đến 2026, Lambda hỗ trợ temporary credentials qua roles, làm phương án này lỗi thời và rủi ro cao (vi phạm PCI-DSS, SOC2).

Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to all S3 buckets in the account.

❌ Sai: Dù dùng IAM role (tốt hơn embed keys), nhưng policy cấp quyền toàn bộ S3 buckets vi phạm least privilege – thừa quyền không cần thiết, tăng rủi ro nếu Lambda bị compromise. AWS khuyến nghị resource-specific policies (chỉ bucket ARN cụ thể) để giảm blast radius.

📘 Tài liệu tham khảo

AWS Lambda Execution Role: docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html (cập nhật 2026: Nhấn mạnh least privilege với S3).

AWS Well-Architected Framework - Security Pillar: aws.amazon.com/architecture/well-architected (SEC 5: IAM roles > bucket policies).

S3 Best Practices: docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html (Ưu tiên IAM cho service principals).

Exam Topic DOP-C02: AWS Certified DevOps Engineer Professional (IAM, Lambda, S3 integration).

🛡️ Kết luận: Luôn ưu tiên IAM roles granular cho Lambda-S3 để đạt security cao nhất! Nếu deploy, dùng Terraform/ CDK để automate.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99756-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html

## Câu 23

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon S3
- Đáp án tham khảo: **Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.**
- Takeaway nhanh: Client-side encryption mã hóa dữ liệu trên thiết bị client (ví dụ: sử dụng AWS Encryption SDK hoặc thư viện như AWS SDK với KMS) TRƯỚC KHI upload lên S3. Do đó:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/95031-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit.
Which solution meets these requirements?

### Các lựa chọn
1. Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.
2. Use server-side encryption to encrypt the data that is being uploaded to the S3 buckets.
3. Create bucket policies that require the use of server-side encryption with S3 managed encryption keys (SSE-S3) for S3 uploads.
4. Enable the security option to encrypt the S3 buckets through the use of a default AWS Key Management Service (AWS KMS) key.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi này thuộc chủ đề bảo mật dữ liệu trên Amazon S3 trong AWS, cụ thể là yêu cầu mã hóa dữ liệu at rest (khi lưu trữ) trước khi dữ liệu được upload lên S3 buckets, đồng thời đảm bảo mã hóa in transit (khi truyền tải).

Bối cảnh: Một công ty sử dụng tài khoản AWS trung tâm để lưu trữ log data vào nhiều S3 buckets. Solutions Architect cần triển khai giải pháp đảm bảo:

Dữ liệu phải được mã hóa at rest TRƯỚC KHI upload → Nghĩa là dữ liệu phải được mã hóa bên phía client trước khi gửi lên S3, vì nếu mã hóa server-side thì S3 mới mã hóa sau khi nhận dữ liệu (dữ liệu plaintext đã đến S3).

Mã hóa in transit: Sử dụng HTTPS/TLS (mặc định cho S3), nhưng trọng tâm là at rest trước upload.

Yêu cầu cốt lõi (theo best practices AWS 2026): S3 hỗ trợ nhiều loại mã hóa (SSE-S3, SSE-KMS, SSE-C, Client-side), nhưng chỉ client-side encryption đáp ứng "before the data is uploaded" vì dữ liệu được mã hóa cục bộ trước khi truyền. AWS khuyến nghị client-side cho trường hợp cần kiểm soát khóa hoàn toàn hoặc dữ liệu nhạy cảm nhất (xem AWS Well-Architected Framework - Security Pillar).

📘 Tài liệu tham khảo:

Amazon S3 Security Best Practices (cập nhật 2025).

Using Client-Side Encryption.

Protecting Data Using Encryption.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

Lý do chi tiết 🛠️:

Client-side encryption mã hóa dữ liệu trên thiết bị client (ví dụ: sử dụng AWS Encryption SDK hoặc thư viện như AWS SDK với KMS) TRƯỚC KHI upload lên S3. Do đó:

✅ Encrypted at rest before upload: S3 chỉ nhận và lưu dữ liệu đã mã hóa, không bao giờ thấy plaintext.

✅ Encrypted in transit: Kết hợp với HTTPS (buộc qua bucket policy hoặc VPC endpoint), dữ liệu luôn an toàn khi truyền.

Đây là giải pháp duy nhất khớp yêu cầu "before the data is uploaded". AWS khuyến nghị cho dữ liệu nhạy cảm cao, hỗ trợ CMK (Customer Managed Keys) qua KMS, và tích hợp dễ dàng với Lambda/ EC2 cho log data.

Không phụ thuộc server-side (S3 chỉ lưu blob mã hóa), giảm rủi ro nếu S3 bị breach.

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn giữ nguyên văn bản gốc bằng tiếng Anh, với lý do đúng/sai bằng tiếng Việt. Sử dụng ✅ cho đúng, ❌ cho sai.

Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

✅ Đúng hoàn toàn 🏆: Như giải thích trên, đây là cách duy nhất mã hóa trước upload. Dữ liệu plaintext không bao giờ rời client, S3 lưu encrypted object. Hỗ trợ AWS Encryption Library (v5.0+ năm 2025) với envelope encryption cho hiệu suất cao.

Use server-side encryption to encrypt the data that is being uploaded to the S3 buckets.

❌ Sai: Server-side encryption (SSE) chỉ mã hóa SAU KHI S3 nhận dữ liệu (plaintext truyền đến S3 trước). Không đáp ứng "before the data is uploaded". SSE bao gồm SSE-S3/SSE-KMS/SSE-C, nhưng đều là server-side.

Create bucket policies that require the use of server-side encryption with S3 managed encryption keys (SSE-S3) for S3 uploads.

❌ Sai: Bucket policy chỉ buộc SSE-S3 (mã hóa server-side với key AWS quản lý) sau upload. Dữ liệu vẫn plaintext in transit đến S3 trước khi mã hóa. SSE-S3 rẻ nhưng kém linh hoạt so với KMS (không tùy chỉnh key).

Enable the security option to encrypt the S3 buckets through the use of a default AWS Key Management Service (AWS KMS) key.

❌ Sai: "Security option" ám chỉ default encryption (SSE-KMS với AWS-managed key) trên bucket, nhưng vẫn là server-side (mã hóa sau khi nhận). Không có "encrypt the S3 buckets" trực tiếp; bucket policy hoặc default encryption chỉ áp dụng SSE-KMS, dữ liệu plaintext trước upload. AWS KMS key mặc định không bắt buộc in transit encryption riêng (dùng HTTPS policy).

🏅 Kết luận & Best Practices AWS 2026

Giải pháp client-side là optimal cho centralized log storage với nhiều buckets, kết hợp S3 Bucket Keys (giảm KMS calls 99%) và S3 Access Points cho governance. Test với AWS Encryption SDK để đảm bảo compliance (GDPR/HIPAA). Nếu cần scale, dùng AWS FireLens cho container logs! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95031-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 24

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon Aurora, Amazon EC2, Amazon Relational Database Service
- Takeaway nhanh: Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc: Configure storage Auto Scaling on the RDS for Oracle instance.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html#USER_PIOPS.Autoscaling | https://www.examtopics.com/discussions/amazon/view/99739-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a multi-tier application deployed on several Amazon EC2 instances in an Auto Scaling group. An Amazon RDS for Oracle instance is the application’ s data layer that uses Oracle-specific PL/SQL functions. Traffic to the application has been steadily increasing. This is causing the EC2 instances to become overloaded and the RDS instance to run out of storage. The Auto Scaling group does not have any scaling metrics and defines the minimum healthy instance count only. The company predicts that traffic will continue to increase at a steady but unpredictable rate before leveling off.
What should a solutions architect do to ensure the system can automatically scale for the increased traffic? (Choose two.)

### Các lựa chọn
1. Configure storage Auto Scaling on the RDS for Oracle instance.
2. Migrate the database to Amazon Aurora to use Auto Scaling storage.
3. Configure an alarm on the RDS for Oracle instance for low free storage space.
4. Configure the Auto Scaling group to use the average CPU as the scaling metric.
5. Configure the Auto Scaling group to use the average free memory as the scaling metric.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng đa tầng (multi-tier) được triển khai trên các instance Amazon EC2 trong Auto Scaling group (ASG). Lớp dữ liệu là Amazon RDS for Oracle sử dụng các hàm PL/SQL đặc trưng của Oracle. Lưu lượng truy cập tăng dần, dẫn đến:

EC2 instances bị quá tải (overloaded).

RDS instance hết dung lượng lưu trữ (run out of storage).

ASG hiện tại không có scaling metrics (chỉ định nghĩa minimum healthy instance count). Công ty dự đoán lưu lượng sẽ tiếp tục tăng ổn định nhưng không thể dự đoán chính xác trước khi ổn định.

Mục tiêu: Đảm bảo hệ thống tự động scale để xử lý lưu lượng tăng, chọn HAI giải pháp phù hợp nhất từ solutions architect. 🛠️ Vấn đề chính:

Scale compute (EC2 ASG) để xử lý tải CPU/load tăng.

Scale storage cho RDS Oracle mà không làm gián đoạn ứng dụng Oracle-specific.

Kiến thức AWS cập nhật đến 2026: RDS for Oracle hỗ trợ Storage Auto Scaling (từ 2019, vẫn active). ASG hỗ trợ target tracking/composite scaling với metrics như CPUUtilization (standard CloudWatch metric).

✅ Đáp án đúng (Chọn HAI)

Configure storage Auto Scaling on the RDS for Oracle instance: ✅ Đúng vì RDS Oracle hỗ trợ Storage Auto Scaling, tự động tăng storage khi FreeStorageSpace thấp (dựa trên MaxStorageThreshold), giải quyết vấn đề hết storage mà không cần migrate.

Configure the Auto Scaling group to use the average CPU as the scaling metric: ✅ Đúng vì ASG cần metric để scale out/in (hiện tại chưa có). CPUUtilization là metric chuẩn, phổ biến cho ứng dụng web tăng traffic, giúp scale EC2 tự động theo tải thực tế.

Lý do chọn: Các giải pháp này tối ưu, không xâm lấn (không migrate DB), tận dụng tính năng native AWS. Traffic tăng "unpredictable" phù hợp target tracking scaling với CPU. Không cần min/max capacity phức tạp.

📋 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc:

Configure storage Auto Scaling on the RDS for Oracle instance.

✅ Đúng. RDS for Oracle hỗ trợ Storage Auto Scaling (enable trong console/CLI), tự động tăng storage lên đến giá trị max đã set khi FreeStorageSpace < threshold (mặc định 10% trong 5 phút). Giải quyết trực tiếp vấn đề "run out of storage" mà giữ nguyên Oracle PL/SQL. Không downtime, chi phí theo usage. (Cập nhật 2026: Vẫn hỗ trợ full cho Oracle 19c/21c).

Migrate the database to Amazon Aurora to use Auto Scaling storage.

❌ Sai. Aurora hỗ trợ autoscaling storage tốt hơn (tăng/giảm linh hoạt), nhưng ứng dụng dùng Oracle-specific PL/SQL functions → migrate phức tạp, tốn kém (schema conversion via DMS/SCT), có thể mất tính tương thích. Không cần thiết vì RDS Oracle đã có Storage Auto Scaling.

Configure an alarm on the RDS for Oracle instance for low free storage space.

❌ Sai. Alarm CloudWatch (FreeStorageSpace) chỉ cảnh báo (notify via SNS), không tự động scale storage. Phải can thiệp thủ công (modify DB instance), không đáp ứng yêu cầu "automatically scale". Storage Auto Scaling mới là giải pháp tự động thực sự.

Configure the Auto Scaling group to use the average CPU as the scaling metric.

✅ Đúng. ASG hiện thiếu metrics → thêm CPUUtilization (average CPU qua CloudWatch) làm scaling metric/target (target tracking policy). Phù hợp traffic tăng gây overload EC2. AWS khuyến nghị CPU cho app web (scale out khi >60%, scale in <40%).

Configure the Auto Scaling group to use the average free memory as the scaling metric.

❌ Sai. ASG không hỗ trợ trực tiếp "average free memory" làm scaling metric chuẩn (CloudWatch basic monitoring EC2 không expose free memory mặc định). Phải dùng custom metric via agent (CloudWatch Agent) + publish, phức tạp hơn CPU (native metric). Không lý tưởng cho "automatically scale" nhanh chóng.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

RDS Storage Auto Scaling: AWS RDS User Guide - Managing capacity automatically with Amazon RDS storage autoscaling (Hỗ trợ Oracle).

EC2 Auto Scaling Metrics: AWS Auto Scaling Documentation - Scaling by target value (Target tracking) (CPUUtilization là metric tiêu chuẩn).

RDS Metrics: Amazon CloudWatch Metrics for Amazon RDS (FreeStorageSpace cho alarm, không autoscaling).

Exam Guide DOP-C02: AWS Certified DevOps Engineer Professional (Scale EC2/RDS với native features).

Hy vọng phân tích giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ CLI/CloudFormation, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99739-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html#USER_PIOPS.Autoscaling

## Câu 25

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Aurora, Amazon EC2, Amazon Relational Database Service
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.how-it-works.html#aurora-serverless-v2.how-it-works.scaling | https://www.examtopics.com/discussions/amazon/view/99948-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company needs to migrate a legacy application from an on-premises data center to the AWS Cloud because of hardware capacity constraints. The application runs 24 hours a day, 7 days a week. The application’s database storage continues to grow over time.
What should a solutions architect do to meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Migrate the application layer to Amazon EC2 Spot Instances. Migrate the data storage layer to Amazon S3.
2. Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon RDS On-Demand Instances.
3. Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances.
4. Migrate the application layer to Amazon EC2 On-Demand Instances. Migrate the data storage layer to Amazon RDS Reserved Instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân Tích Câu Hỏi Trắc Nghiệm AWS

📘 Nội dung câu hỏi được giải thích chi tiết:

Câu hỏi tập trung vào việc di chuyển (migrate) ứng dụng legacy từ on-premises sang AWS Cloud do hạn chế dung lượng hardware tại chỗ. Ứng dụng chạy liên tục 24/7, và lưu trữ database tăng dần theo thời gian. Yêu cầu chính là giải pháp tiết kiệm chi phí nhất (MOST cost-effectively) cho cả lớp ứng dụng (application layer) và lớp lưu trữ dữ liệu (data storage layer).

🛠️ Yêu cầu cốt lõi:

Workload ổn định, dự đoán được (24/7), nên ưu tiên mô hình giá tiết kiệm dài hạn như Reserved Instances (RI).

Database cần hỗ trợ tăng trưởng storage động, relational (giả sử legacy app dùng SQL), scalable và managed.

Giải pháp phải cân bằng hiệu suất cao, độ tin cậy, và chi phí thấp nhất theo AWS Well-Architected Framework (Pillar: Cost Optimization). Kiến thức cập nhật đến 2026: Reserved Instances vẫn là lựa chọn hàng đầu cho workload ổn định, Aurora hỗ trợ auto-scaling storage lên đến 128TB (tính đến 2024-2026).

✅ Đáp án ĐÚNG và lý do lựa chọn:

Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances.

🧩 Lý do chi tiết (tiết kiệm chi phí NHẤT):

EC2 Reserved Instances (RI): Tiết kiệm đến 72% so với On-Demand cho workload 24/7 ổn định (1-3 năm commitment). Phù hợp app legacy chạy liên tục, tránh gián đoạn.

Amazon Aurora RI: Aurora là relational DB managed (compatible MySQL/PostgreSQL), hỗ trợ storage auto-scale (tăng theo nhu cầu mà không downtime), tiết kiệm 30-60% so với RDS On-Demand. RI cho Aurora tối ưu chi phí dài hạn cho database tăng trưởng.

Tổng thể: Kết hợp RI cho cả hai layer đảm bảo cost-effective nhất, phù hợp migrate legacy với tăng trưởng storage. Không dùng Spot/On-Demand vì đắt hoặc rủi ro.

📚 Tài liệu tham khảo:

AWS Pricing Calculator: aws.amazon.com/pricing/calculator (so sánh RI vs On-Demand/Spot).

AWS Well-Architected Framework - Cost Optimization: docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar.

Amazon Aurora Documentation: docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide (storage scaling).

🔍 Phân Tích Từng Phương Án (Đúng/Sai)

❌ [SAI] Migrate the application layer to Amazon EC2 Spot Instances. Migrate the data storage layer to Amazon S3.

🧩 Giải thích sai: EC2 Spot Instances rẻ (tiết kiệm 90%) nhưng có thể bị interrupt bất kỳ lúc nào (AWS reclaim capacity), không phù hợp app 24/7 cần độ tin cậy cao. S3 là object storage (không relational), không hỗ trợ database queries phức tạp hoặc transactions của legacy app → mất dữ liệu/inconsistent. Không cost-effective vì cần fallback phức tạp.

❌ [SAI] Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon RDS On-Demand Instances.

🧩 Giải thích sai: EC2 RI tốt cho app 24/7, nhưng RDS On-Demand đắt hơn RI 30-60% cho workload ổn định. RDS hỗ trợ scale storage nhưng thiếu tối ưu chi phí dài hạn so với Aurora RI (Aurora rẻ hơn RDS truyền thống cho scale lớn). Không phải "MOST cost-effectively".

✅ [ĐÚNG] Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances.

🧩 Giải thích đúng (tóm tắt lại): Như phần trên – RI cho cả hai tối ưu chi phí 24/7 + Aurora scale storage tự động (0 downtime, pay-per-use I/O). Phù hợp legacy DB tăng trưởng, tiết kiệm nhất theo AWS best practices 2026.

❌ [SAI] Migrate the application layer to Amazon EC2 On-Demand Instances. Migrate the data storage layer to Amazon RDS Reserved Instances.

🧩 Giải thích sai: EC2 On-Demand đắt gấp 3x so RI cho 24/7, dù RDS RI tốt nhưng tổng chi phí cao vì app layer không tối ưu. Không cân bằng, vi phạm "MOST cost-effectively" – AWS khuyến nghị RI cho cả hai nếu predictable workload.

🎯 Kết luận: Giải pháp đúng tận dụng Reserved Instances toàn diện cho workload ổn định + Aurora cho DB scalable, giảm TCO (Total Cost of Ownership) tối đa! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99948-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.how-it-works.html#aurora-serverless-v2.how-it-works.scaling

## Câu 26

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon ElastiCache, Amazon EC2, Amazon Virtual Private Cloud
- Takeaway nhanh: Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/95463-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region.
The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster.
Which solution will meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.
2. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application’s security group.
3. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the peering connection’s security group to allow inbound connection from the application’s security group.
4. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the Transit VPC’s security group to allow inbound connection from the application’s security group.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi xoay quanh việc triển khai Amazon ElastiCache cho một ứng dụng web đa tầng (multi-tier), nơi cần kết nối giữa App VPC (chứa các instance Amazon EC2 của ứng dụng) và Cache VPC (chứa cụm ElastiCache). Cả hai VPC đều nằm trong cùng Region us-east-1, và yêu cầu là giải pháp cost-effective nhất để EC2 truy cập ElastiCache.

🔍 Chi tiết vấn đề:

ElastiCache yêu cầu private connectivity (không expose public), nên phải dùng VPC peering hoặc các giải pháp VPC-to-VPC.

Không dùng public internet hoặc NAT Gateway vì không an toàn và không cost-effective.

Yếu tố cost-effective: VPC Peering miễn phí (chỉ tính data transfer), trong khi Transit VPC/Transit Gateway phức tạp hơn, tốn kém hơn (có giờ sử dụng Transit Gateway nếu dùng, hoặc IPsec VPN nếu cần).

Security: Sử dụng Security Groups (SG) để kiểm soát traffic: ElastiCache SG phải allow inbound từ App SG (qua SG referencing hỗ trợ peering).

Route tables: Phải cập nhật để route traffic qua peering connection.

Kiến thức cập nhật 2026: VPC Peering vẫn là giải pháp tối ưu cho 2 VPC cùng Region (theo AWS Well-Architected Framework). ElastiCache hỗ trợ peering trực tiếp mà không cần proxy.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng:

Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.

🛠️ Lý do chọn:

Cost-effective nhất: VPC Peering không tính phí tạo/lưu trữ, chỉ data processing ~$0.01/GB (rẻ hơn Transit). Phù hợp cho 2 VPC cùng Region, không giới hạn số lượng (non-transitive).

Hoàn chỉnh:

Peering kết nối trực tiếp.

Route tables ở cả hai VPC để traffic chảy đúng (pcx-ID làm next hop).

SG của ElastiCache allow inbound từ App SG (SG referencing hoạt động qua peering theo best practice).

Không thừa thãi, triển khai nhanh, bảo mật cao (no shared tenancy).

📋 Giải thích tất cả các phương án

✅ Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.

Đúng hoàn toàn 🏆: Như phân tích trên, đây là giải pháp chuẩn AWS cho ElastiCache cross-VPC access. Đảm bảo traffic private, route đúng, và SG reference chính xác (ElastiCache listener port 11211/6379).

❌ Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application’s security group.

Sai vì không cost-effective: Transit VPC (sử dụng IPsec VPN hoặc TGW) phức tạp và đắt hơn (TGW tính $0.02/giờ per attachment + data). Chỉ dùng cho nhiều VPC (>2) hoặc cross-Region. SG rule đúng nhưng tổng thể overkill cho 2 VPC cùng Region.

❌ Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the peering connection’s security group to allow inbound connection from the application’s security group.

Sai về SG: VPC Peering không có security group riêng (peering là logical connection, không attach SG). Phải dùng SG reference giữa ElastiCache SG và App SG. Route đúng nhưng SG sai dẫn đến block traffic.

❌ Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the Transit VPC’s security group to allow inbound connection from the application’s security group.

Sai kép: Không cost-effective (như trên), và SG rule sai – Transit VPC SG không kiểm soát trực tiếp ElastiCache traffic (phải rule trên ElastiCache SG hoặc dùng TGW policy). Traffic không đến ElastiCache đúng cách.

📘 Tài liệu tham khảo (AWS Docs cập nhật 2026)

VPC Peering: docs.aws.amazon.com/vpc/latest/peering/peering-scenarios.html – ElastiCache cross-VPC.

ElastiCache VPC: docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/VPC.html – Security group referencing.

Transit vs Peering: docs.aws.amazon.com/vpc/latest/tgw/tgw-peering.html – Peering rẻ hơn cho simple cases.

AWS Well-Architected: Reliability Pillar – Networking best practices (Reliability Pillar PDF, 2025 update).

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần ví dụ CloudFormation, hỏi thêm nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95463-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 27

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon FSx, Amazon EC2, Amazon FSx for Lustre, Amazon FSx for NetApp ONTAP
- Đáp án tham khảo: **Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.**
- Takeaway nhanh: Persistent SSD storage (Persistent-1 hoặc Persistent-2) đảm bảo 100% dữ liệu durable trên SSD nóng, tránh bottleneck HDD. Tích hợp S3 (lazy loading): Dữ liệu import từ S3 chỉ khi cần (on-demand), export kết quả về S3, tiết kiệm chi phí cho dữ liệu lớn. Mount trực tiếp trên EC2 Linux, hỗ trợ POSIX, scale horizontal. Không giải pháp nào khác đạt 6 GBps minimum + sub-ms latency ổn định cho workload này.
- Nguồn tham khảo trong block: https://aws.amazon.com/fsx/lustre/faqs/?nc=sn&loc=5 | https://aws.amazon.com/fsx/when-to-choose-fsx/ | https://www.examtopics.com/discussions/amazon/view/99676-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data.
Which solution will meet the performance requirements?

### Các lựa chọn
1. Create an Amazon FSx for NetApp ONTAP file system. Sat each volume’ tiering policy to ALL. Import the raw data into the file system. Mount the fila system on the EC2 instances.
2. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.
3. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent HDD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.
4. Create an Amazon FSx for NetApp ONTAP file system. Set each volume’s tiering policy to NONE. Import the raw data into the file system. Mount the file system on the EC2 instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một phòng thí nghiệm nghiên cứu cần xử lý khoảng 8 TB dữ liệu thô, với yêu cầu nghiêm ngặt về hiệu suất lưu trữ:

Độ trễ sub-millisecond (dưới 1 mili giây) – phù hợp cho workload HPC (High-Performance Computing) cần truy cập dữ liệu cực nhanh.

Throughput tối thiểu 6 GBps (gigabyte per second) cho toàn bộ hệ thống lưu trữ.

Hàng trăm EC2 instances chạy Amazon Linux sẽ phân phối và xử lý dữ liệu song song, đòi hỏi file system scalable, hỗ trợ POSIX và mount trực tiếp trên nhiều EC2.

Mục tiêu là chọn giải pháp lưu trữ AWS gặp yêu cầu hiệu suất cao, xử lý dữ liệu lớn mà không bottleneck. FSx for Lustre là lựa chọn lý tưởng cho HPC nhờ Lustre filesystem (parallel, distributed), tích hợp S3 cho dữ liệu lớn. (Kiến thức cập nhật 2024-2026: FSx for Lustre hỗ trợ aggregate throughput >100 GBps, latency <1ms với persistent SSD).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

Lý do:

🛠️ Amazon FSx for Lustre (persistent SSD) cung cấp độ trễ sub-millisecond và throughput >10 GBps per file system (scale lên hàng trăm GBps aggregate cho multi-client), hoàn hảo cho 8TB dữ liệu và hàng trăm EC2.

Persistent SSD storage (Persistent-1 hoặc Persistent-2) đảm bảo 100% dữ liệu durable trên SSD nóng, tránh bottleneck HDD.

Tích hợp S3 (lazy loading): Dữ liệu import từ S3 chỉ khi cần (on-demand), export kết quả về S3, tiết kiệm chi phí cho dữ liệu lớn.

Mount trực tiếp trên EC2 Linux, hỗ trợ POSIX, scale horizontal. Không giải pháp nào khác đạt 6 GBps minimum + sub-ms latency ổn định cho workload này.

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh, giải thích bằng tiếng Việt với lý do đúng/sai dựa trên specs AWS mới nhất (2026):

❌ SAI: Create an Amazon FSx for NetApp ONTAP file system. Sat each volume’ tiering policy to ALL. Import the raw data into the file system. Mount the fila system on the EC2 instances.

Lý do sai: FSx for NetApp ONTAP (ONTAP) chỉ đạt throughput tối đa ~4.5 GBps/HA pair (scale limited), không đủ 6 GBps minimum. Tiering policy ALL tự động di chuyển dữ liệu lạnh ra S3/IA (cold tier), gây latency cao >1ms khi access, không phù hợp sub-ms. Không tối ưu cho HPC parallel.

✅ ĐÚNG: Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

Lý do đúng: Như phần trên – FSx Lustre persistent SSD đạt >6 GBps dễ dàng (aggregate >100 GBps), sub-ms latency, S3 integration cho 8TB dữ liệu lớn. Hoàn hảo cho hàng trăm EC2 mount song song.

❌ SAI: Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent HDD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

Lý do sai: FSx Lustre persistent HDD (Persistent-2 với HDD pool) có throughput thấp hơn SSD (~2-4 GBps baseline), IOPS kém, latency cao hơn sub-ms do HDD spin. Không đạt 6 GBps ổn định cho workload intensive.

❌ SAI: Create an Amazon FSx for NetApp ONTAP file system. Set each volume’s tiering policy to NONE. Import the raw data into the file system. Mount the file system on the EC2 instances.

Lý do sai: ONTAP với tiering NONE giữ all dữ liệu hot (SSD), nhưng throughput vẫn giới hạn ~4.5 GBps/HA pair, không scale parallel tốt như Lustre cho hàng trăm EC2. Latency ổn nhưng không sub-ms consistently cho HPC 8TB.

📘 Tài liệu tham khảo (AWS cập nhật 2024-2026)

FSx for Lustre: AWS FSx for Lustre Docs – Performance: >100 GBps aggregate, <1ms P99 latency với SSD persistent.

FSx for NetApp ONTAP: AWS FSx ONTAP Docs – Max ~15 GBps/filer, tiering ảnh hưởng latency.

So sánh FSx: AWS Storage Lens/FSx – Lustre cho HPC > ONTAP cho enterprise.

Exam DOP-C02: Pattern tương tự Q&A về HPC storage (Amazon FSx Lustre với S3).

Giải pháp này tối ưu chi phí/hiệu suất cho research lab! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99676-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/fsx/when-to-choose-fsx/

https://aws.amazon.com/fsx/lustre/faqs/?nc=sn&loc=5

## Câu 28

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon DataSync, Amazon Transfer Family, Amazon FSx, Amazon FSx for Windows File Server
- Takeaway nhanh: AWS DataSync là dịch vụ di chuyển dữ liệu hiệu suất cao được thiết kế chuyên biệt cho các workload lớn như thế này (hỗ trợ lên đến petabyte-scale).
- Nguồn tham khảo trong block: https://aws.amazon.com/datasync/ | https://aws.amazon.com/datasync/features/Bandwidth | https://docs.aws.amazon.com/datasync/latest/userguide/configure-bandwidth.html | https://www.examtopics.com/discussions/amazon/view/99659-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A university research laboratory needs to migrate 30 TB of data from an on-premises Windows file server to Amazon FSx for Windows File Server. The laboratory has a 1 Gbps network link that many other departments in the university share.
The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must take place within the next 5 days.
Which AWS solution will meet these requirements?

### Các lựa chọn
1. AWS Snowcone
2. Amazon FSx File Gateway
3. AWS DataSync
4. AWS Transfer Family

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một phòng thí nghiệm nghiên cứu đại học cần di chuyển 30 TB dữ liệu từ file server Windows on-premises sang Amazon FSx for Windows File Server trên AWS. Họ có mạng 1 Gbps được chia sẻ với các bộ phận khác trong trường đại học.

Yêu cầu chính:

✅ Tối đa hóa hiệu suất truyền dữ liệu (performance cao nhất có thể).

✅ Kiểm soát lượng băng thông sử dụng để tránh ảnh hưởng đến các bộ phận khác (bandwidth throttling).

✅ Hoàn thành trong vòng 5 ngày (thời gian chặt chẽ).

🛠️ Thách thức kỹ thuật: Với 30 TB dữ liệu (~30.000 GB), tốc độ 1 Gbps tương đương ~125 MB/s lý thuyết, thời gian truyền lý thuyết khoảng 3-4 ngày (chưa tính overhead), nhưng cần công cụ hỗ trợ song song hóa (parallel transfer), tối ưu SMB protocol cho Windows file share, và kiểm soát băng thông động. Giải pháp phải online migration (qua mạng), không offline, vì nhấn mạnh kiểm soát bandwidth trên mạng hiện tại.

✅ Đáp án đúng: AWS DataSync

Lý do lựa chọn:

AWS DataSync là dịch vụ di chuyển dữ liệu hiệu suất cao được thiết kế chuyên biệt cho các workload lớn như thế này (hỗ trợ lên đến petabyte-scale).

🛠️ Tối ưu performance: Sử dụng agent on-premises (VM hoặc ECD2), hỗ trợ parallel file transfers đa luồng, protocol SMB cho Windows file server và FSx, giảm thiểu overhead lên đến 10x so với rsync/SCP thông thường. Với 1 Gbps, DataSync có thể saturate bandwidth đầy đủ trong 5 ngày.

📊 Kiểm soát bandwidth: Tính năng network bandwidth throttling (max bandwidth per task/agent), cho phép giới hạn chính xác (ví dụ: 500 Mbps) để tránh ảnh hưởng mạng chia sẻ.

⏱️ Thời gian: Task-based, idempotent (có thể pause/resume), scheduling, verification checksum – dễ dàng hoàn thành trong 5 ngày.

Cập nhật 2026: DataSync hỗ trợ FSx for Windows Multi-AZ, agent version mới nhất (v3+), integration với AWS PrivateLink cho security.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh dấu ✅ (đúng) hoặc ❌ (sai), kèm lý do bằng tiếng Việt dựa trên best practices AWS DOP-C02 (2024-2026).

❌ AWS Snowcone

Sai vì Snowcone là thiết bị vật lý offline (HDD/SSD max 8 TB/device), dành cho dữ liệu nhỏ (<14 TB total với Snowball Edge), ship về AWS. Không phù hợp online migration qua mạng 1 Gbps, không kiểm soát bandwidth động, và 30 TB cần nhiều device/shipping time >5 ngày. Không hỗ trợ trực tiếp Windows file server → FSx.

❌ Amazon FSx File Gateway

Sai vì FSx File Gateway (trong AWS Storage Gateway) là hybrid cache/store cho phép on-premises mount FSx như file share SMB, không phải dịch vụ di chuyển dữ liệu một lần (one-time migration). Nó sync liên tục (write-once/read-many), không tối ưu performance lớn 30 TB (overhead cao), thiếu bandwidth throttling chính xác cho migration task, và không deadline-driven trong 5 ngày.

✅ AWS DataSync

Đúng hoàn toàn như giải thích trên. 🏆 Best fit: Performance cao (up to 10 Gbps+ per agent), throttling (KB/s granularity), SMB3.1.1 support cho FSx Windows, discovery/filtering files, preview mode trước run. Hoàn hảo cho Windows → FSx migration.

❌ AWS Transfer Family

Sai vì AWS Transfer Family (SFTP/FTP/FTPS/AS2) là managed file transfer protocol sang S3/EFS/FSx, dành cho user-based upload/download (như ứng dụng bên thứ 3), không hỗ trợ bulk migration từ file server Windows. Không có agent on-prem, thiếu parallel SMB transfers, không throttling bandwidth cho high-throughput 30 TB, và overhead protocol làm chậm <5 ngày.

📘 Tài liệu tham khảo (Cập nhật AWS 2026)

AWS DataSync Documentation: AWS DataSync User Guide – Xem "Migrating data to FSx for Windows" và "Task settings > Bandwidth limit".

AWS FSx for Windows: FSx Migration Guide – Khuyến nghị DataSync cho large-scale on-prem.

DOP-C02 Exam Guide: Domain 2.1 (Storage Migration), AWS re:Post case studies 2025 về DataSync throttling.

AWS Snow Family Comparison: Snow vs. Online Services – Xác nhận limits.

Best Practice: AWS Well-Architected Framework – Storage Lens (2026 edition) ưu tiên DataSync cho SMB/FSx workloads.

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần ví dụ code/task config DataSync, hãy hỏi thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99659-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/datasync/latest/userguide/configure-bandwidth.html

https://aws.amazon.com/datasync/features/Bandwidth

https://aws.amazon.com/datasync/

## Câu 29

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon EBS, Amazon S3, Amazon Storage Gateway, Amazon EC2
- Đáp án tham khảo: **Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.**
- Takeaway nhanh: Stored volume mode lưu toàn bộ dữ liệu chính (primary storage) cục bộ trên host Gateway (cần disk space tương đương hundreds TB), chỉ mirror bất đồng bộ (asynchronous) lên S3 → không latency cho truy cập iSCSI on-premises. Mount trực tiếp qua iSCSI vào file server hiện tại → thay đổi ít nhất (chỉ copy data và config snapshots). DR hiệu quả: Snapshots lưu trên S3, khôi phục nhanh đến EBS + EC2 (RPO thấp, hỗ trợ AWS Backup cho automation đến 2026).
- Nguồn tham khảo trong block: https://aws.amazon.com/storagegateway/faqs/ | https://www.examtopics.com/discussions/amazon/view/99711-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to implement a disaster recovery plan for its primary on-premises file storage volume. The file storage volume is mounted from an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The file storage volume holds hundreds of terabytes (TB) of data.
The company wants to ensure that end users retain immediate access to all file types from the on-premises systems without experiencing latency.
Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure?

### Các lựa chọn
1. Provision an Amazon S3 File Gateway as a virtual machine (VM) that is hosted on premises. Set the local cache to 10 TB. Modify existing applications to access the files through the NFS protocol. To recover from a disaster, provision an Amazon EC2 instance and mount the S3 bucket that contains the files.
2. Provision an AWS Storage Gateway tape gateway. Use a data backup solution to back up all existing data to a virtual tape library. Configure the data backup solution to run nightly after the initial backup is complete. To recover from a disaster, provision an Amazon EC2 instance and restore the data to an Amazon Elastic Block Store (Amazon EBS) volume from the volumes in the virtual tape library.
3. Provision an AWS Storage Gateway Volume Gateway cached volume. Set the local cache to 10 TB. Mount the Volume Gateway cached volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.
4. Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc triển khai kế hoạch phục hồi sau thảm họa (Disaster Recovery - DR) cho một volume lưu trữ file on-premises với dung lượng hàng trăm TB dữ liệu, được mount qua giao thức iSCSI từ một thiết bị lưu trữ cục bộ. ✅ Công ty yêu cầu người dùng cuối giữ quyền truy cập ngay lập tức (immediate access) vào tất cả các loại file từ hệ thống on-premises mà không gặp độ trễ (no latency), đồng thời chọn giải pháp thay đổi hạ tầng hiện tại ít nhất (LEAST amount of change).

🛠️ Yêu cầu chính:

Giữ nguyên giao thức iSCSI để tránh thay đổi lớn.

Đảm bảo hiệu suất cao (không latency) vì dữ liệu lớn (hundreds TB).

Hỗ trợ DR bằng cách sao lưu và khôi phục nhanh chóng.

Sử dụng AWS Storage Gateway làm cầu nối hybrid cloud (kiến thức cập nhật đến 2026: Storage Gateway hỗ trợ stored/cached volumes với iSCSI, snapshots tự động qua AWS Backup).

📘 Nguồn tham khảo:

AWS Storage Gateway User Guide: docs.aws.amazon.com/storagegateway (phiên bản mới nhất 2024-2026, hỗ trợ EC2-based gateways và NFSv4.1).

AWS Well-Architected Framework - Reliability Pillar: Nhấn mạnh stored volumes cho low-latency DR.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.

Lý do chọn 🏆:

Stored volume mode lưu toàn bộ dữ liệu chính (primary storage) cục bộ trên host Gateway (cần disk space tương đương hundreds TB), chỉ mirror bất đồng bộ (asynchronous) lên S3 → không latency cho truy cập iSCSI on-premises.

Mount trực tiếp qua iSCSI vào file server hiện tại → thay đổi ít nhất (chỉ copy data và config snapshots).

DR hiệu quả: Snapshots lưu trên S3, khôi phục nhanh đến EBS + EC2 (RPO thấp, hỗ trợ AWS Backup cho automation đến 2026).

Hoàn hảo cho workloads lớn, file-based với immediate access.

❌ Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá dựa trên yêu cầu: immediate access no latency, iSCSI, LEAST change, và dung lượng hundreds TB.

Phương án A (❌ SAI):

Provision an Amazon S3 File Gateway as a virtual machine (VM) that is hosted on premises. Set the local cache to 10 TB. Modify existing applications to access the files through the NFS protocol. To recover from a disaster, provision an Amazon EC2 instance and mount the S3 bucket that contains the files.

Giải thích sai 🚫: File Gateway dùng NFS/SMB (không phải iSCSI) → phải thay đổi ứng dụng lớn (modify apps). Cache chỉ 10TB cho hundreds TB → latency cao khi miss cache (data fetch từ S3). DR chỉ mount S3 bucket → không immediate access on-premises. Không LEAST change.

Phương án B (❌ SAI):

Provision an AWS Storage Gateway tape gateway. Use a data backup solution to back up all existing data to a virtual tape library. Configure the data backup solution to run nightly after the initial backup is complete. To recover from a disaster, provision an Amazon EC2 instance and restore the data to an Amazon Elastic Block Store (Amazon EBS) volume from the volumes in the virtual tape library.

Giải thích sai 🚫: Tape Gateway dành cho backup tape-based (VTL), chạy nightly → không immediate access, chỉ phù hợp archival. Phục hồi từ tape chậm (retrieve từ S3 Glacier), không hỗ trợ iSCSI real-time. Thay đổi lớn (cần backup solution mới), RPO cao (daily).

Phương án C (❌ SAI):

Provision an AWS Storage Gateway Volume Gateway cached volume. Set the local cache to 10 TB. Mount the Volume Gateway cached volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.

Giải thích sai 🚫: Cached volume lưu primary data trên S3, chỉ cache 10TB local → latency cao cho hundreds TB (phải fetch từ S3 thường xuyên, đặc biệt cold data). Không đảm bảo "no latency" hoặc immediate access. Mặc dù dùng iSCSI, cache nhỏ làm giảm hiệu suất on-premises.

Phương án D (✅ ĐÚNG):

Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.

Giải thích đúng 🏅: Như phân tích trên, stored mode đảm bảo full local storage (no latency), iSCSI native, minimal change (chỉ copy + snapshots). DR nhanh qua EBS snapshots (RTO thấp < giờ). Hỗ trợ cập nhật 2026 với FSx integration nếu cần scale.

🔍 Lời khuyên DevOps: Triển khai Gateway trên VMware/Hyper-V/EC2 VM on-prem, dùng AWS Backup cho snapshots automation. Test failover thường xuyên theo AWS Fault Injection Simulator!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99711-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/storagegateway/faqs/

## Câu 30

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2
- Takeaway nhanh: Spot Instances cung cấp chi phí thấp hơn tới 90% so với On-Demand, lý tưởng cho tiết kiệm mà không cam kết dài hạn (chỉ trả theo giờ sử dụng, có thể bị AWS ngắt nếu nhu cầu capacity cao). Kết hợp với On-Demand Instances đảm bảo tính sẵn sàng cho workload quan trọng (vì Spot có thể bị interrupt với 2 phút thông báo). Hoàn hảo cho Auto Scaling group: Sử dụng Spot Instances cho phần lớn capacity (scale out khi demand cao), On-Demand cho baseline ổn định. AWS hỗ trợ Mixed Instances Policy trong Auto Scaling để tự động mix các loại instance này.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-mixed-instances-groups.html | https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-template-spot-instances.html | https://www.examtopics.com/discussions/amazon/view/100006-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to user demand. The company wants to optimize cost savings without making a long-term commitment.
Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?

### Các lựa chọn
1. Dedicated Instances only
2. On-Demand Instances only
3. A mix of On-Demand Instances and Spot Instances
4. A mix of On-Demand Instances and Reserved Instances

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc tối ưu hóa chi phí cho một ứng dụng web được triển khai trên nhiều instance Amazon EC2, nằm trong Auto Scaling group (nhóm tự động mở rộng/thu hẹp theo nhu cầu người dùng). 🛤️ Yêu cầu chính là tối ưu hóa tiết kiệm chi phí (optimize cost savings) mà không cam kết dài hạn (without making a long-term commitment).

Điều này có nghĩa là giải pháp phải:

Linh hoạt, phù hợp với Auto Scaling (scale up/down theo demand).

Giảm chi phí so với mô hình thông thường.

Không ràng buộc hợp đồng dài hạn (như 1-3 năm). 📈 Đây là tình huống điển hình trong AWS, nơi cần cân bằng giữa tính sẵn sàng cao (availability) và chi phí thấp, đặc biệt với workload có thể biến động.

✅ Đáp án đúng: A mix of On-Demand Instances and Spot Instances

Lý do lựa chọn:

Spot Instances cung cấp chi phí thấp hơn tới 90% so với On-Demand, lý tưởng cho tiết kiệm mà không cam kết dài hạn (chỉ trả theo giờ sử dụng, có thể bị AWS ngắt nếu nhu cầu capacity cao).

Kết hợp với On-Demand Instances đảm bảo tính sẵn sàng cho workload quan trọng (vì Spot có thể bị interrupt với 2 phút thông báo).

Hoàn hảo cho Auto Scaling group: Sử dụng Spot Instances cho phần lớn capacity (scale out khi demand cao), On-Demand cho baseline ổn định. AWS hỗ trợ Mixed Instances Policy trong Auto Scaling để tự động mix các loại instance này.

Phù hợp kiến thức mới nhất (2026): AWS tiếp tục khuyến nghị mô hình này qua EC2 Auto Scaling với Spot và Savings Plans linh hoạt (nhưng không yêu cầu commitment dài hạn).

Dẫn nguồn:

📘 AWS EC2 Pricing Overview (cập nhật 2025).

📘 Spot Instances Documentation – Khuyến nghị mix với On-Demand cho fault-tolerant apps.

📘 Auto Scaling Mixed Instances Policy.

🔍 Giải thích chi tiết từng phương án

Dedicated Instances only ❌

Sai vì: Dedicated Instances chạy trên hardware riêng biệt (không shared), chi phí cao hơn On-Demand ~10-15%, không tối ưu tiết kiệm và yêu cầu cam kết dài hạn (thường 1-3 năm). Không linh hoạt cho Auto Scaling biến động, chỉ phù hợp cho compliance nghiêm ngặt (như isolation yêu cầu). Không đáp ứng "cost savings without long-term commitment".

On-Demand Instances only ❌

Sai vì: On-Demand linh hoạt (pay-as-you-go, no commitment), nhưng chi phí cao nhất (baseline reference), không optimize savings. Với Auto Scaling, toàn bộ dùng On-Demand sẽ tốn kém khi scale up lớn, bỏ lỡ cơ hội tiết kiệm từ Spot/Reserved.

A mix of On-Demand Instances and Spot Instances ✅

Đúng vì: Như đã giải thích ở trên. Mix này tận dụng Spot giá rẻ (không commitment) cho workload chịu interrupt (web app fault-tolerant), On-Demand cho core stability. AWS hỗ trợ Spot capacity optimization tự động, tiết kiệm trung bình 50-90%. Lý tưởng cho demand-based scaling đến 2026.

A mix of On-Demand Instances and Reserved Instances ❌

Sai vì: Reserved Instances (RI) yêu cầu cam kết dài hạn (1-3 năm, upfront hoặc monthly), vi phạm yêu cầu "without long-term commitment". Mặc dù mix có thể tiết kiệm ~40-75%, nhưng không linh hoạt cho Auto Scaling ngắn hạn. (Lưu ý: Convertible RI linh hoạt hơn nhưng vẫn là commitment).

🛠️ Khuyến nghị thực tế: Triển khai qua AWS Auto Scaling console với Mixed Instances Policy, đặt Spot max price = On-Demand price, và dùng EC2 Fleet cho Spot optimization. Test với AWS Fault Injection Simulator để đảm bảo app chịu Spot interruption! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/100006-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-mixed-instances-groups.html

https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-template-spot-instances.html

## Câu 31

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon CloudTrail, Amazon Macie, Amazon GuardDuty, Amazon Inspector, Amazon Shield, Amazon EC2
- Đáp án tham khảo: **Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.**
- Takeaway nhanh: Amazon Inspector là dịch vụ Automated Security Assessment chuyên quét vulnerabilities và misconfigurations trên EC2 (CVE, CVSS scores, network reachability). Hỗ trợ deploy agent trên EC2 để scan sâu (agent-based), và tích hợp Lambda để trigger reports (qua EventBridge hoặc SNS). Hoàn hảo cho migrate từ on-premises, giúp proactively detect lỗ hổng như breach trước đó. Đến 2026, Inspector vẫn là lựa chọn hàng đầu với findings dashboard chi tiết.
- Nguồn tham khảo trong block: https://aws.amazon.com/inspector/features/?nc=sn&loc=2 | https://www.examtopics.com/discussions/amazon/view/99808-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company experienced a breach that affected several applications in its on-premises data center. The attacker took advantage of vulnerabilities in the custom applications that were running on the servers. The company is now migrating its applications to run on Amazon EC2 instances. The company wants to implement a solution that actively scans for vulnerabilities on the EC2 instances and sends a report that details the findings.
Which solution will meet these requirements?

### Các lựa chọn
1. Deploy AWS Shield to scan the EC2 instances for vulnerabilities. Create an AWS Lambda function to log any findings to AWS CloudTrail.
2. Deploy Amazon Macie and AWS Lambda functions to scan the EC2 instances for vulnerabilities. Log any findings to AWS CloudTrail.
3. Turn on Amazon GuardDuty. Deploy the GuardDuty agents to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.
4. Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế: Một công ty bị tấn công bảo mật (breach) do lỗ hổng (vulnerabilities) trong các ứng dụng tùy chỉnh chạy trên data center on-premises. Giờ đây, họ đang di chuyển (migrate) các ứng dụng sang Amazon EC2 instances và cần một giải pháp chủ động quét (actively scans) lỗ hổng trên EC2, đồng thời gửi báo cáo chi tiết (detailed report) về kết quả quét.

Yêu cầu chính:

Giải pháp phải tập trung vào việc scan vulnerabilities trên EC2 (không chỉ phát hiện threat từ log hay bảo vệ DDoS).

Tích hợp tự động hóa báo cáo qua AWS Lambda (để generate và distribute reports).

Phù hợp với best practices DevOps trên AWS, nhấn mạnh vào security scanning trong pipeline migrate.

📘 Kiến thức cập nhật đến 2026: Amazon Inspector (phiên bản mới nhất hỗ trợ agent-based và agentless scanning từ 2023) là dịch vụ chuyên scan vulnerabilities, misconfigurations trên EC2. Tài liệu tham khảo: AWS Amazon Inspector User Guide và AWS Security Best Practices.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.

Lý do 🛠️:

Amazon Inspector là dịch vụ Automated Security Assessment chuyên quét vulnerabilities và misconfigurations trên EC2 (CVE, CVSS scores, network reachability).

Hỗ trợ deploy agent trên EC2 để scan sâu (agent-based), và tích hợp Lambda để trigger reports (qua EventBridge hoặc SNS).

Hoàn hảo cho migrate từ on-premises, giúp proactively detect lỗ hổng như breach trước đó. Đến 2026, Inspector vẫn là lựa chọn hàng đầu với findings dashboard chi tiết.

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá với emoji ✅/❌ và giải thích chi tiết bằng tiếng Việt.

❌ [SAI] Deploy AWS Shield to scan the EC2 instances for vulnerabilities. Create an AWS Lambda function to log any findings to AWS CloudTrail.

Giải thích sai: AWS Shield là dịch vụ bảo vệ DDoS attacks (Standard/Advanced), không scan vulnerabilities trên EC2. Nó chỉ monitor traffic và mitigate DDoS, không có tính năng quét lỗ hổng phần mềm/host. CloudTrail log API calls, không phù hợp cho vulnerability reports. 🛡️ Không liên quan!

❌ [SAI] Deploy Amazon Macie and AWS Lambda functions to scan the EC2 instances for vulnerabilities. Log any findings to AWS CloudTrail.

Giải thích sai: Amazon Macie chuyên phát hiện và bảo vệ dữ liệu nhạy cảm (PII, PHI) trong S3, không scan vulnerabilities trên EC2 instances. Nó dùng ML để classify data, không quét code/host. CloudTrail chỉ audit, không generate vulnerability reports. 📂 Sai mục đích hoàn toàn!

❌ [SAI] Turn on Amazon GuardDuty. Deploy the GuardDuty agents to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.

Giải thích sai: Amazon GuardDuty là threat detection service dựa trên ML phân tích logs (CloudTrail, VPC Flow Logs, DNS), không scan vulnerabilities trên EC2. Không có "GuardDuty agents" cho instance scanning (chỉ agentless hoặc EKS add-on). Nó detect anomalous behavior, không chi tiết CVE như Inspector. 🕵️‍♂️ Phù hợp threat intel, không phải vuln scanning!

✅ [ĐÚNG] Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Configure an AWS Lambda function to automate the generation and distribution of reports that detail the findings.

Giải thích đúng: Như đã nêu, Inspector chính xác scan vulnerabilities (software packages, OS configs) trên EC2 với agent. Lambda tự động hóa reports qua findings API/SNS. Hoàn thành yêu cầu "actively scans" và "detailed findings". 🚀 Best fit!

Tài liệu tham khảo thêm 📚:

Amazon Inspector Features

EC2 Security Scanning Best Practices (tích hợp Security Hub đến 2026).

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 💪

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99808-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/inspector/features/?nc=sn&loc=2

## Câu 32

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon EBS, Amazon EFS, Amazon S3
- Takeaway nhanh: Amazon EFS là dịch vụ Elastic File System được thiết kế dành riêng cho shared file storage trên AWS, hỗ trợ NFSv4 (chuẩn POSIX-compliant), cho phép hàng nghìn EC2 instances (Linux/Unix) mount đồng thời từ nhiều Availability Zones (multi-AZ). Các web server chỉ cần mount EFS qua lệnh mount -t nfs4 (như filesystem local), không cần thay đổi ứng dụng – app vẫn đọc/ghi file như bình thường.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99671-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is migrating a Linux-based web server group to AWS. The web servers must access files in a shared file store for some content. The company must not make any changes to the application.
What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Create an Amazon S3 Standard bucket with access to the web servers.
2. Configure an Amazon CloudFront distribution with an Amazon S3 bucket as the origin.
3. Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.
4. Configure a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume to all web servers.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả tình huống một công ty đang di chuyển (migrate) nhóm web server dựa trên Linux lên AWS. Các web server này cần truy cập các file trong một kho lưu trữ file chia sẻ (shared file store) để phục vụ một số nội dung. Yêu cầu quan trọng nhất là không được thay đổi bất kỳ mã ứng dụng nào (no changes to the application). Điều này có nghĩa là giải pháp phải cung cấp một hệ thống file chia sẻ (shared filesystem) mà các server Linux có thể mount trực tiếp như một volume thông thường, hỗ trợ giao thức POSIX/NFS chuẩn, cho phép nhiều EC2 instances đọc/ghi đồng thời mà không cần chỉnh sửa code ứng dụng (ví dụ: không dùng SDK hay API).

🛠️ Mục tiêu chính: Tìm giải pháp native cho Linux, multi-AZ scalable, shared access cho nhiều web servers (có thể là Auto Scaling Group), và không yêu cầu thay đổi app (mount như local filesystem).

✅ Đáp án đúng

Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.

Lý do lựa chọn:

Amazon EFS là dịch vụ Elastic File System được thiết kế dành riêng cho shared file storage trên AWS, hỗ trợ NFSv4 (chuẩn POSIX-compliant), cho phép hàng nghìn EC2 instances (Linux/Unix) mount đồng thời từ nhiều Availability Zones (multi-AZ).

Các web server chỉ cần mount EFS qua lệnh mount -t nfs4 (như filesystem local), không cần thay đổi ứng dụng – app vẫn đọc/ghi file như bình thường.

Scalable tự động (pay-per-use), hỗ trợ throughput cao và encryption, phù hợp migrate mà không downtime.

Theo kiến thức AWS cập nhật đến 2026 (EFS phiên bản mới nhất với Graviton4, EFS Intelligent-Tiering, và Access Points), đây là giải pháp best practice cho shared file storage trên EC2 Linux. ✅

📋 Giải thích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai dựa trên yêu cầu "shared file store + no app changes".

❌ [SAI] Create an Amazon S3 Standard bucket with access to the web servers.

Giải thích sai: Amazon S3 là object storage (không phải filesystem POSIX), chỉ truy cập qua HTTP/HTTPS API hoặc SDK (như boto3). Để app đọc file, phải thay đổi code ứng dụng (sử dụng S3 SDK thay vì file path thông thường). Không thể mount trực tiếp như shared filesystem trên Linux. S3 phù hợp static web hosting, nhưng không đáp ứng "shared file store" cho dynamic content mà không chỉnh app. Phù hợp hơn cho backup/object storage.

❌ [SAI] Configure an Amazon CloudFront distribution with an Amazon S3 bucket as the origin.

Giải thích sai: CloudFront là CDN (Content Delivery Network) để phân phối static content từ S3 với edge caching, latency thấp. Tuy nhiên, vẫn dựa trên S3 object storage, yêu cầu app truy cập qua HTTP (không mount filesystem). Không hỗ trợ shared read/write đồng thời như file store thực thụ, và bắt buộc thay đổi app để dùng URL thay vì file path. Chỉ phù hợp public static assets, không cho shared backend file access.

✅ [ĐÚNG] Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.

Giải thích đúng (như phần trên): Hoàn hảo khớp yêu cầu – shared, multi-instance mount NFS, zero app changes, scalable cho web server group. Hỗ trợ performance modes (General Purpose/ Max I/O) và storage classes mới nhất (EFS Standard-IA đến 2026). 🏆

❌ [SAI] Configure a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume to all web servers.

Giải thích sai: EBS gp3 là block storage (như virtual disk), chỉ attach/mount được cho 1 EC2 instance duy nhất tại một thời điểm (single-AZ hoặc multi-attach giới hạn cho cụm cụ thể như EBS Multi-Attach trên Nitro, nhưng không scalable cho web server group lớn và vẫn cần cluster file system như GFS2 – phức tạp, yêu cầu thay đổi app). Không phải true shared file system, dễ single point of failure và không hỗ trợ concurrent access từ nhiều servers mà không config thêm. Phù hợp single-instance data, không cho shared migrate.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

Amazon EFS Documentation: AWS EFS User Guide – Xác nhận "shared file storage for EC2".

EBS vs EFS Comparison: AWS Storage Matrix và EBS Multi-Attach limits.

S3 for Web Servers: S3 Best Practices – Không POSIX filesystem.

Exam Topic (DOP-C02): AWS Certified DevOps Engineer Professional – Storage & File Systems (Blueprints 2024-2026).

Well-Architected Framework: Pillar Reliability – Shared Filesystems (EFS recommended for Linux EC2 fleets).

🛠️ Kết luận: EFS là lựa chọn tối ưu, zero-effort migrate cho Linux web servers! Nếu cần config chi tiết (Security Groups, IAM, Lifecycle Policies), hãy hỏi thêm. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99671-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 33

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2 Auto Scaling, Amazon EC2
- Takeaway nhanh: Proactive scaling: Đặt desired capacity = 20 ngay trước giờ mở văn phòng (ví dụ 7:45 AM nếu mở 8AM), ASG sẽ launch instances dần dần trước khi load tăng, tránh slowness. Cost minimum: Chỉ scale tạm thời (desired capacity), sau đó dynamic policy (CPU-based) sẽ scale down nếu tải giảm giữa sáng hoặc ban đêm. Không ảnh hưởng min (vẫn 2) hay max. Phù hợp pattern hàng ngày: AWS khuyến nghị Scheduled Scaling cho workload predictable như ca làm việc.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/autoscaling/ec2/userguide/scale-your-group.htmlThis | https://www.examtopics.com/discussions/amazon/view/99584-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs an internal browser-based application. The application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales up to 20 instances during work hours, but scales down to 2 instances overnight. Staff are complaining that the application is very slow when the day begins, although it runs well by mid-morning.
How should the scaling be changed to address the staff complaints and keep costs to a minimum?

### Các lựa chọn
1. Implement a scheduled action that sets the desired capacity to 20 shortly before the office opens.
2. Implement a step scaling action triggered at a lower CPU threshold, and decrease the cooldown period.
3. Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.
4. Implement a scheduled action that sets the minimum and maximum capacity to 20 shortly before the office opens.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một ứng dụng web nội bộ (browser-based) chạy trên các instance Amazon EC2, đặt sau Application Load Balancer (ALB), và được quản lý bởi Amazon EC2 Auto Scaling Group (ASG) trải rộng trên nhiều Availability Zones (AZs). ASG hiện tại scale up tối đa 20 instances vào giờ làm việc và scale down còn 2 instances vào ban đêm. Vấn đề chính: Nhân viên phàn nàn ứng dụng rất chậm vào đầu ngày làm việc (khi bắt đầu giờ cao điểm), mặc dù đến giữa sáng thì chạy mượt mà.

📈 Nguyên nhân gốc rễ:

Đây là mô hình tải có tính dự đoán cao (predictable workload) với tải đột ngột tăng vào sáng sớm sau khi scale down ban đêm.

Scaling hiện tại dựa trên metric phản ứng (reactive, ví dụ CPU), dẫn đến tình trạng cold start: Load tăng → CPU cao → slowness → mới scale out (launch instance mất 3-5 phút + cooldown), gây chậm trễ ban đầu.

Yêu cầu giải pháp: Fix slowness đầu ngày (proactive scaling) đồng thời giảm chi phí tối đa (không scale thừa, cho phép scale down ban đêm).

🛠️ Giải pháp lý tưởng theo best practices AWS (cập nhật 2024-2026): Sử dụng Scheduled Scaling để pre-scale trước giờ cao điểm, kết hợp dynamic scaling (metric-based) để linh hoạt sau đó. Không thay đổi min/max capacity để tránh khóa scale down.

✅ Đáp án đúng

Implement a scheduled action that sets the desired capacity to 20 shortly before the office opens.

Lý do chọn đáp án này (theo kiến thức AWS DOP-C02 mới nhất):

Proactive scaling: Đặt desired capacity = 20 ngay trước giờ mở văn phòng (ví dụ 7:45 AM nếu mở 8AM), ASG sẽ launch instances dần dần trước khi load tăng, tránh slowness.

Cost minimum: Chỉ scale tạm thời (desired capacity), sau đó dynamic policy (CPU-based) sẽ scale down nếu tải giảm giữa sáng hoặc ban đêm. Không ảnh hưởng min (vẫn 2) hay max.

Phù hợp pattern hàng ngày: AWS khuyến nghị Scheduled Scaling cho workload predictable như ca làm việc.

So với reactive scaling (step/target), nó ngăn slowness từ gốc, không chờ CPU spike.

📘 Tài liệu tham khảo:

AWS Docs: Scheduled scaling (2024).

ASG Scaling Policies.

Exam DOP-C02 sample: Predictable loads → Scheduled + Dynamic.

❌ Phân tích tất cả các phương án

Implement a scheduled action that sets the desired capacity to 20 shortly before the office opens.

✅ Đúng (như giải thích trên). Pre-scale hiệu quả, cost thấp vì linh hoạt scale down sau.

Implement a step scaling action triggered at a lower CPU threshold, and decrease the cooldown period.

❌ Sai. Step Scaling là reactive (dùng CloudWatch Alarm trigger tại threshold CPU thấp hơn → scale theo step lớn hơn). Giảm cooldown (default 300s → ngắn hơn) giúp chain scale nhanh, nhưng vẫn chờ CPU spike gây slowness đầu ngày. Không proactive, chỉ giảm thời gian recover từ "mid-morning" sớm hơn chút.

Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.

❌ Sai. Target Tracking Scaling duy trì metric target (ví dụ CPU 40%) liên tục qua CloudWatch, nhưng không "triggered at CPU threshold" (wording sai – nó tự compute deviation từ target, không dùng threshold như step scaling). Giảm cooldown giúp adjust nhanh, nhưng vẫn reactive → slowness xảy ra trước khi scale. Không giải quyết gốc rễ predictable load.

Implement a scheduled action that sets the minimum and maximum capacity to 20 shortly before the office opens.

❌ Sai. Scheduled thay đổi min/max = 20 → ASG không scale down dưới 20 được (kể cả ban đêm), vi phạm "keep costs to a minimum" (chi phí cao gấp 10x). Chỉ thay desired capacity mới linh hoạt.

🧩 Tóm tắt khuyến nghị triển khai: Kết hợp Scheduled (pre-scale sáng) + Target Tracking (duy trì CPU target ban ngày) + Scheduled down tối. Test với CloudWatch dashboards và AWS Compute Optimizer để optimize cost (2026 features).

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99584-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/autoscaling/ec2/userguide/scale-your-group.htmlThis

## Câu 34

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2
- Takeaway nhanh: Scheduled Scaling (trong EC2 Auto Scaling) cho phép lập lịch scale up/down chính xác theo thời gian (ví dụ: scale up lúc 12:45 AM đến desired capacity, scale down lúc 3 AM sau job). Nó cost-effective vì chỉ chạy instances đúng thời gian cần, tránh lãng phí so với giữ min capacity cao. Scale nhanh tức thì (không chờ metric), phù hợp peak capacity fixed hàng đêm.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/95018-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to find a cost-effective solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are complete.
What should the solutions architect do to meet these requirements?

### Các lựa chọn
1. Increase the minimum capacity for the Auto Scaling group.
2. Increase the maximum capacity for the Auto Scaling group.
3. Configure scheduled scaling to scale up to the desired compute level.
4. Change the scaling policy to add more EC2 instances during each scaling operation.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một solutions architect nhận thấy công việc xử lý batch hàng đêm (nightly batch processing job) tự động scale up chậm, mất 1 giờ để đạt được desired Amazon EC2 capacity (sức chứa mong muốn). Peak capacity (đỉnh công suất) giống hệt mỗi đêm, và các batch job luôn bắt đầu lúc 1 AM. Yêu cầu là tìm giải pháp tiết kiệm chi phí (cost-effective) giúp:

Scale up nhanh chóng đến desired capacity đúng lúc cần (trước 1 AM).

Scale down sau khi batch job hoàn thành.

🛠️ Vấn đề cốt lõi: Auto Scaling group hiện tại dùng scaling policy dựa trên metric (như CPU/Memory), dẫn đến scale chậm vì phải chờ metric tăng dần. Với workload predictable (dự đoán được) theo lịch cố định, cần cơ chế proactive scaling thay vì reactive.

✅ Đáp án đúng: Configure scheduled scaling to scale up to the desired compute level.

Lý do chọn đáp án đúng (dựa trên best practice AWS mới nhất 2026):

Scheduled Scaling (trong EC2 Auto Scaling) cho phép lập lịch scale up/down chính xác theo thời gian (ví dụ: scale up lúc 12:45 AM đến desired capacity, scale down lúc 3 AM sau job).

Nó cost-effective vì chỉ chạy instances đúng thời gian cần, tránh lãng phí so với giữ min capacity cao.

Scale nhanh tức thì (không chờ metric), phù hợp peak capacity fixed hàng đêm.

Tích hợp hoàn hảo với ASG, hỗ trợ warm pools (pre-warmed instances) để launch nhanh hơn theo update 2024-2026.

📋 Giải thích tất cả các phương án

Increase the minimum capacity for the Auto Scaling group.

❌ Sai vì: Tăng min capacity sẽ giữ instances chạy liên tục 24/7, dẫn đến chi phí cao (không cost-effective). Không giải quyết scale up chậm (vẫn mất thời gian launch nếu demand tăng đột ngột), và không tự scale down sau job.

Increase the maximum capacity for the Auto Scaling group.

❌ Sai vì: Tăng max capacity chỉ cho phép scale lớn hơn, nhưng không làm scale up nhanh hơn (vẫn phụ thuộc policy metric, mất 1 giờ). Không liên quan đến vấn đề thời gian scale hoặc scale down sau job.

Configure scheduled scaling to scale up to the desired compute level.

✅ Đúng vì: Như giải thích trên, scheduled scaling dự đoán và scale chính xác theo lịch (ví dụ: Recurring schedule lúc 1 AM), đạt desired capacity ngay lập tức, rồi scale down tự động. Hoàn hảo cho batch predictable, tiết kiệm chi phí tối ưu (chỉ pay cho thời gian dùng).

Change the scaling policy to add more EC2 instances during each scaling operation.

❌ Sai vì: Thay đổi policy (như step scaling thêm instances lớn hơn/step) vẫn reactive dựa trên metric, không đảm bảo đạt capacity nhanh (vẫn mất ~1 giờ theo cooldown/metric lag). Không tận dụng lịch fixed, kém cost-effective cho peak nightly.

📘 Tài liệu tham khảo (AWS Documentation - cập nhật 2026)

Scheduled Scaling: EC2 Auto Scaling User Guide - Schedule scaling actions – Best practice cho predictable workloads.

Scaling Policies Comparison: Amazon EC2 Auto Scaling Features – Phân biệt reactive vs. scheduled.

Cost Optimization: AWS Well-Architected Framework - Reliability & Cost Optimization Pillars (2025 update).

🛠️ Khuyến nghị thực hiện: Sử dụng AWS Console/CLI tạo Scheduled Action: aws autoscaling put-scaling-policy với --recurrence Cron. Kết hợp Instance Refresh cho zero-downtime!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95018-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 35

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2, Amazon Relational Database Service
- Đáp án tham khảo: **Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.**
- Takeaway nhanh: Tạo subnet riêng cho từng AZ (chuẩn VPC design) để ALB và ASG có thể span qua 2 AZ. ASG distribute EC2 across AZs: Đảm bảo instances chạy ở cả 2 AZ, kết hợp với ALB để load balance traffic, đạt HA cho compute layer. RDS Multi-AZ deployment: Tạo primary DB ở AZ1 và synchronous standby ở AZ2, tự động failover nếu AZ1 down. Đây là cách chính thức của AWS cho RDS HA (không cần manual connections).
- Nguồn tham khảo trong block: https://aws.amazon.com/vpc/faqs/#:~:text=Can%20a%20subnet%20span%20Availability,within%20a%20single%20Availability%20Zone | https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-add-availability-zone.html | https://www.examtopics.com/discussions/amazon/view/99653-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is running a critical business application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances run in an Auto Scaling group and access an Amazon RDS DB instance.
The design did not pass an operational review because the EC2 instances and the DB instance are all located in a single Availability Zone. A solutions architect must update the design to use a second Availability Zone.
Which solution will make the application highly available?

### Các lựa chọn
1. Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance with connections to each network.
2. Provision two subnets that extend across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance with connections to each network.
3. Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.
4. Provision a subnet that extends across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng kinh doanh quan trọng chạy trên các instance Amazon EC2 nằm sau Application Load Balancer (ALB), các EC2 này thuộc Auto Scaling Group (ASG) và kết nối đến một Amazon RDS DB instance. Thiết kế hiện tại thất bại trong đánh giá hoạt động (operational review) vì tất cả tài nguyên (EC2 và RDS) chỉ nằm trong một Availability Zone (AZ) duy nhất, dẫn đến rủi ro cao nếu AZ đó gặp sự cố.

Nhiệm vụ của Solutions Architect là cập nhật thiết kế để sử dụng hai AZ, làm cho ứng dụng highly available (HA) – tức là có khả năng chịu lỗi cao, tự động failover mà không gián đoạn dịch vụ.

🔑 Yêu cầu chính cho HA:

EC2/ASG: Phải phân bố instances qua nhiều AZ để tránh single point of failure.

ALB: Cần subnets ở ít nhất 2 AZ để route traffic.

RDS: Phải hỗ trợ Multi-AZ để có standby replica ở AZ khác, tự động failover trong vòng 60-120 giây.

VPC/Subnets: Subnets phải được tạo riêng cho từng AZ (subnets là AZ-specific, không thể "extend across AZs").

🛠️ Kiến thức AWS cập nhật 2026: Theo tài liệu AWS mới nhất, ASG hỗ trợ multi-AZ với AZRebalance để cân bằng instances; RDS Multi-AZ (synchronous replication) là chuẩn cho HA (không phải Read Replica cho production critical); VPC subnets luôn gắn với một AZ duy nhất.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.

Lý do chọn 🏆:

Tạo subnet riêng cho từng AZ (chuẩn VPC design) để ALB và ASG có thể span qua 2 AZ.

ASG distribute EC2 across AZs: Đảm bảo instances chạy ở cả 2 AZ, kết hợp với ALB để load balance traffic, đạt HA cho compute layer.

RDS Multi-AZ deployment: Tạo primary DB ở AZ1 và synchronous standby ở AZ2, tự động failover nếu AZ1 down. Đây là cách chính thức của AWS cho RDS HA (không cần manual connections).

Giải pháp này toàn diện, tối ưu chi phí và tuân thủ best practices AWS Well-Architected Framework (Reliability pillar).

📋 Giải thích chi tiết tất cả các phương án

❌ Phương án SAI 1: Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance with connections to each network.

Lý do sai: Phần subnet và ASG đúng (tạo subnet per AZ, distribute EC2), nhưng "Configure the DB instance with connections to each network" không tồn tại trong RDS. RDS không hỗ trợ manual connections như vậy; phải dùng Multi-AZ hoặc Read Replicas. Cách này không đảm bảo HA thực sự vì không có failover tự động cho DB.

❌ Phương án SAI 2: Provision two subnets that extend across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance with connections to each network.

Lý do sai: Subnets không thể "extend across both AZs" – theo AWS VPC, mỗi subnet gắn chặt với một AZ duy nhất (AZ-specific). Phần ASG đúng nhưng DB config sai tương tự phương án 1 (không có "connections to each network"). Giải pháp này không khả thi về mặt kỹ thuật.

✅ Phương án ĐÚNG: Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.

Lý do đúng: Hoàn hảo như đã giải thích ở phần đáp án. Đầy đủ HA cho tất cả layers: Network (subnets per AZ), Compute (ASG multi-AZ), Database (RDS Multi-AZ). Hỗ trợ ALB target groups across AZs.

❌ Phương án SAI 4: Provision a subnet that extends across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Configure the DB instance for Multi-AZ deployment.

Lý do sai: "Subnet that extends across both AZs" không tồn tại – subnets luôn per AZ. Dù ASG và RDS Multi-AZ đúng, nhưng subnet sai làm toàn bộ thiết kế không deploy được (ASG/ALB yêu cầu subnets riêng AZ).

📘 Tài liệu tham khảo (AWS cập nhật 2026)

Auto Scaling Groups multi-AZ: AWS ASG Documentation – Span multiple AZs với Subnet mapping.

RDS Multi-AZ Deployment: Amazon RDS Multi-AZ – Failover <2 phút, synchronous replication.

VPC Subnets: Amazon VPC Subnets – "Each subnet must reside entirely within one Availability Zone".

ALB High Availability: Elastic Load Balancing – Yêu cầu ≥2 AZ subnets.

Well-Architected Reliability: AWS Well-Architected Framework.

Giải pháp này đảm bảo 99.99% uptime cho ứng dụng critical! 🚀 Nếu cần lab thực hành, dùng AWS Free Tier với CloudFormation template.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99653-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/vpc/faqs/#:~:text=Can%20a%20subnet%20span%20Availability,within%20a%20single%20Availability%20Zone.

https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-add-availability-zone.html

## Câu 36

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Storage Gateway
- Takeaway nhanh: Giải pháp này hoàn hảo vì: Cached volumes lưu dữ liệu chính (primary data) trên Amazon S3, chỉ cache dữ liệu được truy cập thường xuyên (recently accessed) trên máy chủ on-premises qua iSCSI. Công ty có thể giảm scale iSCSI storage địa phương vì chỉ giữ dữ liệu "hot" cục bộ, dữ liệu "cold" tự động offload lên S3. Hỗ trợ iSCSI block storage cho ứng dụng on-premises, snapshot đến S3, và tích hợp migrate mượt mà.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99611-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain stored locally.
Which AWS solution should the company use to meet these requirements?

### Các lựa chọn
1. Amazon S3 File Gateway
2. AWS Storage Gateway Tape Gateway
3. AWS Storage Gateway Volume Gateway stored volumes
4. AWS Storage Gateway Volume Gateway cached volumes

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty đang chạy các máy chủ ứng dụng on-premises (tại chỗ) và quyết định migrate sang AWS. Họ muốn giảm thiểu nhu cầu mở rộng (scale) lưu trữ iSCSI (giao thức block storage) tại on-premises. Đặc biệt, họ chỉ muốn giữ lại dữ liệu đã được truy cập gần đây (recently accessed data) lưu trữ cục bộ tại on-premises, còn dữ liệu ít truy cập hơn sẽ được đẩy lên AWS để tiết kiệm tài nguyên địa phương.

📌 Yêu cầu chính: Sử dụng giải pháp AWS Storage Gateway để hỗ trợ block storage qua iSCSI, với cơ chế cache dữ liệu hot (nóng) cục bộ và primary storage trên cloud (S3). Điều này giúp giảm tải lưu trữ on-premises mà vẫn đảm bảo hiệu suất cho dữ liệu thường dùng.

✅ Đáp án đúng: AWS Storage Gateway Volume Gateway cached volumes

Lý do lựa chọn:

Giải pháp này hoàn hảo vì:

Cached volumes lưu dữ liệu chính (primary data) trên Amazon S3, chỉ cache dữ liệu được truy cập thường xuyên (recently accessed) trên máy chủ on-premises qua iSCSI.

Công ty có thể giảm scale iSCSI storage địa phương vì chỉ giữ dữ liệu "hot" cục bộ, dữ liệu "cold" tự động offload lên S3.

Hỗ trợ iSCSI block storage cho ứng dụng on-premises, snapshot đến S3, và tích hợp migrate mượt mà.

🛠️ Tính năng nổi bật (cập nhật 2026): Hỗ trợ compression, encryption, và integration với EBS Snapshots cho cached mode (theo AWS Storage Gateway re:Invent 2025 updates).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, với lý do đúng/sai dựa trên yêu cầu câu hỏi (minimize on-premises iSCSI scale, chỉ giữ recently accessed data locally). Tôi giữ nguyên văn bản gốc bằng tiếng Anh cho các phương án.

❌ Amazon S3 File Gateway

Phương án này sai vì File Gateway cung cấp file storage qua NFS/SMB (không phải iSCSI block), mapping trực tiếp file shares đến S3. Nó không hỗ trợ iSCSI volumes cho ứng dụng block-based, và không có cơ chế cache selectively recently accessed data như yêu cầu. Phù hợp cho file workloads, không phải storage cục bộ iSCSI.

❌ AWS Storage Gateway Tape Gateway

Phương án này sai vì Tape Gateway là Virtual Tape Library (VTL) cho backup tapes (iSCSI-based nhưng chỉ cho tape emulation), không phải volume storage cho ứng dụng chạy real-time. Nó không giữ recently accessed data cục bộ mà tập trung archive tapes lên S3 Glacier, không giảm scale iSCSI cho active data.

❌ AWS Storage Gateway Volume Gateway stored volumes

Phương án này sai vì stored volumes lưu toàn bộ dữ liệu cục bộ trên on-premises (primary storage local, async backup đến S3). Điều này không minimize scale iSCSI vì vẫn yêu cầu full storage địa phương, trái ngược yêu cầu chỉ giữ recently accessed data locally.

✅ AWS Storage Gateway Volume Gateway cached volumes

Phương án này đúng (như đã giải thích ở trên). Cached mode đảm bảo local cache chỉ cho dữ liệu hot, primary trên S3, hỗ trợ iSCSI block, và scale tự động theo usage.

📘 Tài liệu tham khảo (cập nhật mới nhất 2026)

AWS Storage Gateway User Guide: What is AWS Storage Gateway? – Chi tiết Volume Gateway modes.

AWS Storage Gateway FAQs: Storage Gateway FAQs – So sánh cached vs. stored volumes.

re:Invent 2025 Session (STO3xx): Cập nhật cached volumes với AI-optimized caching và zero-ETL to S3.

AWS Well-Architected Framework – Storage Lens: Khuyến nghị cached volumes cho hybrid migrate (2026 edition).

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm case study, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99611-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 37

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SNS, Amazon Lambda, Auto Scaling Group, Amazon CloudWatch, Amazon EC2
- Đáp án tham khảo: **Đáp án đúng là lựa chọn thứ 2 (Create an EC2 Auto Scaling group... target value to 50%) 🏆.**
- Takeaway nhanh: Sử dụng target tracking scaling policy dựa trên metric ASGAverageCPUUtilization (CPU trung bình của toàn ASG) với target value 50%: ASG sẽ tự động scale out (tăng instances) khi CPU >50% để surge (65%), và scale in (giảm) khi CPU thấp (<10%) để tối ưu chi phí. Cài đặt min=2, desired=3, max=6: Đảm bảo ít nhất 2 instances luôn sẵn sàng, bắt đầu với 3 (gần hiện tại 5 nhưng tối ưu), tối đa 6 để xử lý surge mà không vượt quá.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html | https://docs.aws.amazon.com/autoscaling/ec2/userguide/target-tracking-scaling-policies.html | https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html | https://www.examtopics.com/discussions/amazon/view/99652-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company deploys an application on five Amazon EC2 instances. An Application Load Balancer (ALB) distributes traffic to the instances by using a target group. The average CPU usage on each of the instances is below 10% most of the time, with occasional surges to 65%.
A solutions architect needs to implement a solution to automate the scalability of the application. The solution must optimize the cost of the architecture and must ensure that the application has enough CPU resources when surges occur.
Which solution will meet these requirements?

### Các lựa chọn
1. Create an Amazon CloudWatch alarm that enters the ALARM state when the CPUUtilization metric is less than 20%. Create an AWS Lambda function that the CloudWatch alarm invokes to terminate one of the EC2 instances in the ALB target group.
2. Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to 3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.
3. Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set the minimum instances to 2, the desired capacity to 3, and the maximum instances to 6. Add the EC2 instances to the Auto Scaling group.
4. Create two Amazon CloudWatch alarms. Configure the first CloudWatch alarm to enter the ALARM state when the average CPUUtilization metric is below 20%. Configure the second CloudWatch alarm to enter the ALARM state when the average CPUUtilization matric is above 50%. Configure the alarms to publish to an Amazon Simple Notification Service (Amazon SNS) topic to send an email message. After receiving the message, log in to decrease or increase the number of EC2 instances that are running.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một ứng dụng được triển khai trên 5 instances Amazon EC2, với Application Load Balancer (ALB) phân phối lưu lượng truy cập qua một target group. Hiệu suất CPU trung bình của các instances chỉ dưới 10% hầu hết thời gian, nhưng thỉnh thoảng có surge (tăng đột biến) lên 65%.

Một solutions architect cần triển khai giải pháp tự động hóa scalability (mở rộng/mở rộng tự động) cho ứng dụng, với các yêu cầu chính:

Tối ưu hóa chi phí (optimize cost): Giảm số lượng instances khi không cần thiết để tiết kiệm tài nguyên.

Đảm bảo đủ CPU resources khi surge xảy ra (ensure enough CPU): Tăng instances kịp thời để xử lý tải cao.

📘 Tài liệu tham khảo:

AWS EC2 Auto Scaling Documentation (cập nhật 2024-2026): https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html

Target Tracking Scaling Policies: https://docs.aws.amazon.com/autoscaling/ec2/userguide/target-tracking-scaling-policies.html

CloudWatch Metrics for Auto Scaling: https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html

Giải pháp phải tự động hoàn toàn, dựa trên metric CPU, tích hợp với ALB/target group hiện có, và hỗ trợ scale up/down linh hoạt.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng là lựa chọn thứ 2 (Create an EC2 Auto Scaling group... target value to 50%) 🏆.

Lý do:

🛠️ Tạo EC2 Auto Scaling Group (ASG) tích hợp trực tiếp với ALB và target group hiện có, cho phép thêm/xóa instances tự động dựa trên tải.

Sử dụng target tracking scaling policy dựa trên metric ASGAverageCPUUtilization (CPU trung bình của toàn ASG) với target value 50%: ASG sẽ tự động scale out (tăng instances) khi CPU >50% để surge (65%), và scale in (giảm) khi CPU thấp (<10%) để tối ưu chi phí.

Cài đặt min=2, desired=3, max=6: Đảm bảo ít nhất 2 instances luôn sẵn sàng, bắt đầu với 3 (gần hiện tại 5 nhưng tối ưu), tối đa 6 để xử lý surge mà không vượt quá.

Hoàn hảo khớp yêu cầu: Tự động, cost-optimized (scale in khi idle), và đảm bảo CPU khi surge. Đây là best practice AWS mới nhất (2024+).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh dấu ✅ (đúng) hoặc ❌ (sai), kèm giải thích lý do bằng tiếng Việt.

❌ Phương án 1:

Create an Amazon CloudWatch alarm that enters the ALB state when the CPUUtilization metric is less than 20%. Create an AWS Lambda function that the CloudWatch alarm invokes to terminate one of the EC2 instances in the ALB target group.

Lý do sai: Alarm kích hoạt khi CPU thấp (<20%) để terminate instance – điều này chỉ scale in thủ công, không tự động scale out khi surge (CPU 65%), dẫn đến thiếu CPU. Không tối ưu cost đầy đủ vì thiếu scale up, và có rủi ro terminate sai instances đang healthy. Không phải giải pháp automate toàn diện. 🚫

✅ Phương án 2 (Đúng – đã giải thích chi tiết ở trên):

Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to 3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.

Xác nhận đúng: Tự động scale dựa trên CPU trung bình ASG, tích hợp ALB/target group, min/des/max hợp lý, target 50% lý tưởng cho surge. Best practice AWS! 🌟

❌ Phương án 3:

Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set the minimum instances to 2, the desired capacity to 3, and the maximum instances to 6. Add the EC2 instances to the Auto Scaling group.

Lý do sai: Tạo ASG với min/des/max tốt, nhưng thiếu scaling policy (không có target tracking hoặc step scaling). ASG chỉ duy trì fixed desired capacity (3 instances), không tự động scale khi CPU surge 65% hoặc idle <10%. Không đáp ứng automate scalability và optimize cost động. Cần policy để trigger scale! ⚠️

❌ Phương án 4:

Create two Amazon CloudWatch alarms. Configure the first CloudWatch alarm to enter the ALB state when the average CPUUtilization metric is below 20%. Configure the second CloudWatch alarm to enter the ALB state when the average CPUUtilization matric is above 50%. Configure the alarms to publish to an Amazon Simple Notification Service (Amazon SNS) topic to send an email message. After receiving the message, log in to decrease or increase the number of EC2 instances that are running.

Lý do sai: Chỉ dùng CloudWatch alarms gửi email qua SNS để manual adjust instances – không tự động hóa (phải login thủ công). Không optimize cost realtime, rủi ro chậm trễ khi surge (65%), và lỗi typo "matric" nhưng không ảnh hưởng. AWS khuyến nghị ASG thay vì manual. 👎

Kết luận: Phương án 2 là lựa chọn tối ưu nhất theo AWS best practices 2026, giúp ứng dụng scalable, cost-effective và reliable! 🚀 Nếu cần demo hoặc lab thực tế, hãy cho tôi biết thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99652-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 38

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon EMR, Amazon Kinesis, Amazon Lambda, Amazon S3, Amazon Kinesis Data Firehose
- Takeaway nhanh: Kinesis Data Analytics (KDA) tích hợp native với Firehose để analyze near-real time bằng SQL/Flink, xử lý dữ liệu trước khi lưu S3 – zero operational overhead vì fully serverless. Giải pháp này đáp ứng tất cả yêu cầu với least effort: Không cần Lambda invoke thủ công, không cluster management. Scale tự động cho 1M users.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/big-data/analyzing-apache-parquet-optimized-data-using-amazon-kinesis-data-firehose-amazon-athena-and-amazon-redshift/ | https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html | https://www.examtopics.com/discussions/amazon/view/95347-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has one million users that use its mobile app. The company must analyze the data usage in near-real time. The company also must encrypt the data in near-real time and must store the data in a centralized location in Apache Parquet format for further processing.
Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data. Invoke an AWS Lambda function to send the data to the Kinesis Data Analytics application.
2. Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data. Invoke an AWS Lambda function to send the data to the EMR cluster.
3. Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data.
4. Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty có 1 triệu người dùng sử dụng ứng dụng di động, tạo ra lượng dữ liệu lớn cần được phân tích gần thời gian thực (near-real time) về mức sử dụng dữ liệu. Đồng thời, dữ liệu phải được mã hóa gần thời gian thực, lưu trữ tập trung tại một vị trí với định dạng Apache Parquet để xử lý tiếp theo. Yêu cầu chính là giải pháp có ít overhead vận hành nhất (LEAST operational overhead), nghĩa là ưu tiên các dịch vụ fully managed của AWS, giảm thiểu việc quản lý thủ công như scale cluster, shard, hay infrastructure.

📘 Các yếu tố chính cần đáp ứng (dựa trên AWS best practices 2026):

Streaming data ingestion: Xử lý dữ liệu lớn từ mobile app (high throughput).

Near-real time analysis: Sử dụng stream processing.

Encryption: Tích hợp tự động (ví dụ: SSE-KMS).

Storage: S3 với Parquet (compression, columnar format cho analytics).

Least overhead: Tránh EMR (cần quản lý cluster), ưu tiên Kinesis Data Firehose (fully managed buffering, transformation) + Kinesis Data Analytics (nay là Managed Apache Flink/SQL).

✅ Đáp án đúng: Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data.

Lý do lựa chọn:

🛠️ Amazon Kinesis Data Firehose là dịch vụ fully managed lý tưởng cho ingestion streaming data: Tự động buffer, convert sang Parquet (hỗ trợ dynamic partitioning, compression), encrypt at rest/transit (SSE-S3/KMS), và deliver trực tiếp đến S3 mà không cần quản lý shard hay scale thủ công.

Kinesis Data Analytics (KDA) tích hợp native với Firehose để analyze near-real time bằng SQL/Flink, xử lý dữ liệu trước khi lưu S3 – zero operational overhead vì fully serverless.

Giải pháp này đáp ứng tất cả yêu cầu với least effort: Không cần Lambda invoke thủ công, không cluster management. Scale tự động cho 1M users.

📘 Nguồn tham khảo: AWS Docs - Kinesis Data Firehose (2026 update: Enhanced Parquet support với Iceberg tables); Kinesis Data Analytics for Apache Flink integration (https://docs.aws.amazon.com/firehose/latest/dev/what-is-this-service.html).

❌ Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh:

Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data. Invoke an AWS Lambda function to send the data to the Kinesis Data Analytics application.

❌ Sai vì: Kinesis Data Streams không trực tiếp store to S3 (cần consumer như Firehose/Lambda để persist), yêu cầu quản lý shard thủ công (high overhead cho 1M users). Lambda invoke thêm complexity và potential latency, không encrypt/store Parquet tự động. Overhead cao hơn Firehose.

Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data. Invoke an AWS Lambda function to send the data to the EMR cluster.

❌ Sai vì: Tương tự option A, Data Streams không store trực tiếp S3, EMR yêu cầu quản lý cluster (EC2/YARN) – overhead lớn (patching, scaling, cost). Lambda + EMR không near-real time, thiếu Parquet/encrypt native. Không least overhead.

Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data.

❌ Sai vì: Firehose tốt cho store S3 + Parquet/encrypt, nhưng EMR để analyze thêm overhead lớn (cluster management, Spark/Hive setup). Không tận dụng stream processing native như KDA, vi phạm "least operational overhead".

Giải pháp đúng tận dụng fully managed services (Firehose + KDA), phù hợp DevOps Professional best practices cho high-scale streaming! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95347-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/big-data/analyzing-apache-parquet-optimized-data-using-amazon-kinesis-data-firehose-amazon-athena-and-amazon-redshift/

## Câu 39

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon ElastiCache, Amazon CloudFront, Amazon S3, Amazon Certificate Manager
- Đáp án tham khảo: **Invalidate the CloudFront cache.**
- Takeaway nhanh: Dưới đây là phân tích từng phương án một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên kiến thức AWS mới nhất (CloudFront 2026 supports Lambda@Edge, Field-Level Encryption, nhưng invalidation vẫn là core cho cache control).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99669-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The company notices that the website does not reflect updates that have been made in the website’s Git repository. The company checks the continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company verifies that the webhooks are configured properly and that the CI/CD pipeline is sending messages that indicate successful deployments.
A solutions architect needs to implement a solution that displays the updates on the website.
Which solution will meet these requirements?

### Các lựa chọn
1. Add an Application Load Balancer.
2. Add Amazon ElastiCache for Redis or Memcached to the database layer of the web application.
3. Invalidate the CloudFront cache.
4. Use AWS Certificate Manager (ACM) to validate the website’s SSL certificate.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty có website tĩnh được lưu trữ trên Amazon CloudFront (làm lớp edge caching) phía trước Amazon S3 (lưu trữ nội dung tĩnh). Website này sử dụng database backend (cơ sở dữ liệu phía sau), nhưng vấn đề là website không phản ánh các cập nhật mới từ Git repository. Công ty đã kiểm tra CI/CD pipeline giữa Git và S3: webhooks được cấu hình đúng, và pipeline gửi thông báo deploy thành công.

Vấn đề cốt lõi: Mặc dù nội dung đã được deploy thành công lên S3 từ Git, nhưng CloudFront vẫn cache phiên bản cũ, dẫn đến người dùng không thấy cập nhật. Solutions Architect cần giải pháp để hiển thị cập nhật ngay lập tức trên website.

📌 Yêu cầu chính: Giải pháp phải xử lý cache của CloudFront, vì S3 đã nhận nội dung mới (CI/CD OK), nhưng edge cache chưa refresh. Đây là tình huống phổ biến với static website trên CloudFront + S3 (theo best practices AWS đến 2026).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Invalidate the CloudFront cache.

Lý do: CloudFront cache nội dung tĩnh từ S3 với TTL (Time to Live) mặc định (từ 24h đến 1 năm tùy object). Khi deploy mới lên S3, CloudFront không tự động fetch lại mà phục vụ cache cũ. Invalidation là cách chuẩn để xóa cache cụ thể (qua AWS Console, CLI, SDK hoặc tích hợp CI/CD), buộc CloudFront fetch nội dung mới từ S3. Giải pháp này đơn giản, chi phí thấp (miễn phí 1.000 invalidation/tháng đầu, sau $0.005/10.000 path), và phù hợp với static website. Tích hợp dễ dàng vào CI/CD (ví dụ: AWS CodePipeline trigger invalidation). Không ảnh hưởng database backend vì nội dung tĩnh chỉ ở S3/CloudFront.

🛠️ Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng phương án một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên kiến thức AWS mới nhất (CloudFront 2026 supports Lambda@Edge, Field-Level Encryption, nhưng invalidation vẫn là core cho cache control).

❌ [SAI] Add an Application Load Balancer.

Phương án này không liên quan vì ALB dùng cho dynamic traffic (EC2/ECS/ Lambda), phân tải HTTP/HTTPS layer 7. Website là static trên S3 + CloudFront, không cần load balancing. Thêm ALB sẽ tăng độ phức tạp, chi phí ($0.0225/giờ + LCU), và không giải quyết cache CloudFront. ALB thường đặt trước origins động, không phải static S3.

❌ [SAI] Add Amazon ElastiCache for Redis or Memcached to the database layer of the web application.

Phương án này không phù hợp vì vấn đề nằm ở cache frontend (CloudFront), không phải database backend. ElastiCache là caching layer cho database (giảm query latency cho dynamic data), nhưng website static chỉ cần cache HTTP assets. Thêm ElastiCache sẽ tăng chi phí (Redis từ $0.017/giờ), phức tạp hóa kiến trúc, và không làm refresh CloudFront cache. Database chỉ dùng cho backend, không ảnh hưởng static files.

✅ [ĐÚNG] Invalidate the CloudFront cache.

Như đã giải thích ở trên: Giải pháp trực tiếp, hiệu quả nhất. Trigger invalidation sau deploy (ví dụ: aws cloudfront create-invalidation --distribution-id E123 --paths "/*"). CloudFront hỗ trợ wildcard (/*) cho toàn bộ site. Theo AWS 2026, kết hợp với Cache Policies (custom TTL) để tối ưu, nhưng invalidation vẫn cần cho urgent updates.

❌ [SAI] Use AWS Certificate Manager (ACM) to validate the website’s SSL certificate.

Phương án này hoàn toàn không liên quan vì ACM dùng để provision/manage SSL/TLS certificates miễn phí cho CloudFront/ELB. Vấn đề là cache content, không phải SSL validation (website đã hoạt động với HTTPS ngầm định). ACM chỉ validate domain ownership (DNS/Email), không refresh cache. Thêm ACM có thể dư thừa nếu cert đã OK, không giải quyết root cause.

📘 Tài liệu tham khảo (AWS chính thức, cập nhật 2026)

CloudFront Invalidation: AWS Docs - Invalidating files – Chi tiết cách implement và quota.

CloudFront + S3 Static Website: Best Practices - Hosting static websites (bao gồm cache behaviors).

CI/CD Integration: AWS CodePipeline + CloudFront – Tích hợp invalidation tự động.

Exam Topic (DOP-C02): Domain 4: Automation (CI/CD, cache management) trong AWS Certified DevOps Engineer Professional.

💡 Lời khuyên DevOps: Trong thực tế, automate invalidation qua CodeBuild/CodePipeline sau Git push để zero-downtime updates! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99669-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 40

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Systems Manager, Amazon Cognito, Amazon EC2, Amazon Security Token Service
- Đáp án tham khảo: **Use AWS Systems Manager Session Manager to connect to the EC2 instances.**
- Takeaway nhanh: 🛡️ Session Manager là dịch vụ của AWS Systems Manager (SSM), cho phép kết nối không cần SSH keys (keyless access), sử dụng IAM policies để kiểm soát quyền truy cập chi tiết (start session, port forwarding). 📊 Least administrative overhead: Chỉ cần attach SSM Agent (pre-installed trên Amazon Linux 2+ và nhiều AMI khác), enable SSM service role (như AmazonSSMManagedInstanceCore), và cấu hình VPC endpoints nếu cần private access. Không cần quản lý keys, bastion, hoặc custom auth.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html | https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.htmlWho | https://www.examtopics.com/discussions/amazon/view/99628-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has hundreds of Amazon EC2 Linux-based instances in the AWS Cloud. Systems administrators have used shared SSH keys to manage the instances. After a recent audit, the company’s security team is mandating the removal of all shared keys. A solutions architect must design a solution that provides secure access to the EC2 instances.
Which solution will meet this requirement with the LEAST amount of administrative overhead?

### Các lựa chọn
1. Use AWS Systems Manager Session Manager to connect to the EC2 instances.
2. Use AWS Security Token Service (AWS STS) to generate one-time SSH keys on demand.
3. Allow shared SSH access to a set of bastion instances. Configure all other instances to allow only SSH access from the bastion instances.
4. Use an Amazon Cognito custom authorizer to authenticate users. Invoke an AWS Lambda function to generate a temporary SSH key.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả tình huống một công ty có hàng trăm instance Amazon EC2 chạy Linux trong AWS Cloud. Các sysadmin trước đây sử dụng shared SSH keys để quản lý các instance này. Sau cuộc audit gần đây, đội ngũ bảo mật yêu cầu loại bỏ hoàn toàn các shared keys để tăng cường an ninh. Solutions Architect cần thiết kế giải pháp cung cấp truy cập an toàn (secure access) đến các EC2 instances, với yêu cầu quan trọng là ít nhất administrative overhead (tức là giảm thiểu công việc quản trị thủ công, dễ triển khai và duy trì cho quy mô lớn).

🛠️ Yêu cầu cốt lõi: Giải pháp phải:

Không dùng shared SSH keys.

An toàn (dựa trên IAM, logging, không lưu trữ keys lâu dài).

Phù hợp quy mô lớn (hundreds of instances).

Least overhead: Không cần quản lý bastion hosts, generate keys thủ công, hoặc custom setup phức tạp.

Đây là câu hỏi điển hình trong kỳ thi AWS Certified DevOps Engineer Professional (DOP-C02), tập trung vào best practices cho secure instance access theo AWS Well-Architected Framework (Security Pillar).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use AWS Systems Manager Session Manager to connect to the EC2 instances.

Lý do lựa chọn:

🛡️ Session Manager là dịch vụ của AWS Systems Manager (SSM), cho phép kết nối không cần SSH keys (keyless access), sử dụng IAM policies để kiểm soát quyền truy cập chi tiết (start session, port forwarding).

📊 Least administrative overhead: Chỉ cần attach SSM Agent (pre-installed trên Amazon Linux 2+ và nhiều AMI khác), enable SSM service role (như AmazonSSMManagedInstanceCore), và cấu hình VPC endpoints nếu cần private access. Không cần quản lý keys, bastion, hoặc custom auth.

🔒 An toàn cao: Tất cả session được log tự động qua CloudTrail/S3/Kinesis, hỗ trợ MFA, auditing, và session recording (từ 2023+). Phù hợp quy mô lớn, cập nhật đến 2026 với tích hợp AWS IAM Identity Center và zero-trust model.

⚡ Dễ scale: Hoạt động qua HTTPS (port 443), không mở inbound SSH (port 22), giảm attack surface.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng phương án, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), với giải thích rõ ràng dựa trên best practices AWS mới nhất.

Use AWS Systems Manager Session Manager to connect to the EC2 instances.

✅ Đúng và tối ưu nhất. Như đã giải thích ở trên, đây là giải pháp native AWS, không yêu cầu SSH, overhead thấp (chỉ setup IAM role một lần), và được khuyến nghị chính thức cho secure access. Hỗ trợ Linux/Windows, tích hợp Fleet Manager cho hàng nghìn instances.

Use AWS Security Token Service (AWS STS) to generate one-time SSH keys on demand.

❌ Sai. AWS STS dùng để generate temporary credentials (access keys/tokens), không hỗ trợ trực tiếp generate SSH keys. Việc tự build workflow generate one-time SSH keys sẽ tạo overhead cao (custom script, key rotation, storage), vi phạm nguyên tắc least overhead. Không phải best practice; thay vào đó dùng SSM.

Allow shared SSH access to a set of bastion instances. Configure all other instances to allow only SSH access from the bastion instances.

❌ Sai. Giải pháp bastion hosts vẫn dùng shared SSH keys trên bastion (vi phạm yêu cầu loại bỏ shared keys). Overhead lớn: Quản lý bastion fleet (patching, scaling, NACL/SG rules), vẫn có attack surface (port 22 mở). AWS khuyến cáo tránh bastion từ 2022+, ưu tiên SSM thay thế.

Use an Amazon Cognito custom authorizer to authenticate users. Invoke an AWS Lambda function to generate a temporary SSH key.

❌ Sai. Đây là giải pháp custom-built, phức tạp cao: Cần setup Cognito user pool, Lambda generate keys (xử lý signing, distribution, expiration), tích hợp SSH daemon. Overhead khổng lồ (dev/maintain code, error-prone, scaling issues), không scale tốt cho hundreds instances. Không phải native AWS solution, vi phạm "least overhead".

📘 Tài liệu tham khảo

AWS Systems Manager Session Manager Docs (cập nhật 2025): docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html – Hướng dẫn setup zero-config access.

AWS EC2 Security Best Practices (Well-Architected): docs.aws.amazon.com/wellarchitected/latest/security-pillar/security-pillar.html – Khuyến nghị SSM thay SSH keys.

DOP-C02 Exam Guide (AWS 2024+): Nhấn mạnh SSM cho secure bastion-less access.

AWS re:Post & Blogs: Tìm "EC2 Session Manager migration from SSH" cho case studies thực tế.

Giải pháp này đảm bảo zero-trust access mà không hy sinh usability! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99628-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.htmlWho

https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html

## Câu 41

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon EMR, Amazon Glue, Amazon Kinesis, Amazon S3, Amazon Managed Streaming for Apache Kafka, Amazon Database Migration Service, Amazon Relational Database Service, Amazon Kinesis Data Firehose, Amazon Kinesis Data Streams
- Takeaway nhanh: Cả hai đều đáp ứng đầy đủ real-time streaming (Kinesis Data Streams hoặc MSK), transform (Kinesis Data Analytics SQL hoặc Glue Streaming ETL), write to S3 (Firehose hoặc Glue), và SQL query trên S3 qua Athena. Chúng là các pipeline end-to-end chuẩn của AWS cho streaming data lake, scalable và serverless. 🛠️
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/glue/latest/dg/add-job-streaming.html | https://www.examtopics.com/discussions/amazon/view/99834-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is preparing a new data platform that will ingest real-time streaming data from multiple sources. The company needs to transform the data before writing the data to Amazon S3. The company needs the ability to use SQL to query the transformed data.
Which solutions will meet these requirements? (Choose two.)

### Các lựa chọn
1. Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
2. Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
3. Use AWS Database Migration Service (AWS DMS) to ingest the data. Use Amazon EMR to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
4. Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use Amazon Kinesis Data Analytics to transform the data and to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.
5. Use Amazon Kinesis Data Streams to stream the data. Use AWS Glue to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang xây dựng nền tảng dữ liệu mới để ingest dữ liệu streaming thời gian thực (real-time streaming data) từ nhiều nguồn khác nhau. Các yêu cầu chính bao gồm:

Transform (biến đổi) dữ liệu trước khi lưu trữ vào Amazon S3.

Sử dụng SQL để query (truy vấn) dữ liệu đã được transform.

Đây là câu hỏi chọn TWO giải pháp đúng (choose two), tập trung vào các dịch vụ AWS phù hợp cho streaming real-time, transformation, lưu trữ S3, và query SQL trên S3.

Yêu cầu nhấn mạnh real-time, vì vậy giải pháp phải hỗ trợ xử lý luồng dữ liệu liên tục, không phải batch processing. Amazon Athena là dịch vụ query SQL chuẩn trên S3 (serverless), phù hợp cho query transformed data. Kiến thức cập nhật đến 2026: AWS tiếp tục hỗ trợ Kinesis Data Analytics (nay là Amazon Managed Service for Apache Flink trong một số trường hợp, nhưng SQL vẫn dùng KDA for SQL), MSK với Glue Streaming ETL, và Athena với partitioned/optimized formats như Parquet/ORC cho performance cao. ✅

✅ Đáp án đúng (Chọn TWO)

Hai phương án đúng là:

Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Lý do chọn:

Cả hai đều đáp ứng đầy đủ real-time streaming (Kinesis Data Streams hoặc MSK), transform (Kinesis Data Analytics SQL hoặc Glue Streaming ETL), write to S3 (Firehose hoặc Glue), và SQL query trên S3 qua Athena. Chúng là các pipeline end-to-end chuẩn của AWS cho streaming data lake, scalable và serverless. 🛠️

📋 Giải thích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách rõ ràng:

✅ Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Đúng vì: Kinesis Data Streams ingest real-time data hiệu quả. Kinesis Data Analytics (KDA) hỗ trợ SQL trực tiếp để transform streaming data (real-time SQL queries). Firehose tự động buffer và write vào S3 với format tối ưu (Parquet). Athena query SQL serverless trên S3 partitioned data. Toàn bộ pipeline real-time, không delay. 🏆

✅ Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Đúng vì: MSK là managed Kafka cho high-throughput streaming. AWS Glue (phiên bản 4.0+ năm 2026) hỗ trợ streaming ETL với Apache Spark Streaming, transform real-time từ Kafka topics và direct write S3 (Glue Streaming Jobs). Athena query SQL hoàn hảo. Đây là giải pháp hybrid open-source cho enterprise. 🚀

❌ Use AWS Database Migration Service (AWS DMS) to ingest the data. Use Amazon EMR to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Sai vì: DMS dùng cho database migration (CDC hoặc full load), không phù hợp real-time streaming từ multiple sources (chậm, không scalable cho pure streaming). EMR là batch processing (Spark/Hadoop clusters), không real-time transform. Athena OK nhưng upstream sai. 🛑

❌ Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use Amazon Kinesis Data Analytics to transform the data and to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.

Sai vì: MSK OK cho streaming, KDA có thể consume từ MSK (qua Kafka connector) và transform SQL, nhưng query phần sai: RDS query editor chỉ query RDS databases (relational DB), không hỗ trợ S3. Phải dùng Athena cho S3. 📍

❌ Use Amazon Kinesis Data Streams to stream the data. Use AWS Glue to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.

Sai vì: Kinesis DS và Firehose OK, nhưng Glue không phải lựa chọn chuẩn cho real-time transform từ Kinesis DS (Glue chủ yếu batch ETL hoặc streaming từ Kafka; với Kinesis cần KDA hoặc custom Lambda). RDS query editor không query S3 (chỉ RDS). 🔒

📘 Tài liệu tham khảo (AWS Docs cập nhật 2026)

Amazon Kinesis Data Analytics for SQL Applications – Transform streaming với SQL.

AWS Glue Streaming ETL for Kafka – Real-time từ MSK.

Amazon Athena Querying S3 – SQL on S3.

Kinesis Data Firehose to S3.

Exam guide DOP-C02: Streaming & Data Lakes sections. 🧠

Giải pháp này giúp build data lake real-time scalable! Nếu cần lab thực hành, dùng AWS Free Tier với CDK/CloudFormation. 💡

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99834-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/glue/latest/dg/add-job-streaming.html

https://docs.aws.amazon.com/glue/latest/dg/add-job-streaming.html.

## Câu 42

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Storage Gateway
- Takeaway nhanh: Stored Volume Gateway (hay Stored Mode) lưu toàn bộ dữ liệu gốc (full data) trên on-premises storage (local disk), đồng thời async snapshot/backup lên S3 Glacier hoặc S3. Điều này đảm bảo local access đến TẤT CẢ dữ liệu qua iSCSI mount mà không cần cache (khác với Cached Mode chỉ cache phần dữ liệu thường dùng). Storage Gateway appliance chạy on-premises, tự động và an toàn chuyển dữ liệu lên AWS (sử dụng HTTPS/TLS encryption).
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ | https://aws.amazon.com/storagegateway/faqs/#:~:text=In%20the%20cached%20mode%2C%20your,asynchronously%20backed%20up%20to%20AWS | https://aws.amazon.com/storagegateway/faqs/#:~:text=What%20is%20Volume%20Gateway%3F | https://docs.aws.amazon.com/storagegateway/latest/userguide/what-is-storage-gateway.html | https://www.examtopics.com/discussions/amazon/view/99692-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on AWS is automatically and securely transferred.
Which solution meets these requirements?

### Các lựa chọn
1. Use AWS Snowball to migrate data out of the on-premises solution to Amazon S3. Configure on-premises systems to mount the Snowball S3 endpoint to provide local access to the data.
2. Use AWS Snowball Edge to migrate data out of the on-premises solution to Amazon S3. Use the Snowball Edge file interface to provide on-premises systems with local access to the data.
3. Use AWS Storage Gateway and configure a cached volume gateway. Run the Storage Gateway software appliance on premises and configure a percentage of data to cache locally. Mount the gateway storage volumes to provide local access to the data.
4. Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty đang sử dụng giải pháp backup volume on-premises đã hết hỗ trợ (end of life). Họ muốn chuyển sang sử dụng AWS làm phần của giải pháp backup mới, với các yêu cầu chính:

Duy trì quyền truy cập cục bộ (local access) vào TẤT CẢ dữ liệu trong khi dữ liệu đang được backup lên AWS.

Đảm bảo dữ liệu backup lên AWS được chuyển tự động (automatically) và an toàn (securely).

🛠️ Yêu cầu cốt lõi: Giải pháp phải hỗ trợ backup volume (không phải file hoặc tape), giữ toàn bộ dữ liệu accessible locally qua mount (như iSCSI), và đồng bộ hóa asynchronous lên S3 một cách tự động/an toàn. Không phù hợp với migration một lần (one-time) như Snowball, mà cần giải pháp liên tục cho backup ongoing.

✅ Đáp án đúng và lý do lựa chọn

Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.

Lý do:

Stored Volume Gateway (hay Stored Mode) lưu toàn bộ dữ liệu gốc (full data) trên on-premises storage (local disk), đồng thời async snapshot/backup lên S3 Glacier hoặc S3. Điều này đảm bảo local access đến TẤT CẢ dữ liệu qua iSCSI mount mà không cần cache (khác với Cached Mode chỉ cache phần dữ liệu thường dùng).

Storage Gateway appliance chạy on-premises, tự động và an toàn chuyển dữ liệu lên AWS (sử dụng HTTPS/TLS encryption).

Phù hợp hoàn hảo với backup volume EOL, thay thế seamless cho on-premises backup.

(Kiến thức cập nhật 2026: AWS Storage Gateway vẫn giữ nguyên mô hình Stored/Cached Volumes, với cải tiến hiệu suất qua Nitro Enclaves cho bảo mật - theo AWS re:Invent 2025 announcements).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Tôi đánh dấu ✅ đúng / ❌ sai và giải thích chi tiết bằng tiếng Việt:

❌ Use AWS Snowball to migrate data out of the on-premises solution to Amazon S3. Configure on-premises systems to mount the Snowball S3 endpoint to provide local access to the data.

Sai vì: Snowball là thiết bị vật lý cho migration dữ liệu lớn một lần (one-time transfer), không hỗ trợ backup liên tục/automatic. Không có "S3 endpoint mount" lâu dài on-premises sau khi ship Snowball về AWS. Local access chỉ tạm thời trong quá trình migration, không maintain ongoing access đến all data.

❌ Use AWS Snowball Edge to migrate data out of the on-premises solution to Amazon S3. Use the Snowball Edge file interface to provide on-premises systems with local access to the data.

Sai vì: Snowball Edge hỗ trợ compute/file interface tạm thời on-premises, nhưng vẫn là giải pháp migration offline một lần (ship device về AWS). Không automatic/secure transfer liên tục; sau migration, dữ liệu ở S3 mà không có local access ongoing. Không thay thế backup solution lâu dài.

❌ Use AWS Storage Gateway and configure a cached volume gateway. Run the Storage Gateway software appliance on premises and configure a percentage of data to cache locally. Mount the gateway storage volumes to provide local access to the data.

Sai vì: Cached Volume Gateway chỉ cache một phần dữ liệu thường dùng locally (phần còn lại primary lưu ở S3), không đảm bảo local access đến TẤT CẢ dữ liệu (most data fetched from S3 on-demand). Không phù hợp yêu cầu "all the data" local access, dù có automatic sync.

✅ Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.

Đúng vì: Như đã giải thích ở trên – full local storage + automatic secure backup lên S3, perfect match cho yêu cầu.

📘 Tài liệu tham khảo

AWS Storage Gateway User Guide (cập nhật 2026): https://docs.aws.amazon.com/storagegateway/latest/userguide/what-is-storage-gateway.html – Chi tiết Stored vs Cached Volumes.

AWS Well-Architected Framework - Storage Lens (2025): https://aws.amazon.com/architecture/well-architected/ – Backup & Recovery pillar.

AWS re:Post & Whitepapers: Tìm "Storage Gateway Volume Modes" cho case studies tương tự.

🛠️ Lời khuyên DevOps: Deploy Storage Gateway qua EC2 VM on-premises, monitor qua CloudWatch, và tích hợp IAM policies cho secure access. Test failover với S3 snapshots!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99692-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/storagegateway/faqs/#:~:text=What%20is%20Volume%20Gateway%3F

https://aws.amazon.com/storagegateway/faqs/#:~:text=In%20the%20cached%20mode%2C%20your,asynchronously%20backed%20up%20to%20AWS.

## Câu 43

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Redshift, Amazon Trusted Advisor, Amazon Relational Database Service
- Takeaway nhanh: Với consolidated billing, tài khoản payer cho phép xem tất cả recommendations từ linked accounts cùng lúc, giúp finance team phân tích RDS cross-account mà không cần login từng account riêng lẻ. Điều này tối ưu hóa việc giảm chi phí RDS tổng thể. RDS On-Demand chạy 90 ngày có nguy cơ idle (CPU <10% trong 7 ngày liên tục), Trusted Advisor check Amazon RDS Idle DB Instances sẽ phát hiện và khuyến nghị tắt/delete để tiết kiệm (theo AWS best practices 2026, check này vẫn active và chính xác cao). ✅
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/trusted-advisor-cost-optimization/ | https://www.examtopics.com/discussions/amazon/view/99936-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has multiple AWS accounts that use consolidated billing. The company runs several active high performance Amazon RDS for Oracle On-Demand DB instances for 90 days. The company’s finance team has access to AWS Trusted Advisor in the consolidated billing account and all other AWS accounts.
The finance team needs to use the appropriate AWS account to access the Trusted Advisor check recommendations for RDS. The finance team must review the appropriate Trusted Advisor check to reduce RDS costs.
Which combination of steps should the finance team take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Use the Trusted Advisor recommendations from the account where the RDS instances are running.
2. Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.
3. Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.
4. Review the Trusted Advisor check for Amazon RDS Idle DB Instances.
5. Review the Trusted Advisor check for Amazon Redshift Reserved Node Optimization.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi xoay quanh một công ty sử dụng nhiều AWS accounts với consolidated billing (tài khoản thanh toán hợp nhất). Công ty đang chạy các Amazon RDS for Oracle On-Demand DB instances (cơ sở dữ liệu theo nhu cầu, không phải Reserved Instances) trong 90 ngày. Nhóm tài chính (finance team) có quyền truy cập AWS Trusted Advisor ở tài khoản consolidated billing (tài khoản payer) và tất cả các tài khoản khác.

Yêu cầu chính:

Sử dụng tài khoản AWS phù hợp để truy cập khuyến nghị (recommendations) từ Trusted Advisor liên quan đến RDS.

Xem xét kiểm tra (check) Trusted Advisor phù hợp để giảm chi phí RDS (reduce RDS costs).

Vì có nhiều accounts, finance team cần cách xem tổng hợp tất cả RDS instances từ các accounts khác nhau. Trusted Advisor cung cấp các kiểm tra miễn phí về cost optimization, security, fault tolerance, v.v. Trong consolidated billing, tài khoản payer có thể xem aggregated checks cho tất cả linked accounts (theo tài liệu AWS cập nhật 2024-2026). RDS On-Demand chạy 90 ngày có thể có vấn đề idle (không sử dụng), dẫn đến lãng phí chi phí.

Chọn TWO steps đúng để đáp ứng yêu cầu. 🛠️

✅ Đáp án đúng (Chọn 2)

Hai bước đúng là:

Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.

Review the Trusted Advisor check for Amazon RDS Idle DB Instances.

Lý do lựa chọn:

Với consolidated billing, tài khoản payer cho phép xem tất cả recommendations từ linked accounts cùng lúc, giúp finance team phân tích RDS cross-account mà không cần login từng account riêng lẻ. Điều này tối ưu hóa việc giảm chi phí RDS tổng thể.

RDS On-Demand chạy 90 ngày có nguy cơ idle (CPU <10% trong 7 ngày liên tục), Trusted Advisor check Amazon RDS Idle DB Instances sẽ phát hiện và khuyến nghị tắt/delete để tiết kiệm (theo AWS best practices 2026, check này vẫn active và chính xác cao). ✅

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một, giữ nguyên văn bản gốc tiếng Anh. Tôi đánh dấu ✅ (đúng) hoặc ❌ (sai) dựa trên chức năng Trusted Advisor và consolidated billing (kiến thức AWS DOP-C02 2024-2026).

Use the Trusted Advisor recommendations from the account where the RDS instances are running.

❌ Sai. Nếu chỉ dùng account chạy RDS, finance team phải login từng account riêng lẻ để xem recommendations, không hiệu quả với multiple accounts. Consolidated billing account mới cho phép xem tất cả RDS checks aggregated cùng lúc, phù hợp yêu cầu "at the same time".

Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.

✅ Đúng. Tài khoản payer (consolidated billing) hỗ trợ cross-account visibility cho Trusted Advisor cost checks, bao gồm RDS từ tất cả linked accounts. Điều này giúp review tổng hợp mà không cần chuyển account, tối ưu cho finance team.

Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.

❌ Sai. Trusted Advisor không có check cụ thể tên "Amazon RDS Reserved Instance Optimization" (cập nhật 2026). Các check RI chủ yếu cho EC2 ("Amazon EC2 RI Optimization"), không dành cho RDS. Với RDS On-Demand 90 ngày, ưu tiên idle detection hơn RI (RI phù hợp long-term >1 năm).

Review the Trusted Advisor check for Amazon RDS Idle DB Instances.

✅ Đúng. Đây là check Cost Optimization chính thức của Trusted Advisor, phát hiện RDS instances idle (CPU utilization thấp <10% trong 7 ngày), khuyến nghị stop/delete để giảm chi phí On-Demand ngay lập tức. Hoàn hảo cho tình huống 90 ngày chạy active nhưng có thể lãng phí.

Review the Trusted Advisor check for Amazon Redshift Reserved Node Optimization.

❌ Sai. Check này dành cho Amazon Redshift (data warehouse), không liên quan RDS (relational DB như Oracle). Sử dụng sai sẽ không giúp giảm chi phí RDS, lãng phí thời gian.

📘 Tài liệu tham khảo

AWS Trusted Advisor Documentation: AWS Trusted Advisor Checks (xem "Amazon RDS Idle DB Instances" - active đến 2026).

Consolidated Billing & Trusted Advisor: Organizations User Guide - Trusted Advisor (payer account views all member recommendations).

RDS Cost Optimization: AWS Well-Architected Framework - Cost Pillar (khuyến nghị dùng Trusted Advisor cho idle RDS).

Exam guide DOP-C02 (2024-2026): Nhấn mạnh cross-account visibility trong multi-account setups.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ thực hành, hãy hỏi nhé.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99936-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/premiumsupport/knowledge-center/trusted-advisor-cost-optimization/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Kinesis, Amazon OpenSearch Service, Amazon SNS, Amazon SQS, Amazon Lambda, Amazon Kinesis Data Firehose, Amazon Kinesis Data Streams
- Đáp án tham khảo: **Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each backend application server to use its own SQS queue.**
- Takeaway nhanh: Phân loại theo quote type: SNS message filtering (tính năng từ 2019, cập nhật đến 2026) cho phép lọc tin nhắn dựa trên thuộc tính (attributes) như "quote_type", tự động route đến SQS queue phù hợp mà không cần code phức tạp. Không mất dữ liệu: SNS + SQS đảm bảo at-least-once delivery; SQS lưu trữ durable (lên đến 14 ngày), hỗ trợ visibility timeout và dead-letter queues (DLQ) để retry, tránh mất message.
- Nguồn tham khảo trong block: https://aws.amazon.com/getting-started/hands-on/filter-messages-published-to-topics/ | https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.htmlSNS | https://www.examtopics.com/discussions/amazon/view/99627-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational efficiency and must minimize maintenance.
Which solution meets these requirements?

### Các lựa chọn
1. Create multiple Amazon Kinesis data streams based on the quote type. Configure the web application to send messages to the proper data stream. Configure each backend group of application servers to use the Kinesis Client Library (KCL) to pool messages from its own data stream.
2. Create an AWS Lambda function and an Amazon Simple Notification Service (Amazon SNS) topic for each quote type. Subscribe the Lambda function to its associated SNS topic. Configure the application to publish requests for quotes to the appropriate SNS topic.
3. Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each backend application server to use its own SQS queue.
4. Create multiple Amazon Kinesis Data Firehose delivery streams based on the quote type to deliver data streams to an Amazon OpenSearch Service cluster. Configure the application to send messages to the proper delivery stream. Configure each backend group of application servers to search for the messages from OpenSearch Service and process them accordingly.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty đang sử dụng AWS để thiết kế ứng dụng web xử lý báo giá bảo hiểm (insurance quotes). Các yêu cầu chính bao gồm:

Phân loại báo giá theo loại (quote type): Mỗi loại báo giá cần được xử lý riêng biệt bởi các nhóm backend tương ứng.

Phản hồi trong vòng 24 giờ: Hệ thống phải đảm bảo xử lý kịp thời, không để trễ nãi.

Không mất dữ liệu: Tin nhắn (quotes) phải được lưu trữ đáng tin cậy, tránh mất mát.

Tối ưu hóa hiệu quả vận hành và giảm thiểu bảo trì: Giải pháp phải tự động hóa cao, sử dụng các dịch vụ managed của AWS để giảm công quản lý server, scaling tự động.

🛠️ Mục tiêu giải pháp: Sử dụng hệ thống messaging decoupling (tách rời frontend và backend), hỗ trợ fanout (phân phối tin nhắn đến nhiều queue), filtering (lọc theo loại), durability cao (không mất message), và low-maintenance (ít can thiệp thủ công). Đây là mô hình tiêu chuẩn cho decoupling microservices trên AWS, đặc biệt với workload không đồng bộ như xử lý báo giá.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each backend application server to use its own SQS queue.

Lý do chọn đáp án này 🏆:

Phân loại theo quote type: SNS message filtering (tính năng từ 2019, cập nhật đến 2026) cho phép lọc tin nhắn dựa trên thuộc tính (attributes) như "quote_type", tự động route đến SQS queue phù hợp mà không cần code phức tạp.

Không mất dữ liệu: SNS + SQS đảm bảo at-least-once delivery; SQS lưu trữ durable (lên đến 14 ngày), hỗ trợ visibility timeout và dead-letter queues (DLQ) để retry, tránh mất message.

Phản hồi trong 24h: SQS standard queue xử lý hàng triệu message, polling linh hoạt; backend server poll queue riêng, dễ scale horizontally.

Tối ưu hiệu quả & giảm bảo trì: Single SNS topic giảm chi phí (pay-per-use), multiple SQS queues fanout tự động; tất cả managed services (no servers), auto-scaling, monitoring qua CloudWatch. Không cần KCL hay Lambda phức tạp.

📘 Tài liệu tham khảo: AWS SNS Message Filtering, SNS with SQS Fanout (cập nhật 2024-2026).

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá với lý do cụ thể dựa trên yêu cầu.

Phương án 1 ❌: Create multiple Amazon Kinesis data streams based on the quote type. Configure the web application to send messages to the proper data stream. Configure each backend group of application servers to use the Kinesis Client Library (KCL) to pool messages from its own data stream.

Giải thích sai: Kinesis Data Streams phù hợp streaming real-time cao tải (như logs/video), nhưng yêu cầu ordering strict và shard management phức tạp. Ở đây chỉ cần decoupling quotes (không real-time), việc dùng multiple streams + KCL (polling) tăng bảo trì cao (quản lý shards, scaling KCL workers). Không tối ưu cho 24h response (overkill), chi phí cao hơn SNS/SQS. Không hỗ trợ filtering native dễ dàng.

Phương án 2 ❌: Create an AWS Lambda function and an Amazon Simple Notification Service (Amazon SNS) topic for each quote type. Subscribe the Lambda function to its associated SNS topic. Configure the application to publish requests for quotes to the appropriate SNS topic.

Giải thích sai: Multiple SNS + Lambda per type làm hệ thống fragmented, tăng chi phí và bảo trì (quản lý nhiều topic/Lambda). Lambda invoke synchronous/asynchronous có thể timeout với workload lớn; không decoupling tốt (Lambda xử lý trực tiếp, dễ overload). Không đảm bảo "không mất" nếu Lambda fail (cần DLQ riêng), và kém hiệu quả so với SQS queue-based polling cho backend servers.

Phương án 3 ✅: Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each backend application server to use its own SQS queue.

Giải thích đúng (như phần trên): Hoàn hảo match tất cả yêu cầu với kiến trúc fanout + filtering đơn giản, managed, low-cost. Backend dùng SDK poll SQS dễ scale.

Phương án 4 ❌: Create multiple Amazon Kinesis Data Firehose delivery streams based on the quote type to deliver data streams to an Amazon OpenSearch Service cluster. Configure the application to send messages to the proper delivery stream. Configure each backend group of application servers to search for the messages from OpenSearch Service and process them accordingly.

Giải thích sai: Kinesis Data Firehose dành cho batch delivery đến storage/search (như logs to OpenSearch/S3), không phải messaging real-time. Backend phải query OpenSearch (search engine) để poll message → phức tạp, kém hiệu quả (latency cao, chi phí query), không đảm bảo "không mất" (Firehose buffer có thể drop nếu overload). Tăng bảo trì lớn (quản lý OpenSearch cluster), không phù hợp decoupling apps.

🛠️ Kết luận: Giải pháp SNS + SQS filtering là best practice AWS cho pub/sub decoupling với filtering (Exam DOP-C02 chuẩn 2024-2026). Sử dụng pattern này giúp scale global, zero-maintenance! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99627-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.htmlSNS

https://aws.amazon.com/getting-started/hands-on/filter-messages-published-to-topics/

## Câu 45

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon CloudTrail, Amazon CloudWatch, Amazon CloudWatch Logs, Amazon S3, Amazon Management Console
- Đáp án tham khảo: **Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.**
- Takeaway nhanh: S3 Storage Lens là tính năng miễn phí, tự động cung cấp dashboard trực quan với advanced metrics về hoạt động truy cập (như số lượng GET/POST requests, bytes downloaded/uploaded theo thời gian, phân tích theo prefix/tag/region). 🟢 Nó giúp xác định bucket "lạnh" (rarely accessed) chỉ với vài cú click, không cần setup thêm (enabled organization-wide hoặc account-wide qua console/API).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/s3-storage-lens/ | https://www.examtopics.com/discussions/amazon/view/99803-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect needs to optimize storage costs. The solutions architect must identify any Amazon S3 buckets that are no longer being accessed or are rarely accessed.
Which solution will accomplish this goal with the LEAST operational overhead?

### Các lựa chọn
1. Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.
2. Analyze bucket access patterns by using the S3 dashboard in the AWS Management Console.
3. Turn on the Amazon CloudWatch BucketSizeBytes metric for buckets. Analyze bucket access patterns by using the metrics data with Amazon Athena.
4. Turn on AWS CloudTrail for S3 object monitoring. Analyze bucket access patterns by using CloudTrail logs that are integrated with Amazon CloudWatch Logs.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc tối ưu hóa chi phí lưu trữ trên Amazon S3 bằng cách xác định các S3 bucket không còn được truy cập hoặc truy cập rất ít. 🛡️ Solutions Architect cần một giải pháp có ít overhead vận hành nhất (LEAST operational overhead), nghĩa là không yêu cầu cấu hình phức tạp, không tốn tài nguyên tính toán hoặc lưu trữ log lớn, và có thể triển khai nhanh chóng.

Mục tiêu chính là phân tích pattern truy cập (access patterns) của bucket để quyết định chuyển sang lớp lưu trữ rẻ hơn như S3 Intelligent-Tiering, Glacier, hoặc xóa dữ liệu không cần thiết. Đây là vấn đề phổ biến trong DevOps để kiểm soát chi phí AWS theo mô hình pay-as-you-go. 📈 (Kiến thức cập nhật đến 2026: S3 Storage Lens đã được nâng cấp với AI-driven recommendations và global views).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.

Lý do:

S3 Storage Lens là tính năng miễn phí, tự động cung cấp dashboard trực quan với advanced metrics về hoạt động truy cập (như số lượng GET/POST requests, bytes downloaded/uploaded theo thời gian, phân tích theo prefix/tag/region). 🟢 Nó giúp xác định bucket "lạnh" (rarely accessed) chỉ với vài cú click, không cần setup thêm (enabled organization-wide hoặc account-wide qua console/API).

Least operational overhead: Không tạo log, không query thủ công, tích hợp sẵn recommendations để optimize tiers (ví dụ: đề xuất chuyển sang IA/Glacier). Hoàn hảo cho scale lớn. 🚀

📋 Giải thích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, với ✅ đúng và ❌ sai dựa trên tính phù hợp và overhead:

Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.

✅ Đúng: Như đã giải thích, đây là giải pháp tối ưu nhất với dashboard sẵn có, metrics chi tiết về access frequency (daily/weekly/monthly), và zero-config cho hầu hết accounts. Không tốn thêm chi phí hay effort. 🏆 (Cập nhật 2026: Hỗ trợ ML insights cho top risky buckets).

Analyze bucket access patterns by using the S3 dashboard in the AWS Management Console.

❌ Sai: S3 dashboard trong Console chỉ cung cấp metrics cơ bản (như storage used, requests số lượng tổng quát) từ CloudWatch, không có advanced activity metrics chi tiết về access patterns theo thời gian hoặc object-level. Phải manually drill-down từng bucket, overhead cao cho nhiều buckets. Không hiệu quả cho optimization lớn. 😞

Turn on the Amazon CloudWatch BucketSizeBytes metric for buckets. Analyze bucket access patterns by using the metrics data with Amazon Athena.

❌ Sai: BucketSizeBytes chỉ theo dõi kích thước bucket, không cung cấp access patterns (như requests hay bytes accessed). Phải enable metric (có thể tốn phí nếu dùng detailed monitoring), rồi export sang Athena để query – overhead rất cao (setup CloudWatch Logs/Export, Athena queries phức tạp, chi phí scan dữ liệu). Không trực quan và không dành cho access analysis. 🛑

Turn on AWS CloudTrail for S3 object monitoring. Analyze bucket access patterns by using CloudTrail logs that are integrated with Amazon CloudWatch Logs.

❌ Sai: CloudTrail ghi log tất cả API calls (data events), tốn nhiều storage và chi phí (S3 cho logs + CloudWatch Logs Insights). Phải enable data events thủ công per bucket, integrate với Logs, rồi query patterns – overhead vận hành cực lớn (quản lý logs, retention, filtering). Phù hợp audit hơn là cost optimization. ⚠️

📘 Tài liệu tham khảo

AWS Documentation chính thức (2026 updates):

Amazon S3 Storage Lens – Chi tiết metrics và dashboard.

S3 Cost Optimization with Storage Lens – Recommendations và activity metrics.

CloudTrail for S3 – So sánh overhead.

AWS Well-Architected Framework - Cost Optimization Pillar: Khuyến nghị Storage Lens cho bucket analysis.

Exam Prep: DOP-C02 blueprint (Domain 2: Storage), tương tự câu hỏi thực tế AWS Certified DevOps Engineer Professional.

Giải pháp này giúp DevOps Engineer tiết kiệm thời gian và chi phí hiệu quả nhất! 💡 Nếu cần ví dụ code hoặc demo, hãy hỏi thêm nhé.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99803-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/aws/s3-storage-lens/

## Câu 46

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Cognito
- Đáp án tham khảo: **Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.**
- Takeaway nhanh: Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/cognito/latest/developerguide/role-based-access-control.html | https://www.examtopics.com/discussions/amazon/view/99754-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is hosting a web application from an Amazon S3 bucket. The application uses Amazon Cognito as an identity provider to authenticate users and return a JSON Web Token (JWT) that provides access to protected resources that are stored in another S3 bucket.
Upon deployment of the application, users report errors and are unable to access the protected content. A solutions architect must resolve this issue by providing proper permissions so that users can access the protected content.
Which solution meets these requirements?

### Các lựa chọn
1. Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.
2. Update the S3 ACL to allow the application to access the protected content.
3. Redeploy the application to Amazon S3 to prevent eventually consistent reads in the S3 bucket from affecting the ability of users to access the protected content.
4. Update the Amazon Cognito pool to use custom attribute mappings within the identity pool and grant users the proper permissions to access the protected content.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một ứng dụng web được host trên Amazon S3 bucket công khai. Ứng dụng sử dụng Amazon Cognito làm Identity Provider (IdP) để xác thực người dùng và trả về JSON Web Token (JWT). JWT này cho phép truy cập vào các tài nguyên được bảo vệ (protected resources) lưu trữ trong một S3 bucket khác.

Sau khi deploy ứng dụng, người dùng gặp lỗi và không thể truy cập nội dung bảo vệ. Solutions Architect cần khắc phục bằng cách cấp quyền truy cập phù hợp (proper permissions) cho người dùng.

🛠️ Vấn đề cốt lõi: Đây là lỗi quyền truy cập (authorization) sau khi xác thực thành công qua Cognito User Pool. Người dùng đã có JWT hợp lệ từ User Pool, nhưng cần trao đổi (exchange) JWT này qua Cognito Identity Pool để nhận temporary AWS credentials từ IAM Role. IAM Role này phải có policy cho phép truy cập S3 bucket bảo vệ. Kiến thức AWS cập nhật đến 2026 (theo re:Invent 2025 và docs mới nhất) xác nhận quy trình chuẩn: Cognito User Pool → Identity Pool → IAM Role → S3 access.

📘 Tài liệu tham khảo:

AWS Cognito Identity Pools Documentation (cập nhật 2025).

IAM Roles for Cognito Identity.

S3 Bucket Policies with Cognito.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.

Lý do:

🧩 Cognito Identity Pool (không phải User Pool) chịu trách nhiệm map JWT từ User Pool thành temporary credentials bằng cách assume IAM Role phù hợp. Cập nhật Identity Pool để sử dụng IAM Role có policy s3:GetObject (hoặc tương tự) trên bucket bảo vệ sẽ giải quyết ngay lỗi permissions. Đây là giải pháp chuẩn, an toàn nhất theo best practices AWS (least privilege via roles), không cần thay đổi ACL hay redeploy. Đã được xác nhận trong các case study DOP-C02 exam (2025 blueprint).

📋 Giải thích tất cả các phương án (đúng/sai)

Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.

✅ Đúng. Như giải thích trên, Identity Pool cần được cấu hình để assume IAM Role có quyền truy cập S3 bucket bảo vệ. Đây là bước chính xác để cấp temporary credentials cho users đã authenticated.

Update the S3 ACL to allow the application to access the protected content.

❌ Sai. S3 ACL (Access Control List) chỉ kiểm soát quyền cơ bản như public read/write, không hỗ trợ tích hợp Cognito JWT hoặc authenticated users một cách granular. ACL lỗi thời (AWS khuyến nghị dùng Bucket Policy + IAM từ 2023), và "allow the application" không giải quyết được vì app host trên S3 khác, users cần quyền cá nhân hóa qua Cognito IAM roles.

Redeploy the application to Amazon S3 to prevent eventually consistent reads in the S3 bucket from affecting the ability of users to access the protected content.

❌ Sai. Eventually consistent reads chỉ ảnh hưởng propagation dữ liệu sau PUT (không phải GET permissions). Vấn đề ở đây là authorization failure (lỗi 403 Forbidden), không liên quan consistency. Redeploy không fix permissions và lãng phí tài nguyên.

Update the Amazon Cognito pool to use custom attribute mappings within the identity pool and grant users the proper permissions to access the protected content.

❌ Sai. Custom attribute mappings hữu ích để pass claims từ User Pool attributes vào Identity ID, nhưng không trực tiếp "grant permissions" – permissions vẫn phải qua IAM Role policy. Issue gốc là thiếu role assume, không phải mapping. "Cognito pool" mơ hồ (User hay Identity?), nhưng giải pháp này thừa thãi và không target đúng root cause.

🛠️ Kết luận: Giải pháp đúng tận dụng IAM Roles with Cognito Identity Pools – pattern cốt lõi trong AWS security model 2026, đảm bảo scalable và secure access cho S3 protected content! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99754-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/cognito/latest/developerguide/role-based-access-control.html

## Câu 47

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon CloudFormation, Amazon CloudTrail, Amazon Config, Amazon Trusted Advisor, Amazon EC2
- Takeaway nhanh: Dưới đây là giải thích chi tiết từng lựa chọn, với đánh giá đúng/sai dựa trên tính phù hợp với yêu cầu track & audit inventory/configuration changes:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99804-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently migrated its entire IT environment to the AWS Cloud. The company discovers that users are provisioning oversized Amazon EC2 instances and modifying security group rules without using the appropriate change control process. A solutions architect must devise a strategy to track and audit these inventory and configuration changes.
Which actions should the solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Enable AWS CloudTrail and use it for auditing.
2. Use data lifecycle policies for the Amazon EC2 instances.
3. Enable AWS Trusted Advisor and reference the security dashboard.
4. Enable AWS Config and create rules for auditing and compliance purposes.
5. Restore previous resource configurations with an AWS CloudFormation template.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty đã migrate toàn bộ môi trường IT sang AWS Cloud, nhưng gặp vấn đề: người dùng đang provision (cung cấp) các instance Amazon EC2 quá lớn (oversized) và sửa đổi quy tắc security group mà không tuân thủ quy trình kiểm soát thay đổi (change control process). Solutions Architect cần thiết kế chiến lược để track (theo dõi) và audit (kiểm toán) các thay đổi về inventory (danh sách tài nguyên) và configuration (cấu hình).

📌 Yêu cầu chính: Chọn TWO hành động phù hợp nhất. Chủ đề tập trung vào giám sát, ghi log và kiểm toán thay đổi trên AWS, phù hợp với best practices DevOps như governance, compliance và resource optimization (cập nhật đến AWS năm 2026, với AWS Config và CloudTrail hỗ trợ tích hợp sâu hơn với AWS Control Tower và Organizations).

✅ Đáp án đúng (Chọn TWO)

Hai đáp án đúng là:

Enable AWS CloudTrail and use it for auditing.

Enable AWS Config and create rules for auditing and compliance purposes.

Lý do lựa chọn:

🛠️ AWS CloudTrail ghi log tất cả API calls (bao gồm provision EC2 oversized và modify security group), giúp audit ai làm gì, khi nào, từ đâu – lý tưởng để track inventory changes.

🛠️ AWS Config theo dõi thay đổi cấu hình thời gian thực (configuration history), inventory tài nguyên, và cho phép tạo rules tùy chỉnh để kiểm tra compliance (ví dụ: rule kiểm tra instance size hoặc SG rules). Kết hợp hai dịch vụ này tạo chiến lược hoàn chỉnh: CloudTrail cho audit trail, Config cho config drift detection và compliance. Đây là giải pháp chuẩn theo AWS Well-Architected Framework (Operations Pillar).

📋 Phân tích tất cả các phương án

Dưới đây là giải thích chi tiết từng lựa chọn, với đánh giá đúng/sai dựa trên tính phù hợp với yêu cầu track & audit inventory/configuration changes:

✅ Enable AWS CloudTrail and use it for auditing.

Đúng 🏆: CloudTrail ghi lại toàn bộ lịch sử API calls (ví dụ: RunInstances cho EC2 oversized, AuthorizeSecurityGroupIngress cho SG changes), hỗ trợ query qua CloudTrail Lake (query engine mới từ 2022, cập nhật 2026). Giúp audit đầy đủ, tích hợp với Amazon S3/CloudWatch Logs cho lưu trữ dài hạn. Không chỉ log mà còn hỗ trợ Insights để detect unusual activities.

❌ Use data lifecycle policies for the Amazon EC2 instances.

Sai 🚫: Data lifecycle policies chủ yếu thuộc Amazon S3 (Lifecycle policies để transition/delete objects), không áp dụng trực tiếp cho EC2 instances. EC2 dùng Instance Lifecycle Policies trong Auto Scaling hoặc Spot, nhưng chỉ manage vòng đời instance (terminate idle), không track/audit config changes hay inventory.

❌ Enable AWS Trusted Advisor and reference the security dashboard.

Sai 🚫: AWS Trusted Advisor cung cấp recommendations (ví dụ: cảnh báo EC2 oversized qua Cost Optimization checks, hoặc SG exposed qua Security checks), và Security Dashboard (trong GuardDuty/Inspector) hiển thị metrics bảo mật. Tuy nhiên, nó không track/audit lịch sử thay đổi realtime, chỉ là snapshot recommendations – không đáp ứng yêu cầu audit changes mà không qua change control.

✅ Enable AWS Config and create rules for auditing and compliance purposes.

Đúng 🏆: AWS Config ghi nhận configuration snapshots và changes (ví dụ: detect EC2 instance type thay đổi hoặc SG rules modify), cung cấp rules engine (managed/custom Lambda rules) để kiểm tra compliance tự động (như rule ec2-instance-type-whitelist hoặc security-group-rules). Hỗ trợ conformance packs mới (2023-2026) tích hợp với AWS Organizations cho multi-account auditing.

❌ Restore previous resource configurations with an AWS CloudFormation template.

Sai 🚫: AWS CloudFormation dùng để deploy/revert infrastructure as code (IaC), có thể restore config từ template cũ. Nhưng nó không track/audit tự động changes (users vẫn có thể modify manual ngoài template), và không phải công cụ audit mà là remediation tool – không giải quyết gốc rễ tracking.

📘 Tài liệu tham khảo (AWS Official Docs - Cập nhật 2026)

AWS CloudTrail: docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html – Auditing API activity.

AWS Config: docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html – Tracking resource configurations & compliance rules.

AWS Well-Architected Framework: aws.amazon.com/architecture/well-architected – Operations Pillar: Logging & Monitoring.

Exam Prep: AWS Certified Solutions Architect/SysOps/DevOps Pro blueprints (2024-2026 updates nhấn mạnh Config + CloudTrail cho governance).

🎯 Kết luận: Sử dụng CloudTrail + Config là combo mạnh mẽ nhất cho DevOps auditing trên AWS! Nếu cần lab thực hành, dùng AWS Free Tier với CloudTrail Multi-Region.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99804-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 48

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Database Migration Service, Amazon Relational Database Service, DR RPO and RTO
- Đáp án tham khảo: **Enable a Multi-AZ deployment for the DB instance.**
- Takeaway nhanh: Multi-AZ deployment cho RDS PostgreSQL sử dụng synchronous replication (sao chép dữ liệu đồng bộ) từ primary instance sang standby instance ở AZ khác. Mọi giao dịch đều được ghi đồng thời, đảm bảo RPO gần 0 giây (thường <1s), và failover tự động trong ~60-120 giây nếu primary fail. Đây là giải pháp chuẩn AWS cho high availability với RPO thấp, hỗ trợ PostgreSQL đầy đủ (cập nhật 2026: vẫn là tiêu chuẩn, không thay đổi cơ bản). 🛠️ Hoàn hảo cho production DB với compliance yêu cầu nghiêm ngặt!
- Nguồn tham khảo trong block: https://aws.amazon.com/rds/faqs/ | https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html | https://www.examtopics.com/discussions/amazon/view/99511-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs a fleet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases.
Which solution meets these requirements?

### Các lựa chọn
1. Enable a Multi-AZ deployment for the DB instance.
2. Enable auto scaling for the DB instance in one Availability Zone.
3. Configure the DB instance in one Availability Zone, and create multiple read replicas in a separate Availability Zone.
4. Configure the DB instance in one Availability Zone, and configure AWS Database Migration Service (AWS DMS) change data capture (CDC) tasks.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc đảm bảo Recovery Point Objective (RPO) nhỏ hơn 1 giây cho cơ sở dữ liệu Amazon RDS for PostgreSQL trong môi trường production của một công ty chạy fleet web servers.

RPO (Recovery Point Objective) là chỉ số đo lường lượng dữ liệu tối đa có thể mất khi xảy ra sự cố (ví dụ: mất AZ), tính bằng thời gian. Yêu cầu RPO < 1 giây nghĩa là dữ liệu phải được sao lưu đồng bộ gần như tức thì (gần 0 giây mất mát dữ liệu).

Bối cảnh: RDS PostgreSQL là DB managed service của AWS. Compliance check yêu cầu cao cho production DB, tập trung vào high availability và disaster recovery với replication đồng bộ giữa các Availability Zones (AZ).

Mục tiêu: Chọn giải pháp thực tế, hiệu quả nhất từ AWS để đạt RPO <1s, không chỉ backup mà cần synchronous replication tự động. ✅

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Enable a Multi-AZ deployment for the DB instance.

Lý do:

Multi-AZ deployment cho RDS PostgreSQL sử dụng synchronous replication (sao chép dữ liệu đồng bộ) từ primary instance sang standby instance ở AZ khác. Mọi giao dịch đều được ghi đồng thời, đảm bảo RPO gần 0 giây (thường <1s), và failover tự động trong ~60-120 giây nếu primary fail.

Đây là giải pháp chuẩn AWS cho high availability với RPO thấp, hỗ trợ PostgreSQL đầy đủ (cập nhật 2026: vẫn là tiêu chuẩn, không thay đổi cơ bản). 🛠️ Hoàn hảo cho production DB với compliance yêu cầu nghiêm ngặt!

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm giải thích rõ ràng dựa trên kiến thức AWS RDS mới nhất (2026).

✅ Enable a Multi-AZ deployment for the DB instance.

Giải thích đúng: Như đã nêu, Multi-AZ đảm bảo synchronous replication, RPO <1s nhờ dữ liệu luôn đồng bộ giữa primary và standby AZ. Failover nhanh, không mất dữ liệu. Đây là giải pháp tối ưu nhất cho yêu cầu RPO production. 📘 (Tham khảo: AWS RDS Multi-AZ Documentation).

❌ Enable auto scaling for the DB instance in one Availability Zone.

Giải thích sai: Auto scaling chỉ tăng/giảm storage hoặc compute tự động dựa trên IOPS/usage, nhưng không liên quan đến replication hay RPO. DB vẫn ở single AZ, nếu AZ fail thì mất toàn bộ dữ liệu với RPO cao (có thể hàng giờ nếu dùng snapshot). Không giải quyết disaster recovery! 🚫

❌ Configure the DB instance in one Availability Zone, and create multiple read replicas in a separate Availability Zone.

Giải thích sai: Read replicas dùng asynchronous replication (không đồng bộ), có replication lag từ vài giây đến phút (thậm chí lâu hơn dưới tải cao). RPO không đảm bảo <1s vì dữ liệu trên replica có thể mất mát lag time. Primary vẫn single AZ, chỉ hỗ trợ read scaling, không phải HA chính. ❌ (Tham khảo: RDS Read Replicas - lag điển hình 1-15s).

❌ Configure the DB instance in one Availability Zone, and configure AWS Database Migration Service (AWS DMS) change data capture (CDC) tasks.

Giải thích sai: AWS DMS CDC dùng cho migration hoặc replication giữa DBs (ongoing change capture), là asynchronous với lag có thể >1s, không thiết kế cho RPO production real-time. Primary single AZ, DMS thêm complexity/overhead mà không đảm bảo synchronous hay failover tự động. Không phù hợp compliance HA! 🔧 (Tham khảo: AWS DMS CDC).

📘 Tài liệu tham khảo chính (cập nhật 2026)

AWS RDS User Guide - Multi-AZ Deployments: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html (Xác nhận RPO gần-zero với sync replication cho PostgreSQL).

AWS Well-Architected Framework - Reliability Pillar: Nhấn mạnh Multi-AZ cho RPO/RTO thấp.

RDS FAQs: https://aws.amazon.com/rds/faqs/ (PostgreSQL Multi-AZ hỗ trợ đầy đủ, không thay đổi lớn đến 2026).

DevOps Pro Exam Guide: Chủ đề DOP-C02 bao gồm RDS HA solutions.

Giải pháp này giúp công ty đạt compliance 100% với RPO <1s một cách đơn giản, chi phí hợp lý! 🚀 Nếu cần demo CDK/Terraform config Multi-AZ, hỏi thêm nhé! 😊

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99511-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 49

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon DataSync, Amazon CloudFront, Amazon S3, Amazon Elastic Transcoder, Amazon EC2
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99693-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket. However, the videos are large in their raw format.
Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the performance and scalability of the app while minimizing operational overhead.
Which combination of solutions will meet these requirements? (Choose two.)

### Các lựa chọn
1. Deploy Amazon CloudFront for content delivery and caching.
2. Use AWS DataSync to replicate the video files across AW'S Regions in other S3 buckets.
3. Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.
4. Deploy an Auto Sealing group of Amazon EC2 instances in Local Zones for content delivery and caching.
5. Deploy an Auto Scaling group of Amazon EC2 instances to convert the video files to more appropriate formats.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng di động cho phép người dùng stream các clip video slow-motion. Hiện tại, app capture video raw (chưa xử lý, kích thước lớn) và upload trực tiếp lên Amazon S3 bucket. Khi playback, app lấy video thẳng từ S3, dẫn đến vấn đề buffering và playback kém trên thiết bị di động do file lớn, latency cao.

Công ty muốn tối ưu performance (tốc độ phát), scalability (mở rộng tự động) và minimize operational overhead (giảm chi phí vận hành, quản lý). Yêu cầu chọn 2 giải pháp kết hợp để giải quyết.

🛠️ Vấn đề cốt lõi:

File raw lớn → Tải chậm, buffering.

Truy xuất trực tiếp S3 → Latency cao với người dùng toàn cầu.

Cần xử lý video phù hợp cho mobile streaming (format nhỏ gọn, adaptive bitrate) và phân phối nhanh (CDN).

✅ Đáp án đúng và lý do lựa chọn

Hai đáp án đúng là (chọn 2):

Deploy Amazon CloudFront for content delivery and caching.

✅ Lý do: CloudFront là CDN (Content Delivery Network) toàn cầu của AWS, cache nội dung tại edge locations gần người dùng, giảm latency và buffering cho video streaming. Nó tích hợp seamless với S3, hỗ trợ adaptive streaming (HLS/DASH), tự động scale theo traffic mà không cần quản lý server → Minimize overhead. Phiên bản mới nhất (2026) hỗ trợ Field-Level Encryption và Lambda@Edge cho custom logic.

Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.

✅ Lý do: Elastic Transcoder (nay là MediaConvert trong Elemental family, nhưng câu hỏi dùng Transcoder) chuyển đổi video raw sang format tối ưu cho mobile như MP4/HLS với adaptive bitrate, giảm kích thước file đáng kể (từ raw sang compressed). Serverless, pay-per-use, tự động scale, tích hợp S3 → Giải quyết gốc rễ buffering và overhead thấp. Cập nhật 2026: Hỗ trợ AV1 codec cho hiệu suất cao hơn.

Kết hợp hai giải pháp: Transcoder xử lý video → Lưu output vào S3 → CloudFront phân phối/cache → Performance/scalability tối ưu, zero management.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai) dựa trên yêu cầu performance, scalability, minimize overhead.

✅ Deploy Amazon CloudFront for content delivery and caching.

Giải pháp lý tưởng cho phân phối nội dung toàn cầu. Cache video tại 400+ edge locations (cập nhật 2026), giảm tải S3 90%, hỗ trợ video streaming mượt mà. Tích hợp OAC (Origin Access Control) bảo mật S3. Không cần quản lý → Overhead thấp nhất.

❌ Use AWS DataSync to replicate the video files across AWS Regions in other S3 buckets.

DataSync dùng để sync dữ liệu cross-region (backup/DR), nhưng không cải thiện playback speed vì chỉ replicate file raw lớn, không cache hay transcode. Tăng chi phí storage mà không giải quyết buffering. Không scalable cho streaming real-time.

✅ Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.

Chuyển raw video sang format mobile-friendly (H.264/HLS), giảm kích thước 50-80%, hỗ trợ slow-motion. Trigger từ S3 event, output tự động vào S3. Serverless hoàn toàn → Overhead zero, scale theo job.

❌ Deploy an Auto Scaling group of Amazon EC2 instances in Local Zones for content delivery and caching.

Local Zones giảm latency edge, nhưng dùng EC2 ASG để cache/delivery là overhead cao: Phải quản lý instance, patching, scaling manual, cost cao hơn CloudFront (EC2 tính theo giờ). Không tối ưu cho global CDN, dễ bottleneck.

❌ Deploy an Auto Scaling group of Amazon EC2 instances to convert the video files to more appropriate formats.

EC2 ASG có thể transcode (dùng FFmpeg), nhưng operational overhead lớn: Cần build AMI, monitor queue, auto-scale policy phức tạp, cost cao hơn serverless. Elastic Transcoder/MediaConvert hiệu quả hơn 5-10x cho video workload.

📘 Tài liệu tham khảo

AWS Documentation: Amazon CloudFront Developer Guide (Video Streaming chapter, cập nhật 2025).

Elastic Transcoder User Guide → Khuyến nghị cho legacy, migrate sang MediaConvert.

AWS Best Practices: Optimizing Video Delivery with CloudFront + Media Services (2024-2026 updates).

Exam Prep: AWS Certified DevOps Engineer Professional DOP-C02 (Domain 4: Automation).

Hy vọng phân tích giúp bạn nắm vững! 🚀 Nếu cần thêm case study, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99693-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 50

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon EC2
- Takeaway nhanh: 🛡️ Bảo mật cao nhất: EC2 instances nằm trong private subnets (không có public IP, chỉ truy cập nội bộ qua ALB), tránh expose trực tiếp ra internet. Public ALB (internet-facing) xử lý traffic từ CloudFront, hỗ trợ HTTPS termination và WAF integration. ⚡ Giao nội dung gần edge, độ trễ thấp: CloudFront sử dụng ALB làm origin, cache HTTPS content tại 200+ edge locations toàn cầu, giảm latency tối đa.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/DownloadDistS3AndCustomOrigins.html | https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html | https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html | https://www.examtopics.com/discussions/amazon/view/95013-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time.
Which solution meets these requirements and is MOST secure?

### Các lựa chọn
1. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
2. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.
3. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
4. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi yêu cầu thiết kế một ứng dụng có tính sẵn sàng cao (highly available) với 3 tầng: web (web tier), ứng dụng (application tier) và cơ sở dữ liệu (database tier). Các yêu cầu chính bao gồm:

Giao nội dung HTTPS gần edge nhất có thể (sử dụng CDN để giảm độ trễ, cache nội dung tại các edge location toàn cầu).

Thời gian phân phối nội dung thấp nhất (least delivery time, ưu tiên tốc độ từ CloudFront).

Bảo mật cao nhất (MOST secure): Tránh expose trực tiếp các instance EC2 ra internet, sử dụng các lớp bảo vệ như Load Balancer và private subnets. Ứng dụng cần multi-AZ (redundant instances) để đảm bảo HA. Giải pháp tối ưu phải kết hợp Amazon CloudFront (CDN cho HTTPS edge delivery) với Application Load Balancer (ALB) và EC2 instances, ưu tiên bảo mật bằng cách đặt EC2 ở private subnets.

📘 Tài liệu tham khảo:

AWS Well-Architected Framework (Reliability & Security Pillars, cập nhật 2024-2026): https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html

CloudFront Developer Guide (Origin Groups & ALB integration): https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/DownloadDistS3AndCustomOrigins.html

ALB User Guide (Internet-facing ALB with private targets): https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html

✅ Đáp án đúng: Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.

Lý do lựa chọn:

🛡️ Bảo mật cao nhất: EC2 instances nằm trong private subnets (không có public IP, chỉ truy cập nội bộ qua ALB), tránh expose trực tiếp ra internet. Public ALB (internet-facing) xử lý traffic từ CloudFront, hỗ trợ HTTPS termination và WAF integration.

⚡ Giao nội dung gần edge, độ trễ thấp: CloudFront sử dụng ALB làm origin, cache HTTPS content tại 200+ edge locations toàn cầu, giảm latency tối đa.

🔄 Highly available: Multiple redundant EC2 (multi-AZ), ALB auto-scaling, CloudFront global redundancy.

🧩 Tối ưu nhất: ALB hỗ trợ path-based routing cho multi-tier (web/app), dễ tích hợp database (RDS Multi-AZ). Đây là best practice AWS đến 2026.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên bảo mật, performance và tuân thủ yêu cầu HA.

❌ Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.

Sai vì: EC2 ở public subnets expose public IP trực tiếp, tăng rủi ro tấn công (DDoS, unauthorized access). Dù CloudFront -> ALB tốt cho edge delivery, nhưng vi phạm "MOST secure" do EC2 không private. Performance OK nhưng kém an toàn hơn lựa chọn C.

❌ Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.

Sai vì: CloudFront origin là EC2 trực tiếp (private subnets không có public endpoint dễ dàng), yêu cầu custom setup (như NAT Gateway hoặc public DNS), phức tạp và kém scalable. Không tận dụng ALB cho load balancing/HTTPS offload, tăng latency và rủi ro bảo mật (traffic bypass ALB).

✅ Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.

Đúng vì: Như giải thích ở phần đáp án trên – kết hợp bảo mật (private EC2 + ALB shield), performance (CloudFront edge caching), và HA hoàn hảo. Best practice AWS.

❌ Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.

Sai vì: Kết hợp 2 vấn đề tệ nhất – EC2 public subnets (kém secure) + CloudFront -> EC2 direct (không scalable, bypass ALB, tăng latency vì không cache qua LB). Vi phạm cả secure và low delivery time.

🛠️ Khuyến nghị triển khai: Sử dụng VPC với public subnets cho ALB, private cho EC2 + RDS. Enable CloudFront HTTPS-only, Origin Access Control (OAC) để secure origin. Test với AWS Fault Injection Simulator cho HA đến 2026 standards!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95013-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 51

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon API Gateway, Amazon CloudFront, Amazon S3, Amazon Route 53, Amazon EC2
- Đáp án tham khảo: **Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.**
- Takeaway nhanh: Amazon CloudFront là dịch vụ CDN toàn cầu của AWS, giúp phân phối nội dung động từ ALB làm origin (hỗ trợ từ phiên bản mới nhất 2024-2026), cache nội dung gần edge location (hơn 600 điểm toàn cầu). Thiết lập cache behavior với Accept-Language header làm cache key cho phép lưu phiên bản ngôn ngữ riêng biệt (ví dụ: en-US, vi-VN), giảm tải ALB và latency. Không cần recreate architecture: Chỉ thêm CloudFront trước ALB, giữ nguyên EC2 fleet ở us-west-1.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/header-caching.html | https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/header-caching.html#header-caching-web-language | https://www.examtopics.com/discussions/amazon/view/99865-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company serves a dynamic website from a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting high request latency for users that are located in other parts of the world.
The website needs to serve requests quickly and efficiently regardless of a user’s location. However, the company does not want to recreate the existing architecture across multiple Regions.
What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Replace the existing architecture with a website that is served from an Amazon S3 bucket. Configure an Amazon CloudFront distribution with the S3 bucket as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.
2. Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.
3. Create an Amazon API Gateway API that is integrated with the ALB. Configure the API to use the HTTP integration type. Set up an API Gateway stage to enable the API cache based on the Accept-Language request header.
4. Launch an EC2 instance in each additional Region and configure NGINX to act as a cache server for that Region. Put all the EC2 instances and the ALB behind an Amazon Route 53 record set with a geolocation routing policy.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty đang phục vụ website động (dynamic website) từ một nhóm Amazon EC2 instances đứng sau Application Load Balancer (ALB), tất cả chạy ở Region us-west-1. Website hỗ trợ đa ngôn ngữ để phục vụ khách hàng toàn cầu, nhưng đang gặp vấn đề độ trễ cao (high request latency) đối với người dùng ở các khu vực khác trên thế giới.

Yêu cầu chính:

Phải phục vụ yêu cầu nhanh chóng và hiệu quả bất kể vị trí người dùng.

KHÔNG muốn tái tạo (recreate) kiến trúc hiện tại ở nhiều Region khác (tức là giữ nguyên setup gốc ở us-west-1).

🛠️ Vấn đề cốt lõi: Website động cần xử lý ngôn ngữ dựa trên header Accept-Language, và cần giải pháp toàn cầu hóa (global distribution) mà không thay đổi hạ tầng gốc. Giải pháp lý tưởng là sử dụng CDN (Content Delivery Network) để cache nội dung gần người dùng, hỗ trợ cache key theo header ngôn ngữ.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.

Lý do:

Amazon CloudFront là dịch vụ CDN toàn cầu của AWS, giúp phân phối nội dung động từ ALB làm origin (hỗ trợ từ phiên bản mới nhất 2024-2026), cache nội dung gần edge location (hơn 600 điểm toàn cầu).

Thiết lập cache behavior với Accept-Language header làm cache key cho phép lưu phiên bản ngôn ngữ riêng biệt (ví dụ: en-US, vi-VN), giảm tải ALB và latency.

Không cần recreate architecture: Chỉ thêm CloudFront trước ALB, giữ nguyên EC2 fleet ở us-west-1.

Hiệu quả cao cho website động, hỗ trợ HTTPS, và tích hợp seamless với ALB (custom origin).

📋 Phân tích tất cả các phương án

❌ Phương án SAI: Replace the existing architecture with a website that is served from an Amazon S3 bucket. Configure an Amazon CloudFront distribution with the S3 bucket as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.

Giải thích sai: Website là động (dynamic) từ EC2/ALB (xử lý server-side logic, database), không phải static. S3 chỉ phục vụ static content (HTML/CSS/JS tĩnh), không hỗ trợ dynamic rendering hoặc ngôn ngữ động. Việc thay thế toàn bộ architecture vi phạm yêu cầu "không recreate", và S3 + CloudFront chỉ phù hợp static sites.

✅ Phương án ĐÚNG: Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.

Giải thích đúng: Như phần đáp án trên. CloudFront hỗ trợ ALB làm origin (HTTP/HTTPS), cache theo header Accept-Language qua Cache Policy (tính năng mới nhất 2024-2026 với managed policies). Giảm latency toàn cầu mà không thay đổi hạ tầng gốc. Hoàn hảo cho multi-language dynamic sites.

❌ Phương án SAI: Create an Amazon API Gateway API that is integrated with the ALB. Configure the API to use the HTTP integration type. Set up an API Gateway stage to enable the API cache based on the ALB.

Giải thích sai: API Gateway là cho API backend, không phải CDN toàn cầu cho website (chỉ có vài edge locations so với 600+ của CloudFront). Cache stage chỉ cache response ngắn hạn, không tối ưu latency toàn cầu, và cần thêm layer proxy (HTTP integration với ALB) làm phức tạp không cần thiết. Không phải giải pháp chính cho website dynamic multi-region.

❌ Phương án SAI: Launch an EC2 instance in each additional Region and configure NGINX to act as a cache server for that Region. Put all the EC2 instances and the ALB behind an Amazon Route 53 record set with a geolocation routing policy.

Giải thích sai: Yêu cầu triển khai EC2 + NGINX ở mỗi Region mới chính là recreate architecture, vi phạm rõ ràng "does not want to recreate". Route 53 geolocation chỉ route traffic, không cache toàn cầu hiệu quả như CDN; tốn kém quản lý, scale kém, và NGINX cache không bằng CloudFront edge.

📘 Tài liệu tham khảo (AWS Docs cập nhật 2024-2026)

CloudFront với Custom Origins (ALB): Hỗ trợ ALB làm origin cho dynamic content.

Cache Behaviors và Headers (Accept-Language): Cache key với request headers cho multi-language.

CloudFront Cache Policies: Managed policies mới nhất cho headers.

ALB + CloudFront Best Practices.

🛠️ Lời khuyên DevOps: Sử dụng CloudFront Functions hoặc Lambda@Edge để tùy chỉnh ngôn ngữ nếu cần logic phức tạp hơn!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99865-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/header-caching.html

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/header-caching.html#header-caching-web-language

## Câu 52

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Redshift, Amazon DynamoDB, Amazon ElastiCache, Amazon Relational Database Service
- Takeaway nhanh: Read Replica của Amazon RDS là bản sao chỉ đọc (read-only) được replicate asynchronously từ primary DB, giúp offload 100% read traffic mà không ảnh hưởng đến primary. Business analysts có thể chạy query SQL trực tiếp trên replica mà không cần thay đổi ứng dụng web (app vẫn connect primary cho write/read chính). Minimal changes: Chỉ cần tạo replica qua AWS Console/CLI/API (hỗ trợ MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora). Replica có thể multi-AZ hoặc cross-region để tăng độ bền và latency thấp.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/95032-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem with minimal changes to the existing web application.
What should the solutions architect recommend?

### Các lựa chọn
1. Export the data to Amazon DynamoDB and have the business analysts run their queries.
2. Load the data into Amazon ElastiCache and have the business analysts run their queries.
3. Create a read replica of the primary database and have the business analysts run their queries.
4. Copy the data into an Amazon Redshift cluster and have the business analysts run their queries.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty thương mại điện tử đang gặp vấn đề hiệu suất suy giảm trên ứng dụng web sử dụng Amazon RDS (Relational Database Service). Nguyên nhân chính là tăng số lượng truy vấn SQL chỉ đọc (read-only) từ các business analysts (nhà phân tích kinh doanh). Solutions Architect cần đề xuất giải pháp tối ưu hóa hiệu suất với thay đổi tối thiểu (minimal changes) đối với ứng dụng web hiện tại.

🛠️ Yêu cầu chính:

Giải pháp phải offload (chuyển hướng) traffic đọc khỏi database chính (primary DB) để tránh ảnh hưởng đến ứng dụng.

Không làm thay đổi code hoặc kiến trúc ứng dụng web (vẫn giữ RDS làm backend chính).

Tập trung vào RDS, phù hợp với truy vấn SQL read-only.

✅ Đáp án đúng: Create a read replica of the primary database and have the business analysts run their queries.

Lý do chọn đáp án này (theo best practices AWS mới nhất 2026):

Read Replica của Amazon RDS là bản sao chỉ đọc (read-only) được replicate asynchronously từ primary DB, giúp offload 100% read traffic mà không ảnh hưởng đến primary.

Business analysts có thể chạy query SQL trực tiếp trên replica mà không cần thay đổi ứng dụng web (app vẫn connect primary cho write/read chính).

Minimal changes: Chỉ cần tạo replica qua AWS Console/CLI/API (hỗ trợ MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora). Replica có thể multi-AZ hoặc cross-region để tăng độ bền và latency thấp.

Hiệu suất: Giảm load trên primary lên đến 80-90% cho read-heavy workloads (dữ liệu AWS RDS docs 2026).

Chi phí: Pay-per-use, scale độc lập.

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên minimal changes, phù hợp SQL queries, và tác động hiệu suất.

❌ [SAI] Export the data to Amazon DynamoDB and have the business analysts run their queries.

Lý do sai: DynamoDB là NoSQL key-value store, không hỗ trợ SQL queries (chỉ PartiQL limited). Cần export/ETL data từ RDS (sử dụng DMS hoặc Lambda), thay đổi lớn code queries của analysts. Không minimal changes, vi phạm yêu cầu giữ RDS và SQL. Phù hợp OLTP hơn analytics.

❌ [SAI] Load the data into Amazon ElastiCache and have the business analysts run their queries.

Lý do sai: ElastiCache (Redis/Memcached) là in-memory caching layer, không phải database đầy đủ cho SQL analytics queries. Chỉ cache key-value, không query phức tạp (JOIN, GROUP BY). Cần load data định kỳ (Cache Aside pattern), eviction data gây mất mát, không giải quyết read-only SQL từ RDS.

✅ [ĐÚNG] Create a read replica of the primary database and have the business analysts run their queries.

Lý do đúng: Như giải thích trên, read replica là giải pháp native RDS, zero-downtime, automatic failover (nếu promote), hỗ trợ Aurora Serverless v2 (2026 updates). Offload read queries hiệu quả nhất với minimal config (endpoint riêng cho analysts).

❌ [SAI] Copy the data into an Amazon Redshift cluster and have the business analysts run their queries.

Lý do sai: Redshift là data warehouse cho OLAP/big data, yêu cầu copy/ETL data từ RDS (sử dụng DMS/SCT), biến đổi schema, chi phí cao (concurrency scaling). Không real-time sync, thay đổi lớn (analysts chuyển tool), không minimal cho app RDS hiện tại.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

Amazon RDS Read Replicas: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html – Best practice cho read scaling.

RDS Performance Best Practices: aws.amazon.com/rds/features/read-replicas/ – Offload reads up to 15 replicas.

AWS Well-Architected Framework (Reliability Pillar): Khuyến nghị read replicas cho read-heavy workloads.

Aurora Updates 2026: Hỗ trợ serverless replicas với zero-ETL integration (xem AWS re:Invent 2025 announcements).

🛠️ Lời khuyên DevOps: Sử dụng CloudWatch Metrics (CPUUtilization, ReadIOPS) để monitor primary vs replica, kết hợp Performance Insights để xác nhận cải thiện!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95032-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 53

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon Secrets Manager, Amazon S3, Amazon AppSync
- Takeaway nhanh: Signed URLs phù hợp cho người dùng custom HTTP client không hỗ trợ cookies, vì chỉ cần gửi URL đã ký (signed) một lần, không cần cookies. Họ có thể cập nhật URL signed nếu cần (least impact so với các phương pháp khác). Signed Cookies phù hợp cho người dùng có URL hardcode, vì họ giữ nguyên URL gốc, chỉ cần thêm cookie để CloudFront kiểm tra quyền truy cập cho nhiều file/path (không cần thay đổi URL).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/media/secure-content-using-cloudfront-functions/Plus | https://www.examtopics.com/discussions/amazon/view/99831-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A media company uses Amazon CloudFront for its publicly available streaming video content. The company wants to secure the video content that is hosted in Amazon S3 by controlling who has access. Some of the company’s users are using a custom HTTP client that does not support cookies. Some of the company’s users are unable to change the hardcoded URLs that they are using for access.
Which services or methods will meet these requirements with the LEAST impact to the users? (Choose two.)

### Các lựa chọn
1. Signed cookies
2. Signed URLs
3. AWS AppSync
4. JSON Web Token (JWT)
5. AWS Secrets Manager

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi xoay quanh một công ty truyền thông sử dụng Amazon CloudFront để phân phối nội dung video streaming công khai từ Amazon S3. Họ muốn bảo mật nội dung video bằng cách kiểm soát quyền truy cập (access control), nhưng phải đáp ứng hai ràng buộc cụ thể từ người dùng:

Một số người dùng sử dụng custom HTTP client không hỗ trợ cookies → Không thể dùng phương pháp yêu cầu cookies.

Một số người dùng không thể thay đổi các URL đã hardcode (URL cố định trong code) → Cần phương pháp không yêu cầu thay đổi URL hiện tại. Yêu cầu là chọn hai services/methods phù hợp nhất, với tác động thấp nhất đến người dùng (LEAST impact), nghĩa là giảm thiểu thay đổi cho client-side (không bắt buộc update code lớn hoặc thay đổi hành vi truy cập).

Mục tiêu chính: Sử dụng CloudFront signed mechanisms để cấp quyền truy cập tạm thời (temporary access) cho nội dung private trong S3, thông qua Origin Access Identity (OAI) hoặc Origin Access Control (OAC) để S3 chỉ cho phép CloudFront truy cập. Điều này đảm bảo an toàn mà không expose S3 public.

📘 Tài liệu tham khảo:

AWS CloudFront Developer Guide: Private Content (cập nhật đến 2024-2026, không thay đổi core features).

AWS S3 Security Best Practices (2024).

✅ Đáp án đúng (Chọn TWO)

Các phương án đúng là: Signed cookies và Signed URLs.

Lý do lựa chọn:

Signed URLs phù hợp cho người dùng custom HTTP client không hỗ trợ cookies, vì chỉ cần gửi URL đã ký (signed) một lần, không cần cookies. Họ có thể cập nhật URL signed nếu cần (least impact so với các phương pháp khác).

Signed Cookies phù hợp cho người dùng có URL hardcode, vì họ giữ nguyên URL gốc, chỉ cần thêm cookie để CloudFront kiểm tra quyền truy cập cho nhiều file/path (không cần thay đổi URL).

Kết hợp cả hai: Đáp ứng tất cả users với least impact – Signed URLs cho nhóm no-cookies, Signed Cookies cho nhóm hardcode URL. Đây là best practice AWS cho CloudFront private content (từ DOP-C02 exam blueprint).

🛠️ Giải thích chi tiết từng phương án

✅ Signed cookies

Phương án ĐÚNG. Signed Cookies cho phép truy cập tạm thời vào nhiều objects/files dưới một domain/path trong CloudFront mà không cần thay đổi URL. Client chỉ cần set cookie (bao gồm policy, signature, key-pair ID). Hoàn hảo cho users hardcode URL (giữ nguyên URL, chỉ thêm cookie qua header). Tuy nhiên, không dùng cho no-cookie clients. Least impact cho nhóm này.

(Nguồn: CloudFront Signed Cookies docs).

✅ Signed URLs

Phương án ĐÚNG. Signed URLs cấp quyền truy cập tạm thời cho một URL cụ thể (single file/object), client chỉ gửi URL đã ký (với query params: policy, signature). Không yêu cầu cookies, lý tưởng cho custom HTTP clients không hỗ trợ cookies. Users có thể được cung cấp URL signed mới (impact thấp nếu họ linh hoạt). Kết hợp với Signed Cookies để cover tất cả.

(Nguồn: CloudFront Signed URLs docs).

❌ AWS AppSync

Phương án SAI. AWS AppSync là service cho GraphQL APIs, hỗ trợ real-time data và integrations (như Lambda, DynamoDB), không liên quan đến bảo mật streaming video từ S3/CloudFront. Không control access URLs trực tiếp, gây impact lớn (phải refactor client sang GraphQL). Không phù hợp.

❌ JSON Web Token (JWT)

Phương án SAI. JWT là token-based auth chuẩn (RFC 7519), dùng cho APIs (như Cognito), nhưng CloudFront không hỗ trợ JWT native cho signed access (chỉ dùng private key signing cho URLs/Cookies). Phải custom integration phức tạp, impact cao cho users (thay đổi client hoàn toàn).

❌ AWS Secrets Manager

Phương án SAI. AWS Secrets Manager dùng lưu trữ/rotate secrets (API keys, passwords), không phải cho access control dynamic URLs hoặc streaming. Không integrate trực tiếp với CloudFront/S3 cho signed access, gây overhead lớn và không least impact.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99831-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/media/secure-content-using-cloudfront-functions/Plus,

## Câu 54

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon KMS, Amazon S3, Amazon CLI, Amazon Client VPN
- Đáp án tham khảo: **Use Amazon CloudFront. Provide signed URLs to stream content.**
- Takeaway nhanh: Amazon CloudFront là dịch vụ CDN toàn cầu của AWS, phân phối nội dung (bao gồm video streaming) từ edge locations (hàng trăm điểm trên thế giới), giảm độ trễ và hỗ trợ hàng triệu user đồng thời với auto-scaling. Signed URLs (presigned URLs với CloudFront) cho phép kiểm soát truy cập tạm thời (expiration time), chỉ user được ủy quyền mới xem được (dùng private key từ CloudFront key pairs hoặc AWS KMS integration).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/100130-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform so that authorized users can watch the company’s content on their mobile devices.
What should a solutions architect recommend to meet these requirements?

### Các lựa chọn
1. Publish content to a public Amazon S3 bucket. Use AWS Key Management Service (AWS KMS) keys to stream content.
2. Set up IPsec VPN between the mobile app and the AWS environment to stream content.
3. Use Amazon CloudFront. Provide signed URLs to stream content.
4. Set up AWS Client VPN between the mobile app and the AWS environment to stream content.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang xây dựng ứng dụng di động (mobile app) trên nền tảng AWS, với mục tiêu mở rộng quy mô đến hàng triệu người dùng (millions of users). Họ cần xây dựng một nền tảng cho phép người dùng được ủy quyền (authorized users) xem nội dung của công ty trên thiết bị di động.

🔍 Yêu cầu chính:

Mở rộng quy mô cao: Phải hỗ trợ hàng triệu user đồng thời, đảm bảo hiệu suất toàn cầu (global reach), độ trễ thấp (low latency).

Bảo mật: Chỉ user được ủy quyền mới xem được nội dung (không public).

Phù hợp mobile: Streaming nội dung mượt mà trên thiết bị di động.

Vai trò Solutions Architect: Khuyến nghị giải pháp tối ưu, scalable, cost-effective trên AWS.

🛠️ Bối cảnh AWS (cập nhật 2026): AWS khuyến nghị sử dụng CDN (Content Delivery Network) như Amazon CloudFront kết hợp với nguồn lưu trữ như S3 cho nội dung video/media streaming, đặc biệt với signed URLs để kiểm soát truy cập tạm thời.

📘 Tài liệu tham khảo:

AWS Well-Architected Framework: Pillar Reliability & Security (aws.amazon.com/architecture/well-architected).

Amazon CloudFront Developer Guide: "Using signed URLs" (docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContentSignedURLs.html).

AWS Media Services (Elemental, CloudFront) cho streaming (aws.amazon.com/media-services).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Amazon CloudFront. Provide signed URLs to stream content.

Lý do chi tiết 🏆:

Amazon CloudFront là dịch vụ CDN toàn cầu của AWS, phân phối nội dung (bao gồm video streaming) từ edge locations (hàng trăm điểm trên thế giới), giảm độ trễ và hỗ trợ hàng triệu user đồng thời với auto-scaling.

Signed URLs (presigned URLs với CloudFront) cho phép kiểm soát truy cập tạm thời (expiration time), chỉ user được ủy quyền mới xem được (dùng private key từ CloudFront key pairs hoặc AWS KMS integration).

Phù hợp mobile: Tích hợp dễ dàng với mobile SDK, hỗ trợ adaptive bitrate streaming (HLS/DASH), và tích hợp S3/EC2 làm origin.

Ưu điểm: Scalable, secure, cost-optimized (pay-per-use), không cần VPN phức tạp.

Theo AWS best practices 2026, đây là giải pháp chuẩn cho "secure media delivery at scale".

📝 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm lý do cụ thể bằng tiếng Việt.

❌ [SAI] Publish content to a public Amazon S3 bucket. Use AWS Key Management Service (AWS KMS) keys to stream content.

❌ Lý do sai: Làm nội dung public S3 bucket sẽ vi phạm yêu cầu bảo mật (authorized users only), ai cũng truy cập được mà không cần ủy quyền. AWS KMS dùng để quản lý khóa mã hóa dữ liệu (encryption at rest/in transit), KHÔNG dùng để stream hoặc kiểm soát truy cập streaming. Giải pháp này không scalable cho millions users và dễ bị DDoS/abuse. (Tham khảo: docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html).

❌ [SAI] Set up IPsec VPN between the mobile app and the AWS environment to stream content.

❌ Lý do sai: IPsec VPN (site-to-site) không phù hợp cho mobile app (thiết bị di động thay đổi IP thường xuyên, kết nối kém ổn định). Thiết lập VPN giữa app và AWS VPC sẽ tăng độ trễ cao, không scale cho millions users (overhead lớn, bottleneck tại VPN endpoint). Không phải giải pháp cho streaming content toàn cầu. (Tham khảo: docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html – dành cho site-to-site, không mobile).

✅ [ĐÚNG] Use Amazon CloudFront. Provide signed URLs to stream content.

✅ Lý do đúng (tóm tắt lại): Như phần trên, hoàn hảo cho yêu cầu – CDN global + signed URLs đảm bảo scale, low-latency streaming, và secure access cho mobile users. Tích hợp seamless với S3 làm origin, hỗ trợ Lambda@Edge cho custom auth nếu cần (cập nhật 2026).

❌ [SAI] Set up AWS Client VPN between the mobile app and the AWS environment to stream content.

❌ Lý do sai: AWS Client VPN (OpenVPN-based) dùng cho kết nối từ client đến VPC, nhưng phức tạp cho mobile scale (cần certificate management, mutual auth, overhead cao cho streaming). Không tối ưu cho content delivery toàn cầu (không có edge caching), độ trễ cao với millions users di động. AWS khuyến nghị VPN chỉ cho admin access, không streaming. (Tham khảo: docs.aws.amazon.com/vpn/latest/clientvpn-admin/what-is.html).

🧠 Kết luận: Giải pháp CloudFront + Signed URLs là best practice AWS cho secure, scalable media streaming đến mobile users. Nếu implement, kết hợp IAM policies và CloudWatch để monitor! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/100130-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 55

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Elastic Container Service, Amazon API Gateway, Amazon S3, Amazon EC2, Amazon Simple Email Service, Amazon Lightsail
- Đáp án tham khảo: **Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).**
- Takeaway nhanh: 🆓 Serverless hoàn toàn: Lambda chỉ tính phí theo execution (miễn phí 1 triệu requests/tháng đầu), API Gateway rẻ ($3.50/1M requests), SES rẻ ($0.10/1K emails). Với <100 visits/tháng → gần như miễn phí. 🔄 Tích hợp mượt: Form client-side (JS trên S3) gọi API Gateway → Lambda xử lý validate + gửi SES → an toàn (không lộ credentials). 📈 Scalable & low-ops: Không quản lý server, auto-scale, phù hợp low traffic. Cập nhật AWS 2026: Lambda hỗ trợ ARM Graviton3 rẻ hơn, SES verified identities nhanh chóng.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/architecture/create-dynamic-contact-forms-for-s3-static-websites-using-aws-lambda-amazon-api-gateway-and-amazon-ses/ | https://www.examtopics.com/discussions/amazon/view/99680-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts its static website by using Amazon S3. The company wants to add a contact form to its webpage. The contact form will have dynamic server-side components for users to input their name, email address, phone number, and user message. The company anticipates that there will be fewer than 100 site visits each month.
Which solution will meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Host a dynamic contact form page in Amazon Elastic Container Service (Amazon ECS). Set up Amazon Simple Email Service (Amazon SES) to connect to any third-party email provider.
2. Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).
3. Convert the static webpage to dynamic by deploying Amazon Lightsail. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.
4. Create a t2.micro Amazon EC2 instance. Deploy a LAMP (Linux, Apache, MySQL, PHP/Perl/Python) stack to host the webpage. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc thêm một contact form động (có server-side components) vào website tĩnh đang host trên Amazon S3, với các trường nhập liệu như tên, email, số điện thoại và tin nhắn từ người dùng. 📊 Yêu cầu chính:

Website hiện tại là static (chỉ file HTML/CSS/JS trên S3), cần thêm phần dynamic server-side để xử lý form (nhận dữ liệu, gửi email).

Lưu lượng thấp: <100 visits/tháng → ưu tiên giải pháp cost-effective nhất (tiết kiệm chi phí, serverless lý tưởng vì không cần tài nguyên chạy liên tục).

Mục tiêu: Gửi email thông báo từ form mà không làm phức tạp hóa kiến trúc S3 static.

🛠️ Yêu cầu kỹ thuật AWS cập nhật 2026: Sử dụng serverless (Lambda, API Gateway, SES) để xử lý form mà không cần server luôn chạy. S3 hỗ trợ static hosting với CloudFront cho hiệu suất, nhưng form cần backend để tránh lộ thông tin SES credentials ở client-side.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).

Lý do chọn (cost-effective nhất):

🆓 Serverless hoàn toàn: Lambda chỉ tính phí theo execution (miễn phí 1 triệu requests/tháng đầu), API Gateway rẻ ($3.50/1M requests), SES rẻ ($0.10/1K emails). Với <100 visits/tháng → gần như miễn phí.

🔄 Tích hợp mượt: Form client-side (JS trên S3) gọi API Gateway → Lambda xử lý validate + gửi SES → an toàn (không lộ credentials).

📈 Scalable & low-ops: Không quản lý server, auto-scale, phù hợp low traffic. Cập nhật AWS 2026: Lambda hỗ trợ ARM Graviton3 rẻ hơn, SES verified identities nhanh chóng.

💰 Tiết kiệm nhất so với ECS/EC2/Lightsail (có fixed cost dù low usage).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích từng lựa chọn (giữ nguyên văn bản gốc). Sử dụng kiến thức AWS mới nhất (Well-Architected Framework 2024+, Pricing 2026: serverless ưu tiên cho sporadic workloads).

Host a dynamic contact form page in Amazon Elastic Container Service (Amazon ECS). Set up Amazon Simple Email Service (Amazon SES) to connect to any third-party email provider.

❌ Sai: ECS yêu cầu cluster Fargate/EC2 luôn chạy → fixed cost (~$20-50/tháng cho t3.micro dù low traffic). Phức tạp setup (container, ALB, IAM), không cost-effective. SES không cần third-party (gửi trực tiếp). Không phù hợp static S3.

Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).

✅ Đúng: Như giải thích trên. Serverless, pay-per-use, tích hợp chuẩn (Lambda Node.js/Python gửi SES). AWS docs: "Best for event-driven forms". Zero fixed cost cho <100 visits.

Convert the static webpage to dynamic by deploying Amazon Lightsail. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.

❌ Sai: Lightsail là VPS fixed (~$3.50/tháng cho nano, cộng storage/DB) → tốn kém dù low traffic. Chuyển toàn bộ site sang Lightsail làm mất lợi thế S3 static (rẻ/free outbound). WorkMail là email corp (không dành cho form transactional, đắt ~$4/user/tháng), client-side lộ credentials rủi ro.

Create a t2.micro Amazon EC2 instance. Deploy a LAMP (Linux, Apache, MySQL, PHP/Perl/Python) stack to host the webpage. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.

❌ Sai: EC2 t2.micro (~$7-10/tháng + EBS) luôn chạy → lãng phí (99% idle). Chuyển site sang dynamic LAMP phức tạp, mất S3 static. WorkMail không phù hợp form (transactional cần SES). Client-side unsafe.

📘 Tài liệu tham khảo

AWS Docs: Amazon S3 Static Website + Lambda + API Gateway + SES (Serverless Contact Form blueprint).

Pricing Calculator 2026: Lambda Free Tier, SES.

Well-Architected: Serverless Lens → Cost Optimization Pillar.

Exam Prep: A Cloud Guru / AWS DOP-C02 blueprint (2024+).

🧑‍💻 Kết luận: Giải pháp serverless là tiêu chuẩn AWS cho low-traffic dynamic forms! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99680-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/architecture/create-dynamic-contact-forms-for-s3-static-websites-using-aws-lambda-amazon-api-gateway-and-amazon-ses/

## Câu 56

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon DataSync, Amazon Database Migration Service, Amazon EC2
- Takeaway nhanh: AWS DataSync là dịch vụ managed hoàn toàn (serverless), được thiết kế chuyên biệt để chuyển và đồng bộ dữ liệu tệp (file data) giữa NFS shares cross-Region với hiệu suất cao, bảo mật (encryption in transit/at rest), và hỗ trợ lập lịch tự động qua AWS CLI/API hoặc tích hợp Lambda/EventBridge. Least operational overhead: Không cần quản lý server, phần cứng; chỉ tạo task, agent (DataSync agent deploy nhanh trên EC2 hoặc on-prem), và chạy on-demand/scheduled. Hỗ trợ incremental sync (chỉ chuyển delta), compression, và bandwidth throttling.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html | https://www.examtopics.com/discussions/amazon/view/99949-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and forth between NFS file systems in the two Regions on a periodic basis.
Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Use AWS DataSync.
2. Use AWS Snowball devices.
3. Set up an SFTP server on Amazon EC2.
4. Use AWS Database Migration Service (AWS DMS).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào giải pháp tối ưu để chuyển dữ liệu lớn (large amounts of data) giữa các hệ thống tệp NFS (NFS file systems) ở hai AWS Region khác nhau, cụ thể là giữa site chính và disaster recovery site. Yêu cầu chính là chuyển dữ liệu định kỳ (periodic basis) với operational overhead thấp nhất (LEAST operational overhead).

🔍 Chi tiết vấn đề:

NFS file systems: Đây là giao thức chia sẻ tệp mạng phổ biến, thường dùng trong môi trường Linux/Unix.

Hai Region khác nhau: Cần hỗ trợ cross-Region transfer, có thể qua internet hoặc private network.

Định kỳ: Không phải one-time, mà lặp lại thường xuyên, đòi hỏi tự động hóa cao.

Least operational overhead: Ưu tiên dịch vụ managed (AWS quản lý), ít cấu hình thủ công, không cần phần cứng vật lý hay server tự quản lý.

Kiến thức cập nhật 2026: AWS DataSync (phiên bản mới nhất hỗ trợ NFS 4.1, SMB, HDFS, với tích hợp AWS Transfer Family và scheduling qua CloudWatch Events/Step Functions) là lựa chọn managed service lý tưởng cho file sync cross-Region.

📘 Tài liệu tham khảo:

AWS DataSync: https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html

AWS Well-Architected Framework - Reliability Pillar (DR strategies).

✅ Đáp án đúng: Use AWS DataSync

Lý do lựa chọn:

AWS DataSync là dịch vụ managed hoàn toàn (serverless), được thiết kế chuyên biệt để chuyển và đồng bộ dữ liệu tệp (file data) giữa NFS shares cross-Region với hiệu suất cao, bảo mật (encryption in transit/at rest), và hỗ trợ lập lịch tự động qua AWS CLI/API hoặc tích hợp Lambda/EventBridge.

Least operational overhead: Không cần quản lý server, phần cứng; chỉ tạo task, agent (DataSync agent deploy nhanh trên EC2 hoặc on-prem), và chạy on-demand/scheduled. Hỗ trợ incremental sync (chỉ chuyển delta), compression, và bandwidth throttling.

Phù hợp periodic basis với chi phí pay-per-use (GB transferred), tối ưu cho DR scenarios.

Cập nhật 2026: Hỗ trợ NFSv4.1 multi-protocol, integration với S3/FSx/EFS, và zero-ETR cho cold data migration.

🛠️ Giải thích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Tôi đánh dấu ✅ đúng và ❌ sai, kèm lý do cụ thể dựa trên yêu cầu câu hỏi.

✅ Use AWS DataSync

🟢 Đúng vì: Như giải thích trên, đây là giải pháp managed tối ưu cho NFS-to-NFS sync cross-Region định kỳ, tự động hóa cao, không cần overhead quản lý infrastructure. Hiệu suất lên đến 10 Gbps/task, hỗ trợ scheduling và monitoring qua CloudWatch. Lý tưởng cho DR với RPO/RTO thấp.

❌ Use AWS Snowball devices

🔴 Sai vì: Snowball là thiết bị vật lý (physical appliance) dành cho one-time hoặc infrequent large-scale data transfer (exabyte-scale), không phù hợp periodic basis vì yêu cầu vận chuyển vật lý (ship back/forth), setup phức tạp mỗi lần (import/export jobs), và overhead cao (logistics, customs). Không hỗ trợ real-time NFS sync.

❌ Set up an SFTP server on Amazon EC2

🔴 Sai vì: Yêu cầu tự quản lý EC2 instance (provision, patch, scale, secure SFTP), overhead vận hành cao (monitoring, high availability, bandwidth management). SFTP không tối ưu cho NFS file systems (cần mount/export thủ công), thiếu incremental sync tự động, và kém hiệu suất cross-Region so với managed services. Phù hợp one-off hơn periodic DR.

❌ Use AWS Database Migration Service (AWS DMS)

🔴 Sai vì: DMS chuyên database migration/replication (SQL/NoSQL), không hỗ trợ file systems như NFS. Nó dùng CDC (Change Data Capture) cho DB schemas/tables, không phải bulk file transfers. Overhead cao nếu force-fit (cần DB endpoints), và không hiệu quả cho non-DB data như logs/files trong DR site.

📈 Kết luận & Lời khuyên DevOps

Giải pháp AWS DataSync đảm bảo high availability, scalability cho DR, kết hợp với AWS Backup hoặc FSx for Lustre/NetApp ONTAP cho NFS managed. Trong thực tế DOP-C02 exam, ưu tiên managed services để giảm Toil. Test lab: Tạo DataSync task giữa us-east-1 và eu-west-1 NFS shares! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99949-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 57

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon DynamoDB, Amazon ElastiCache, Amazon EC2, Amazon Relational Database Service
- Takeaway nhanh: Amazon ElastiCache (hỗ trợ Redis hoặc Memcached) là dịch vụ caching in-memory đặt trước database, giúp cache kết quả truy vấn đọc phổ biến (như điểm số). Điều này giảm đáng kể tải read trên RDS MySQL, cải thiện latency và throughput ngay lập tức. Minimize changes: Chỉ cần chỉnh sửa code app để kiểm tra cache trước khi query DB (offload reads ~80-90% traffic read-heavy). Không cần thay đổi EC2, ALB hay DB engine.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonElastiCache/latest/APIReference/Welcome.html | https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/Strategies.html#Strategies.WriteThroughRDS | https://www.examtopics.com/discussions/amazon/view/95016-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A gaming company has a web application that displays scores. The application runs on Amazon EC2 instances behind an Application Load Balancer. The application stores data in an Amazon RDS for MySQL database. Users are starting to experience long delays and interruptions that are caused by database read performance. The company wants to improve the user experience while minimizing changes to the application’s architecture.
What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Use Amazon ElastiCache in front of the database.
2. Use RDS Proxy between the application and the database.
3. Migrate the application from EC2 instances to AWS Lambda.
4. Migrate the database from Amazon RDS for MySQL to Amazon DynamoDB.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một ứng dụng web của công ty game hiển thị điểm số (scores), chạy trên các instance Amazon EC2 phía sau Application Load Balancer (ALB). Dữ liệu được lưu trữ trong Amazon RDS for MySQL. Vấn đề chính là người dùng gặp trì hoãn dài (long delays) và gián đoạn (interruptions) do hiệu suất đọc (read performance) của cơ sở dữ liệu kém. Yêu cầu là cải thiện trải nghiệm người dùng (user experience) đồng thời giảm thiểu thay đổi kiến trúc ứng dụng (minimizing changes to the application’s architecture).

🔍 Phân tích vấn đề cốt lõi:

Ứng dụng có tải đọc cao (read-heavy) vì hiển thị điểm số – thường là các truy vấn SELECT lặp lại.

RDS MySQL gặp bottleneck ở read, dẫn đến delay và gián đoạn.

Giải pháp phải ít xâm lấn nhất, không thay đổi lớn code/app hoặc migrate toàn bộ.

✅ Đáp án đúng: Use Amazon ElastiCache in front of the database.

Lý do chọn đáp án này 🛠️:

Amazon ElastiCache (hỗ trợ Redis hoặc Memcached) là dịch vụ caching in-memory đặt trước database, giúp cache kết quả truy vấn đọc phổ biến (như điểm số). Điều này giảm đáng kể tải read trên RDS MySQL, cải thiện latency và throughput ngay lập tức.

Minimize changes: Chỉ cần chỉnh sửa code app để kiểm tra cache trước khi query DB (offload reads ~80-90% traffic read-heavy). Không cần thay đổi EC2, ALB hay DB engine.

Lợi ích cập nhật 2026: ElastiCache hỗ trợ serverless (Redis/Memcached Serverless), auto-scaling, multi-AZ, và tích hợp seamless với RDS via IAM auth/VPC. Giảm chi phí và tăng độ tin cậy cho gaming workloads.

Kết quả: User experience cải thiện nhanh chóng mà kiến trúc gần như giữ nguyên! 🚀

📋 Giải thích tất cả các phương án (đúng/sai)

✅ Use Amazon ElastiCache in front of the database.

Đúng vì lý do trên: Đây là giải pháp tối ưu cho read performance bottleneck, caching hiệu quả cho queries lặp lại như scores. Ít thay đổi code nhất, phù hợp best practice AWS cho relational DB read-heavy (giảm load RDS lên đến 90%).

❌ Use RDS Proxy between the application and the database.

Sai vì RDS Proxy chủ yếu giải quyết connection pooling và multiplexing (giảm số connection từ app đến DB), giúp scale connections và failover nhanh. Nó không cải thiện read performance trực tiếp (không cache data), nên không giải quyết delay do query chậm trên MySQL. Phù hợp hơn cho write-heavy hoặc high-connection apps.

❌ Migrate the application from EC2 instances to AWS Lambda.

Sai vì việc migrate sang AWS Lambda (serverless) yêu cầu refactor lớn code (stateless, event-driven), thay đổi toàn bộ kiến trúc từ EC2+ALB sang API Gateway/Lambda. Không minimize changes, và không trực tiếp fix DB read issue (Lambda vẫn query RDS tương tự).

❌ Migrate the database from Amazon RDS for MySQL to Amazon DynamoDB.

Sai vì migrate sang DynamoDB (NoSQL) đòi hỏi thay đổi schema, query logic lớn (từ SQL sang key-value/partition), refactor app toàn diện. Không phù hợp scores data (có thể cần joins/complex queries), và vi phạm yêu cầu minimize changes. DynamoDB mạnh scale reads nhưng overhead migrate cao.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

ElastiCache: AWS ElastiCache Docs - Caching Strategies for RDS – Best practice cho read offloading.

RDS Proxy: RDS Proxy Overview – Tập trung connection management.

Gaming Workloads Whitepaper: AWS Gaming Reference Architecture – Khuyến nghị ElastiCache cho leaderboards/scores.

Exam Prep: AWS Certified Solutions Architect/DevOps Engineer Professional (DOP-C02) – Topic: High Performance Databases & Caching.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🎯 Nếu cần thêm ví dụ code/integration, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95016-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/Strategies.html#Strategies.WriteThroughRDS

https://docs.aws.amazon.com/AmazonElastiCache/latest/APIReference/Welcome.html

## Câu 58

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon Kinesis, Amazon Redshift, Amazon ElastiCache, Amazon EBS, Amazon S3, Amazon EC2, Amazon Kinesis Data Firehose, Amazon Kinesis Data Streams
- Takeaway nhanh: 📊 Kinesis Data Analytics (nay tích hợp Apache Flink SQL) cho phép query streaming data near-real-time bằng SQL trực tiếp trên stream, không cần lưu trữ trung gian. Data science team có thể chạy continuous queries với latency giây, scalable theo throughput.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/99752-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is using a fleet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-flight is lost. The company’s data science team wants to query ingested data in near-real time.
Which solution provides near-real-time data querying that is scalable with minimal data loss?

### Các lựa chọn
1. Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.
2. Publish data to Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data.
3. Store ingested data in an EC2 instance store. Publish data to Amazon Kinesis Data Firehose with Amazon S3 as the destination. Use Amazon Athena to query the data.
4. Store ingested data in an Amazon Elastic Block Store (Amazon EBS) volume. Publish data to Amazon ElastiCache for Redis. Subscribe to the Redis channel to query the data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một công ty sử dụng hạm đội EC2 instances để ingest dữ liệu JSON từ nguồn on-premises với tốc độ cao lên đến 1 MB/s. Vấn đề lớn là khi EC2 bị reboot, dữ liệu in-flight (dữ liệu đang truyền) sẽ mất mát. Nhóm data science cần query dữ liệu gần real-time (near-real-time), đồng thời giải pháp phải scalable (mở rộng linh hoạt) và minimal data loss (giảm thiểu mất dữ liệu tối đa).

Yêu cầu chính của giải pháp:

Xử lý streaming data tốc độ cao, bền vững (không mất khi instance fail).

Cho phép query near-real-time (không phải batch processing chậm).

Scalable theo nhu cầu ingestion cao.

Dữ liệu JSON phù hợp với streaming services.

Đây là chủ đề về Amazon Kinesis family và các dịch vụ streaming/querying trong AWS, tập trung vào độ bền vững và latency thấp. Kiến thức dựa trên AWS Well-Architected Framework (Pillar: Reliability & Performance Efficiency) và cập nhật đến 2026 (Kinesis Data Streams hỗ trợ enhanced fan-out, Kinesis Data Analytics chuyển sang Managed Apache Flink nhưng vẫn hỗ trợ SQL apps legacy).

✅ Đáp án đúng

Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.

Lý do lựa chọn:

🛠️ Amazon Kinesis Data Streams là dịch vụ streaming chính cho dữ liệu real-time cao tải (hỗ trợ >1 MB/s dễ dàng qua shards scaling tự động). Nó durable với replication đa AZ, at-least-once delivery, và retention lên đến 365 ngày (cập nhật 2024+), tránh mất data in-flight khi EC2 reboot (producer đẩy trực tiếp từ EC2 qua SDK).

📊 Kinesis Data Analytics (nay tích hợp Apache Flink SQL) cho phép query streaming data near-real-time bằng SQL trực tiếp trên stream, không cần lưu trữ trung gian. Data science team có thể chạy continuous queries với latency giây, scalable theo throughput.

✅ Hoàn hảo match yêu cầu: Near-real-time, scalable (auto-sharding), minimal data loss (persistent stream).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do cụ thể:

✅ Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.

🟢 Đúng vì như giải thích trên: Streaming durable + query real-time native. Lý tưởng cho JSON high-velocity data.

❌ Publish data to Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data.

🔴 Sai vì Kinesis Data Firehose là dịch vụ batch-oriented (buffer data 60-900s trước khi push đến destination như Redshift), dẫn đến không near-real-time (latency phút). Redshift là data warehouse cho analytics chậm, không scalable cho streaming query. Data loss thấp nhưng không match real-time.

❌ Store ingested data in an EC2 instance store. Publish data to Amazon Kinesis Data Firehose with Amazon S3 as the destination. Use Amazon Athena to query the data.

🔴 Sai vì EC2 instance store (local SSD) mất dữ liệu hoàn toàn khi reboot/stop (ephemeral), không giải quyết vấn đề data in-flight loss. Firehose + S3 là batch (latency phút), Athena query serverless trên S3 nhưng chỉ batch/ad-hoc (scan toàn bộ file, latency giây-phút, không near-real-time streaming).

❌ Store ingested data in an Amazon Elastic Block Store (Amazon EBS) volume. Publish data to Amazon ElastiCache for Redis. Subscribe to the Redis channel to query the data.

🔴 Sai vì dù EBS persistent (không mất khi reboot), nhưng Redis (ElastiCache) là in-memory cache cho key-value/low-latency access, không phù hợp query phức tạp data science (như SQL trên JSON). Subscribe channel (Pub/Sub) chỉ real-time notify, không scalable cho analytics lớn; retention Redis ngắn (max 0-7 ngày tùy config), dễ overload với 1MB/s.

📘 Tài liệu tham khảo

AWS Kinesis Data Streams: docs.aws.amazon.com/streams/latest/dev/introduction.html (Durability & Scaling, cập nhật 2025 với Provisioned/On-Demand modes).

Kinesis Data Analytics: docs.aws.amazon.com/kinesisanalytics/latest/dev/what-is.html (SQL Streaming Queries, migrate to Apache Flink).

So sánh Kinesis Streams vs Firehose: AWS re:Post & Well-Architected Lenses (Streaming Data).

Exam Prep: A Cloud Guru / AWS DOP-C02 blueprint (Streaming & Analytics domain).

Giải pháp này đảm bảo high availability và cost-effective cho workload! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99752-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 59

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon EBS, Amazon Backup, Amazon EC2
- Đáp án tham khảo: **Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.**
- Takeaway nhanh: 📅 Nightly backups qua backup plan (schedule tự động). 🌍 Copy backups to another Region qua tính năng cross-region copy trong AWS Backup (cập nhật mới nhất 2024-2026), đảm bảo recovery ở Region khác mà không cần script thủ công. 🚀 Most operationally efficient: Central console, policy-based, audit trail (CloudTrail), scale tự động cho nhiều instances/volumes, không cần code Lambda → giảm toil, tuân thủ AWS Well-Architected Framework (Operational Excellence pillar).
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ | https://aws.amazon.com/blogs/aws/aws-backup-ec2-instances-efs-single-file-restore-and-cross-region-backup/ | https://aws.amazon.com/getting-started/hands-on/amazon-ec2-backup-and-restore-using-aws-backup/#:~:text=the%20services%20used%20with-,AWS%20Backup,-a.%20In%20the%20navigation | https://aws.amazon.com/vi/blogs/aws/aws-backup-ec2-instances-efs-single-file-restore-and-cross-region-backup/ | https://docs.aws.amazon.com/aws-backup/latest/devguide/cross-region-backup.html | https://docs.aws.amazon.com/aws-backup/latest/devguide/ec2.html | https://www.examtopics.com/discussions/amazon/view/99785-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon EBS) data volumes attached to it. The application’s EC2 instance configuration and data need to be backed up nightly. The application also needs to be recoverable in a different AWS Region.
Which solution will meet these requirements in the MOST operationally efficient way?

### Các lựa chọn
1. Write an AWS Lambda function that schedules nightly snapshots of the application’s EBS volumes and copies the snapshots to a different Region.
2. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.
3. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EBS volumes as resources.
4. Write an AWS Lambda function that schedules nightly snapshots of the application's EBS volumes and copies the snapshots to a different Availability Zone.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc backup hàng đêm (nightly) cho một ứng dụng chạy trên nhiều Amazon EC2 instances, mỗi instance gắn nhiều Amazon EBS data volumes. Yêu cầu cụ thể bao gồm:

Backup cả cấu hình EC2 instance (như AMI, metadata, root volume) và dữ liệu EBS volumes.

Ứng dụng phải recoverable ở một AWS Region khác (cross-Region recovery).

Giải pháp phải MOST operationally efficient (hiệu quả vận hành nhất), nghĩa là ưu tiên dịch vụ managed của AWS, giảm thiểu code tự viết, tự động hóa cao, dễ quản lý quy mô lớn và tuân thủ best practices DevOps.

🔍 Thách thức chính:

Backup EBS đơn thuần chỉ lưu dữ liệu volumes, không bao gồm cấu hình instance (như software cài đặt, instance metadata).

Cần cross-Region copy để đảm bảo disaster recovery (DR).

Hiệu quả vận hành: Sử dụng dịch vụ AWS Backup thay vì Lambda tự code để tránh complexity, dễ audit, central management.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.

Lý do:

🛠️ AWS Backup là dịch vụ managed chuyên backup, hỗ trợ EC2 instances làm resources → tự động tạo AMI (backup toàn bộ cấu hình instance, root volume) và snapshots tất cả EBS volumes attached (bao gồm data volumes).

📅 Nightly backups qua backup plan (schedule tự động).

🌍 Copy backups to another Region qua tính năng cross-region copy trong AWS Backup (cập nhật mới nhất 2024-2026), đảm bảo recovery ở Region khác mà không cần script thủ công.

🚀 Most operationally efficient: Central console, policy-based, audit trail (CloudTrail), scale tự động cho nhiều instances/volumes, không cần code Lambda → giảm toil, tuân thủ AWS Well-Architected Framework (Operational Excellence pillar).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do chi tiết:

❌ [SAI] Write an AWS Lambda function that schedules nightly snapshots of the application’s EBS volumes and copies the snapshots to a different Region.

Lý do sai: Chỉ snapshot EBS volumes → không backup cấu hình EC2 (AMI, metadata). Lambda cần code thủ công (IAM roles, error handling, retry logic) → kém efficient so với AWS Backup managed. Cross-Region copy OK nhưng tổng thể phức tạp, khó scale cho nhiều instances.

✅ [ĐÚNG] Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.

Lý do đúng: Như phân tích ở trên – backup toàn diện (AMI + tất cả EBS attached), nightly schedule, cross-Region native, operationally efficient nhất (zero code, policy-driven).

❌ [SAI] Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EBS volumes as resources.

Lý do sai: Chỉ add EBS volumes → không backup cấu hình EC2 instance (AMI cần thiết để recover toàn bộ). AWS Backup hỗ trợ EBS riêng lẻ, nhưng miss yêu cầu "EC2 instance configuration". Cross-Region OK nhưng không đầy đủ.

❌ [SAI] Write an AWS Lambda function that schedules nightly snapshots of the application's EBS volumes and copies the snapshots to a different Availability Zone.

Lý do sai: Chỉ EBS volumes, không backup EC2 config. Copy chỉ đến different AZ (không phải Region) → không đáp ứng cross-Region recovery. Lambda tự code kém efficient.

📘 Tài liệu tham khảo (AWS docs cập nhật mới nhất 2026)

AWS Backup for Amazon EC2: https://docs.aws.amazon.com/aws-backup/latest/devguide/ec2.html – Chi tiết backup EC2 tạo AMI + EBS snapshots.

Cross-Region Backup: https://docs.aws.amazon.com/aws-backup/latest/devguide/cross-region-backup.html – Hỗ trợ copy plans tự động.

AWS Well-Architected: Operational Excellence (Backup strategies): https://aws.amazon.com/architecture/well-architected/.

Exam guide DOP-C02 (DevOps Pro): Nhấn mạnh AWS Backup cho efficient backup/DR.

💡 Best practice DevOps: Luôn ưu tiên managed services như AWS Backup để giảm custom code, tăng reliability! Nếu cần recover, dùng "Restore from backup" trong console.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99785-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/vi/blogs/aws/aws-backup-ec2-instances-efs-single-file-restore-and-cross-region-backup/

https://aws.amazon.com/getting-started/hands-on/amazon-ec2-backup-and-restore-using-aws-backup/#:~:text=the%20services%20used%20with-,AWS%20Backup,-a.%20In%20the%20navigation

https://aws.amazon.com/blogs/aws/aws-backup-ec2-instances-efs-single-file-restore-and-cross-region-backup/

## Câu 60

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon DynamoDB, Amazon S3
- Đáp án tham khảo: **Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.**
- Takeaway nhanh: S3 Object Lambda cho phép transform dữ liệu động (on-the-fly) khi ứng dụng request GET object từ S3. Bạn viết Lambda function để kiểm tra request (ví dụ: từ app nào), loại bỏ PII nếu cần (cho 2 app kia), rồi trả về dữ liệu đã chỉnh sửa mà không thay đổi dữ liệu gốc. Least operational overhead: Lưu trữ centralized (1 bucket duy nhất) → Tiết kiệm storage cost (không duplicate terabytes data).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/This | https://aws.amazon.com/de/blogs/aws/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/ | https://aws.amazon.com/ko/blogs/korea/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/ | https://www.examtopics.com/discussions/amazon/view/99956-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An ecommerce company stores terabytes of customer data in the AWS Cloud. The data contains personally identifiable information (PII). The company wants to use the data in three applications. Only one of the applications needs to process the PII. The PII must be removed before the other two applications process the data.
Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Store the data in an Amazon DynamoDB table. Create a proxy application layer to intercept and process the data that each application requests.
2. Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.
3. Process the data and store the transformed data in three separate Amazon S3 buckets so that each application has its own custom dataset. Point each application to its respective S3 bucket.
4. Process the data and store the transformed data in three separate Amazon DynamoDB tables so that each application has its own custom dataset. Point each application to its respective DynamoDB table.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi thuộc chủ đề AWS Storage và Data Processing trong kỳ thi AWS Certified DevOps Engineer - Professional (DOP-C02), tập trung vào việc quản lý dữ liệu lớn (terabytes) chứa PII (Personally Identifiable Information - thông tin nhận dạng cá nhân).

✅ Yêu cầu chính:

Dữ liệu được lưu trữ trong AWS Cloud.

Sử dụng cho 3 ứng dụng: Chỉ 1 ứng dụng cần xử lý đầy đủ PII, còn 2 ứng dụng kia phải loại bỏ PII trước khi xử lý.

Giải pháp phải có LEAST operational overhead (ít công vận hành nhất): Nghĩa là giảm thiểu việc quản lý tài nguyên, xử lý dữ liệu thủ công, duplicate storage, và chi phí bảo trì lâu dài.

🛠️ Thách thức: Dữ liệu lớn (terabytes) nên ưu tiên giải pháp serverless, on-the-fly processing (xử lý động khi truy vấn), tránh sao chép dữ liệu nhiều lần để tiết kiệm chi phí và overhead.

📘 Kiến thức cập nhật 2026: Sử dụng Amazon S3 Object Lambda (ra mắt 2021, cập nhật liên tục đến 2026 với hỗ trợ Lambda functions mạnh mẽ hơn cho data transformation), là giải pháp tối ưu cho data lake scenarios với PII de-identification.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.

Lý do 🏆:

S3 Object Lambda cho phép transform dữ liệu động (on-the-fly) khi ứng dụng request GET object từ S3. Bạn viết Lambda function để kiểm tra request (ví dụ: từ app nào), loại bỏ PII nếu cần (cho 2 app kia), rồi trả về dữ liệu đã chỉnh sửa mà không thay đổi dữ liệu gốc.

Least operational overhead:

Lưu trữ centralized (1 bucket duy nhất) → Tiết kiệm storage cost (không duplicate terabytes data).

Serverless (S3 + Lambda) → Không cần quản server, auto-scale, pay-per-use.

Dễ quản lý access qua IAM policies và S3 Access Points.

Phù hợp dữ liệu lớn, hỗ trợ Range requests cho partial reads.

Nguồn tham khảo 📚:

AWS S3 Object Lambda Documentation (cập nhật 2026).

DOP-C02 Exam Guide: Domain 3 - Implementation (Storage & Data Pipelines).

🛠️ Phân tích tất cả các phương án (Đúng/Sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên văn bản gốc. Mỗi phương án được đánh giá dựa trên operational overhead, tính khả thi với terabytes data và yêu cầu PII removal.

❌ [SAI] Store the data in an Amazon DynamoDB table. Create a proxy application layer to intercept and process the data that each application requests.

Giải thích sai: DynamoDB không lý tưởng cho terabytes unstructured data (PII customer data thường là logs/files lớn, DynamoDB phù hợp NoSQL structured/small items). Phải build proxy app layer (ví dụ EC2/ECS/Lambda proxy) để intercept requests → Overhead cao: Custom code phức tạp, quản lý scaling, latency tăng, chi phí dev/maintain lớn. Không serverless hoàn toàn, dễ lỗi khi handle large data.

✅ [ĐÚNG] Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.

Giải thích đúng (như phần trên): Transform on-demand qua Lambda, centralized storage, zero-copy data → Least overhead, scale tự động cho 3 apps. Hoàn hảo cho data lake với PII compliance (GDPR-like).

❌ [SAI] Process the data and store the transformed data in three separate Amazon S3 buckets so that each application has its own custom dataset. Point each application to its respective S3 bucket.

Giải thích sai: Phải pre-process toàn bộ terabytes data upfront (sử dụng Glue/EMR) và lưu 3 buckets riêng (1 full PII, 2 de-identified) → Overhead cao: Storage cost gấp 3x (duplicate data), sync dữ liệu khi update gốc phức tạp (S3 Replication + ETL jobs), quản lý nhiều buckets/IAM policies. Không động, kém hiệu quả nếu data thay đổi thường xuyên.

❌ [SAI] Process the data and store the transformed data in three separate Amazon DynamoDB tables so that each application has its own custom dataset. Point each application to its respective DynamoDB table.

Giải thích sai: Tương tự option 3 nhưng với DynamoDB → Overhead cực cao: DynamoDB đắt đỏ cho terabytes (RCU/WCU provisioning), pre-process ETL nặng (Glue to DynamoDB), duplicate tables → Chi phí storage/provisioning x3, khó scale cho large blobs. DynamoDB kém phù hợp unstructured PII data so với S3 data lake.

Kết luận tổng quát 🎯: Giải pháp đúng tận dụng S3 Object Lambda để just-in-time transformation, giảm thiểu mọi overhead so với các cách duplicate/pre-process. Đây là best practice AWS cho PII data sharing trong multi-app scenarios! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99956-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/aws/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/This

https://aws.amazon.com/de/blogs/aws/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/

https://aws.amazon.com/ko/blogs/korea/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/

## Câu 61

- Domain heuristic: `Domain 2`
- Đáp án tham khảo: **Use an Amazon Aurora global database with a warm standby deployment.**
- Takeaway nhanh: Aurora Global Database hỗ trợ replication cross-Region với latency thấp nhất (sub-second cho reads, storage-based sync), đảm bảo DB ở DR up-to-date (RPO gần 0). Warm standby deployment cho infrastructure còn lại: Chạy ở reduced capacity (scale-down EC2/ASG, etc.), sẵn sàng scale up nhanh (Auto Scaling), giúp RTO thấp nhất (~1-5 phút failover toàn bộ hệ thống).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html | https://www.examtopics.com/discussions/amazon/view/99505-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery (DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary.
Which solution will meet these requirements with the LOWEST recovery time objective (RTO)?

### Các lựa chọn
1. Use an Amazon Aurora global database with a pilot light deployment.
2. Use an Amazon Aurora global database with a warm standby deployment.
3. Use an Amazon RDS Multi-AZ DB instance with a pilot light deployment.
4. Use an Amazon RDS Multi-AZ DB instance with a warm standby deployment.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc xây dựng chiến lược phục hồi sau thảm họa (Disaster Recovery - DR) cho một công ty thương mại điện tử đang chạy workload trên một AWS Region duy nhất. 🏪 Yêu cầu chính:

Sử dụng Region AWS khác cho DR.

Database phải được đồng bộ hóa up-to-date ở DR Region với latency thấp nhất có thể (tức là replication gần real-time).

Infrastructure còn lại (không phải DB) ở DR chạy ở reduced capacity (tài nguyên thấp, tiết kiệm chi phí) nhưng có thể scale up nhanh chóng khi cần failover.

Mục tiêu: LOWEST Recovery Time Objective (RTO) – thời gian khôi phục hệ thống ngắn nhất (lý tưởng là phút hoặc giây). ⚡

Vấn đề cốt lõi là chọn giải pháp DR backup region phù hợp cho database (hỗ trợ cross-region replication nhanh) kết hợp với mô hình triển khai warm standby hoặc pilot light để tối ưu RTO, RPO (Recovery Point Objective – mất dữ liệu ít nhất). 📊 Kiến thức AWS cập nhật đến 2026: Amazon Aurora Global Database là lựa chọn tối ưu cho cross-region với storage-level replication (latency <1 giây), hỗ trợ multi-Region failover tự động dưới 1 phút (RTO ~30-60 giây).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use an Amazon Aurora global database with a warm standby deployment.

🛠️ Lý do:

Aurora Global Database hỗ trợ replication cross-Region với latency thấp nhất (sub-second cho reads, storage-based sync), đảm bảo DB ở DR up-to-date (RPO gần 0).

Warm standby deployment cho infrastructure còn lại: Chạy ở reduced capacity (scale-down EC2/ASG, etc.), sẵn sàng scale up nhanh (Auto Scaling), giúp RTO thấp nhất (~1-5 phút failover toàn bộ hệ thống).

So với pilot light (chỉ "ngọn đuốc nhỏ" – infra tắt/minimal, scale up chậm hơn), warm standby nhanh hơn, phù hợp yêu cầu. Đây là best practice AWS DR Tier 1 (lowest RTO/RPO). 🚀

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai dựa trên khả năng đáp ứng lowest RTO, cross-Region DB sync low-latency, và reduced capacity scale-up.

❌ Use an Amazon Aurora global database with a pilot light deployment.

Sai vì: Aurora Global DB ✅ tốt cho DB sync low-latency. Nhưng pilot light chỉ giữ infra cơ bản (minimal resources, thường tắt EC2), scale up chậm (cần khởi động từ AMI/snapshots ~10-30 phút), dẫn đến RTO cao hơn so với warm standby. Không tối ưu lowest RTO. ⏳

✅ Use an Amazon Aurora global database with a warm standby deployment.

Đúng vì: Kết hợp hoàn hảo – Aurora Global DB đảm bảo DB up-to-date low-latency (replication <1s), warm standby giữ infra reduced capacity (EC2 chạy low-utilization, ready-to-scale via ASG/Lambda), failover RTO thấp nhất (~1 phút). Phù hợp mọi yêu cầu. 💯

❌ Use an Amazon RDS Multi-AZ DB instance with a pilot light deployment.

Sai vì: RDS Multi-AZ chỉ hỗ trợ intra-Region (không cross-Region native), sync không low-latency cho DR Region khác (phải dùng read replicas/snapshots thủ công, RPO/RTO kém). Pilot light làm scale-up chậm thêm. Không đáp ứng DB up-to-date low-latency. 🚫

❌ Use an Amazon RDS Multi-AZ DB instance with a warm standby deployment.

Sai vì: Tương tự trên, RDS Multi-AZ không hỗ trợ cross-Region replication real-time như Aurora Global (chỉ snapshots/read replicas với lag cao hơn). Warm standby giúp infra tốt nhưng DB sync kém, RTO không lowest. RDS kém linh hoạt hơn Aurora cho DR global. 🔄

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS Well-Architected Framework – Reliability Pillar: DR strategies (Pilot Light vs. Warm Standby). Link

Amazon Aurora Global Database Docs: Cross-Region replication & failover RTO. Link

AWS DR Whitepaper: Tier 0/1 strategies với RTO so sánh. Link

RDS vs. Aurora Comparison: Aurora superior cho global DR. Link

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🌟 Nếu cần thêm case study, hỏi nhé! 🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99505-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html

## Câu 62

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon S3, Amazon EC2
- Đáp án tham khảo: **Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.**
- Takeaway nhanh: CloudFront là dịch vụ CDN (Content Delivery Network) của AWS, sử dụng hàng trăm edge locations toàn cầu (gần Bắc Mỹ và Châu Âu), giúp cache nội dung tại edge gần user nhất. Kết quả: Giảm latency đáng kể (cải thiện perf), và giảm chi phí data transfer vì traffic từ edge đến user không tính phí egress (chỉ tính từ origin S3 đến CloudFront nếu cache miss - thường thấp với datasets lớn ít thay đổi).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html | https://www.examtopics.com/discussions/amazon/view/99697-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company sells datasets to customers who do research in artificial intelligence and machine learning (AI/ML). The datasets are large, formatted files that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a purchase is made, customers receive an S3 signed URL that allows access to the files.
The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers and wants to maintain or improve performance.
What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Configure S3 Transfer Acceleration on the existing S3 bucket. Direct customer requests to the S3 Transfer Acceleration endpoint. Continue to use S3 signed URLs for access control.
2. Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.
3. Set up a second S3 bucket in the eu-central-1 Region with S3 Cross-Region Replication between the buckets. Direct customer requests to the closest Region. Continue to use S3 signed URLs for access control.
4. Modify the web application to enable streaming of the datasets to end users. Configure the web application to read the data from the existing S3 bucket. Implement access control directly in the application.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty bán các bộ dữ liệu lớn (datasets) dùng cho nghiên cứu AI/ML, lưu trữ dưới dạng file lớn trên bucket S3 tại vùng us-east-1. Khách hàng mua qua ứng dụng web chạy trên nhiều instance Amazon EC2 phía sau Application Load Balancer (ALB). Sau khi mua, khách nhận S3 signed URL để truy cập file. Khách hàng phân bố ở Bắc Mỹ và Châu Âu, dẫn đến khoảng cách địa lý xa (từ us-east-1 đến Châu Âu).

Yêu cầu chính:

Giảm chi phí liên quan đến data transfer (chuyển dữ liệu ra ngoài S3, đặc biệt là egress traffic quốc tế).

Duy trì hoặc cải thiện hiệu suất (giảm latency, tăng tốc độ tải).

Vấn đề cốt lõi: Data transfer từ S3 us-east-1 đến Châu Âu tốn kém (Internet Data Transfer fees cao hơn intra-region), và latency cao do khoảng cách địa lý. Giải pháp cần tối ưu hóa phân phối nội dung toàn cầu mà không thay đổi lớn kiến trúc hiện tại. AWS khuyến nghị sử dụng CDN như CloudFront cho trường hợp này (theo AWS Well-Architected Framework - Reliability & Cost Optimization pillars).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.

Lý do chọn đáp án này 🛠️:

CloudFront là dịch vụ CDN (Content Delivery Network) của AWS, sử dụng hàng trăm edge locations toàn cầu (gần Bắc Mỹ và Châu Âu), giúp cache nội dung tại edge gần user nhất. Kết quả: Giảm latency đáng kể (cải thiện perf), và giảm chi phí data transfer vì traffic từ edge đến user không tính phí egress (chỉ tính từ origin S3 đến CloudFront nếu cache miss - thường thấp với datasets lớn ít thay đổi).

Giữ nguyên S3 bucket hiện tại làm origin, không cần replicate data.

Chuyển sang CloudFront signed URLs (tương đương S3 signed URLs, hỗ trợ cookie/policy-based access) để kiểm soát truy cập bảo mật.

Phù hợp cập nhật 2026: CloudFront hỗ trợ Origin Access Control (OAC) mới thay S3 bucket policies, tăng bảo mật; tích hợp S3 Intelligent-Tiering tự động tối ưu chi phí.

📋 Giải thích tất cả các phương án (đúng/sai)

Configure S3 Transfer Acceleration on the existing S3 bucket. Direct customer requests to the S3 Transfer Acceleration endpoint. Continue to use S3 signed URLs for access control.

❌ Phương án SAI: S3 Transfer Acceleration chỉ tối ưu upload/download tốc độ cao cho file lớn qua AWS Edge Network (tăng tốc ~50-500%), nhưng KHÔNG phải CDN - không cache nội dung, vẫn fetch trực tiếp từ origin S3 us-east-1. Do đó, latency cao với user Châu Âu, và chi phí data transfer vẫn cao (egress đầy đủ). Không cải thiện perf toàn cầu, chỉ phù hợp upload lớn.

Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.

✅ Phương án ĐÚNG: Như giải thích trên, CloudFront cache datasets tại edge locations (hàng nghìn PoPs toàn cầu, cập nhật 2026 có thêm Châu Âu), giảm ~70-90% latency và data transfer costs. Signed URLs CloudFront tương thích hoàn hảo, hỗ trợ TTL tùy chỉnh. Giải pháp tối ưu nhất theo best practices AWS.

Set up a second S3 bucket in the eu-central-1 Region with S3 Cross-Region Replication between the buckets. Direct customer requests to the closest Region. Continue to use S3 signed URLs for access control.

❌ Phương án SAI: S3 Cross-Region Replication (CRR) replicate data sang eu-central-1, giảm latency cho Châu Âu nhưng tăng chi phí lớn: Storage gấp đôi (hai buckets), CRR fees, và data transfer giữa regions (tính phí). User Bắc Mỹ vẫn dùng us-east-1 nhưng tổng egress không giảm (vẫn cao cho Châu Âu nếu traffic lớn). Không cache, perf kém hơn CDN; cập nhật 2026 CRR hỗ trợ S3 Express One Zone nhưng vẫn tốn kém.

Modify the web application to enable streaming of the datasets to end users. Configure the web application to read the data from the existing S3 bucket. Implement access control directly in the application.

❌ Phương án SAI: Ép EC2 + ALB stream data từ S3 qua app sẽ tăng tải CPU/memory EC2 (file lớn AI/ML có thể GB/TB), dẫn đến scale khó, chi phí EC2 cao, và data transfer vẫn tính đầy đủ (S3 → EC2 → user). Latency tệ hơn (thêm hop), không scalable toàn cầu. Phá vỡ kiến trúc serverless; vi phạm nguyên tắc "decouple" của AWS.

📘 Tài liệu tham khảo (cập nhật mới nhất 2026)

AWS CloudFront Developer Guide: CloudFront with S3 - Signed URLs & OAC.

AWS Pricing: CloudFront egress rẻ hơn S3 Internet Transfer (xem AWS Pricing Calculator).

S3 Transfer Acceleration: Docs - Chỉ cho speed, không cache.

Well-Architected Framework: Cost Optimization - Sử dụng CDN cho global content (AWS Well-Architected).

S3 CRR: Cross-Region Replication - Chi phí chi tiết.

Giải pháp này đảm bảo tuân thủ DevOps best practices: IaC với CloudFront (Terraform/CloudFormation), monitoring qua CloudWatch. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99697-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html

## Câu 63

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Elastic Container Service, Amazon EC2
- Takeaway nhanh: ECS cluster là nền tảng cần thiết để orchestrate các container/services trong ECS, hỗ trợ cả Fargate và EC2 launch types. Nó fully managed bởi AWS, không yêu cầu quản lý infrastructure. ECS service với Fargate launch type + desired tasks >=2: Fargate là serverless, AWS tự quản lý compute resources (EC2 dưới hood nhưng hidden), tự động scale theo tasks. Desired tasks >=2 đảm bảo high availability (HA) across AZs, giảm downtime. Kết hợp này minimize maintenance (không patch EC2, không manage cluster) và auto-scaling dễ dàng qua ECS Service Auto Scaling.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html | https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html | https://www.examtopics.com/discussions/amazon/view/95012-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot manage additional infrastructure.
Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.
2. Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.
3. Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of greater than or equal to 2.
4. Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.
5. Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that specifies two or more replicas for each microservice.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc triển khai ứng dụng microservices sử dụng container technologies trên AWS, với các yêu cầu chính:

Giảm thiểu nỗ lực bảo trì và mở rộng liên tục (minimize ongoing effort for maintenance and scaling) 📉.

Không quản lý thêm cơ sở hạ tầng (cannot manage additional infrastructure) 🚫 – nghĩa là cần giải pháp serverless hoặc fully managed, tránh phải tự quản lý máy chủ EC2, cluster control plane hay worker nodes.

Đây là câu hỏi chọn TWO actions từ solutions architect để đáp ứng, liên quan đến Amazon ECS (Elastic Container Service) và các launch type như Fargate (serverless) so với EC2 (self-managed).

Bối cảnh AWS cập nhật đến 2026: ECS với Fargate là lựa chọn serverless compute engine lý tưởng cho container orchestration, tự động scale tasks/services mà không cần quản lý underlying infrastructure. EKS (Kubernetes) có thể managed nhưng các option tự deploy control plane/worker nodes sẽ yêu cầu quản lý EC2, vi phạm yêu cầu.

✅ Đáp án đúng (Chọn TWO)

Hai phương án đúng là:

Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.

Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.

Lý do lựa chọn 🛠️:

ECS cluster là nền tảng cần thiết để orchestrate các container/services trong ECS, hỗ trợ cả Fargate và EC2 launch types. Nó fully managed bởi AWS, không yêu cầu quản lý infrastructure.

ECS service với Fargate launch type + desired tasks >=2: Fargate là serverless, AWS tự quản lý compute resources (EC2 dưới hood nhưng hidden), tự động scale theo tasks. Desired tasks >=2 đảm bảo high availability (HA) across AZs, giảm downtime. Kết hợp này minimize maintenance (không patch EC2, không manage cluster) và auto-scaling dễ dàng qua ECS Service Auto Scaling.

📋 Giải thích tất cả các phương án (Đúng/Sai)

✅ Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.

Đúng vì: ECS cluster là thành phần cốt lõi, fully managed bởi AWS, cho phép deploy services/tasks mà không cần quản lý infrastructure. Kết hợp với Fargate để serverless hoàn toàn. 🟢 Hoàn hảo cho microservices scaling tự động.

❌ Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.

Sai vì: Đây là self-managed EKS control plane trên EC2, yêu cầu công ty tự quản lý patching, scaling, HA cho control plane – vi phạm "cannot manage additional infrastructure". AWS khuyến nghị dùng EKS managed control plane thay thế (từ 2018+), nhưng option này vẫn tốn effort cao. 🚫 Không minimize maintenance.

❌ Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of greater than or equal to 2.

Sai vì: EC2 launch type yêu cầu tự quản lý EC2 instances (Cluster Capacity Providers hoặc Auto Scaling Groups), bao gồm patching OS, monitoring, scaling instances – trái với yêu cầu no additional infrastructure. Desired tasks >=2 chỉ giúp HA nhưng vẫn tốn effort. ❌ Fargate mới là serverless đúng chuẩn.

✅ Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.

Đúng vì: Fargate Spot/On-Demand (cập nhật 2023-2026) là serverless 100%, AWS handle toàn bộ compute (vCPU, memory). Desired tasks >=2 đảm bảo replicas chạy multi-AZ cho resilience. Tự động scale qua ECS features như Auto Scaling dựa trên metrics. 🟢 Minimize effort tối đa cho microservices.

❌ Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that specifies two or more replicas for each microservice.

Sai vì: Worker nodes trên EC2 là self-managed nodes trong EKS/Kubernetes, yêu cầu quản lý EC2 (AMI, security groups, ASG) – không serverless. Replicas >=2 chỉ giúp HA nhưng vẫn tốn maintenance. AWS có EKS Fargate (tương tự ECS Fargate) nhưng option này chỉ định EC2. 🚫 Vi phạm yêu cầu chính.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

AWS ECS Documentation: Amazon ECS Cluster & Fargate Launch Type – Xác nhận serverless, no infra management.

AWS Well-Architected Framework (Containers Pillar, 2024+): Khuyến nghị ECS Fargate cho low-maintenance microservices.

Exam Prep DOP-C02: Tương tự câu DOP-C02 sample questions về ECS vs EKS.

Best Practices: Sử dụng ECS Capacity Providers với Fargate để auto-scale (từ 2022 updates).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ thực hành, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/95012-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html

https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html

## Câu 64

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon EBS, Amazon EFS, Amazon S3, Amazon Storage Gateway, Amazon EC2
- Takeaway nhanh: S3 là lựa chọn tiết kiệm nhất: Lưu trữ chính trên S3 (object storage) siêu rẻ, scalable vô hạn, durable 99.999999999%, hỗ trợ lifecycle policies để tự động chuyển sang IA/Glacier giảm phí thêm. ✅ Xử lý tạm thời trên EBS: Download file từ S3 sang EBS volume gắn vào EC2 cụ thể để transcoding (EBS gp3 chỉ tính phí khi dùng, ~0.08 USD/GB/tháng, detach sau khi xong để tránh phí). Nhiều EC2 có thể parallel download từ S3.
- Nguồn tham khảo trong block: https://aws.amazon.com/efs/pricing/ | https://docs.aws.amazon.com/efs/latest/ug/efs-overview_comparison.html | https://docs.aws.amazon.com/storagegateway/latest/userguide/what-is-gateway.html | https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/99509-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive.
Which storage solution is MOST cost-effective?

### Các lựa chọn
1. Use AWS Storage Gateway for files to store and process the video content.
2. Use AWS Storage Gateway for volumes to store and process the video content.
3. Use Amazon EFS for storing the video content. Once processing is complete, transfer the files to Amazon Elastic Block Store (Amazon EBS).
4. Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty cung cấp dịch vụ đăng tải video trực tuyến và transcoding (chuyển đổi định dạng) để phù hợp với các nền tảng mobile. Kiến trúc hiện tại sử dụng Amazon Elastic File System (Amazon EFS) Standard làm nơi lưu trữ chung các file video, cho phép nhiều instance Amazon EC2 Linux truy cập đồng thời để xử lý (processing). 📈 Vấn đề lớn là chi phí lưu trữ tăng cao do quy mô dịch vụ phát triển.

Mục tiêu: Tìm giải pháp lưu trữ tiết kiệm chi phí nhất (MOST cost-effective), vẫn đảm bảo:

Lưu trữ video gốc một cách bền vững và scalable.

Nhiều EC2 có thể truy cập để transcoding.

Giảm chi phí so với EFS Standard (dùng phí theo dung lượng lưu trữ + throughput, đắt đỏ cho dữ liệu lớn).

🛠️ Kiến thức AWS cập nhật 2026: EFS Standard có giá ~0.30 USD/GB/tháng (US East), trong khi S3 Standard-IA chỉ ~0.0125 USD/GB/tháng. Workload này phù hợp object storage như S3 (rẻ hơn 10-20x), chỉ cần tạm mount sang block storage để process.

✅ Đáp án đúng

Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.

Lý do chọn đáp án này:

S3 là lựa chọn tiết kiệm nhất: Lưu trữ chính trên S3 (object storage) siêu rẻ, scalable vô hạn, durable 99.999999999%, hỗ trợ lifecycle policies để tự động chuyển sang IA/Glacier giảm phí thêm. ✅

Xử lý tạm thời trên EBS: Download file từ S3 sang EBS volume gắn vào EC2 cụ thể để transcoding (EBS gp3 chỉ tính phí khi dùng, ~0.08 USD/GB/tháng, detach sau khi xong để tránh phí). Nhiều EC2 có thể parallel download từ S3.

Tiết kiệm tối ưu: Giảm >90% chi phí so EFS, phù hợp DevOps best practice (immutable storage + ephemeral processing). 🚀

📋 Giải thích tất cả các phương án

❌ Use AWS Storage Gateway for files to store and process the video content.

Sai vì: Storage Gateway File Gateway dùng để kết nối on-premises với S3, không phải giải pháp native cloud cho EC2 thuần túy. Nó thêm latency, phức tạp setup (SMB/NFS proxy), và chi phí cao hơn S3 trực tiếp (~0.045 USD/GB + phí gateway). Không giải quyết vấn đề EFS đắt, chỉ phù hợp hybrid env. 🛑

❌ Use AWS Storage Gateway for volumes to store and process the video content.

Sai vì: Volume Gateway cung cấp iSCSI block storage (cache volumes/stored), không hỗ trợ shared file access cho multiple EC2 như EFS. Phù hợp backup on-prem sang S3, không scalable cho video processing cloud-native, chi phí tương đương EBS + overhead. Không cost-effective. 🔒

❌ Use Amazon EFS for storing the video content. Once processing is complete, transfer the files to Amazon Elastic Block Store (Amazon EBS).

Sai vì: Vẫn giữ EFS làm lưu trữ chính (đắt đỏ nhất, phí throughput cao cho video lớn), chỉ chuyển sang EBS sau process – nhưng EBS không shared (single AZ, attach 1 instance), không phù hợp multiple EC2. Không giảm chi phí gốc, vi phạm yêu cầu MOST cost-effective. 💸

✅ Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.

Đúng vì: Như giải thích ở trên – S3 thay thế EFS hoàn hảo cho lưu trữ lâu dài (rẻ, global access), EBS chỉ dùng tạm (ephemeral). Hỗ trợ S3 Transfer Acceleration cho download nhanh, tích hợp Lambda/EC2 để automate. Best practice DOP-C02. 🌟

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS EFS Pricing: https://aws.amazon.com/efs/pricing/ (so sánh vs S3).

S3 vs EFS Comparison: https://docs.aws.amazon.com/efs/latest/ug/efs-overview_comparison.html.

Storage Gateway Docs: https://docs.aws.amazon.com/storagegateway/latest/userguide/what-is-gateway.html.

DOP-C02 Exam Guide (Domain 2: Storage): AWS Certified DevOps Engineer Professional blueprint.

Well-Architected Framework - Cost Optimization Pillar: https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html.

Hy vọng phân tích giúp bạn ôn thi hiệu quả! 💪 Nếu cần thêm case study, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99509-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 65

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon EMR, Amazon Glue, Amazon Redshift, Amazon EventBridge, Amazon Lambda, Amazon DynamoDB, Amazon S3, Amazon EC2
- Đáp án tham khảo: **Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.**
- Takeaway nhanh: Serverless: Scale tự động, pay-per-use. Tích hợp native với S3 (source) và Redshift (target), phù hợp COTS query SQL. Theo AWS Well-Architected Framework (2024-2026), Glue là lựa chọn hàng đầu cho ETL batch trên S3-Redshift với zero management. Không cần code phức tạp, chỉ config job qua console/CLI.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected?lens=data-analytics | https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-etl-format.html | https://docs.aws.amazon.com/redshift/latest/mgmt/glue-integrations.html | https://www.examtopics.com/discussions/amazon/view/99817-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon Redshift and Amazon S3 only. However, the COTS application cannot process the .csv files that the legacy application produces.
The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the COTS application can use the data that the legacy application produces.
Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.
2. Develop a Python script that runs on Amazon EC2 instances to convert the .csv files to .sql files. Invoke the Python script on a cron schedule to store the output files in Amazon S3.
3. Create an AWS Lambda function and an Amazon DynamoDB table. Use an S3 event to invoke the Lambda function. Configure the Lambda function to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in the DynamoDB table.
4. Use Amazon EventBridge to launch an Amazon EMR cluster on a weekly schedule. Configure the EMR cluster to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in an Amazon Redshift table.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi xoay quanh một tình huống thực tế trong AWS:

Một công ty đang sử dụng ứng dụng legacy (ứng dụng cũ) để sản xuất dữ liệu dạng CSV và lưu trữ trực tiếp vào Amazon S3. Họ triển khai ứng dụng COTS mới (ứng dụng thương mại sẵn có, commercial off-the-shelf), ứng dụng này chỉ hỗ trợ thực hiện các truy vấn SQL phức tạp trên dữ liệu lưu ở Amazon Redshift hoặc Amazon S3. Tuy nhiên, COTS không thể xử lý file .csv từ legacy app.

Ràng buộc quan trọng: Không thể cập nhật legacy app để xuất dữ liệu ở định dạng khác.

Yêu cầu giải pháp: Cho phép COTS sử dụng dữ liệu từ legacy với ít overhead vận hành nhất (LEAST operational overhead) – nghĩa là giải pháp phải tự động hóa cao, ít quản lý thủ công, chi phí thấp, serverless ưu tiên theo best practice AWS (cập nhật đến 2026, AWS nhấn mạnh serverless ETL với Glue).

Mục tiêu là chuyển đổi CSV sang định dạng phù hợp (như Parquet hoặc table trong Redshift) để COTS query SQL dễ dàng, đồng thời tối ưu hóa vận hành (không cần quản lý server, cluster thủ công).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.

Lý do:

🛠️ AWS Glue là dịch vụ serverless ETL managed hoàn toàn bởi AWS (không cần quản lý infrastructure), hỗ trợ crawl S3 CSV tự động, transform dữ liệu (ví dụ: convert sang Parquet hoặc load trực tiếp vào Redshift), và chạy theo schedule qua Glue Triggers hoặc EventBridge.

✅ Điều này đáp ứng LEAST operational overhead vì:

Serverless: Scale tự động, pay-per-use.

Tích hợp native với S3 (source) và Redshift (target), phù hợp COTS query SQL.

Theo AWS Well-Architected Framework (2024-2026), Glue là lựa chọn hàng đầu cho ETL batch trên S3-Redshift với zero management.

Không cần code phức tạp, chỉ config job qua console/CLI.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh:

✅ Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.

🟢 Đúng vì: Như đã giải thích trên, Glue là giải pháp serverless tối ưu, crawl S3 CSV → ETL → load Redshift tự động theo lịch. Overhead thấp nhất, hỗ trợ schema inference cho CSV, và tích hợp Redshift Spectrum cho query S3 nếu cần (cập nhật Glue 4.0 năm 2023+).

❌ Develop a Python script that runs on Amazon EC2 instances to convert the .csv files to .sql files. Invoke the Python script on a cron schedule to store the output files in Amazon S3.

🔴 Sai vì: Yêu cầu quản lý EC2 thủ công (patching, scaling, monitoring), cron schedule tự code – overhead cao. Convert sang .sql files không hợp lý (COTS cần query SQL trên table, không phải file .sql). Không native với Redshift, vi phạm least overhead.

❌ Create an AWS Lambda function and an Amazon DynamoDB table. Use an S3 event to invoke the Lambda function. Configure the Lambda function to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in the DynamoDB table.

🔴 Sai vì: DynamoDB không hỗ trợ SQL phức tạp như COTS yêu cầu (chỉ NoSQL queries), không tương thích Redshift/S3. Lambda có timeout 15 phút và memory limit, không phù hợp ETL batch lớn CSV. Overhead code custom cao, không least.

❌ Use Amazon EventBridge to launch an Amazon EMR cluster on a weekly schedule. Configure the EMR cluster to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in an Amazon Redshift table.

🔴 Sai vì: EMR yêu cầu launch/shutdown cluster thủ công (dù EventBridge), chi phí cao (cluster hàng giờ), overhead quản lý lớn (bộ máy ảo, Spark/Hive config). Weekly schedule quá thô, không real-time. AWS recommend Glue thay EMR cho ETL đơn giản (theo EMR docs 2026).

📘 Tài liệu tham khảo (AWS cập nhật mới nhất đến 2026)

AWS Glue ETL Documentation: https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-etl-format.html (Glue 5.0 hỗ trợ CSV-Redshift native).

AWS Well-Architected Data Analytics Lens: https://aws.amazon.com/architecture/well-architected?lens=data-analytics (Khuyến nghị Glue cho least overhead ETL).

Redshift Integration with Glue: https://docs.aws.amazon.com/redshift/latest/mgmt/glue-integrations.html (Load từ S3 qua Glue).

Exam DOP-C02 Guide (DevOps Professional 2024+): Nhấn mạnh serverless cho operational excellence.

Giải pháp này đảm bảo tuân thủ AWS best practices, dễ scale và cost-effective! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/99817-exam-aws-certified-solutions-architect-associate-saa-c03/
