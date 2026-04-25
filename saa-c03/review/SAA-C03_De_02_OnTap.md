# SAA-C03 - Bộ Ôn Tập Chi Tiết - Đề 02

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 02 tham khảo từ Đề Internet - devcloudly
- Blueprint tham chiếu: `w:\SAA-C03\AWS-Certified-Solutions-Architect-Associate_Exam-Guide.pdf`
- Ghi chú kỹ thuật: đề 2 -> đề 16 được dựng từ mốc reset số câu `65 -> 1` trong file nguồn.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon EC2 | 34 |
| Amazon S3 | 32 |
| Amazon Lambda | 20 |
| Amazon Relational Database Service | 11 |
| Auto Scaling Group | 10 |
| Amazon EBS | 8 |
| Amazon Virtual Private Cloud | 8 |
| Amazon KMS | 7 |
| Amazon API Gateway | 7 |
| Amazon SQS | 7 |
| Amazon CloudWatch | 7 |
| Amazon EFS | 6 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon S3 | 6 |
| Auto Scaling Group | 4 |
| Amazon SQS | 3 |
| Amazon API Gateway | 2 |
| Amazon RDS Proxy | 1 |
| Amazon EC2 | 1 |
| Amazon FSx | 1 |
| Amazon DynamoDB | 1 |
| Amazon Aurora | 1 |
| Amazon Elastic Kubernetes Service | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| sqs | 137 |
| kms | 104 |
| multi-az | 100 |
| dynamodb | 100 |
| serverless | 78 |
| api gateway | 62 |
| cloudfront | 54 |
| latency | 53 |
| direct connect | 51 |
| lifecycle | 45 |

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

### Amazon Relational Database Service
- RDS hợp cho relational workloads cần SQL, transactions, backup managed, patching managed.
- Luôn tách bạch: Multi-AZ cho HA/failover, read replica cho scale đọc, RDS Proxy cho connection pooling.
- Đề hay hỏi migration, encryption, snapshot, backup retention, read-heavy vs write-heavy.

### Auto Scaling Group
- ASG là công cụ scale EC2 theo policy/metrics/schedule, đồng thời tự thay instance unhealthy.
- Đi cùng ALB/NLB, launch template, mixed instances, spot/on-demand blend, warm pool.
- Nếu đề hỏi stateless web/app tier cần elasticity và self-healing, ASG là ứng viên rất mạnh.

### Amazon EBS
- Block storage cho EC2, phù hợp boot volume, database local disks, transactional workload.
- Cần nắm gp3 vs io1/io2 vs st1/sc1, snapshot, encryption, resize, Multi-Attach chỉ trong các ngữ cảnh rất đặc biệt.
- Khi đề nói IOPS, throughput block storage, boot disk, volume snapshot thì EBS là trung tâm.

### Amazon Virtual Private Cloud
- VPC là nền tảng networking: subnets, route tables, IGW, NAT, NACL, security groups, endpoints.
- Nắm rõ public/private subnet, SG vs NACL, route flows, VPC peering, Transit Gateway, PrivateLink, endpoints.
- SAA hỏi VPC rất nhiều vì hầu như bài nào có security, hybrid, private access hay cost network đều chạm VPC.

### Amazon KMS
- Service trung tâm cho encryption at rest. Đề rất hay chạm tới key rotation, key policy, CloudTrail audit, cross-account usage.
- AWS managed key ít vận hành hơn; customer managed key mạnh hơn về policy và sharing.
- Nhiều câu S3/EBS/RDS/FSx/DynamoDB encryption sẽ xoay quanh KMS.

## Pattern Key-Notes

### sqs
- SQS dùng để decouple producer-consumer, buffer traffic, retry, DLQ. FIFO khi cần ordering + deduplication.
- Standard queue ưu tiên throughput gần như không giới hạn; FIFO ưu tiên ordering exactly-once processing semantics ở mức thiết kế.
- Nếu đề hỏi strict ordering, idempotency, xử lý không mất message: hãy nhìn vào SQS FIFO.

### kms
- AWS managed key rẻ và đỡ vận hành hơn; customer managed key dùng khi cần policy chi tiết, share cross-account, audit/rotation control sâu hơn.
- KMS câu hỏi hay bẫy ở cross-account snapshot sharing, key rotation, CloudTrail audit, và khác biệt với CloudHSM.
- At-rest encryption của S3, EBS, RDS, DynamoDB, EFS, Redshift đều thường gắn với KMS.

### multi-az
- RDS Multi-AZ là cho HA/failover, không phải để scale read.
- Multi-AZ phù hợp khi đề nhấn mạnh availability, failover tự động, hạn chế downtime, đồng bộ dữ liệu giữa AZ.
- Nếu đề hỏi tăng throughput đọc, hãy nghĩ read replica trước; nếu đề hỏi chịu lỗi production DB, hãy nghĩ Multi-AZ.

### dynamodb
- DynamoDB hợp với key-value/document, low-latency ở quy mô lớn, serverless, auto scaling, global tables, TTL.
- Nếu đề yêu cầu schema linh hoạt, scale cực lớn, latency thấp nhất, không cần join/phức tạp SQL, DynamoDB thường thắng RDS.
- Nắm thêm DAX, partition key, sort key, GSI/LSI, on-demand vs provisioned.

### serverless
- Serverless thắng khi tải biến thiên, ít vận hành, cần scale nhanh, trả tiền theo mức dùng.
- Bộ đôi xuất hiện rất nhiều: API Gateway + Lambda + DynamoDB/SQS/SNS/EventBridge.
- Nhưng đừng ép serverless vào workload cần stateful long-running compute, custom kernel, hay network control sâu.

### api gateway
- API Gateway phù hợp cho REST/HTTP/WebSocket API managed, auth, throttling, stages, usage plan, integration với Lambda/ECS/ALB.
- Nếu cần queue/ordering/durable buffering thì API Gateway không tự giải quyết, phải ghép thêm SQS, SNS, EventBridge hoặc backend phù hợp.
- Bài toán public API managed với auth và rate limiting rất hay ra API Gateway.

## Cách Học Đề Này

- Đọc nhanh bảng domain focus để biết đề nghiêng về Secure, Resilient, Performance hay Cost.
- Học thuộc trước các service note và pattern note ở trên, sau đó mới làm lại từng câu.
- Với câu sai, đừng chỉ nhớ đáp án đúng; hãy nhớ vì sao các distractor sai theo tiêu chí exam như `least ops`, `least cost`, `HA`, `latency`, `immutability`.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Lambda, Auto Scaling Group, Amazon S3, Amazon Aurora, Amazon Route 53, Amazon EC2, Amazon Relational Database Service, Amazon RDS Proxy
- Đáp án tham khảo: **Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.**
- Takeaway nhanh: ➡️ Least effort: Chỉ cần config vài bước AWS-native (không code custom, không multi-Region phức tạp), phù hợp HA intra-Region chuẩn best practice. Nguồn tham khảo:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/database/improving-application-availability-with-amazon-rds-proxy/ | https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy.html | https://www.examtopics.com/discussions/amazon/view/85594-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data. Which solution will meet these requirements with the LEAST operational effort?

### Các lựa chọn
1. Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross-Region Replication.
2. Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.
3. Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.
4. Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc tăng tính sẵn sàng cao (High Availability - HA) cho một ứng dụng web kinh doanh quan trọng chạy trên Amazon EC2 phía sau Application Load Balancer (ALB), với Auto Scaling Group (ASG) quản lý EC2. Cơ sở dữ liệu là Amazon Aurora PostgreSQL đang triển khai ở một Availability Zone (AZ) duy nhất.

Yêu cầu chính:

HA với thời gian downtime tối thiểu (minimum downtime).

Mất dữ liệu tối thiểu (minimum loss of data).

Ít nỗ lực vận hành nhất (LEAST operational effort).

📘 Bối cảnh AWS cập nhật 2026: ALB tự động phân phối lưu lượng qua nhiều AZ. ASG hỗ trợ multi-AZ để scale và recover tự động. Aurora PostgreSQL hỗ trợ Multi-AZ deployment với failover tự động dưới 60 giây, RPO gần zero (dữ liệu đồng bộ). RDS Proxy (ra mắt 2020, cập nhật liên tục) giúp quản lý kết nối, hỗ trợ failover seamless cho Aurora mà không cần thay đổi code ứng dụng lớn.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.

Lý do chi tiết:

🛠️ Multi-AZ cho ASG: ASG trải rộng nhiều AZ trong cùng Region, ALB tự động cân bằng tải và ASG tự scale/launch instance mới nếu AZ fail → downtime gần zero cho compute layer.

🛠️ Aurora Multi-AZ: Chuyển DB từ single-AZ sang Multi-AZ, tạo standby replica ở AZ khác với failover tự động <60s, RPO=0 (dữ liệu đồng bộ async replication).

🛠️ RDS Proxy: Làm trung gian kết nối ứng dụng-DB, hỗ trợ connection pooling, automatic failover mà không mất kết nối (ứng dụng reconnect seamless), giảm operational effort vì config một lần qua console/CLI.

➡️ Least effort: Chỉ cần config vài bước AWS-native (không code custom, không multi-Region phức tạp), phù hợp HA intra-Region chuẩn best practice.

Nguồn tham khảo:

📘 AWS Auto Scaling Documentation (Multi-AZ support).

📘 Aurora Multi-AZ (failover <60s).

📘 RDS Proxy for Aurora (2026 updates: enhanced multiplexing).

❌ Phân tích tất cả các phương án (đúng/sai)

Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross-Region Replication.

❌ Sai: Multi-Region tăng latency cao (cross-Region traffic), Route 53 failover ~1-2 phút (không minimum downtime). Cross-Region Replication cho Aurora là async → data loss lớn (RPO cao). Operational effort cao (quản lý multi-Region, DNS TTL, data sync). Không least effort cho HA cơ bản.

Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.

✅ Đúng: Như giải thích trên, kết hợp hoàn hảo AWS-native features cho HA intra-Region, failover nhanh, zero data loss, config đơn giản nhất.

Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.

❌ Sai: ASG single-AZ → toàn bộ app fail nếu AZ outage. Snapshot hourly → data loss lên đến 1 giờ (RPO=60 phút), recover thủ công kéo dài downtime hàng giờ. Effort cao (manual recovery, scripting), vi phạm minimum downtime/data loss.

Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

❌ Sai: Multi-Region phức tạp + latency cao. App phải thay đổi code để write S3 → eventual consistency, Lambda delay xử lý → data loss/inconsistency. Effort cực cao (code refactor, Lambda management, error handling), không phù hợp business-critical app.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85594-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy.html

https://aws.amazon.com/blogs/database/improving-application-availability-with-amazon-rds-proxy/

## Câu 02

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon EBS, Amazon EFS, Amazon S3, Amazon S3 Glacier, Amazon EC2
- Đáp án tham khảo: **Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage**
- Takeaway nhanh: Amazon EC2 Instance Store ✅: Cung cấp hiệu suất I/O cao nhất (lên đến hàng triệu IOPS với NVMe SSD local, latency thấp nhất <1ms), phù hợp cho 10TB video processing tạm thời (ephemeral data). Không persistent nhưng lý tưởng cho workload high-perf như encoding/transcoding. Amazon S3 ✅: Độ bền 11 9's (99.999999999%), scale vô hạn đến petabytes, hoàn hảo cho 300TB media content thường xuyên truy cập.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#instance-store-volumesinstance | https://www.examtopics.com/discussions/amazon/view/85432-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A media company is evaluating the possibility of moving its systems to the AWS Cloud. The company needs at least 10 TB of storage with the maximum possible I/O performance for video processing, 300 TB of very durable storage for storing media content, and 900 TB of storage to meet requirements for archival media that is not in use anymore. Which set of services should a solutions architect recommend to meet these requirements?

### Các lựa chọn
1. Amazon EBS for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
2. Amazon EBS for maximum performance, Amazon EFS for durable data storage, and Amazon S3 Glacier for archival storage
3. Amazon EC2 instance store for maximum performance, Amazon EFS for durable data storage, and Amazon S3 for archival storage
4. Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi này thuộc chủ đề thiết kế lưu trữ trên AWS (AWS Storage Services) trong kỳ thi AWS Certified Solutions Architect hoặc DevOps Engineer Professional. Một công ty truyền thông đang xem xét di chuyển hệ thống lên AWS Cloud với các yêu cầu lưu trữ cụ thể:

Ít nhất 10 TB lưu trữ với hiệu suất I/O tối đa 🛠️ cho xử lý video (video processing) – cần tốc độ đọc/ghi cực cao, thường dành cho workload tạm thời, hiệu suất cao.

300 TB lưu trữ rất bền vững (very durable) 📈 cho nội dung media – ưu tiên độ bền dữ liệu cao (durability >99.999999999%), khả năng mở rộng lớn và chi phí hợp lý.

900 TB lưu trữ lưu trữ (archival) 🗄️ cho media không còn sử dụng – cần chi phí thấp, truy cập infrequent, hỗ trợ lưu trữ dài hạn.

Solutions Architect cần khuyến nghị bộ dịch vụ phù hợp nhất để đáp ứng chính xác các yêu cầu này, dựa trên đặc tính của từng dịch vụ AWS (cập nhật đến 2026: S3 Intelligent-Tiering, Glacier Flexible Retrieval, và Instance Store với NVMe SSD trên các instance như i4i, m6i).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage

Lý do chi tiết:

Amazon EC2 Instance Store ✅: Cung cấp hiệu suất I/O cao nhất (lên đến hàng triệu IOPS với NVMe SSD local, latency thấp nhất <1ms), phù hợp cho 10TB video processing tạm thời (ephemeral data). Không persistent nhưng lý tưởng cho workload high-perf như encoding/transcoding.

Amazon S3 ✅: Độ bền 11 9's (99.999999999%), scale vô hạn đến petabytes, hoàn hảo cho 300TB media content thường xuyên truy cập.

Amazon S3 Glacier ✅: Lưu trữ archival chi phí thấp (khoảng $0.004/GB/tháng), hỗ trợ 900TB media ít truy cập, với retrieval options như Flexible Retrieval (5-12 giờ).

Bộ này tối ưu chi phí, hiệu suất và độ bền theo Well-Architected Framework (Reliability & Performance Efficiency Pillars).

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên đặc tính dịch vụ AWS mới nhất (2026): Instance Store vượt trội EBS về I/O thuần túy, S3 là chuẩn cho durable object storage.

❌ [SAI] Amazon EBS for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage

Lý do sai: Amazon EBS (io2 Block Express) chỉ đạt tối đa ~256.000 IOPS và throughput 4.000 MB/s – không phải maximum I/O so với Instance Store (hàng triệu IOPS, local SSD). EBS phù hợp persistent block storage nhưng kém hơn cho video processing high-perf tạm thời. Phần còn lại (S3 + Glacier) đúng nhưng thiếu chính xác ở performance.

❌ [SAI] Amazon EBS for maximum performance, Amazon EFS for durable data storage, and Amazon S3 Glacier for archival storage

Lý do sai: EBS không phải maximum performance (như trên). Amazon EFS (NFS file storage) có độ bền 99.999999999% nhưng không "very durable" tối ưu cho 300TB media – EFS đắt hơn (~$0.30/GB/tháng), latency cao hơn S3 (object storage), và kém scale cho unstructured data như video. Glacier đúng cho archival nhưng tổng thể không khớp.

❌ [SAI] Amazon EC2 instance store for maximum performance, Amazon EFS for durable data storage, and Amazon S3 for archival storage

Lý do sai: Instance Store đúng cho maximum performance (10TB high I/O). Nhưng Amazon EFS không phù hợp durable storage cho 300TB media (file system chia sẻ, chi phí cao, không optimized cho media objects). Amazon S3 không dành cho archival – dùng S3 Standard đắt (~$0.023/GB/tháng), thiếu retrieval thấp chi phí như Glacier; nên dùng S3 Glacier/Deep Archive cho 900TB ít truy cập.

✅ [ĐÚNG] Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage

Lý do đúng: Hoàn hảo khớp yêu cầu – Instance Store cho perf đỉnh cao 🏆, S3 cho durable/hot data, Glacier cho cold archival. Tối ưu theo AWS Storage Lens và Cost Optimization.

📘 Tài liệu tham khảo (AWS chính thức, cập nhật 2026)

EC2 Instance Store: docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-store.html – Highest IOPS for temporary workloads.

Amazon S3 Durability: aws.amazon.com/s3/faqs/#durability – 11 9's durability.

S3 Glacier: aws.amazon.com/s3/storage-classes/glacier – Archival tiers (Flexible/Instant Retrieval).

EBS vs Instance Store: aws.amazon.com/ebs/performance – So sánh I/O metrics.

AWS Well-Architected Storage: aws.amazon.com/architecture/well-architected – Reliability pillar.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ thực tế hoặc diagram, hãy hỏi nhé.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85432-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#instance-store-volumesinstance

## Câu 03

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Glue, Amazon S3
- Takeaway nhanh: AWS Glue Job Bookmarks là tính năng chuyên dụng để theo dõi tiến độ xử lý dữ liệu từ nguồn như S3. Khi kích hoạt, Glue sẽ ghi nhớ vị trí cuối cùng đã xử lý (dựa trên key/path của file hoặc partition), giúp job chỉ xử lý dữ liệu mới thêm vào mà không reprocess dữ liệu cũ. Điều này hoàn hảo cho job chạy định kỳ với dữ liệu incremental như XML trong S3. Theo tài liệu AWS mới nhất (2024-2026), Job Bookmarks hỗ trợ các định dạng như XML và có các chế độ như job.bookmark (mặc định cho S3), đảm bảo hiệu suất tối ưu mà không cần thay đổi logic code. ✅ Giải pháp hiệu quả, an toàn và native!
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/glue/latest/dg/monitor-continuations.html | https://www.examtopics.com/discussions/amazon/view/85781-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an AWS Glue extract, transform, and load (ETL) job that runs every day at the same time. The job processes XML data that is in an Amazon S3 bucket. New data is added to the S3 bucket every day. A solutions architect notices that AWS Glue is processing all the data during each run. What should the solutions architect do to prevent AWS Glue from reprocessing old data?

### Các lựa chọn
1. Edit the job to use job bookmarks.
2. Edit the job to delete data after the data is processed.
3. Edit the job by setting the NumberOfWorkers field to 1.
4. Use a FindMatches machine learning (ML) transform.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một công ty đang sử dụng AWS Glue ETL job chạy hàng ngày vào cùng một thời điểm để xử lý dữ liệu XML lưu trữ trong Amazon S3 bucket. Mỗi ngày, dữ liệu mới được thêm vào bucket, nhưng vấn đề là AWS Glue đang xử lý lại toàn bộ dữ liệu cũ (reprocessing) trong mỗi lần chạy, dẫn đến lãng phí tài nguyên, thời gian và chi phí.

Mục tiêu: Solutions Architect cần tìm cách ngăn chặn việc xử lý lại dữ liệu cũ, chỉ xử lý dữ liệu mới thôi. Đây là vấn đề phổ biến với các job Glue xử lý dữ liệu incremental từ S3, nơi Glue mặc định quét toàn bộ dataset trừ khi cấu hình cơ chế theo dõi tiến độ.

✅ Đáp án đúng: Edit the job to use job bookmarks

Lý do lựa chọn:

AWS Glue Job Bookmarks là tính năng chuyên dụng để theo dõi tiến độ xử lý dữ liệu từ nguồn như S3. Khi kích hoạt, Glue sẽ ghi nhớ vị trí cuối cùng đã xử lý (dựa trên key/path của file hoặc partition), giúp job chỉ xử lý dữ liệu mới thêm vào mà không reprocess dữ liệu cũ. Điều này hoàn hảo cho job chạy định kỳ với dữ liệu incremental như XML trong S3.

Theo tài liệu AWS mới nhất (2024-2026), Job Bookmarks hỗ trợ các định dạng như XML và có các chế độ như job.bookmark (mặc định cho S3), đảm bảo hiệu suất tối ưu mà không cần thay đổi logic code. ✅ Giải pháp hiệu quả, an toàn và native!

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Tôi đánh dấu ✅ cho đúng và ❌ cho sai, kèm giải thích rõ ràng:

Edit the job to use job bookmarks.

✅ Đúng. Như đã giải thích ở trên, Job Bookmarks là cơ chế built-in của AWS Glue để tránh reprocessing bằng cách lưu trạng thái xử lý (source và target). Với S3 XML data, nó tự động detect file mới dựa trên key hoặc partition. Không ảnh hưởng đến dữ liệu gốc, dễ enable qua Glue console/CLI ( --job-bookmark-option job-bookmark-enable). Hoàn hảo cho job daily! 🛠️

Edit the job to delete data after the data is processed.

❌ Sai. Việc xóa dữ liệu sau xử lý sẽ mất dữ liệu gốc vĩnh viễn, vi phạm nguyên tắc lưu trữ dữ liệu bền vững trong S3 (immutable storage). Không giải quyết vấn đề reprocessing mà còn tạo rủi ro data loss, không phù hợp với best practice AWS (S3 lifecycle cho retention). Rất nguy hiểm cho production! 🚫

Edit the job by setting the NumberOfWorkers field to 1.

❌ Sai. Tham số NumberOfWorkers chỉ kiểm soát số lượng worker nodes (G.1X/G.2X/DPU) để scale job, không liên quan đến việc filter dữ liệu cũ/mới. Nó có thể làm job chậm hơn (single worker), nhưng vẫn reprocess toàn bộ data, lãng phí hơn. Không giải quyết root cause! ⚠️

Use a FindMatches machine learning (ML) transform.

❌ Sai. FindMatches là ML transform trong Glue để entity resolution (tìm match dữ liệu duplicate), không dùng để theo dõi tiến độ xử lý incremental hay tránh reprocessing S3 data. Nó dành cho data cleaning/ML tasks, không liên quan đến vấn đề này. Sử dụng sai sẽ phức tạp hóa job vô ích! 🤖

📘 Tài liệu tham khảo (cập nhật AWS 2024-2026)

AWS Glue Developer Guide - Job Bookmarks: docs.aws.amazon.com/glue/latest/dg/monitor-continuations.html – Chi tiết cách enable và troubleshoot.

AWS Glue Best Practices: docs.aws.amazon.com/glue/latest/dg/optimize-performance-etl.html – Khuyến nghị dùng bookmarks cho incremental ETL.

AWS Well-Architected Framework - Reliability Pillar: Nhấn mạnh incremental processing để tối ưu chi phí/data durability.

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm ví dụ code Glue script, cứ hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85781-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/glue/latest/dg/monitor-continuations.html

## Câu 04

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Elastic Container Service, Amazon ElastiCache, Amazon CloudFront, Amazon Aurora, Amazon Fargate, Amazon EC2
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86658-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is running a multi-tier web application on premises. The web application is containerized and runs on a number of Linux hosts connected to a PostgreSQL database that contains user records. The operational overhead of maintaining the infrastructure and capacity planning is limiting the company's growth. A solutions architect must improve the application's infrastructure. Which combination of actions should the solutions architect take to accomplish this? (Choose two.)

### Các lựa chọn
1. Migrate the PostgreSQL database to Amazon Aurora.
2. Migrate the web application to be hosted on Amazon EC2 instances.
3. Set up an Amazon CloudFront distribution for the web application content.
4. Set up Amazon ElastiCache between the web application and the PostgreSQL database.
5. Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi trắc nghiệm AWS

📖 Nội dung câu hỏi:

Câu hỏi mô tả một công ty đang chạy ứng dụng web đa tầng (multi-tier web application) trên cơ sở hạ tầng on-premises. Ứng dụng này đã được container hóa (containerized) và chạy trên nhiều host Linux, kết nối với cơ sở dữ liệu PostgreSQL chứa hồ sơ người dùng. Vấn đề chính là gánh nặng vận hành (operational overhead) khi duy trì hạ tầng và lập kế hoạch dung lượng (capacity planning) đang hạn chế sự phát triển của công ty. Kiến trúc sư giải pháp (solutions architect) cần cải thiện hạ tầng ứng dụng.

Yêu cầu chọn TWO hành động kết hợp để đạt mục tiêu: giảm thiểu việc quản lý thủ công hạ tầng (như patch OS, scale server) và tự động hóa dung lượng (auto-scaling).

Đây là câu hỏi kiểu chọn hai đáp án đúng (Choose two), tập trung vào dịch chuyển (migration) sang các dịch vụ managed/serverless của AWS để loại bỏ overhead on-premises. Kiến thức dựa trên AWS cập nhật đến 2026: ECS/Fargate hỗ trợ container orchestration serverless, Aurora là DB managed PostgreSQL-compatible với auto-scaling đa AZ.

✅ Đáp án đúng (Chọn TWO):

Migrate the PostgreSQL database to Amazon Aurora.

Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).

🛠️ Lý do chọn đáp án đúng:

Hai hành động này trực tiếp giải quyết vấn đề bằng cách di chuyển toàn bộ stack sang managed/serverless services, loại bỏ nhu cầu quản lý host Linux và DB thủ công:

Amazon Aurora: Dịch vụ DB PostgreSQL-compatible fully managed, tự động scale storage/compute, multi-AZ high availability, backup tự động – giảm 100% overhead DB on-premises.

AWS Fargate + Amazon ECS: Fargate là serverless compute cho containers (không quản lý EC2), ECS orchestrate tự động scale theo demand, phù hợp app containerized – giải quyết capacity planning và maintenance host Linux.

Kết hợp chúng tạo kiến trúc serverless-native, scalable, cost-optimized (pay-per-use).

🔍 Phân tích TẤT CẢ các phương án (Đúng/Sai)

✅ Migrate the PostgreSQL database to Amazon Aurora.

Đúng: Aurora là dịch vụ RDS managed PostgreSQL-compatible (Aurora PostgreSQL), hỗ trợ auto-scaling read replicas, serverless v2 (từ 2022, cập nhật 2026 vẫn dẫn đầu), zero-ETL integration. Giảm overhead bằng cách AWS quản lý patching, backup, failover – trực tiếp thay thế PostgreSQL on-premises.

❌ Migrate the web application to be hosted on Amazon EC2 instances.

Sai: EC2 yêu cầu quản lý instances thủ công (AMI, patching, Auto Scaling Groups), không giảm operational overhead so với Linux hosts on-premises. Chỉ là "cloudify" chứ không serverless, vẫn cần capacity planning – trái ngược mục tiêu.

❌ Set up an Amazon CloudFront distribution for the web application content.

Sai: CloudFront là CDN cho static/dynamic content, cải thiện latency/global distribution nhưng không giải quyết infra overhead (vẫn giữ host Linux và DB on-premises). Không liên quan đến maintenance/capacity planning của app servers hay DB.

❌ Set up Amazon ElastiCache between the web application and the PostgreSQL database.

Sai: ElastiCache (Redis/Memcached managed) thêm caching layer để giảm load DB, cải thiện performance nhưng không loại bỏ overhead hạ tầng chính (vẫn phải quản lý hosts và PostgreSQL). Chỉ là optimization phụ, không phải migration infra.

✅ Migrate the web application to be hosted on AWS Fargate with Amazon ECS.

Đúng: Fargate (serverless compute engine từ 2017, cập nhật 2026 với ECS Anywhere/EKS hỗ trợ) + ECS (orchestrator) cho phép chạy containers mà không quản lý underlying servers. Tự động scale theo CPU/memory metrics, tích hợp ALB – lý tưởng cho containerized multi-tier app, giảm capacity planning 100%.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

Aurora: Amazon Aurora User Guide – Serverless v2 auto-pause/resume.

Fargate + ECS: AWS Fargate Developer Guide – Zero infrastructure management.

Exam Topic DOP-C02: AWS Certified DevOps Engineer Professional – Migration strategies, serverless architectures (Well-Architected Framework pillar: Operational Excellence).

💡 Lời khuyên DevOps: Sử dụng AWS Migration Hub hoặc DMS cho migration thực tế, kết hợp CloudWatch/Container Insights để monitor post-migration! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86658-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 05

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon S3
- Takeaway nhanh: Khi kích hoạt Requester Pays trên bucket, người yêu cầu (requester - ở đây là công ty marketing châu Âu) sẽ chịu toàn bộ chi phí requests (GET, PUT) và data transfer out (từ US sang EU). Công ty khảo sát (bucket owner) KHÔNG trả phí transfer, chỉ trả storage và requests của chính mình. Điều này giảm tối đa chi phí cho họ với dữ liệu lớn 3TB+. Dễ triển khai: Chỉ cần enable qua Console/CLI/API, không copy dữ liệu, không cần thay đổi bucket khác.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonS3/latest/userguide/RequesterPaysBuckets.html | https://www.examtopics.com/discussions/amazon/view/85738-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A survey company has gathered data for several years from areas in the United States. The company hosts the data in an Amazon S3 bucket that is 3 TB in size and growing. The company has started to share the data with a European marketing firm that has S3 buckets. The company wants to ensure that its data transfer costs remain as low as possible. Which solution will meet these requirements?

### Các lựa chọn
1. Configure the Requester Pays feature on the company's S3 bucket.
2. Configure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing firm's S3 buckets.
3. Configure cross-account access for the marketing firm so that the marketing firm has access to the company's S3 bucket.
4. Configure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing firm's S3 buckets.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty khảo sát Mỹ đã thu thập dữ liệu trong nhiều năm, lưu trữ trong Amazon S3 bucket dung lượng 3 TB và đang tăng dần. Bây giờ, họ muốn chia sẻ dữ liệu này với một công ty marketing châu Âu (có các S3 bucket riêng). Yêu cầu chính là giữ chi phí chuyển dữ liệu (data transfer costs) ở mức thấp nhất có thể cho công ty khảo sát.

🔍 Vấn đề cốt lõi:

Dữ liệu lớn (3 TB+), chia sẻ quốc tế (từ Mỹ sang châu Âu, tức khác Region: US vs EU).

Chi phí S3 bao gồm: requests, storage, và data transfer out (khi dữ liệu rời bucket ra internet hoặc Region khác).

Mặc định, bucket owner (công ty khảo sát) chịu chi phí data transfer out khi người khác truy cập (GET objects).

Giải pháp cần tối ưu chi phí cho owner, không ảnh hưởng đến việc chia sẻ dữ liệu.

📈 Bối cảnh AWS cập nhật 2026: S3 vẫn giữ cơ chế pricing data transfer theo Region (intra-Region miễn phí, inter-Region/outbound tính phí). Không có thay đổi lớn về Requester Pays hoặc CRR từ 2023-2026.

✅ Đáp án đúng: Configure the Requester Pays feature on the company's S3 bucket.

Lý do lựa chọn:

Khi kích hoạt Requester Pays trên bucket, người yêu cầu (requester - ở đây là công ty marketing châu Âu) sẽ chịu toàn bộ chi phí requests (GET, PUT) và data transfer out (từ US sang EU).

Công ty khảo sát (bucket owner) KHÔNG trả phí transfer, chỉ trả storage và requests của chính mình. Điều này giảm tối đa chi phí cho họ với dữ liệu lớn 3TB+.

Dễ triển khai: Chỉ cần enable qua Console/CLI/API, không copy dữ liệu, không cần thay đổi bucket khác.

Hoàn hảo cho chia sẻ mà không mất kiểm soát dữ liệu gốc. 🛡️

📋 Giải thích tất cả các phương án (đúng/sai)

✅ Configure the Requester Pays feature on the company's S3 bucket.

Đúng vì như đã giải thích: Chuyển gánh nặng chi phí transfer sang requester (marketing firm), owner chỉ trả storage. Tiết kiệm lớn cho data out inter-Region (US-EU). Không cần replicate/sync dữ liệu. 💰

❌ Configure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing firm's S3 buckets.

Sai vì CRR sao chép dữ liệu tự động sang bucket khác (cross-account, cross-Region), nhưng owner vẫn trả chi phí replication (data transfer vào bucket đích) + storage kép. Marketing firm trả storage của họ, nhưng tổng chi phí cho owner tăng cao (replication ~0.02$/GB inter-Region + ongoing sync). Không tối ưu cho "low as possible". 🚫

❌ Configure cross-account access for the marketing firm so that the marketing firm has access to the company's S3 bucket.

Sai vì chỉ cấp quyền truy cập (qua IAM roles/policies, bucket policy), marketing firm vẫn GET data trực tiếp từ bucket gốc. Owner vẫn chịu toàn bộ data transfer out (cao cho 3TB+ sang EU). Không giải quyết gốc rễ chi phí transfer. 🔓

❌ Configure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing firm's S3 buckets.

Sai vì Intelligent-Tiering chỉ tối ưu storage costs (tự động di chuyển giữa tiers dựa trên access), không ảnh hưởng transfer. "Sync" (qua S3 Batch/Replication/Sync CLI) tạo chi phí replication/transfer kép tương tự CRR, owner trả outbound + sync ongoing. Không giảm transfer khi marketing truy cập. 📊

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

Requester Pays: Amazon S3 Requester Pays - Xác nhận requester trả transfer out.

S3 Pricing: Amazon S3 Pricing - Data transfer out inter-Region ~0.02-0.09$/GB (US-EU).

CRR & Transfer: S3 Replication - Owner pays replication costs.

Best Practices: AWS Well-Architected Framework - Cost Optimization Pillar (S3 sharing với Requester Pays).

Giải pháp này DevOps-friendly, dễ automate qua CDK/Terraform! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85738-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonS3/latest/userguide/RequesterPaysBuckets.html

## Câu 06

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2, Amazon Relational Database Service, Amazon Virtual Private Cloud, NAT gateways
- Takeaway nhanh: Đặt EC2 vào private subnets (qua ASG) đảm bảo không expose public. RDS Multi-AZ trong private subnets cung cấp HA (failover tự động giữa AZs) và bảo mật. Kết hợp hoàn hảo với NAT outbound cho payment processing. Two public subnets (one per AZ) cho ALB (public-facing, HA) và NAT Gateways (one per AZ, resilient outbound).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85221-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs its two-tier ecommerce website on AWS. The web tier consists of a load balancer that sends traffic to Amazon EC2 instances. The database tier uses an Amazon RDS DB instance. The EC2 instances and the RDS DB instance should not be exposed to the public internet. The EC2 instances require internet access to complete payment processing of orders through a third-party web service. The application must be highly available. Which combination of configuration options will meet these requirements? (Choose two.)

### Các lựa chọn
1. Use an Auto Scaling group to launch the EC2 instances in private subnets. Deploy an RDS Multi-AZ DB instance in private subnets.
2. Configure a VPC with two private subnets and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the private subnets.
3. Use an Auto Scaling group to launch the EC2 instances in public subnets across two Availability Zones. Deploy an RDS Multi-AZ DB instance in private subnets.
4. Configure a VPC with one public subnet, one private subnet, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnet. D. Configure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng website thương mại điện tử (ecommerce) hai tầng (two-tier) chạy trên AWS, với yêu cầu bảo mật cao và tính sẵn sàng cao (highly available). Cụ thể:

Web tier: Sử dụng load balancer (Application Load Balancer - ALB) để phân phối traffic đến các Amazon EC2 instances.

Database tier: Sử dụng Amazon RDS DB instance.

Yêu cầu bảo mật chính 📍:

EC2 instances và RDS DB không được expose trực tiếp ra public internet (không có public IP, tránh rủi ro tấn công).

Yêu cầu kết nối outbound 🌐: EC2 cần truy cập internet (outbound) để xử lý thanh toán qua third-party web service (ví dụ: gọi API payment gateway).

Yêu cầu HA ⚡: Toàn bộ ứng dụng phải có tính sẵn sàng cao, thường nghĩa là triển khai across multiple Availability Zones (ít nhất 2 AZs) để tránh single point of failure.

Mục tiêu: Chọn TWO configuration options kết hợp để đáp ứng tất cả yêu cầu trên.

Giải pháp lý tưởng theo best practice AWS (cập nhật đến 2026):

VPC với public subnets (cho ALB và NAT Gateway) và private subnets (cho EC2 & RDS).

NAT Gateway (one per AZ) trong public subnets để EC2 outbound internet mà không cần public IP.

ALB trong public subnets (across AZs) để nhận traffic public inbound.

Auto Scaling Group (ASG) cho EC2 trong private subnets (across AZs).

RDS Multi-AZ trong private subnets để HA cho DB. 🛠️ Lưu ý kiến trúc: Không dùng Internet Gateway (IGW) trực tiếp cho private resources; dùng NAT cho outbound. ALB phải public-facing.

✅ Đáp án đúng và lý do lựa chọn

Các đáp án đúng: A và D (D là "Configure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.")

Lý do chọn A:

Đặt EC2 vào private subnets (qua ASG) đảm bảo không expose public.

RDS Multi-AZ trong private subnets cung cấp HA (failover tự động giữa AZs) và bảo mật.

Kết hợp hoàn hảo với NAT outbound cho payment processing.

Lý do chọn D:

Two public subnets (one per AZ) cho ALB (public-facing, HA) và NAT Gateways (one per AZ, resilient outbound).

Two private subnets (one per AZ) cho EC2/RDS.

Đảm bảo HA across 2 AZs, traffic inbound qua ALB public → EC2 private → RDS private, outbound qua NAT.

Đây là best practice VPC cho web app 3-tier (public/private), cập nhật AWS 2026 (không thay đổi cơ bản).

Kết hợp A + D meet 100% yêu cầu: Bảo mật, outbound, HA. Các option khác thiếu hoặc sai một phần.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng phương án một cách chi tiết, giữ nguyên text gốc tiếng Anh. Tôi đánh dấu ✅ đúng/sai ❌, giải thích lý do bằng tiếng Việt rõ ràng dựa trên kiến thức AWS VPC/ALB/RDS mới nhất.

Use an Auto Scaling group to launch the EC2 instances in private subnets. Deploy an RDS Multi-AZ DB instance in private subnets.

✅ Đúng.

🧩 EC2 trong private subnets tránh public exposure hoàn toàn. ASG đảm bảo scale HA across AZs. RDS Multi-AZ (standby replica ở AZ khác) cung cấp failover <60s, đặt private để bảo mật. Hoàn hảo cho web tier private + DB HA, chỉ cần NAT outbound bổ sung.

Configure a VPC with two private subnets and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the private subnets.

❌ Sai.

🛠️ VPC chỉ có private subnets (không public) → ALB private không nhận traffic internet (inbound fail). NAT cần public subnet + IGW để hoạt động đúng. Không meet "web tier nhận traffic public", thiếu HA inbound.

Use an Auto Scaling group to launch the EC2 instances in public subnets across two Availability Zones. Deploy an RDS Multi-AZ DB instance in private subnets.

❌ Sai.

📍 EC2 trong public subnets → expose trực tiếp internet (public IP/ELB), vi phạm yêu cầu bảo mật. RDS private OK nhưng EC2 public không an toàn cho payment processing (rủi ro hack).

Configure a VPC with one public subnet, one private subnet, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnet.

❌ Sai (dù gần đúng nhưng không HA đầy đủ).

🧩 "One public subnet" (singular, thường 1 AZ) + "one private" không hỗ trợ ALB span multiple AZs đúng cách → thiếu HA (ALB cần ≥2 subnets different AZs cho cross-zone LB). Two NAT không thể đặt hết trong 1 public subnet (NAT per AZ/subnet). Không resilient nếu AZ fail.

D. Configure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.

✅ Đúng.

🌐 Standard VPC layout cho HA: 2 public subnets (AZ1/AZ2) cho ALB (internet-facing) & NAT (outbound resilient). 2 private (AZ1/AZ2) cho EC2/RDS. Traffic flow: Internet → ALB public → EC2 private → RDS private; EC2 outbound → NAT → internet. Meet bảo mật + HA + payment.

📘 Tài liệu tham khảo (AWS docs cập nhật 2026)

VPC với NAT & Private Subnets: AWS VPC User Guide - Scenario 2: VPC with Public and Private Subnets (NAT) – Best practice cho web app.

ALB Deployment: Elastic Load Balancing - ALB in Public Subnets – Yêu cầu multiple AZs subnets cho HA.

RDS Multi-AZ: Amazon RDS Multi-AZ Deployments – Private chỉ, failover tự động.

DevOps Best Practices: AWS Well-Architected Framework (Reliability Pillar, 2024 update) – Khuyến nghị NAT Gateway per AZ cho HA outbound.

Exam Reference: DOP-C02 (DevOps Pro) sample questions về VPC security/HA.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần sơ đồ kiến trúc, hãy hỏi thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85221-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 07

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon DynamoDB, Amazon EBS, Amazon S3, Amazon S3 Glacier, DR RPO and RTO
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/PointInTimeRecovery.html | https://www.examtopics.com/discussions/amazon/view/85603-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour. What should the solutions architect recommend to meet these requirements?

### Các lựa chọn
1. Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.
2. Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.
3. Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.
4. Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế giải pháp backup và phục hồi dữ liệu cho ứng dụng mua sắm sử dụng Amazon DynamoDB lưu trữ thông tin khách hàng. Tình huống cụ thể là data corruption (dữ liệu bị hỏng), và yêu cầu phải đáp ứng:

RPO (Recovery Point Objective) = 15 phút: Mức mất dữ liệu tối đa chỉ 15 phút (nghĩa là có thể phục hồi dữ liệu gần với thời điểm corruption nhất).

RTO (Recovery Time Objective) = 1 giờ: Thời gian phục hồi hệ thống tối đa 1 giờ.

🛠️ Solutions Architect cần đề xuất giải pháp tối ưu sử dụng tính năng của AWS DynamoDB để đạt RPO/RTO này. DynamoDB là dịch vụ NoSQL quản lý hoàn toàn (managed), nên các giải pháp phải tận dụng các tính năng built-in như PITR (Point-in-Time Recovery), global tables, hoặc export/import.

📘 Kiến thức cập nhật AWS 2026: Theo tài liệu AWS mới nhất (DynamoDB Developer Guide), PITR hỗ trợ continuous backups với granularity 5 giây, retention lên đến 35 ngày, RPO gần 0 giây, và RTO thường dưới 1 giờ tùy kích thước table (có thể nhanh hơn với Parallel Scan).

✅ Đáp án đúng và lý do lựa chọn

Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.

🧩 Lý do đúng:

PITR (Point-in-Time Recovery) là tính năng built-in của DynamoDB (enable on-demand), cung cấp continuous backups tự động mỗi 5 giây, cho phép restore table mới đến bất kỳ điểm thời gian nào trong 35 ngày qua (retention mặc định 35 ngày, có thể tùy chỉnh).

Đáp ứng RPO 15 phút: Granularity 5 giây << 15 phút, mất dữ liệu tối đa chỉ vài giây.

Đáp ứng RTO 1 giờ: Restore tạo table mới nhanh chóng (thời gian phụ thuộc kích thước dữ liệu, thường <1 giờ; AWS tối ưu hóa với continuous backup).

Đây là giải pháp chuẩn và hiệu quả nhất cho data corruption, không cần export/import thủ công.

Dẫn nguồn:

AWS DynamoDB PITR Docs (cập nhật 2025-2026, xác nhận RPO/RTO thấp).

❌ Giải thích tất cả các phương án (đúng/sai)

[SAI] Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region. 🛠️ Giải thích sai: Global Tables dùng cho multi-region replication (active-active replication async), giúp disaster recovery (DR) khi region outage, nhưng KHÔNG hỗ trợ PITR hoặc rollback corruption. Nếu corruption xảy ra đồng bộ, replicate sang region khác vẫn bị hỏng. RPO phụ thuộc latency replication (~giây đến phút, nhưng không granular PITR), và không meet chính xác yêu cầu corruption recovery. Failover chỉ switch traffic, không restore point-in-time.

[ĐÚNG] Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time. ✅ Giải thích đúng (như phần trên): Hoàn hảo cho RPO 15p (granularity 5s) và RTO 1h, restore tạo table mới sạch sẽ trước corruption.

[SAI] Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB. 🛠️ Giải thích sai: Export DynamoDB sang S3 (qua Export to S3 feature) chỉ hàng ngày (không continuous), nên RPO = 24 giờ >> 15 phút. S3 Glacier có retrieval time từ vài giờ đến ngày (Standard: 3-5h, Expedited: phút nhưng đắt), KHÔNG meet RTO 1h. Import thủ công từ S3 vào DynamoDB mất thời gian dài, không tự động.

[SAI] Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot. 🛠️ Giải thích sai: DynamoDB là dịch vụ serverless managed, KHÔNG sử dụng EBS volumes (không có underlying EC2/EBS). Không thể snapshot EBS cho DynamoDB table. Đây là nhầm lẫn cơ bản; EBS dùng cho EC2/RDS, không áp dụng. Nếu cố, sẽ fail hoàn toàn.

🛡️ Kết luận: PITR là lựa chọn best practice cho DynamoDB backup/recovery theo AWS Well-Architected Framework (Reliability Pillar). Enable PITR chỉ tốn phí storage (~$0.20/GB/tháng), rất economical! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85603-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/PointInTimeRecovery.html

## Câu 08

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon CloudTrail, Amazon S3
- Takeaway nhanh: Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects. S3 Object Lock + Versioning: Bắt buộc để kích hoạt WORM, ngăn object bị ghi đè hoặc xóa. Legal Hold: Áp dụng "giữ pháp lý" lên object, giữ chúng immutable vô thời hạn (không có retention period cố định), chỉ xóa được khi remove legal hold. Hoàn hảo cho "nonspecific amount of time until the company decides".
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonS3/latest/userguide/batch-ops-legal-hold.htmlThe | https://www.examtopics.com/discussions/amazon/view/85634-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecific amount of time until the company decides to modify the objects. Only specific users in the company's AWS account can have the ability 10 delete the objects. What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.
2. Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket’s default retention mode for new objects.
3. Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notification, restore the modified objects from any backup versions that the company has.
4. Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi yêu cầu một giải pháp lưu trữ dữ liệu trên Amazon S3 với các ràng buộc nghiêm ngặt:

Dữ liệu không thể bị thay đổi (immutable - không thể ghi đè hoặc sửa).

Các object mới upload phải giữ nguyên vô thời hạn (nonspecific amount of time) cho đến khi công ty quyết định thay đổi.

Chỉ specific users trong AWS account mới có quyền xóa (delete) các object này.

🛠️ Yêu cầu cốt lõi: Sử dụng tính năng S3 Object Lock để áp dụng mô hình WORM (Write Once, Read Many), kết hợp versioning (bắt buộc cho Object Lock), và kiểm soát quyền xóa chặt chẽ qua IAM. Giải pháp phải ngăn chặn thay đổi ngay từ đầu, không chỉ phát hiện sau, và phù hợp với thời gian giữ không xác định (không phải thời gian cố định như 100 năm).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng:

Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

Lý do chọn đáp án này (dựa trên AWS best practices 2024-2026):

S3 Object Lock + Versioning: Bắt buộc để kích hoạt WORM, ngăn object bị ghi đè hoặc xóa.

Legal Hold: Áp dụng "giữ pháp lý" lên object, giữ chúng immutable vô thời hạn (không có retention period cố định), chỉ xóa được khi remove legal hold. Hoàn hảo cho "nonspecific amount of time until the company decides".

IAM permission s3:PutObjectLegalHold: Chỉ cấp cho specific users, cho phép họ remove legal hold rồi mới xóa object. Đảm bảo kiểm soát chặt chẽ.

✅ Ưu điểm: Ngăn thay đổi 100%, linh hoạt thời gian, tuân thủ quy định (như SEC Rule 17a-4). Không cần retention period dài hạn cố định.

📋 Phân tích tất cả các phương án

Phương án A (❌ Sai):

Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.

Giải thích sai: S3 Glacier vault là dịch vụ lưu trữ lạnh dài hạn riêng biệt (không phải S3 bucket), dùng cho Glacier Flexible Retrieval hoặc Deep Archive. Vault lock chỉ áp dụng cho Glacier, không lưu trữ object S3 trực tiếp. Không đáp ứng "store data in Amazon S3" và không hỗ trợ upload/access nhanh cho object mới. ❌ Không phù hợp với yêu cầu S3.

Phương án B (❌ Sai):

Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket’s default retention mode for new objects.

Giải thích sai: S3 Object Lock đúng hướng, nhưng retention period 100 years là thời gian cố định (specific), không linh hoạt "nonspecific until company decides". Governance mode cho phép admin/root override retention dễ dàng (không ngăn chặn tuyệt đối). Không hỗ trợ xóa chỉ cho specific users mà không remove retention trước. ❌ Không khớp "nonspecific time" và kiểm soát xóa.

Phương án C (❌ Sai):

Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notification, restore the modified objects from any backup versions that the company has.

Giải thích sai: Chỉ phát hiện và khôi phục sau khi thay đổi (reactive), không ngăn chặn thay đổi từ đầu (prevent). CloudTrail ghi log API, nhưng không làm object immutable. Phụ thuộc backup (không bắt buộc), và ai cũng có thể modify nếu có quyền. ❌ Không đáp ứng "prevent the data from being changed".

📘 Tài liệu tham khảo (AWS cập nhật 2024-2026)

S3 Object Lock & Legal Hold: Amazon S3 Object Lock - Hướng dẫn chi tiết về legal hold (indefinite retention) và versioning yêu cầu.

IAM Permissions cho Object Lock: S3 Object Lock IAM Actions - Xác nhận s3:PutObjectLegalHold để quản lý hold/xóa.

So sánh Governance vs Compliance/Legal Hold: S3 Retention Modes.

Best Practices DevOps: AWS Well-Architected Framework - Reliability Pillar (S3 Immutability).

🛠️ Lời khuyên DevOps: Test Object Lock trên bucket dev trước khi prod. Sử dụng S3 Bucket Policies + IAM Conditions để fine-tune quyền specific users! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85634-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonS3/latest/userguide/batch-ops-legal-hold.htmlThe

## Câu 09

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon KMS, Amazon Secrets Manager, Amazon EBS, Amazon S3, Amazon EC2
- Đáp án tham khảo: **Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.**
- Takeaway nhanh: AWS KMS customer managed key (CMK): Cho phép mã hóa/giải mã near real-time qua API calls (Encrypt/Decrypt APIs), highly secure với HSM-backed keys, AWS quản lý toàn bộ lifecycle (rotation tự động tùy chọn). EC2 IAM role: Gán quyền sử dụng KMS key (kms:Encrypt, kms:Decrypt) mà không cần hardcode credentials, tuân thủ least privilege. Amazon S3: Lưu trữ encrypted data với highly available (multi-AZ, 11 9's durability), serverless, không cần quản lý volume hay instance. Ứng dụng trên EC2 có thể gọi KMS để encrypt trước khi upload S3.
- Nguồn tham khảo trong block: https://aws.amazon.com/ebs/features/EBS | https://aws.amazon.com/s3/faqs/ | https://docs.aws.amazon.com/kms/latest/developerguide/ | https://www.examtopics.com/discussions/amazon/view/85186-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company's containerized application runs on an Amazon EC2 instance. The application needs to download security certificates before it can communicate with other business applications. The company wants a highly secure solution to encrypt and decrypt the certificates in near real time. The solution also needs to store data in highly available storage after the data is encrypted. Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Create AWS Secrets Manager secrets for encrypted certificates. Manually update the certificates as needed. Control access to the data by using fine-grained IAM access.
2. Create an AWS Lambda function that uses the Python cryptography library to receive and perform encryption operations. Store the function in an Amazon S3 bucket.
3. Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.
4. Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon Elastic Block Store (Amazon EBS) volumes.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng containerized đang chạy trên Amazon EC2 instance. Ứng dụng này cần tải xuống (download) các security certificates trước khi có thể giao tiếp (communicate) với các ứng dụng kinh doanh khác. Yêu cầu chính là một giải pháp highly secure để encrypt và decrypt certificates gần như thời gian thực (near real time), đồng thời lưu trữ dữ liệu đã mã hóa vào highly available storage sau khi mã hóa. Giải pháp phải có operational overhead thấp nhất (LEAST operational overhead).

🔑 Các yếu tố cốt lõi cần đáp ứng:

Bảo mật cao: Sử dụng dịch vụ AWS managed để quản lý khóa mã hóa (keys) và mã hóa/giải mã.

Near real-time: Hỗ trợ API calls nhanh chóng cho encrypt/decrypt.

Highly available storage: Lưu trữ dữ liệu mã hóa phải có tính sẵn sàng cao, multi-AZ, durable (không phụ thuộc vào một instance duy nhất).

Least overhead: Tối ưu hóa, sử dụng dịch vụ serverless/managed, tránh tự quản lý code hoặc manual intervention.

📘 Tài liệu tham khảo:

AWS KMS Developer Guide (cập nhật 2025): https://docs.aws.amazon.com/kms/latest/developerguide/

Amazon S3 Durability & Availability (99.999999999% durability): https://aws.amazon.com/s3/faqs/

AWS Well-Architected Framework - Security Pillar (2026 edition).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.

🛠️ Lý do chi tiết:

AWS KMS customer managed key (CMK): Cho phép mã hóa/giải mã near real-time qua API calls (Encrypt/Decrypt APIs), highly secure với HSM-backed keys, AWS quản lý toàn bộ lifecycle (rotation tự động tùy chọn).

EC2 IAM role: Gán quyền sử dụng KMS key (kms:Encrypt, kms:Decrypt) mà không cần hardcode credentials, tuân thủ least privilege.

Amazon S3: Lưu trữ encrypted data với highly available (multi-AZ, 11 9's durability), serverless, không cần quản lý volume hay instance. Ứng dụng trên EC2 có thể gọi KMS để encrypt trước khi upload S3.

Least overhead: Toàn bộ là managed services, không code custom, không manual update, scale tự động. Phù hợp DevOps best practices.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng phương án một cách chi tiết, đánh dấu ✅ đúng hoặc ❌ sai, với lý do dựa trên yêu cầu câu hỏi:

❌ [SAI] Create AWS Secrets Manager secrets for encrypted certificates. Manually update the certificates as needed. Control access to the data by using fine-grained IAM access.

Phương án này sử dụng AWS Secrets Manager để lưu secrets đã mã hóa, nhưng yêu cầu manually update certificates gây overhead cao (không tự động). Secrets Manager chủ yếu retrieve secrets đã decrypt sẵn, không hỗ trợ encrypt/decrypt arbitrary data near real-time như certificates tải về. Không lưu encrypted data vào HA storage riêng (Secrets Manager là managed secrets store, không phải general storage). Overhead cao do manual intervention, vi phạm "least overhead".

❌ [SAI] Create an AWS Lambda function that uses the Python cryptography library to receive and perform encryption operations. Store the function in an Amazon S3 bucket.

Phương án dùng Lambda với thư viện cryptography Python để mã hóa, nhưng tự implement crypto lib không secure bằng KMS (dễ lỗi key management, compliance issues). Lambda code được upload như ZIP vào S3, nhưng "store function in S3" không chính xác (Lambda là service riêng). Overhead cao: Phát triển/maintain code custom, xử lý errors, scaling, không near real-time như KMS API. Không đề cập HA storage cho encrypted data.

✅ [ĐÚNG] Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.

Như đã giải thích ở trên: Hoàn hảo khớp tất cả yêu cầu với KMS cho secure near real-time encrypt/decrypt, IAM role cho access, S3 cho HA storage. Zero custom code, fully managed.

❌ [SAI] Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon Elastic Block Store (Amazon EBS) volumes.

KMS và EC2 role tốt, nhưng Amazon EBS không phải highly available storage: EBS là block storage gắn với EC2 instance (single AZ, nếu instance fail thì mất data trừ khi snapshot). Phải quản lý volume attach/detach/snapshot thủ công, overhead cao hơn S3 (object storage multi-AZ). Không phù hợp cho certificates cần HA.

🔥 Kết luận: Giải pháp đúng tận dụng AWS managed services tối ưu cho DevOps, đảm bảo security, availability và low ops theo AWS best practices 2026! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85186-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/ebs/features/EBS

## Câu 10

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Systems Manager, Amazon KMS, Amazon Secrets Manager, Amazon S3, Amazon Relational Database Service
- Đáp án tham khảo: **Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to allow the web servers to access AWS Secrets Manager.**
- Takeaway nhanh: 🛡️ AWS Secrets Manager là dịch vụ chuyên dụng để lưu trữ, quản lý và xoay vòng tự động credentials (bao gồm username/password cho RDS MySQL). Nó tích hợp trực tiếp với RDS, cho phép rotation mà không downtime (sử dụng Lambda function để thay đổi password DB và cập nhật secret). 📱 Web servers (thường chạy trên EC2 hoặc ECS) có thể Retrieve secrets động qua AWS SDK/CLI với IAM role policy (ví dụ: secretsmanager:GetSecretValue), tránh lưu hard-code.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html | https://www.examtopics.com/discussions/amazon/view/85753-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently. Which solution meets these requirements?

### Các lựa chọn
1. Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.
2. Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.
3. Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.
4. Store the database user credentials in files encrypted with AWS Key Management Service (AWS KMS) on the web server file system. The web server should be able to decrypt the files and access the database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong môi trường AWS: Một công ty có nhiều web servers cần truy cập thường xuyên vào một Amazon RDS MySQL Multi-AZ DB instance (cơ sở dữ liệu MySQL với tính sẵn sàng cao qua Multi-AZ deployment). Yêu cầu chính là tìm phương pháp an toàn để web servers kết nối DB, đồng thời đáp ứng yêu cầu bảo mật: xoay vòng (rotate) credentials (tài khoản người dùng DB) thường xuyên.

🔑 Các yếu tố cốt lõi cần giải quyết:

Bảo mật kết nối: Tránh lưu credentials trực tiếp trên server (rủi ro lộ thông tin).

Xoay vòng credentials: Tự động thay đổi mật khẩu định kỳ mà không gián đoạn dịch vụ.

Quy mô: Áp dụng cho nhiều web servers, sử dụng IAM để kiểm soát truy cập.

Tích hợp RDS MySQL: Giải pháp phải hỗ trợ RDS, đặc biệt Multi-AZ để đảm bảo HA.

Đây là chủ đề quản lý bí mật (secrets management) trong DevOps trên AWS, nhấn mạnh vào zero-trust security và least privilege principle theo best practices AWS (cập nhật đến 2026, với Secrets Manager hỗ trợ rotation tự động cho RDS MySQL 8.0+ và các phiên bản trước).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to allow the web servers to access AWS Secrets Manager.

Lý do chi tiết:

🛡️ AWS Secrets Manager là dịch vụ chuyên dụng để lưu trữ, quản lý và xoay vòng tự động credentials (bao gồm username/password cho RDS MySQL). Nó tích hợp trực tiếp với RDS, cho phép rotation mà không downtime (sử dụng Lambda function để thay đổi password DB và cập nhật secret).

📱 Web servers (thường chạy trên EC2 hoặc ECS) có thể Retrieve secrets động qua AWS SDK/CLI với IAM role policy (ví dụ: secretsmanager:GetSecretValue), tránh lưu hard-code.

🔄 Rotation thường xuyên: Cấu hình lịch rotation (hàng ngày/tuần), hỗ trợ Multi-AZ (RDS primary/standby tự sync).

✅ Hoàn hảo match yêu cầu: An toàn cao (encryption at rest/transit với KMS), audit trail qua CloudTrail, và scalable cho nhiều servers.

📋 Phân tích tất cả các phương án

✅ Phương án ĐÚNG:

Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.

Giải thích: Như trên, đây là best practice AWS (AWS Well-Architected Framework - Security Pillar). Secrets Manager hỗ trợ RDS rotation native từ 2018 và cập nhật 2026 với cải tiến caching (TTL cho GetSecretValue). Sử dụng IAM policy như {"Effect": "Allow", "Action": "secretsmanager:GetSecretValue", "Resource": "*"} gắn vào EC2 role.

❌ Phương án SAI:

Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.

Giải thích: AWS Systems Manager OpsCenter dùng để quản lý operational issues (như alarms, incidents từ CloudWatch), KHÔNG phải lưu trữ secrets. OpsCenter không hỗ trợ rotation credentials hay retrieve động cho DB connect. Sử dụng sai sẽ vi phạm security (không encryption chuyên secrets) và không scale cho web servers.

❌ Phương án SAI:

Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.

Giải thích: S3 bucket (dù server-side encryption với KMS) chỉ lưu tĩnh object, KHÔNG hỗ trợ rotation tự động. Phải manual update file credentials → rủi ro downtime khi rotate, lộ secrets nếu bucket policy lỏng lẻo. Không phải best practice cho dynamic secrets (AWS khuyến cáo dùng Secrets Manager thay vì S3 cho credentials).

❌ Phương án SAI:

Store the database user credentials in files encrypted with AWS Key Management Service (AWS KMS) on the web server file system. The web server should be able to decrypt the files and access the database.

Giải thích: Lưu file trên file system EC2 (dù encrypt KMS) vẫn rủi ro cao (server compromise → lộ file). KHÔNG rotate tự động (phải script thủ công, phức tạp với Multi-AZ). Vi phạm principle "secrets không lưu local", dễ lỗi human và không audit tốt (CloudTrail không track file local).

📘 Tài liệu tham khảo (cập nhật AWS 2026)

AWS Secrets Manager - Rotating RDS credentials: docs.aws.amazon.com/secretsmanager/latest/userguide/rotating-secrets-tutorial.html (Hướng dẫn chi tiết rotation MySQL Multi-AZ).

RDS Integration: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-secrets-manager.html (Tích hợp native từ RDS 2018+, hỗ trợ MySQL 5.7/8.0+).

Well-Architected Framework - Security: aws.amazon.com/architecture/well-architected/security-pillar (Khuyến cáo Secrets Manager cho DB secrets).

Exam Prep DOP-C02: AWS Official Practice Exams (2023-2026 updates nhấn mạnh Secrets Manager > Parameter Store/S3 cho rotation).

🛠️ Lời khuyên DevOps: Implement với SDK (boto3 Python: client.get_secret_value), cache secret 4-20 phút để optimize performance!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85753-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html

## Câu 11

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EC2, Amazon Virtual Private Cloud, Security groups
- Takeaway nhanh: Application instances chỉ allow SSH từ private IP của bastion (cùng VPC, nội bộ), tránh expose ra internet. Điều này tuân thủ zero trust model và AWS best practices cho bastion (EC2 Instance Connect hoặc SSM Session Manager làm thay thế hiện đại hơn, nhưng câu hỏi tập trung Security Groups). Kết hợp hai bước này tạo chain truy cập an toàn: On-prem → Bastion (public IP) → Apps (private IP).
- Nguồn tham khảo trong block: https://aws.amazon.com/solutions/implementations/linux-bastion/Good | https://www.examtopics.com/discussions/amazon/view/85613-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently launched Linux-based application instances on Amazon EC2 in a private subnet and launched a Linux-based bastion host on an Amazon EC2 instance in a public subnet of a VPC. A solutions architect needs to connect from the on-premises network, through the company's internet connection, to the bastion host, and to the application servers. The solutions architect must make sure that the security groups of all the EC2 instances will allow that access. Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Replace the current security group of the bastion host with one that only allows inbound access from the application instances.
2. Replace the current security group of the bastion host with one that only allows inbound access from the internal IP range for the company.
3. Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.
4. Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.
5. Replace the current security group of the application instances with one that allows inbound SSH access from only the public IP address of the bastion host.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS VPC:

Một công ty đã triển khai các instance ứng dụng Linux trên Amazon EC2 nằm trong private subnet (không tiếp xúc trực tiếp với internet), và một bastion host Linux trên EC2 nằm trong public subnet. Solutions Architect cần thiết lập kết nối từ mạng on-premises (qua kết nối internet của công ty) đến bastion host trước, sau đó từ bastion host đến các application servers.

Yêu cầu chính: Cấu hình Security Groups của tất cả EC2 instances để chỉ cho phép truy cập hợp lệ, đảm bảo an toàn (least privilege principle).

Kết nối flow: On-premises → Internet → Bastion (public) → Application (private).

Giao thức: SSH (port 22) cho Linux.

Đây là câu hỏi chọn TWO bước kết hợp để đáp ứng yêu cầu, dựa trên best practices AWS về bastion host và security groups (không dùng public IP cho kết nối nội bộ VPC).

📘 Kiến thức cập nhật 2026: Security Groups vẫn hoạt động như stateful firewall (cho phép return traffic tự động), hỗ trợ IPv4/IPv6, và tích hợp chặt chẽ với VPC Flow Logs/Network ACLs (theo AWS VPC User Guide mới nhất).

✅ Đáp án đúng (Chọn TWO)

Hai lựa chọn đúng là:

Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.

Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.

Lý do lựa chọn:

🛠️ Bastion host cần cho phép inbound SSH từ external IP range của công ty (on-premises IPs qua internet) để kết nối an toàn từ xa.

Application instances chỉ allow SSH từ private IP của bastion (cùng VPC, nội bộ), tránh expose ra internet. Điều này tuân thủ zero trust model và AWS best practices cho bastion (EC2 Instance Connect hoặc SSM Session Manager làm thay thế hiện đại hơn, nhưng câu hỏi tập trung Security Groups). Kết hợp hai bước này tạo chain truy cập an toàn: On-prem → Bastion (public IP) → Apps (private IP).

🔍 Phân tích chi tiết TẤT CẢ các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá ✅ (Đúng) hoặc ❌ (Sai), kèm giải thích đầy đủ bằng tiếng Việt:

❌ [SAI] Replace the current security group of the bastion host with one that only allows inbound access from the application instances.

Lý do sai: Bastion host cần kết nối TỪ on-premises (external), không phải từ application instances (private subnet). Allow từ apps sẽ chặn kết nối ban đầu từ internet, làm bastion không thể truy cập được. Security Groups là stateful nhưng inbound rule phải chính xác nguồn gốc.

❌ [SAI] Replace the current security group of the bastion host with one that only allows inbound access from the internal IP range for the company.

Lý do sai: Kết nối đến bastion qua internet từ on-premises, nên nguồn là external/public IPs (không phải internal IPs nội bộ công ty). Internal IP range chỉ dùng cho kết nối VPC-to-VPC hoặc VPN/Direct Connect, không áp dụng ở đây (tránh mở rộng lỗ hổng).

✅ [ĐÚNG] Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.

Lý do đúng: Đây là bước chính xác cho bastion ở public subnet. Rule inbound SSH (TCP 22) chỉ từ external IP range của công ty (ví dụ: CIDR on-premises như 203.0.113.0/24), đảm bảo chỉ admin công ty truy cập được qua internet. Giảm rủi ro tấn công brute-force từ anywhere.

✅ [ĐÚNG] Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.

Lý do đúng: Application ở private subnet chỉ cần SSH từ private IP của bastion (ví dụ: 10.0.1.10/32 trong VPC). Không dùng public IP bastion vì kết nối nội bộ VPC qua private networking (ENI), an toàn hơn và tránh NAT/public exposure.

❌ [SAI] Replace the current security group of the application instances with one that allows inbound SSH access from only the public IP address of the bastion host.

Lý do sai: Bastion có public IP nhưng khi SSH đến apps (cùng VPC/private subnet), nó sử dụng private IP (không route qua public IP). Allow public IP sẽ không match traffic thực tế (traffic đi nội bộ), dẫn đến kết nối thất bại. Đây là lỗi phổ biến newbie commit.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS VPC User Guide: Security groups for your EC2 instances – Chi tiết inbound/outbound rules và bastion examples.

AWS Best Practices: Bastion hosts and SSH handling – Khuyến nghị dùng private IP cho internal jumps.

EC2 User Guide: Connect to instances in private subnets – Session Manager thay thế bastion truyền thống.

Exam Tips (ACloudGuru/AWS Training): DOP-C02 blueprint phần "Implementation Secure Applications" (Security Groups 20% trọng số).

Hy vọng phân tích này giúp bạn ôn thi DevOps Professional hiệu quả! 🚀 Nếu cần ví dụ CloudFormation code, hỏi thêm nhé.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85613-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/solutions/implementations/linux-bastion/Good

## Câu 12

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Auto Scaling Group, Amazon CloudFront, Amazon GuardDuty, Amazon Shield, Amazon EC2, Amazon Virtual Private Cloud, Network ACLs, Amazon Shield Advanced
- Takeaway nhanh: Configure the website to use Amazon CloudFront for both static and dynamic content.
- Nguồn tham khảo trong block: https://aws.amazon.com/shield/ | https://www.examtopics.com/discussions/amazon/view/85342-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website. Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)

### Các lựa chọn
1. Use AWS Shield Advanced to stop the DDoS attack.
2. Configure Amazon GuardDuty to automatically block the attackers.
3. Configure the website to use Amazon CloudFront for both static and dynamic content.
4. Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.
5. Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi yêu cầu một Solutions Architect thiết kế hạ tầng highly available (có tính sẵn sàng cao) cho một website chạy trên Windows web servers đặt trên Amazon EC2 instances. Thách thức chính là phải chống lại các cuộc tấn công DDoS quy mô lớn (phát sinh từ hàng ngàn IP addresses), đồng thời không chấp nhận downtime (nghĩa là website phải luôn hoạt động liên tục).

🔑 Yêu cầu chọn TWO actions (hai hành động) phù hợp nhất để bảo vệ website. Đây là tình huống thực tế trong AWS, nơi DDoS attack có thể làm quá tải EC2 trực tiếp, nên cần các dịch vụ phân tán traffic và bảo vệ chuyên dụng. Kiến thức dựa trên AWS Well-Architected Framework (2023-2026 updates), nhấn mạnh Reliability Pillar và Security Pillar, với Shield Advanced được nâng cấp hỗ trợ AI-driven mitigation cho volumetric attacks lớn hơn.

✅ Đáp án đúng (Chọn TWO)

Hai lựa chọn đúng là:

Use AWS Shield Advanced to stop the DDoS attack.

Lý do: AWS Shield Advanced là dịch vụ chuyên chống DDoS Layer 3/4/7 quy mô lớn (volumetric, protocol, application), tự động mitigate từ hàng ngàn IP mà không cần can thiệp thủ công. Nó tích hợp với EC2, cung cấp DDoS Response Team (DRT) 24/7, cost protection (hoàn tiền nếu attack gây chi phí tăng), và visibility qua dashboards. Phù hợp hoàn hảo cho no-downtime.

Configure the website to use Amazon CloudFront for both static and dynamic content.

Lý do: CloudFront là CDN toàn cầu, phân tán traffic đến edge locations (hàng trăm PoP), hấp thụ DDoS trước khi chạm EC2 origin. Hỗ trợ dynamic content qua origin shielding và Lambda@Edge. Kết hợp Shield Standard (miễn phí) hoặc Advanced, giúp scale globally mà không downtime. Đây là best practice cho web apps trên EC2.

📋 Giải thích tất cả các phương án (Đúng/Sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi giải thích dựa trên tính khả thi, scalability cho DDoS lớn, và no-downtime requirement (cập nhật AWS 2026: Shield Advanced nay có ML-based auto-mitigation nhanh hơn 50%).

✅ Use AWS Shield Advanced to stop the DDoS attack.

Giải thích đúng: Đây là lựa chọn hàng đầu cho DDoS lớn từ thousands IPs. Shield Advanced cung cấp proactive engagement, inline mitigation, và tích hợp trực tiếp với EC2/ELB. Không chỉ block mà còn monitor real-time qua Shield metrics in CloudWatch. Hoàn hảo cho highly available infra mà không gây downtime (mitigate at edge). 🛡️

❌ Configure Amazon GuardDuty to automatically block the attackers.

Giải thích sai: GuardDuty là dịch vụ threat detection (phát hiện unusual behavior qua ML trên logs VPC Flow, CloudTrail), không phải công cụ block tự động. Nó chỉ generate findings/alerts, cần tích hợp Lambda/Firewall Manager để block – quá chậm và không scale cho DDoS volumetric lớn (hàng ngàn IPs). Không phù hợp no-downtime vì detection chỉ sau attack. 👎

✅ Configure the website to use Amazon CloudFront for both static and dynamic content.

Giải thích đúng: CloudFront offload traffic đến edge, giảm tải EC2 trực tiếp. Với AWS Shield integration, tự động scrub DDoS Layer 7. Hỗ trợ dynamic content (API Gateway, ALB origin), cache static assets, và origin failover cho HA. Best practice từ AWS DDoS Whitepaper: giảm attack surface 99%. 🌐

❌ Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.

Giải thích sai: Lambda có thể parse logs để add IPs vào NACLs, nhưng không scale cho thousands IPs (NACL limits: 20 rules/entry mỗi direction, đánh số sequential). Quá trình reactive, gây latency/block legit traffic (false positives), và downtime khi update ACLs (propagation ~60s). Không phải giải pháp enterprise cho DDoS lớn. ⚠️

❌ Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.

Giải thích sai: Spot Instances rẻ nhưng không reliable (có thể interrupt bất kỳ lúc nào), vi phạm highly available + no-downtime. Scaling policy dựa CPU không chống DDoS (attack volumetric không phải CPU spike nhất quán), và Spot dễ bị terminate trong high demand. Chỉ dùng cho fault-tolerant workloads, không phải web critical. 🚫

📘 Tài liệu tham khảo (AWS Official - Cập nhật 2026)

AWS Shield Advanced: docs.aws.amazon.com/waf/latest/developerguide/ddos-overview.html & aws.amazon.com/shield/ – Chi tiết mitigation cho large-scale DDoS.

CloudFront DDoS Protection: docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/ddos.html.

AWS DDoS Resilience Whitepaper: d1.awsstatic.com/whitepapers/aws-ddos-resilience.pdf.

Exam Prep: AWS Certified Solutions Architect Pro DOP-C02 guide (2024-2026 blueprints).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm case studies, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85342-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/shield/

## Câu 13

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon EC2, Amazon Virtual Private Cloud
- Takeaway nhanh: Kết hợp này tạo ra luồng truy cập private hoàn toàn trong AWS network (không qua internet), sử dụng VPC Gateway Endpoint (miễn phí, hiệu suất cao) để route traffic S3 trực tiếp từ VPC đến S3 service. Bucket policy bổ sung layer bảo mật thứ hai bằng cách chỉ cho phép truy cập từ VPC cụ thể (dựa trên aws:SourceVpce condition), ngăn chặn truy cập từ bên ngoài. 🛡️ Ưu điểm: Tuân thủ AWS Well-Architected Framework (Security Pillar), cập nhật đến 2026 với hỗ trợ S3 Gateway Endpoint policy version mới nhất (bao gồm integration với VPC Endpoints cho S3 Object Lambda nếu cần).
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/s3-private-connection-no-authentication/ | https://www.examtopics.com/discussions/amazon/view/85903-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is storing sensitive user information in an Amazon S3 bucket. The company wants to provide secure access to this bucket from the application tier running on Amazon EC2 instances inside a VPC. Which combination of steps should a solutions architect take to accomplish this? (Choose two.)

### Các lựa chọn
1. Configure a VPC gateway endpoint for Amazon S3 within the VPC.
2. Create a bucket policy to make the objects in the S3 bucket public.
3. Create a bucket policy that limits access to only the application tier running in the VPC.
4. Create an IAM user with an S3 access policy and copy the IAM credentials to the EC2 instance.
5. Create a NAT instance and have the EC2 instances use the NAT instance to access the S3 bucket.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc cung cấp truy cập an toàn (secure access) đến một Amazon S3 bucket chứa thông tin người dùng nhạy cảm từ application tier chạy trên Amazon EC2 instances nằm trong VPC.

✅ Mục tiêu chính: Đảm bảo EC2 instances có thể truy cập S3 mà không đi qua internet công khai, giảm rủi ro lộ dữ liệu nhạy cảm, đồng thời tuân thủ nguyên tắc least privilege (quyền hạn tối thiểu).

🛠️ Yêu cầu chọn TWO steps kết hợp: Đây là câu hỏi kiểu "Choose two" điển hình trong kỳ thi AWS, nhấn mạnh vào các giải pháp VPC-native để tối ưu hóa bảo mật và hiệu suất (không dùng NAT Gateway hoặc public routing).

✅ Đáp án đúng (Chọn TWO)

Hai phương án đúng là:

Configure a VPC gateway endpoint for Amazon S3 within the VPC.

Create a bucket policy that limits access to only the application tier running in the VPC.

Lý do lựa chọn 📈:

Kết hợp này tạo ra luồng truy cập private hoàn toàn trong AWS network (không qua internet), sử dụng VPC Gateway Endpoint (miễn phí, hiệu suất cao) để route traffic S3 trực tiếp từ VPC đến S3 service.

Bucket policy bổ sung layer bảo mật thứ hai bằng cách chỉ cho phép truy cập từ VPC cụ thể (dựa trên aws:SourceVpce condition), ngăn chặn truy cập từ bên ngoài.

🛡️ Ưu điểm: Tuân thủ AWS Well-Architected Framework (Security Pillar), cập nhật đến 2026 với hỗ trợ S3 Gateway Endpoint policy version mới nhất (bao gồm integration với VPC Endpoints cho S3 Object Lambda nếu cần).

🔍 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá ✅ (đúng) hoặc ❌ (sai), kèm giải thích lý do dựa trên best practices AWS mới nhất.

Configure a VPC gateway endpoint for Amazon S3 within the VPC. ✅

Giải thích: Đây là bước cốt lõi để enable private connectivity từ VPC đến S3. Gateway Endpoint (không phải Interface Endpoint) dành riêng cho S3/DynamoDB, không tốn phí data transfer, tự động scale và hỗ trợ prefix lists (com.amazonaws.region.s3). Trong phiên bản AWS 2026, nó tích hợp tốt với VPC Flow Logs để monitor traffic private. Không có endpoint thì traffic sẽ route public qua IGW/NAT.

Create a bucket policy to make the objects in the S3 bucket public. ❌

Giải thích: Phương án này vi phạm hoàn toàn yêu cầu bảo mật, vì làm objects publicly accessible (ai cũng đọc được qua internet). S3 bucket policy với Principal: "*" sẽ expose dữ liệu nhạy cảm, trái ngược Security Pillar. AWS khuyến cáo Block Public Access mặc định từ 2023+.

Create a bucket policy that limits access to only the application tier running in the VPC. ✅

Giải thích: Bucket policy sử dụng condition keys như aws:SourceVpce hoặc aws:SourceVpc để restrict chỉ từ VPC endpoint cụ thể. Ví dụ policy JSON: {"Condition": {"StringEquals": {"aws:SourceVpce": "vpce-xxx"}}}. Kết hợp với endpoint ở trên tạo defense-in-depth, cập nhật 2026 hỗ trợ IAM Access Analyzer để audit policy tự động.

Create an IAM user with an S3 access policy and copy the IAM credentials to the EC2 instance. ❌

Giải thích: Cách này không an toàn và không scale, vì copy credentials (Access Key/Secret) dễ bị leak (vi phạm IAM best practices). Thay vào đó, dùng IAM Roles for EC2 (attach policy trực tiếp, temporary credentials via metadata service). Hardcode creds trên instance là anti-pattern từ AWS 2020+.

Create a NAT instance and have the EC2 instances use the NAT instance to access the S3 bucket. ❌

Giải thích: NAT Instance/Gateway dùng để outbound internet access (public route), nhưng với S3 nên dùng Gateway Endpoint để private routing (tiết kiệm chi phí, latency thấp hơn). NAT vẫn đi qua public internet endpoint của S3, không đáp ứng "secure access" và kém hiệu quả hơn endpoint (AWS deprecated NAT Instance từ 2023, ưu tiên NAT Gateway).

📘 Tài liệu tham khảo

AWS Documentation (2026 update): VPC Endpoints for Amazon S3 & S3 Bucket Policies with VPC Endpoints.

AWS Well-Architected Framework: Security Pillar - Pillar 1.1 (PrivateLink & Endpoints).

Exam Prep: AWS Certified Solutions Architect/DevOps Engineer Official Practice (Question DOP-C02 ~ S3 VPC Access).

🧑‍💻 Tips thi chứng chỉ: Luôn ưu tiên Gateway Endpoint + Policy cho S3 in VPC; kiểm tra via AWS Console > VPC > Endpoints.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85903-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/premiumsupport/knowledge-center/s3-private-connection-no-authentication/

## Câu 14

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon DataSync, Amazon Direct Connect, Amazon S3, Amazon Database Migration Service
- Đáp án tham khảo: **AWS DataSync over AWS Direct Connect**
- Takeaway nhanh: AWS DataSync là dịch vụ chuyên chuyển file dữ liệu lớn từ on-premises (hỗ trợ NFS, SMB, HDFS, SAN như trong câu hỏi) sang S3 một cách tự động, incremental sync, hỗ trợ 10 TB/ngày dễ dàng với agent on-prem và task scheduling. Nó có retry tự động, checksum verification, đảm bảo integrity & reliability cao. Over AWS Direct Connect: Sử dụng kết nối riêng tư (private) từ on-prem đến AWS VPC (qua Direct Connect Gateway hoặc VPC Endpoint), không qua public internet → bảo mật tối đa (encrypted, no public exposure), độ tin cậy cao nhất (99.99% SLA, low latency <10ms, bandwidth lên đến 100 Gbps), phù hợp sensitive data và near-real-time.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85801-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company receives 10 TB of instrumentation data each day from several machines located at a single factory. The data consists of JSON files stored on a storage area network (SAN) in an on-premises data center located within the factory. The company wants to send this data to Amazon S3 where it can be accessed by several additional systems that provide critical near-real-time analytics. A secure transfer is important because the data is considered sensitive. Which solution offers the MOST reliable data transfer?

### Các lựa chọn
1. AWS DataSync over public internet
2. AWS DataSync over AWS Direct Connect
3. AWS Database Migration Service (AWS DMS) over public internet
4. AWS Database Migration Service (AWS DMS) over AWS Direct Connect

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong môi trường AWS DevOps: Một công ty nhận 10 TB dữ liệu instrumentation (dữ liệu đo lường từ máy móc) mỗi ngày từ các máy tại nhà máy duy nhất. Dữ liệu ở dạng file JSON lưu trên SAN (Storage Area Network) tại data center on-premises trong nhà máy. Mục tiêu là chuyển dữ liệu này đến Amazon S3 để các hệ thống khác truy cập, phục vụ analytics gần real-time (near-real-time). Yêu cầu quan trọng là chuyển dữ liệu an toàn (secure) vì dữ liệu nhạy cảm (sensitive).

Câu hỏi tập trung vào giải pháp chuyển dữ liệu đáng tin cậy NHẤT (MOST reliable), nghĩa là ưu tiên tính ổn định, bảo mật cao, băng thông lớn, độ trễ thấp cho khối lượng dữ liệu khổng lồ (10 TB/ngày ~ 115 MB/giây nếu liên tục), tránh public internet để giảm rủi ro và tăng độ tin cậy.

🛠️ Yếu tố chính cần xem xét (dựa trên best practices AWS 2026):

Loại dữ liệu: File JSON (không phải database), nên cần tool file transfer/sync, không phải DB migration.

Bảo mật: Sensitive data → ưu tiên private connection như AWS Direct Connect (dedicated, encrypted).

Độ tin cậy: High throughput, retry mechanism, monitoring tốt.

Near-real-time: Cần transfer nhanh, ổn định để analytics kịp thời.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: AWS DataSync over AWS Direct Connect

🧩 Lý do chi tiết:

AWS DataSync là dịch vụ chuyên chuyển file dữ liệu lớn từ on-premises (hỗ trợ NFS, SMB, HDFS, SAN như trong câu hỏi) sang S3 một cách tự động, incremental sync, hỗ trợ 10 TB/ngày dễ dàng với agent on-prem và task scheduling. Nó có retry tự động, checksum verification, đảm bảo integrity & reliability cao.

Over AWS Direct Connect: Sử dụng kết nối riêng tư (private) từ on-prem đến AWS VPC (qua Direct Connect Gateway hoặc VPC Endpoint), không qua public internet → bảo mật tối đa (encrypted, no public exposure), độ tin cậy cao nhất (99.99% SLA, low latency <10ms, bandwidth lên đến 100 Gbps), phù hợp sensitive data và near-real-time.

Đây là giải pháp AWS khuyến nghị cho large-scale file transfer on-prem to S3 (cập nhật 2026: DataSync hỗ trợ S3 Intelligent-Tiering tự động).

📋 Giải thích tất cả các phương án (Đúng/Sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá dựa trên phù hợp với dữ liệu file JSON (không phải DB), bảo mật, độ tin cậy và throughput.

❌ [SAI] AWS DataSync over public internet

Phân tích sai: AWS DataSync phù hợp cho file transfer (JSON trên SAN → S3), nhưng over public internet sử dụng Public VPC Endpoint → không an toàn cho sensitive data (dễ bị intercept, DDoS), độ tin cậy thấp hơn (phụ thuộc internet biến động, throttling). Không phải "MOST reliable" vì thiếu dedicated bandwidth.

✅ [ĐÚNG] AWS DataSync over AWS Direct Connect

Phân tích đúng: Như đã giải thích ở trên – kết hợp hoàn hảo: DataSync xử lý file sync hiệu quả + Direct Connect đảm bảo private, reliable transfer với high throughput (hỗ trợ 10 TB/ngày mà không gián đoạn). AWS best practice cho hybrid file migration.

❌ [SAI] AWS Database Migration Service (AWS DMS) over public internet

Phân tích sai: AWS DMS chuyên migrate database (CDC, full load từ RDBMS/NoSQL), KHÔNG hỗ trợ file JSON trên SAN (không phải DB source). Over public internet còn kém bảo mật và low reliability cho file transfer lớn. DMS không optimize cho S3 file sync.

❌ [SAI] AWS Database Migration Service (AWS DMS) over AWS Direct Connect

Phân tích sai: Dù Direct Connect tốt cho reliability, nhưng DMS vẫn SAI vì không dành cho file transfer (JSON files trên SAN không phải database). DMS chỉ migrate schema/data từ DB engines, không sync file hệ thống tệp. Sử dụng sẽ fail task hoặc inefficient.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS DataSync Documentation: docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html – Hỗ trợ on-prem SAN to S3, Direct Connect integration.

AWS Direct Connect: docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html – Private connectivity cho reliability.

AWS DMS vs DataSync: aws.amazon.com/blogs/database/choosing-the-right-aws-service-for-your-data-transfer-needs/ – DMS cho DB, DataSync cho files.

AWS Well-Architected Framework (Reliability Pillar): Khuyến nghị DataSync + Direct Connect cho hybrid large-scale transfer.

Exam Prep DOP-C02: Topic "Hybrid Architectures" & "Data Transfer Services".

🛠️ Lời khuyên DevOps: Implement DataSync với CloudWatch monitoring, IAM roles least-privilege, và VPC Endpoints để tối ưu! Nếu cần scale, kết hợp AWS Snowball cho initial bulk transfer.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85801-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 15

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Glue, Amazon Kinesis, Amazon Lambda, Amazon API Gateway, Amazon S3, Amazon EC2, Amazon Kinesis Data Firehose
- Takeaway nhanh: Configure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.
- Nguồn tham khảo trong block: https://aws.amazon.com/glue/I | https://www.examtopics.com/discussions/amazon/view/85740-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company needs to configure a real-time data ingestion architecture for its application. The company needs an API, a process that transforms data as the data is streamed, and a storage solution for the data. Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Deploy an Amazon EC2 instance to host an API that sends data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.
2. Deploy an Amazon EC2 instance to host an API that sends data to AWS Glue. Stop source/destination checking on the EC2 instance. Use AWS Glue to transform the data and to send the data to Amazon S3.
3. Configure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.
4. Configure an Amazon API Gateway API to send data to AWS Glue. Use AWS Lambda functions to transform the data. Use AWS Glue to send the data to Amazon S3.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi

Câu hỏi yêu cầu thiết kế một kiến trúc ingestion dữ liệu thời gian thực (real-time) cho ứng dụng của công ty, bao gồm ba thành phần chính:

API để nhận dữ liệu từ ứng dụng.

Quá trình biến đổi (transform) dữ liệu trong lúc dữ liệu đang được stream (không phải batch).

Giải pháp lưu trữ dữ liệu (ví dụ: Amazon S3).

Mục tiêu là chọn giải pháp có operational overhead thấp nhất (least operational overhead), nghĩa là ưu tiên các dịch vụ serverless, fully managed của AWS để giảm thiểu việc quản lý server, scaling, patching, v.v. Kiến trúc phải hỗ trợ real-time streaming với transform on-the-fly.

Dựa trên kiến thức AWS cập nhật đến năm 2026 (AWS Kinesis Data Streams/Firehose phiên bản mới nhất hỗ trợ enhanced fan-out, Lambda integration mượt mà hơn, API Gateway với HTTP/2 và WebSocket cho real-time), giải pháp lý tưởng là sử dụng các dịch vụ managed hoàn toàn. 📘

✅ Đáp án đúng và lý do chọn

Đáp án đúng là phương án thứ 3:

Configure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

Lý do chọn (bằng tiếng Việt):

✅ Kiến trúc này hoàn toàn serverless và managed, không cần quản lý bất kỳ instance nào:

API Gateway thay thế API tự host, tự động scale, tích hợp trực tiếp với Kinesis Data Streams qua integration HTTP/REST.

Kinesis Data Streams xử lý streaming real-time với throughput cao (hàng triệu records/giây).

Kinesis Data Firehose làm buffer/transform/delivery: dùng Lambda để transform dữ liệu streamed ngay lập tức (record-by-record), rồi lưu vào S3 (storage bền vững, cost-effective).

Least overhead: AWS lo scaling, monitoring, fault-tolerance. Phù hợp real-time ingestion theo AWS best practices (Well-Architected Framework: Reliability & Cost Optimization pillars).

🛠️ Không có điểm yếu về real-time hay overhead so với các option khác.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng phương án một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi cái được đánh dấu ✅ ĐÚNG hoặc ❌ SAI, kèm lý do cụ thể bằng tiếng Việt:

Phương án 1 (❌ SAI):

Deploy an Amazon EC2 instance to host an API that sends data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

Giải thích sai: Phần còn lại (Kinesis Stream + Firehose + Lambda + S3) đúng cho real-time transform và storage, nhưng deploy EC2 để host API tạo overhead lớn: phải tự manage EC2 (scaling, patching, high availability, Auto Scaling Group). Không phải least overhead vì EC2 không serverless.

Phương án 2 (❌ SAI):

Deploy an Amazon EC2 instance to host an API that sends data to AWS Glue. Stop source/destination checking on the EC2 instance. Use AWS Glue to transform the data and to send the data to Amazon S3.

Giải thích sai: AWS Glue là dịch vụ ETL batch-oriented (chạy job định kỳ, không real-time streaming). Không phù hợp ingestion real-time. "Stop source/destination checking" là trick VPC/EC2 không liên quan đến Glue, làm phức tạp hóa. EC2 host API lại overhead cao. Toàn bộ không đáp ứng real-time transform.

Phương án 3 (✅ ĐÚNG):

Configure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

Giải thích đúng: Như phần trên, full serverless flow: API Gateway → Kinesis Stream (real-time ingest) → Firehose (buffer/transform via Lambda) → S3. Overhead thấp nhất, scale tự động, tích hợp native (API Gateway direct integration với Kinesis từ 2023+).

Phương án 4 (❌ SAI):

Configure an Amazon API Gateway API to send data to AWS Glue. Use AWS Lambda functions to transform the data. Use AWS Glue to send the data to Amazon S3.

Giải thích sai: Glue không hỗ trợ direct streaming ingestion từ API Gateway (Glue Streaming Jobs mới từ 2024 chỉ cho Spark Streaming, setup phức tạp, không phải real-time simple như Kinesis). Lambda transform + Glue → S3 không mượt mà cho real-time (Glue vẫn batch-ish). Overhead cao hơn Kinesis/Firehose dù API Gateway tốt.

📘 Tài liệu tham khảo (AWS docs cập nhật 2026)

API Gateway + Kinesis integration: docs.aws.amazon.com/apigateway/latest/developerguide/set-up-integrations.html (Direct proxy to Kinesis).

Kinesis Data Firehose with Lambda transform: docs.aws.amazon.com/firehose/latest/dev/data-transformation.html (Real-time record transformation).

AWS Well-Architected: Streaming Data: aws.amazon.com/architecture/well-architected/streaming-data-lake (Least overhead patterns).

Exam guide DOP-C02: Streaming architectures trong DevOps Professional (2024+ updates).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần demo CDK/Terraform, hỏi thêm nhé.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85740-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/glue/I

## Câu 16

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon EFS, Amazon Storage Gateway, Amazon FSx, Amazon EC2, Amazon FSx for Lustre
- Đáp án tham khảo: **Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.**
- Takeaway nhanh: 📈 Phù hợp gaming: Hiệu suất cao (hàng triệu IOPS), scale đến PB, lazy loading từ S3 cho dữ liệu lớn. 🔗 On-premises access: Mount FSx từ origin/application server qua VPC (kết nối VPN/Direct Connect/PrivateLink). "Attach" ở đây nghĩa là mount filesystem đến server.
- Nguồn tham khảo trong block: https://aws.amazon.com/fsx/lustre/ | https://aws.amazon.com/fsx/lustre/?nc1=h_ls#:~:text=Amazon%20FSx%20for%20Lustre%20provides%20fully%20managed%20shared%20storage%20with%20the%20scalability%20and%20performance%20of%20the%20popular%20Lustre%20file%20system | https://www.examtopics.com/discussions/amazon/view/85811-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is implementing a shared storage solution for a gaming application that is hosted in an on-premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed. Which solution meets these requirements?

### Các lựa chọn
1. Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.
2. Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
3. Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.
4. Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang triển khai giải pháp lưu trữ chia sẻ (shared storage) cho ứng dụng game được host tại data center on-premises (trên máy chủ cục bộ, không phải AWS cloud). Yêu cầu chính bao gồm:

Hỗ trợ Lustre clients (các client sử dụng giao thức Lustre để truy cập dữ liệu) – Lustre là file system parallel cao hiệu suất, thường dùng cho HPC và gaming/big data.

Giải pháp phải fully managed (AWS quản lý hoàn toàn, không cần tự quản lý hạ tầng).

Cần kết nối origin server (máy chủ gốc on-premises) và application server (máy chủ ứng dụng) với storage.

Mục tiêu: Tìm giải pháp AWS fully managed hỗ trợ Lustre, accessible từ on-premises qua kết nối mạng (như VPN/Direct Connect). Kiến thức cập nhật 2026: Amazon FSx for Lustre là dịch vụ managed Lustre hàng đầu, tích hợp tốt với on-premises qua VPC peering/VPN/Direct Connect, hỗ trợ gaming workloads cao IOPS.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

Lý do:

🛠️ Amazon FSx for Lustre là dịch vụ fully managed duy nhất của AWS cung cấp file system Lustre native, hỗ trợ Lustre clients trực tiếp (mount qua NFSv4.1 hoặc s3fs cho S3 data repository).

📈 Phù hợp gaming: Hiệu suất cao (hàng triệu IOPS), scale đến PB, lazy loading từ S3 cho dữ liệu lớn.

🔗 On-premises access: Mount FSx từ origin/application server qua VPC (kết nối VPN/Direct Connect/PrivateLink). "Attach" ở đây nghĩa là mount filesystem đến server.

✅ Đầy đủ yêu cầu: Fully managed, Lustre support, shared storage.

📋 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do cụ thể dựa trên tài liệu AWS mới nhất (2026).

Phương án A (❌ SAI):

Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.

Giải thích: AWS Storage Gateway File Gateway chỉ hỗ trợ NFS/SMB, không hỗ trợ Lustre clients. Nó là hybrid storage cho on-premises cache data lên S3, nhưng không phải Lustre file system. Không đáp ứng "Lustre clients" và không fully managed cho Lustre workload gaming.

Phương án B (❌ SAI):

Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.

Giải thích: EC2 Windows với file share role (SMB) không hỗ trợ Lustre (Lustre là Linux-based, không Windows native). EC2 không fully managed (phải tự install/config/maintain), không phù hợp shared storage Lustre cho gaming on-premises. Chi phí cao, phức tạp.

Phương án C (❌ SAI):

Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.

Giải thích: Amazon EFS không hỗ trợ Lustre – EFS dùng NFSv4.1, không có config Lustre (dù có Elastic File Cache nhưng không fully managed Lustre). EFS dành regional shared file storage, nhưng không mount Lustre clients. Không đáp ứng yêu cầu chính xác.

Phương án D (✅ ĐÚNG):

Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

Giải thích: Hoàn hảo như đã nêu ở phần đáp án đúng. FSx for Lustre fully managed, native Lustre, hỗ trợ on-premises mount qua network connectivity. Cập nhật 2026: Hỗ trợ Persistent/Scratch deployment, S3 integration cho gaming data pipelines.

📘 Tài liệu tham khảo

AWS FSx for Lustre Documentation: Amazon FSx for Lustre – Xác nhận fully managed Lustre, on-premises access via VPC.

AWS Storage Gateway: File Gateway Protocols – Chỉ NFS/SMB.

AWS EFS: EFS Features – Không Lustre.

Exam Topic DOP-C02: Shared storage for HPC/gaming thường chỉ FSx Lustre.

AWS Well-Architected Framework (2026): Gaming workloads recommend FSx Lustre for high-throughput.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm ví dụ thực hành, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85811-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/fsx/lustre/

https://aws.amazon.com/fsx/lustre/?nc1=h_ls#:~:text=Amazon%20FSx%20for%20Lustre%20provides%20fully%20managed%20shared%20storage%20with%20the%20scalability%20and%20performance%20of%20the%20popular%20Lustre%20file%20system.

## Câu 17

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EMR, Amazon Kinesis, Amazon EventBridge, Amazon SQS, Amazon Lambda, Amazon DynamoDB, Amazon CloudWatch, Amazon S3, Amazon Aurora, Amazon EC2, Amazon Kinesis Data Streams
- Đáp án tham khảo: **Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.**
- Takeaway nhanh: Least overhead: Toàn bộ serverless (S3 + SQS + Lambda + DynamoDB), Well-Architected Framework (Serverless pillar) khuyến nghị. Không cần provision capacity, monitor chỉ metrics cơ bản.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86676-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is designing an application where users upload small files into Amazon S3. After a user uploads a file, the file requires one-time simple processing to transform the data and save the data in JSON format for later analysis. Each file must be processed as quickly as possible after it is uploaded. Demand will vary. On some days, users will upload a high number of files. On other days, users will upload a few files or no files. Which solution meets these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Configure Amazon EMR to read text files from Amazon S3. Run processing scripts to transform the data. Store the resulting JSON file in an Amazon Aurora DB cluster.
2. Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use Amazon EC2 instances to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.
3. Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.
4. Configure Amazon EventBridge (Amazon CloudWatch Events) to send an event to Amazon Kinesis Data Streams when a new file is uploaded. Use an AWS Lambda function to consume the event from the stream and process the data. Store the resulting JSON file in an Amazon Aurora DB cluster.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế một giải pháp xử lý file nhỏ được upload lên Amazon S3 một cách nhanh chóng nhất có thể sau khi upload, với yêu cầu transform dữ liệu đơn giản một lần và lưu dưới dạng JSON để phân tích sau. 📤

Yêu cầu chính:

File nhỏ, xử lý đơn giản (không phức tạp).

Xử lý ngay lập tức sau upload.

Demand biến động: Ngày cao điểm có nhiều file, ngày thấp có ít hoặc không file.

Tiêu chí quan trọng nhất: Giải pháp với LEAST operational overhead (ít công vận hành nhất, ưu tiên serverless, tự động scale, không quản lý server).

🛠️ Vấn đề cốt lõi: Cần trigger xử lý tự động từ S3 event, xử lý serverless để scale theo demand mà không cần quản lý infrastructure (như EC2 hay EMR), lưu trữ JSON phù hợp (NoSQL như DynamoDB tốt hơn relational DB cho JSON không cấu trúc).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

Lý do chọn:

✅ S3 event notification → SQS: S3 hỗ trợ gửi event trực tiếp đến SQS (tính năng native từ 2018, cập nhật 2024-2026 vẫn là best practice). SQS decouples (tách biệt), queueing xử lý burst traffic (nhiều file cao điểm), retry tự động nếu Lambda fail, FIFO hoặc Standard queue phù hợp file nhỏ.

✅ AWS Lambda: Serverless, auto-scale theo demand, cold start <1s cho workload nhỏ, zero operational overhead (không quản lý server). Xử lý nhanh (invoke sau S3 event ~giây), tích hợp SQS trigger native.

✅ DynamoDB: NoSQL serverless, pay-per-use, lưu JSON linh hoạt (Document model), query nhanh cho analysis, auto-scale theo traffic.

Least overhead: Toàn bộ serverless (S3 + SQS + Lambda + DynamoDB), Well-Architected Framework (Serverless pillar) khuyến nghị. Không cần provision capacity, monitor chỉ metrics cơ bản.

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên văn bản gốc tiếng Anh của phương án, chỉ giải thích bằng tiếng Việt với emoji đánh dấu.

❌ Phương án SAI: Configure Amazon EMR to read text files from Amazon S3. Run processing scripts to transform the data. Store the resulting JSON file in an Amazon Aurora DB cluster.

Giải thích sai: EMR là dịch vụ managed Hadoop/Spark cho big data phức tạp (cluster-based), overkill cho file nhỏ/simple processing → operational overhead cao (provision cluster, manage nodes, scale thủ công). Aurora là relational DB, không tối ưu lưu JSON (cần schema rigid). Không trigger tự động nhanh từ S3, vi phạm "xử lý nhanh nhất" và "least overhead". 🛑

❌ Phương án SAI: Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use Amazon EC2 instances to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

Giải thích sai: S3 → SQS tốt cho decoupling, DynamoDB phù hợp JSON. Nhưng EC2 instances yêu cầu quản lý server (AMI, Auto Scaling Group, patching, monitoring) → overhead cao, không auto-scale mịn như Lambda (cần custom poller từ queue). Không serverless, vi phạm "least overhead" đặc biệt với demand biến động. 🚫

✅ Phương án ĐÚNG: Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

Giải thích đúng: Như phần ✅ trên. Hoàn hảo match yêu cầu: Event-driven, serverless full-stack, scale theo demand (SQS buffer burst, Lambda concurrent executions lên hàng nghìn), xử lý nhanh (<1 phút end-to-end), zero server management. Best practice AWS 2026. 🎯

❌ Phương án SAI: Configure Amazon EventBridge (Amazon CloudWatch Events) to send an event to Amazon Kinesis Data Streams when a new file is uploaded. Use an AWS Lambda function to consume the event from the stream and process the data. Store the resulting JSON file in an Amazon Aurora DB cluster.

Giải thích sai: EventBridge + Kinesis dành cho high-throughput streaming data (real-time, continuous), overkill cho file nhỏ/discrete uploads (shard management, throughput provision, data retention phí). Trigger S3 → EventBridge → Kinesis phức tạp hơn S3 direct → SQS/Lambda. Aurora không phù hợp JSON → schema overhead. Không least overhead. 📉

📘 Tài liệu tham khảo (AWS cập nhật 2024-2026)

S3 Event Notifications: docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html (hỗ trợ SQS/Lambda native).

Lambda with SQS: docs.aws.amazon.com/lambda/latest/dg/with-sqs.html (trigger dead-letter queue xử lý fail).

Well-Architected Framework - Serverless: aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-lens.whitepapers-wa-card-sort.sort-by=item.additionalFields.sortDate&wa-lens.whitepapers-wa-card-sort.sort-order=desc (Lens: Serverless, Operational Excellence).

DynamoDB for JSON: docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes (Map/Document types).

Giải pháp này đảm bảo 99.99% availability, cost hiệu quả (~$0.0004/1k requests Lambda). Nếu cần code sample Lambda, hỏi thêm nhé! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86676-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 18

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon API Gateway, Amazon S3, Amazon Virtual Private Cloud
- Đáp án tham khảo: **Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.**
- Takeaway nhanh: S3 VPC Gateway Endpoint (Gateway type, không phải Interface) cho phép traffic từ VPC đến S3 đi qua mạng AWS backbone, không qua internet, nên zero data transfer fees cho intra-region (cùng region). Endpoint policy kiểm soát quyền truy cập cụ thể đến buckets, tăng bảo mật (IAM policy-based). Hiệu suất cao: Low latency, full throughput, hỗ trợ upload/download lớn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85604-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs. How can the solutions architect meet this requirement?

### Các lựa chọn
1. Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.
2. Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.
3. Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.
4. Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào một ứng dụng xử lý ảnh của công ty, cần upload và download hình ảnh thường xuyên từ các Amazon S3 buckets nằm cùng AWS Region với ứng dụng. 🛤️ Solutions Architect nhận thấy chi phí data transfer fees tăng cao, cần triển khai giải pháp giảm chi phí này.

🔍 Vấn đề cốt lõi:

Truy cập S3 từ VPC thường đi qua Internet Gateway (IGW) hoặc NAT Gateway, dẫn đến phí data transfer out (khoảng 0.09 USD/GB cho traffic ra internet, ngay cả cùng region).

Mục tiêu: Tối ưu hóa traffic nội bộ AWS, tránh phí transfer không cần thiết mà vẫn giữ bảo mật và hiệu suất cao.

Ngữ cảnh AWS cập nhật 2026: S3 VPC Gateway Endpoint vẫn là giải pháp chuẩn (không thay đổi lớn từ 2023), hỗ trợ zero-cost data transfer cho traffic intra-region qua endpoint.

📘 Tài liệu tham khảo:

AWS VPC Endpoints Documentation (cập nhật 2025).

Amazon S3 Pricing (Data Transfer: Free qua VPC Endpoint cùng region).

AWS Well-Architected Framework - Cost Optimization Pillar.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

Lý do chi tiết 🏆:

S3 VPC Gateway Endpoint (Gateway type, không phải Interface) cho phép traffic từ VPC đến S3 đi qua mạng AWS backbone, không qua internet, nên zero data transfer fees cho intra-region (cùng region).

Endpoint policy kiểm soát quyền truy cập cụ thể đến buckets, tăng bảo mật (IAM policy-based).

Hiệu suất cao: Low latency, full throughput, hỗ trợ upload/download lớn.

Tiết kiệm chi phí: Giảm ngay lập tức phí transfer out (tiết kiệm ~90% so với IGW/NAT).

Dễ triển khai: Route table tự động route prefix 0.0.0.0/0 đến S3 qua endpoint (không cần public IP).

❌ Giải thích tất cả các phương án (đúng/sai)

Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.

❌ Sai: API Gateway dùng cho REST/HTTP APIs, không phải proxy/route trực tiếp S3 traffic. Điều chỉnh route table không hỗ trợ API Gateway cho S3 (chỉ cho VPC Endpoint). Vẫn tốn phí transfer qua public internet + phí API Gateway (~3.50 USD/million requests). Không giảm chi phí, phức tạp vô ích. 🛑

Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.

❌ Sai: NAT Gateway dùng cho private subnet ra internet, traffic S3 vẫn qua public internet → vẫn tốn data transfer out fees (0.09 USD/GB + NAT hourly fee ~0.045 USD/giờ). Endpoint policy không áp dụng cho NAT (chỉ cho VPC Endpoints). Không giải quyết gốc rễ. 💸

Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.

❌ Sai: Public subnet + IGW làm traffic đi qua internet công khai, tốn đầy đủ data transfer out fees dù cùng region. Bảo mật kém (public exposure), không tận dụng mạng nội bộ AWS. Tăng chi phí thay vì giảm. 🌐

Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

✅ Đúng: Như giải thích trên, đây là best practice AWS cho S3 access từ VPC, zero-cost + secure + performant. Route table update prefix list (pl-xxxxx) tự động route traffic. Hoàn hảo cho upload/download frequent. 🚀

🛠️ Khuyến nghị triển khai thực tế:

Tạo VPC Endpoint: aws ec2 create-vpc-endpoint --vpc-id vpc-xxx --service-name com.amazonaws.[region].s3.

Attach policy: Full access hoặc restrict buckets.

Update route table: Add route pl-xxxxx → vpce-xxx. Kiểm tra CloudWatch Metrics cho traffic savings! 📊

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85604-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 19

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon Lambda, Amazon DynamoDB, Amazon CloudWatch, Amazon S3, Amazon Backup
- Đáp án tham khảo: **Use AWS Backup to create backup schedules and retention policies for the table.**
- Takeaway nhanh: AWS Backup là dịch vụ managed trung tâm (centralized) hỗ trợ DynamoDB với lịch backup tự động (schedules), chính sách lưu trữ linh hoạt (retention policies) lên đến 100 năm, và tuân thủ quy định (audit trails qua AWS CloudTrail). 🛡️ Hiệu quả vận hành cao nhất: Không cần code custom, vault-based management, cross-region copy, và tích hợp S3 Glacier cho lưu trữ dài hạn rẻ tiền. Giảm toil cho DevOps team so với các giải pháp thủ công.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/database/part-2-set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/I | https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/backuprestore_HowItWorksAWS.html | https://www.examtopics.com/discussions/amazon/view/85742-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company needs to keep user transaction data in an Amazon DynamoDB table. The company must retain the data for 7 years. What is the MOST operationally efficient solution that meets these requirements?

### Các lựa chọn
1. Use DynamoDB point-in-time recovery to back up the table continuously.
2. Use AWS Backup to create backup schedules and retention policies for the table.
3. Create an on-demand backup of the table by using the DynamoDB console. Store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.
4. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to invoke an AWS Lambda function. Configure the Lambda function to back up the table and to store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc lưu trữ và bảo vệ dữ liệu giao dịch người dùng trong bảng Amazon DynamoDB với yêu cầu giữ dữ liệu ít nhất 7 năm. 🔄

Yêu cầu chính: Giải pháp phải hiệu quả vận hành nhất (MOST operationally efficient), nghĩa là tự động hóa cao, dễ quản lý, chi phí tối ưu, hỗ trợ chính sách lưu trữ dài hạn (retention policy), và tích hợp tốt với các dịch vụ AWS.

Thách thức: DynamoDB là NoSQL database, dữ liệu giao dịch cần backup liên tục hoặc theo lịch để tránh mất mát, đồng thời tuân thủ quy định lưu trữ 7 năm (compliance như GDPR, HIPAA).

Bối cảnh cập nhật 2026: AWS khuyến nghị sử dụng các dịch vụ managed như AWS Backup cho backup DynamoDB (hỗ trợ từ 2020 và cải tiến liên tục), thay vì giải pháp custom để giảm operational overhead. PITR chỉ hỗ trợ recovery lên đến 35 ngày, không phù hợp dài hạn. 📈

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use AWS Backup to create backup schedules and retention policies for the table.

Lý do:

AWS Backup là dịch vụ managed trung tâm (centralized) hỗ trợ DynamoDB với lịch backup tự động (schedules), chính sách lưu trữ linh hoạt (retention policies) lên đến 100 năm, và tuân thủ quy định (audit trails qua AWS CloudTrail). 🛡️

Hiệu quả vận hành cao nhất: Không cần code custom, vault-based management, cross-region copy, và tích hợp S3 Glacier cho lưu trữ dài hạn rẻ tiền. Giảm toil cho DevOps team so với các giải pháp thủ công.

Phù hợp best practice AWS Well-Architected Framework (Reliability & Cost Optimization pillars). 💡

📋 Giải thích tất cả các phương án (đúng/sai)

✅ Use AWS Backup to create backup schedules and retention policies for the table.

Phương án này đúng vì AWS Backup cung cấp backup theo lịch (daily/weekly/monthly) và retention policy chính xác 7 năm cho DynamoDB tables. Nó hỗ trợ continuous backup, restore point-in-time, và lưu trữ tối ưu chi phí (S3 Intelligent-Tiering/Glacier). Đây là giải pháp managed, scalable, và operationally efficient nhất theo docs AWS 2026. Không cần can thiệp thủ công, dễ audit.

❌ Use DynamoDB point-in-time recovery to back up the table continuously.

Phương án này sai vì Point-in-Time Recovery (PITR) chỉ hỗ trợ khôi phục dữ liệu trong 35 ngày gần nhất (tối đa billing cycle), không đáp ứng yêu cầu 7 năm. PITR dùng cho disaster recovery ngắn hạn, không phải lưu trữ dài hạn (không export ra S3 tự động). Chi phí cao nếu enable liên tục mà không cần thiết.

❌ Create an on-demand backup of the table by using the DynamoDB console. Store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

Phương án này sai vì on-demand backup là thủ công (qua console/API), không tự động theo lịch, dẫn đến operational inefficiency (phải chạy định kỳ bằng tay). Export sang S3 cần export job riêng (DynamoDB Export to S3 feature), và S3 Lifecycle chỉ quản lý storage class, không phải backup logic đầy đủ. Không centralized, khó scale cho production.

❌ Create an Amazon EventBridge (Amazon CloudWatch Events) rule to invoke an AWS Lambda function. Configure the Lambda function to back up the table and to store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

Phương án này sai vì đây là giải pháp custom phức tạp (EventBridge + Lambda + S3), yêu cầu code để export DynamoDB (sử dụng DynamoDB Export hoặc scan table), maintain code, handle errors, và permissions. Không efficient so với AWS Backup managed service – tăng toil, chi phí dev/debug, và rủi ro failure. S3 Lifecycle chỉ hỗ trợ retention cơ bản, thiếu audit/compliance đầy đủ.

📘 Tài liệu tham khảo (AWS Docs cập nhật 2026)

AWS Backup for DynamoDB – Chi tiết schedules & retention.

DynamoDB Backups & Restores – So sánh PITR vs. AWS Backup.

DynamoDB Export to S3 – Lý do custom export kém efficient.

AWS Well-Architected: Reliability Pillar (Backup Strategies). 🌐

Giải pháp này giúp công ty tuân thủ 7 năm retention một cách tối ưu nhất! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85742-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/database/part-2-set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/I

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/backuprestore_HowItWorksAWS.html

## Câu 20

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SNS, Amazon SQS, Amazon Lambda, Amazon Relational Database Service
- Takeaway nhanh: Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Integrating.Lambda.htmlTo | https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.overview.html | https://www.examtopics.com/discussions/amazon/view/85427-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an automobile sales website that stores its listings in a database on Amazon RDS. When an automobile is sold, the listing needs to be removed from the website and the data must be sent to multiple target systems. Which design should a solutions architect recommend?

### Các lựa chọn
1. Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.
2. Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) FIFO queue for the targets to consume.
3. Subscribe to an RDS event notification and send an Amazon Simple Queue Service (Amazon SQS) queue fanned out to multiple Amazon Simple Notification Service (Amazon SNS) topics. Use AWS Lambda functions to update the targets.
4. Subscribe to an RDS event notification and send an Amazon Simple Notification Service (Amazon SNS) topic fanned out to multiple Amazon Simple Queue Service (Amazon SQS) queues. Use AWS Lambda functions to update the targets.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi xoay quanh một website bán ô tô của công ty, nơi lưu trữ thông tin listings (danh sách xe) trong cơ sở dữ liệu trên Amazon RDS. Khi một chiếc ô tô được bán, cần thực hiện hai hành động chính:

❌ Xóa listing khỏi website (cập nhật/xóa dữ liệu trong RDS).

📤 Gửi dữ liệu liên quan đến nhiều hệ thống đích (multiple target systems) một cách đáng tin cậy, decoupled (tách biệt).

Solutions Architect cần recommend design pattern tối ưu để xử lý sự kiện này trên AWS, đảm bảo tính scalable, reliable và không phụ thuộc trực tiếp vào ứng dụng website.

🛠️ Thách thức chính: RDS không hỗ trợ trigger tự động trên thay đổi dữ liệu row-level (như update/delete một record cụ thể). RDS events chỉ dùng cho các sự kiện quản lý instance (ví dụ: backup, failover), không phải data changes. Do đó, cần cơ chế phát hiện thay đổi từ ứng dụng (app-triggered) hoặc CDC (Change Data Capture), nhưng ở đây ưu tiên giải pháp đơn giản, serverless.

✅ Đáp án đúng

Đáp án đúng là phương án đầu tiên:

Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.

Lý do lựa chọn:

🧩 Giải pháp này tận dụng application logic (website app) để trigger Lambda ngay khi update RDS (ví dụ: sau lệnh DELETE/UPDATE). Lambda gửi message chứa data vào SQS standard queue, cho phép multiple targets (poller Lambda/ECS) consume độc lập, đảm bảo decoupling, at-least-once delivery và scalability. SQS standard phù hợp vì không yêu cầu ordering nghiêm ngặt (FIFO không cần thiết cho listing sold), hỗ trợ high throughput (>3000 msg/s với batching). Đây là best practice cho event-driven architecture trên AWS (2024-2026), tránh tight coupling với RDS.

📘 Nguồn: AWS Well-Architected Framework - Reliability Pillar; SQS Docs.

🔍 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng phương án giữ nguyên văn bản gốc bằng tiếng Anh, với giải thích đúng/sai bằng tiếng Việt. Sử dụng kiến thức AWS mới nhất (re:Post 2026, không thay đổi cốt lõi RDS events).

✅ Phương án ĐÚNG:

Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.

🛠️ Tại sao đúng? Ứng dụng website trigger Lambda đồng bộ/bất đồng bộ khi update RDS (qua SDK/API), Lambda đẩy data vào SQS standard queue. Targets (multiple) poll queue để process, hỗ trợ retry/DLQ tự động. Serverless, cost-effective (~$0.40/million requests), scale auto. Phù hợp real-time decoupling mà không cần CDC phức tạp như DMS/Aurora binlog.

❌ Phương án SAI:

Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) FIFO queue for the targets to consume.

🚫 Tại sao sai? Tương tự phương án đúng nhưng dùng SQS FIFO thay standard. FIFO yêu cầu message group ID để ordering, throughput thấp hơn (300 msg/s max), đắt hơn (gấp đôi phí), và không cần thiết cho use case này (listing sold không cần exactly-once/ordering nghiêm ngặt). Standard SQS linh hoạt hơn cho multiple consumers không ordered.

❌ Phương án SAI:

Subscribe to an RDS event notification and send an Amazon Simple Queue Service (Amazon SQS) queue fanned out to multiple Amazon Simple Notification Service (Amazon SNS) topics. Use AWS Lambda functions to update the targets.

🚫 Tại sao sai? RDS event notifications chỉ capture management events (backup, scale, delete instance), KHÔNG detect data changes (row update/delete). Logic "SQS queue fanned out to SNS topics" sai hướng (SQS không fanout trực tiếp ra SNS; phải dùng SNS -> SQS). Thiết kế rối rắm, không reliable cho data sync.

❌ Phương án SAI:

Subscribe to an RDS event notification and send an Amazon Simple Notification Service (Amazon SNS) topic fanned out to multiple Amazon Simple Queue Service (Amazon SQS) queues. Use AWS Lambda functions to update the targets.

🚫 Tại sao sai? Tương tự, RDS events KHÔNG trigger trên data update (xem docs: chỉ ~50 event categories như RDS-EVENT-0001 cho snapshots). Fanout SNS -> multiple SQS đúng pattern, nhưng gốc rễ sai vì không detect được "automobile sold". Lambda subscribers chỉ nhận event metadata, thiếu data chi tiết cần gửi targets.

📚 Tài liệu tham khảo chính (cập nhật 2026)

🛠️ RDS Monitoring & Events – Xác nhận RDS events không cho data changes.

📤 SQS Standard vs FIFO – Standard ưu tiên cho non-ordered workloads.

🔄 Event-Driven Architecture on AWS – Best practice Lambda + SQS cho decoupling.

📘 AWS DOP-C02 Exam Guide (2024): Topic "Decouple & Reliable Storage".

Giải pháp này đảm bảo 99.99% durability và scale seamless! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85427-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.overview.html

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Integrating.Lambda.htmlTo

## Câu 21

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Relational Database Service
- Takeaway nhanh: Read Replicas là giải pháp chuẩn của AWS RDS MySQL để tách biệt read/write traffic một cách nhanh chóng (tạo replica chỉ mất vài phút). Primary DB xử lý write, replicas xử lý read. Cùng compute/storage resources (same size instance) đảm bảo replicas có hiệu suất tương đương primary, tránh tình trạng bottleneck nếu read traffic nặng (half size sẽ chậm hơn, replication lag tăng). Theo best practices AWS (cập nhật 2024-2026), replicas nên match hoặc lớn hơn primary cho workload cân bằng.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html | https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html | https://www.examtopics.com/discussions/amazon/view/85906-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An application allows users at a company's headquarters to access product data. The product data is stored in an Amazon RDS MySQL DB instance. The operations team has isolated an application performance slowdown and wants to separate read traffic from write traffic. A solutions architect needs to optimize the application's performance quickly. What should the solutions architect recommend?

### Các lựa chọn
1. Change the existing database to a Multi-AZ deployment. Serve the read requests from the primary Availability Zone.
2. Change the existing database to a Multi-AZ deployment. Serve the read requests from the secondary Availability Zone.
3. Create read replicas for the database. Configure the read replicas with half of the compute and storage resources as the source database.
4. Create read replicas for the database. Configure the read replicas with the same compute and storage resources as the source database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng cho phép người dùng tại trụ sở công ty truy cập dữ liệu sản phẩm được lưu trữ trong Amazon RDS MySQL DB instance. Đội ngũ vận hành (operations team) phát hiện hiệu suất ứng dụng bị chậm lại do lưu lượng đọc (read traffic) và ghi (write traffic) bị lẫn lộn trên cùng một DB instance. Kiến trúc sư giải pháp (solutions architect) cần tối ưu hóa hiệu suất nhanh chóng bằng cách tách biệt read traffic khỏi write traffic.

✅ Mục tiêu chính: Scale out read operations mà không ảnh hưởng đến primary DB (chịu trách nhiệm write), tận dụng tính năng native của RDS MySQL để triển khai nhanh (quickly).

🛠️ Bối cảnh AWS: RDS MySQL hỗ trợ Read Replicas để offload read queries, giúp tăng throughput đọc lên đến hàng trăm nghìn operations/giây, với replication lag thấp (thường <1 giây).

✅ Đáp án đúng và lý do lựa chọn

Create read replicas for the database. Configure the read replicas với the same compute and storage resources as the source database.

Lý do chi tiết:

Read Replicas là giải pháp chuẩn của AWS RDS MySQL để tách biệt read/write traffic một cách nhanh chóng (tạo replica chỉ mất vài phút). Primary DB xử lý write, replicas xử lý read.

Cùng compute/storage resources (same size instance) đảm bảo replicas có hiệu suất tương đương primary, tránh tình trạng bottleneck nếu read traffic nặng (half size sẽ chậm hơn, replication lag tăng). Theo best practices AWS (cập nhật 2024-2026), replicas nên match hoặc lớn hơn primary cho workload cân bằng.

Triển khai nhanh: Sử dụng AWS Console/CLI, hỗ trợ Multi-AZ cho replicas từ 2021, và Performance Insights để monitor.

🧩 Lợi ích: Giảm tải primary lên đến 100x, chi phí tối ưu (pay-per-use), tự động failover nếu cần.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích từng lựa chọn (giữ nguyên text gốc tiếng Anh). Tôi đánh dấu ✅ đúng hoặc ❌ sai, kèm giải thích chi tiết bằng tiếng Việt dựa trên tài liệu AWS mới nhất (2026).

❌ [SAI] Change the existing database to a Multi-AZ deployment. Serve the read requests from the primary Availability Zone.

Giải thích sai: Multi-AZ chỉ cung cấp high availability (HA) bằng cách tạo standby replica synchronous cho failover (không read từ standby). Primary AZ vẫn chịu toàn bộ read/write traffic, không tách biệt được → không giải quyết slowdown. Serve read từ primary càng làm tình hình tệ hơn. (AWS Docs: Multi-AZ là cho disaster recovery, không scale read).

❌ [SAI] Change the existing database to a Multi-AZ deployment. Serve the read requests from the secondary Availability Zone.

Giải thích sai: Secondary AZ trong Multi-AZ là standby instance (read-only nhưng không được khuyến nghị serve read traffic vì nó đồng bộ synchronous, ưu tiên failover chứ không offload read). AWS không hỗ trợ route read traffic đến secondary Multi-AZ một cách native (chỉ failover tự động). Việc cố serve read từ secondary có thể gây consistency issues và không scale hiệu quả. (Cập nhật 2026: Vẫn giữ nguyên, khuyến cáo dùng Read Replicas riêng).

❌ [SAI] Create read replicas for the database. Configure the read replicas with half of the compute and storage resources as the source database.

Giải thích sai: Read Replicas đúng hướng để tách read/write, nhưng half resources (ví dụ primary db.m5.4xlarge → replica db.m5.2xlarge) sẽ tạo bottleneck vì replicas yếu hơn, replication lag tăng (có thể >5s), không xử lý read traffic lớn → hiệu suất tổng thể vẫn chậm. AWS best practices: Khuyến nghị same hoặc larger size cho replicas để match workload (RDS Sizing Guide 2026).

✅ [ĐÚNG] Create read replicas for the database. Configure the read replicas with the same compute and storage resources as the source database.

Giải thích đúng (như phần trên): Hoàn hảo cho quick optimization, scale read linearly (lên đến 15 replicas/region), hỗ trợ cross-region, và tích hợp CloudWatch/Enhanced Monitoring. Lag thấp, consistent data.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

Amazon RDS Read Replicas: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html – Chi tiết tạo replicas, sizing best practices.

RDS Multi-AZ vs Read Replicas: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html#USER_ReadRepl.SizeDifferences – So sánh rõ ràng.

RDS Best Practices (DO-OP Exam Guide): AWS Well-Architected Framework – Reliability Pillar: Scale reads với replicas full-size.

Performance Insights: aws.amazon.com/rds/features/performance-insights/ – Monitor read/write traffic (miễn phí 7 ngày).

🛠️ Lời khuyên DevOps: Sau triển khai, dùng RDS Proxy nếu app có connection pooling cao, và Route 53 hoặc app logic để route read queries đến replicas!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85906-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html)

## Câu 22

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Direct Connect, Amazon CLI
- Takeaway nhanh: Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Tôi đánh dấu ✅ đúng hoặc ❌ sai, kèm giải thích bằng tiếng Việt.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/hybrid/ | https://docs.aws.amazon.com/directconnect/latest/UserGuide/ | https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-vpn.html | https://www.examtopics.com/discussions/amazon/view/85593-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower traffic if the primary connection fails. What should the solutions architect do to meet these requirements?

### Các lựa chọn
1. Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.
2. Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.
3. Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.
4. Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế kiến trúc hybrid (kết hợp on-premises và AWS) để mở rộng hạ tầng on-premises của công ty lên AWS. Các yêu cầu chính bao gồm:

Kết nối highly available (có tính sẵn sàng cao) với consistent low latency (độ trễ thấp ổn định) đến một AWS Region cụ thể.

Minimize costs (giảm thiểu chi phí).

Chấp nhận slower traffic (lưu lượng chậm hơn) nếu kết nối chính (primary) bị lỗi.

🛠️ Giải pháp lý tưởng: Sử dụng kết nối dedicated private như AWS Direct Connect làm primary để đảm bảo low latency và consistent performance, kết hợp backup rẻ tiền hơn như VPN để failover, phù hợp với việc chấp nhận slower traffic khi backup kích hoạt. Điều này cân bằng giữa performance, availability và cost theo AWS Well-Architected Framework (Pillar: Reliability & Cost Optimization).

📘 Nguồn tham khảo:

AWS Direct Connect User Guide (cập nhật 2024-2026): https://docs.aws.amazon.com/directconnect/latest/UserGuide/

AWS Hybrid Networking Best Practices: https://aws.amazon.com/architecture/hybrid/

AWS Well-Architected Framework (Reliability Pillar, 2024 edition).

✅ Đáp án đúng

Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

Lý do lựa chọn:

✅ Direct Connect primary: Cung cấp kết nối dedicated private fiber-optic, đảm bảo low latency ổn định (thường <10ms đến Region), bandwidth cao (1Gbps-100Gbps), không phụ thuộc internet công cộng → Phù hợp "consistent low latency".

✅ VPN backup: Rẻ hơn nhiều (pay-per-hour, no port fees), sử dụng Site-to-Site VPN over internet → Minimize costs, và chấp nhận "slower traffic" (latency cao hơn, variable ~50-200ms).

✅ Highly available: Cấu hình failover tự động qua BGP routing (advertise routes với preferred prefix trên DX, withdraw khi fail → route sang VPN). Hỗ trợ Hosted VIF hoặc Public/Private VIF cho hybrid setup.

🛠️ Cập nhật 2026: AWS vẫn khuyến nghị combo DX + VPN cho hybrid cost-effective, với cải tiến như DX Gateway cho multi-Region failover (ra mắt 2023, stable đến 2026).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Tôi đánh dấu ✅ đúng hoặc ❌ sai, kèm giải thích bằng tiếng Việt.

✅ Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

🟢 Đúng hoàn hảo: Như giải thích trên, kết hợp DX (low latency primary) + VPN (cheap backup) đáp ứng đầy đủ yêu cầu highly available, low latency chính, minimize costs, và chấp nhận slower failover. Sử dụng AWS Site-to-Site VPN với Virtual Private Gateway để route failover qua BGP metrics.

❌ Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.

🔴 Sai: VPN primary không đảm bảo consistent low latency (phụ thuộc internet công khai, jitter cao, packet loss). Second VPN chỉ tăng redundancy nhưng vẫn không low latency, và chi phí thấp nhưng không đáp ứng "highly available with consistent low latency" → Không phù hợp primary connection.

❌ Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.

🔴 Sai: DX primary tốt, nhưng second DX đến cùng Region rất đắt đỏ (port fees hàng tháng ~$0.03/GB + setup cao), không minimize costs. SLA chỉ 99.99% per connection, second DX cùng location không tăng availability đáng kể (shared risk), và không chấp nhận "slower traffic" vì backup vẫn fast như primary.

❌ Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.

🔴 Sai: Không tồn tại "Direct Connect failover attribute" trong AWS CLI. DX hỗ trợ failover qua BGP, LAG (Link Aggregation Group), hoặc DX Gateway, nhưng CLI không tự động "create backup connection". Phải provision thủ công trước (như VPN hoặc second DX). Đây là hiểu lầm về tính năng → Không khả thi, không minimize costs.

🧠 Kết luận: Phương án đúng tối ưu hóa Reliability (failover nhanh <1 phút qua BGP) và Cost (DX ~$0.02-$0.30/GB + VPN ~$0.05/hour). Khuyến nghị test với AWS Network Load Testing hoặc Reachability Analyzer! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85593-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-direct-connect-vpn.html

## Câu 23

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon S3
- Đáp án tham khảo: **Enable the versioning and MFA Delete features on the S3 bucket.**
- Takeaway nhanh: Versioning (phiên bản hóa) cho phép lưu trữ nhiều phiên bản của object, nên ngay cả khi object bị xóa, phiên bản cũ vẫn tồn tại và có thể khôi phục dễ dàng qua console, CLI hoặc API. MFA Delete yêu cầu multi-factor authentication (MFA) để thực hiện các hành động xóa vĩnh viễn (như xóa version cụ thể hoặc disable versioning), ngăn chặn xóa nhầm do lỗi con người.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonS3/latest/userguide/MultiFactorAuthenticationDelete.html | https://www.examtopics.com/discussions/amazon/view/85808-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company uses Amazon S3 to store its confidential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution. What should a solutions architect do to secure the audit documents?

### Các lựa chọn
1. Enable the versioning and MFA Delete features on the S3 bucket.
2. Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.
3. Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.
4. Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc bảo vệ tài liệu kiểm toán bí mật được lưu trữ trên Amazon S3 bucket. Bucket hiện tại đã áp dụng bucket policies để giới hạn quyền truy cập theo nguyên tắc least privilege (quyền tối thiểu cần thiết) dành cho IAM user credentials của đội ngũ audit. Tuy nhiên, các quản lý lo ngại về rủi ro xóa nhầm tài liệu (accidental deletion), và họ muốn một giải pháp an toàn hơn để ngăn chặn tình huống này.

🛡️ Mục tiêu chính: Tăng cường bảo mật chống xóa object trong bucket mà không ảnh hưởng đến quyền truy cập hợp lệ. Giải pháp phải tuân thủ các tính năng S3 mới nhất (cập nhật đến 2026, theo AWS S3 Versioning và MFA Delete features).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Enable the versioning and MFA Delete features on the S3 bucket.

Lý do:

Versioning (phiên bản hóa) cho phép lưu trữ nhiều phiên bản của object, nên ngay cả khi object bị xóa, phiên bản cũ vẫn tồn tại và có thể khôi phục dễ dàng qua console, CLI hoặc API.

MFA Delete yêu cầu multi-factor authentication (MFA) để thực hiện các hành động xóa vĩnh viễn (như xóa version cụ thể hoặc disable versioning), ngăn chặn xóa nhầm do lỗi con người.

🛠️ Kết hợp hai tính năng này là giải pháp tối ưu, trực tiếp giải quyết lo ngại về accidental deletion mà không thay đổi quyền IAM hiện tại. Đây là best practice theo AWS Well-Architected Framework (Security Pillar).

📘 Tài liệu tham khảo:

AWS S3 Versioning

AWS S3 MFA Delete

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích chi tiết từng lựa chọn. Tôi giữ nguyên văn bản gốc tiếng Anh của phương án, chỉ giải thích bằng tiếng Việt với emoji nổi bật:

Enable the versioning and MFA Delete features on the S3 bucket.

✅ Đúng: Như đã giải thích ở trên, versioning bảo vệ bằng cách giữ lịch sử phiên bản object, còn MFA Delete thêm lớp xác thực đa yếu tố cho hành động xóa. Giải pháp này trực tiếp và hiệu quả nhất cho bucket S3, không yêu cầu thay đổi IAM hoặc policy phức tạp. Hoạt động ngay cả với quyền least privilege hiện tại.

Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.

❌ Sai: MFA trên IAM user chỉ bảo vệ quá trình đăng nhập và sử dụng credentials (như console access), không ngăn chặn hành động s3:DeleteObject sau khi đã authenticated. Người dùng vẫn có thể xóa object qua API/CLI mà không cần MFA thêm. Không giải quyết accidental deletion trực tiếp.

Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.

❌ Sai: S3 Lifecycle policy áp dụng trên bucket, không phải trên IAM user accounts. Lifecycle dùng để tự động hóa chuyển đổi/ xóa object theo thời gian (như transition to Glacier), không hỗ trợ deny action theo ngày cụ thể (như "during audit dates") hoặc gắn với IAM. Đây là hiểu lầm sai về tính năng; để deny action cần dùng bucket policy hoặc IAM policy, không phải Lifecycle.

Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.

❌ Sai: KMS encrypt bảo vệ tính toàn vẹn và bí mật dữ liệu (confidentiality), nhưng không ngăn xóa object (deletion). Nếu deny KMS key access, audit team không đọc được object (vi phạm least privilege hiện tại), và object vẫn có thể bị xóa mà không cần decrypt. Không liên quan đến accidental deletion.

🧠 Kết luận: Giải pháp đúng tận dụng tính năng native của S3, dễ triển khai và scale cao. Nếu áp dụng thực tế, hãy test versioning trước khi enable MFA Delete để tránh lockout! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85808-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonS3/latest/userguide/MultiFactorAuthenticationDelete.html

## Câu 24

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Athena, Amazon Kinesis, Amazon QuickSight, Amazon Redshift, Amazon Lambda, Amazon Q, Amazon API Gateway, Amazon S3
- Đáp án tham khảo: **Use Amazon API Gateway with AWS Lambda.**
- Takeaway nhanh: API Gateway cung cấp REST API đầy đủ (HTTP/REST endpoints) để expose dữ liệu vị trí, hỗ trợ truy xuất real-time/low-latency từ client (app/mobile). AWS Lambda xử lý logic storing/retrieving (ví dụ: nhận location từ IoT devices, lưu vào DynamoDB, query và return qua API). Multi-tier hoàn chỉnh: API Gateway (API tier) + Lambda (compute tier) + storage (DynamoDB/S3) – scalable, serverless, auto-scale cho peak hours.
- Nguồn tham khảo trong block: https://aws.amazon.com/documentation-overview/kinesis-data-analytics/)Also | https://www.examtopics.com/discussions/amazon/view/85212-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A bicycle sharing company is developing a multi-tier architecture to track the location of its bicycles during peak operating hours. The company wants to use these data points in its existing analytics platform. A solutions architect must determine the most viable multi-tier option to support this architecture. The data points must be accessible from the REST API. Which action meets these requirements for storing and retrieving location data?

### Các lựa chọn
1. Use Amazon Athena with Amazon S3.
2. Use Amazon API Gateway with AWS Lambda.
3. Use Amazon QuickSight with Amazon Redshift.
4. Use Amazon API Gateway with Amazon Kinesis Data Analytics.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty chia sẻ xe đạp đang xây dựng kiến trúc multi-tier (đa tầng) để theo dõi vị trí xe đạp trong giờ cao điểm (peak operating hours). Dữ liệu vị trí (location data points) cần được lưu trữ (storing) và truy xuất (retrieving) để tích hợp vào nền tảng phân tích hiện có (existing analytics platform). Solutions Architect phải chọn giải pháp multi-tier khả thi nhất, với yêu cầu quan trọng: dữ liệu phải accessible qua REST API.

Multi-tier architecture: Thường bao gồm các tầng như presentation (API), application (compute/logic), data (storage), phù hợp cho ứng dụng scalable như tracking real-time.

Yêu cầu cốt lõi:

Lưu trữ và truy xuất dữ liệu vị trí (có thể real-time hoặc near real-time).

REST API làm giao diện chính để access dữ liệu (không phải query trực tiếp hay visualization).

Hỗ trợ analytics platform hiện tại (dữ liệu cần dễ export hoặc integrate).

Bối cảnh AWS (cập nhật 2026): AWS ưu tiên serverless cho multi-tier như API Gateway (API tier) + Lambda (app tier) + DynamoDB/S3 (data tier) để track location, vì scalable, low-latency cho IoT/tracking apps.

📘 Tài liệu tham khảo:

AWS Well-Architected Framework: Serverless Multi-Tier Architectures (aws.amazon.com/architecture).

AWS Documentation: API Gateway + Lambda for REST APIs (docs.aws.amazon.com/apigateway).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Amazon API Gateway with AWS Lambda.

Lý do 🛠️:

API Gateway cung cấp REST API đầy đủ (HTTP/REST endpoints) để expose dữ liệu vị trí, hỗ trợ truy xuất real-time/low-latency từ client (app/mobile).

AWS Lambda xử lý logic storing/retrieving (ví dụ: nhận location từ IoT devices, lưu vào DynamoDB, query và return qua API).

Multi-tier hoàn chỉnh: API Gateway (API tier) + Lambda (compute tier) + storage (DynamoDB/S3) – scalable, serverless, auto-scale cho peak hours.

Tích hợp analytics: Lambda dễ export data sang S3/Redshift cho existing platform.

Phù hợp nhất cho tracking location (IoT-like), chi phí thấp, không cần manage servers (cập nhật 2026: Lambda hỗ trợ Graviton3, API Gateway v2.0 với HTTP APIs nhanh hơn).

📋 Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên yêu cầu storing/retrieving qua REST API và multi-tier.

❌ Use Amazon Athena with Amazon S3.

Sai vì: Athena là query engine serverless cho dữ liệu S3 (query SQL), không cung cấp REST API trực tiếp để store/retrieve real-time. S3 chỉ lưu trữ object, không phù hợp tracking location peak hours (batch-oriented). Không tạo multi-tier API-accessible; chỉ dùng cho analytics query, không integrate mượt với REST client.

✅ Use Amazon API Gateway with AWS Lambda.

Đúng vì: Như giải thích trên – REST API native từ API Gateway + Lambda xử lý store (e.g., DynamoDB putItem) và retrieve (queryItem). Hoàn hảo cho multi-tier serverless, hỗ trợ WebSocket cho real-time tracking (cập nhật 2026: Tích hợp Lambda SnapStart cho cold-start <100ms). Dễ pipe data sang analytics (S3/Kinesis).

❌ Use Amazon QuickSight with Amazon Redshift.

Sai vì: QuickSight là BI visualization tool, Redshift là data warehouse cho analytics lớn (batch ETL). Không có REST API để store/retrieve location data real-time; QuickSight chỉ dashboard, không expose API endpoints. Không phù hợp multi-tier tracking (Redshift latency cao cho peak hours, chi phí cao).

❌ Use Amazon API Gateway with Amazon Kinesis Data Analytics.

Sai vì: API Gateway cung cấp REST API, nhưng Kinesis Data Analytics (nay là Managed Service for Apache Flink) xử lý streaming analytics (real-time processing streams), không phải storing/retrieving đơn giản. Phù hợp process data-in-motion, nhưng không lưu trữ persistent cho query REST (cần thêm storage như S3/DynamoDB). Quá phức tạp cho location tracking cơ bản, không direct retrieve.

🧠 Kết luận nổi bật: Giải pháp serverless (API Gateway + Lambda) là best practice AWS 2026 cho RESTful multi-tier apps với IoT/tracking, đảm bảo scalability và integration analytics. Tránh over-engineering với streaming/BI tools!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85212-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/documentation-overview/kinesis-data-analytics/)Also

## Câu 25

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon DynamoDB
- Takeaway nhanh: Pay-per-request: Chỉ tính phí theo số request thực tế (1/4 chi phí provisioned nếu idle), hoàn hảo cho buổi sáng không dùng → tiết kiệm chi phí lớn. Tự động scale tức thì: Xử lý spikes "rất nhanh" (burst capacity lên 40,000 RCU/WCU/giây mà không cần config), phù hợp traffic unpredictable buổi tối. Không có khái niệm throttle do under-provision. Không cần quản lý auto scaling policy phức tạp, giảm operational overhead (Ops burden) – phù hợp DevOps best practice.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadWriteCapacityMode.html#HowItWorks.OnDemand | https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TroubleshootingThrottling.htmlThis | https://www.examtopics.com/discussions/amazon/view/85743-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is planning to use an Amazon DynamoDB table for data storage. The company is concerned about cost optimization. The table will not be used on most mornings. In the evenings, the read and write traffic will often be unpredictable. When traffic spikes occur, they will happen very quickly. What should a solutions architect recommend?

### Các lựa chọn
1. Create a DynamoDB table in on-demand capacity mode.
2. Create a DynamoDB table with a global secondary index.
3. Create a DynamoDB table with provisioned capacity and auto scaling.
4. Create a DynamoDB table in provisioned capacity mode, and configure it as a global table.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi trắc nghiệm AWS DynamoDB

Chào bạn! 👋 Tôi là một AWS Certified DevOps Engineer Professional với kinh nghiệm sâu rộng về các dịch vụ AWS, đặc biệt là DynamoDB. Hôm nay, tôi sẽ phân tích kỹ lưỡng câu hỏi này theo đúng yêu cầu của bạn. Câu hỏi tập trung vào tối ưu hóa chi phí (cost optimization) cho một bảng DynamoDB với mô hình sử dụng đặc thù:

Bảng không được sử dụng hầu hết vào buổi sáng (thời gian idle thấp traffic).

Buổi tối: Traffic đọc/ghi không thể dự đoán (unpredictable), và spikes xảy ra rất nhanh (very quickly).

Mục tiêu là chọn giải pháp giúp tiết kiệm chi phí mà vẫn xử lý được traffic đột biến mà không bị throttle (hạn chế throughput). DynamoDB cung cấp hai mode chính: On-Demand (tự động scale theo request, pay-per-use) và Provisioned (cấu hình RCU/WCU cố định, có auto scaling). Với pattern này, cần giải pháp không yêu cầu dự phòng trước để tránh lãng phí khi idle, nhưng scale nhanh chóng khi spike.

📘 Tài liệu tham khảo chính:

AWS DynamoDB Developer Guide: Capacity Modes (cập nhật 2024-2026, On-Demand hỗ trợ burst lên đến 40,000 RCU/WCU ngay lập tức).

AWS Well-Architected Framework: Cost Optimization Pillar (Reliability & Performance cho NoSQL).

AWS re:Post & Exam Dumps DOP-C02 (DevOps Professional 2024).

✅ Đáp án đúng: Create a DynamoDB table in on-demand capacity mode.

Lý do lựa chọn chi tiết:

🛠️ On-Demand capacity mode là lựa chọn tối ưu nhất vì:

Pay-per-request: Chỉ tính phí theo số request thực tế (1/4 chi phí provisioned nếu idle), hoàn hảo cho buổi sáng không dùng → tiết kiệm chi phí lớn.

Tự động scale tức thì: Xử lý spikes "rất nhanh" (burst capacity lên 40,000 RCU/WCU/giây mà không cần config), phù hợp traffic unpredictable buổi tối. Không có khái niệm throttle do under-provision.

Không cần quản lý auto scaling policy phức tạp, giảm operational overhead (Ops burden) – phù hợp DevOps best practice.

Cập nhật 2026: On-Demand hỗ trợ DynamoDB Standard Table với SLA 99.999% availability, và tích hợp tốt với AWS Budgets cho cost monitoring.

📋 Phân tích tất cả các phương án (Đúng/Sai)

✅ Create a DynamoDB table in on-demand capacity mode.

Giải thích đúng: Như trên, lý tưởng cho workload unpredictable + idle periods. Tiết kiệm 100% chi phí khi không dùng (không tính phí minimum), scale nhanh <1 giây. Best fit cho cost optimization theo AWS Well-Architected.

❌ Create a DynamoDB table with a global secondary index.

Giải thích sai: Global Secondary Index (GSI) chỉ giúp query linh hoạt hơn trên non-key attributes, không giải quyết cost optimization hay traffic spikes. GSI còn tăng chi phí (riêng RCU/WCU cho index), và có thể throttle nếu index provisioned không đủ. Không liên quan đến capacity mode.

❌ Create a DynamoDB table with provisioned capacity and auto scaling.

Giải thích sai: Provisioned mode yêu cầu set RCU/WCU cố định trước, lãng phí chi phí buổi sáng idle (phải trả minimum dù không dùng). Auto scaling chỉ điều chỉnh sau 1-5 phút (target tracking), không kịp spikes "rất nhanh" → dễ throttle. Không optimal cho unpredictable traffic; AWS recommend On-Demand thay thế.

❌ Create a DynamoDB table in provisioned capacity mode, and configure it as a global table.

Giải thích sai: Provisioned mode như trên đã kém, cộng thêm Global Table (multi-region replication) tăng chi phí replication + RTO/RPO thấp, chỉ phù hợp HA/DR global, không phải cost opt. Spikes vẫn gặp vấn đề scale chậm, và global table yêu cầu provisioned mode ở tất cả regions → chi phí cao hơn.

Kết luận 💡: On-Demand là "no-brainer" cho scenario này. Nếu implement, combine với DynamoDB Accelerator (DAX) cho read cache nếu cần low-latency, hoặc AWS Cost Explorer để monitor. Bạn có câu hỏi nào khác không? 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85743-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadWriteCapacityMode.html#HowItWorks.OnDemand

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TroubleshootingThrottling.htmlThis

## Câu 26

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon Certificate Manager
- Đáp án tham khảo: **Use AWS Key Management Service (AWS KMS) to protect the encryption keys.**
- Takeaway nhanh: AWS KMS là dịch vụ fully managed key management chuyên dụng cho việc tạo, lưu trữ, quản lý và sử dụng khóa mã hóa symmetric/asymmetric. Nó giảm operational burden tối đa vì AWS chịu trách nhiệm về scalability (hàng triệu requests/giây), HA (99.99% SLA), key rotation tự động, audit logs qua CloudTrail. Hỗ trợ developers dễ dàng tích hợp qua SDK/API (Java, Python...), envelope encryption cho ứng dụng.
- Nguồn tham khảo trong block: https://aws.amazon.com/kms/faqs/#:~:text=If%20you%20are%20a%20developer%20who%20needs%20to%20digitally,a%20broad%20set%20of%20industry%20and%20regional%20compliance%20regimes.Most | https://www.examtopics.com/discussions/amazon/view/85942-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to build a scalable key management infrastructure to support developers who need to encrypt data in their applications. What should a solutions architect do to reduce the operational burden?

### Các lựa chọn
1. Use multi-factor authentication (MFA) to protect the encryption keys.
2. Use AWS Key Management Service (AWS KMS) to protect the encryption keys.
3. Use AWS Certificate Manager (ACM) to create, store, and assign the encryption keys.
4. Use an IAM policy to limit the scope of users who have access permissions to protect the encryption keys.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc xây dựng một hạ tầng quản lý khóa (key management infrastructure) có khả năng mở rộng (scalable) để hỗ trợ các lập trình viên (developers) mã hóa dữ liệu trong ứng dụng của họ. Mục tiêu chính là giảm gánh nặng vận hành (operational burden) cho solutions architect.

📝 Chi tiết câu hỏi:

Công ty cần một giải pháp managed và scalable để quản lý khóa mã hóa, tránh tự xây dựng hệ thống phức tạp (như HSM tự quản lý).

Nhấn mạnh vào bảo vệ khóa mã hóa (protect the encryption keys), không chỉ mã hóa dữ liệu mà còn quản lý khóa một cách an toàn, dễ dàng tích hợp với các dịch vụ AWS khác như S3, EBS, RDS.

Giải pháp phải giảm operational burden, nghĩa là ưu tiên dịch vụ AWS managed service để tránh phải lo về patching, scaling, high availability, backup... (theo AWS Well-Architected Framework - Pillar Reliability và Security).

🛠️ Bối cảnh AWS mới nhất (đến 2026): AWS KMS hỗ trợ key rotation tự động, multi-Region keys, integration với AWS Secrets Manager, và các tính năng mới như KMS Custom Key Store với CloudHSM, giúp scalable mà không cần quản lý hạ tầng.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use AWS Key Management Service (AWS KMS) to protect the encryption keys.

Lý do:

AWS KMS là dịch vụ fully managed key management chuyên dụng cho việc tạo, lưu trữ, quản lý và sử dụng khóa mã hóa symmetric/asymmetric. Nó giảm operational burden tối đa vì AWS chịu trách nhiệm về scalability (hàng triệu requests/giây), HA (99.99% SLA), key rotation tự động, audit logs qua CloudTrail.

Hỗ trợ developers dễ dàng tích hợp qua SDK/API (Java, Python...), envelope encryption cho ứng dụng.

Phù hợp hoàn hảo với yêu cầu "scalable key management infrastructure" mà không cần tự build.

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết:

❌ Use multi-factor authentication (MFA) to protect the encryption keys.

Phương án này sai vì MFA chỉ là biện pháp bảo mật truy cập (authentication) cho IAM users/roles, không phải dịch vụ quản lý khóa mã hóa. Nó không xây dựng hạ tầng key management scalable, mà chỉ tăng lớp bảo vệ login – không giải quyết vấn đề mã hóa dữ liệu cho developers hay giảm operational burden.

✅ Use AWS Key Management Service (AWS KMS) to protect the encryption keys.

Phương án này đúng (như đã giải thích ở trên). KMS là lựa chọn tối ưu theo best practices AWS, hỗ trợ FIPS 140-2/3 validated HSM, và tích hợp sâu với 100+ dịch vụ AWS.

❌ Use AWS Certificate Manager (ACM) to create, store, and assign the encryption keys.

Phương án này sai vì ACM chuyên quản lý certificates (SSL/TLS) cho HTTPS, không phải encryption keys cho dữ liệu ứng dụng (data at rest/transit). ACM không hỗ trợ symmetric keys hay envelope encryption; dùng sai sẽ không scalable cho developers mã hóa data.

❌ Use an IAM policy to limit the scope of users who have access permissions to protect the encryption keys.

Phương án này sai vì IAM policy chỉ là công cụ kiểm soát truy cập (authorization), không tạo ra hạ tầng quản lý khóa. Nó bổ trợ cho KMS (qua key policies), nhưng không thay thế được việc build scalable infrastructure – vẫn cần KMS hoặc tương đương để lưu trữ/quản lý keys.

📘 Tài liệu tham khảo

AWS KMS Documentation: AWS Key Management Service (cập nhật 2024-2026: hỗ trợ post-quantum cryptography previews).

AWS Well-Architected Framework - Security Pillar: Khuyến nghị KMS cho key management để giảm operational overhead.

AWS Security Best Practices: Encrypting Data at Rest.

Exam Prep: AWS Certified Solutions Architect Professional DOP-C02 blueprint (Domain 2: Design Resilient Architectures).

Hy vọng phân tích này giúp bạn nắm vững! 🚀 Nếu cần thêm ví dụ code hoặc lab, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85942-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/kms/faqs/#:~:text=If%20you%20are%20a%20developer%20who%20needs%20to%20digitally,a%20broad%20set%20of%20industry%20and%20regional%20compliance%20regimes.Most

## Câu 27

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EC2, Security groups
- Takeaway nhanh: Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html | https://www.examtopics.com/discussions/amazon/view/85346-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company. How should security groups be configured in this situation? (Choose two.)

### Các lựa chọn
1. Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.
2. Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.
3. Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.
4. Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.
5. Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng web hai tầng (two-tier web application) được thiết kế bởi Solutions Architect trên AWS:

Tầng web (web tier): Được host trên các instance Amazon EC2 trong public subnets, tiếp xúc trực tiếp với internet (public-facing), thường phục vụ traffic HTTPS trên port 443.

Tầng database (database tier): Chạy Microsoft SQL Server trên Amazon EC2 trong private subnet, không tiếp xúc trực tiếp với internet để đảm bảo bảo mật cao (security là ưu tiên hàng đầu).

Mục tiêu: Cấu hình Security Groups (SG) để cho phép giao tiếp an toàn giữa các tầng, đồng thời bảo vệ khỏi truy cập không mong muốn. Security Groups hoạt động như stateful firewall (tự động cho phép return traffic), chỉ cần cấu hình inbound rules chính là đủ trong hầu hết trường hợp. Câu hỏi yêu cầu chọn hai lựa chọn đúng theo best practice AWS (cập nhật đến 2026, không thay đổi cơ bản so với phiên bản VPC hiện tại).

📘 Tài liệu tham khảo:

AWS VPC Security Groups (Reference: Rule evaluation, referencing other SGs).

AWS Well-Architected Framework - Security Pillar (Best practices for tiered apps).

✅ Đáp án đúng (Chọn hai)

Hai lựa chọn đúng là:

Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

Lý do: Tầng web public-facing cần chấp nhận traffic HTTPS từ internet (anywhere: 0.0.0.0/0) trên port 443 để người dùng truy cập. Đây là inbound rule chuẩn cho web server công khai, tuân thủ nguyên tắc least privilege bằng cách chỉ mở port cần thiết.

Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.

Lý do: Database MS SQL Server lắng nghe trên port 1433. Private subnet chỉ cho phép web tier (qua SG reference) kết nối inbound, không mở cho internet. Sử dụng SG-to-SG referencing là best practice bảo mật cao, động và không cần hardcode IP.

🛠️ Lưu ý chung: Outbound rules mặc định cho phép tất cả traffic (ephemeral ports), nên không cần config outbound cụ thể cho web-to-DB flow (stateful nature của SG).

🧩 Phân tích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh, đánh dấu ✅ (đúng) hoặc ❌ (sai), kèm giải thích bằng tiếng Việt:

✅ Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

🟢 Đúng: Inbound từ internet (0.0.0.0/0) trên port 443 là bắt buộc cho web tier public-facing phục vụ HTTPS. Không mở port này thì ứng dụng không accessible.

❌ Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.

🔴 Sai: Outbound từ web tier không cần chỉ định "from 0.0.0.0/0" trên port 443 (web không gửi HTTPS ra internet). Outbound mặc định đã cho phép kết nối đến DB (port 1433), và "from 0.0.0.0/0" là outbound source không hợp lý (outbound dùng destination CIDR).

✅ Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.

🟢 Đúng: Inbound chỉ port 1433 (MS SQL) từ SG của web tier là chính xác, đảm bảo chỉ web server kết nối được DB trong private subnet. SG referencing linh hoạt và an toàn hơn IP-based rules.

❌ Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.

🔴 Sai: DB không cần outbound cụ thể đến web trên 443/1433 (DB không initiate kết nối HTTPS hoặc SQL ra ngoài). Outbound mặc định đủ cho return traffic, và config này thừa + mở rộng không cần thiết.

❌ Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.

🔴 Sai: DB chỉ cần inbound 1433 (SQL), không cần 443 (HTTPS dành cho web). Mở thêm 443 vi phạm least privilege, tăng rủi ro bảo mật dù chỉ từ web SG.

Hy vọng phân tích này giúp bạn nắm vững Security Groups best practices cho multi-tier apps! 🚀 Nếu cần ví dụ CloudFormation hoặc Terraform, hãy hỏi thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85346-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html

## Câu 28

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon EC2
- Đáp án tham khảo: **Implement EC2 Spot Instances.**
- Takeaway nhanh: EC2 Spot Instances cung cấp giá rẻ hơn đến 90% so với On-Demand (dữ liệu AWS 2026), lý tưởng cho workload stateless, fault-tolerant, và có thể bị interrupt (2 phút warning trước khi AWS reclaim capacity). Hỗ trợ scalable qua EC2 Spot Fleet, Spot Blocks (cho thời gian dự đoán), hoặc Auto Scaling Groups với Spot Instances (Mixed Instances Policy với Capacity-optimized allocation strategy mới nhất).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86038-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a highly dynamic batch processing job that uses many Amazon EC2 instances to complete it. The job is stateless in nature, can be started and stopped at any given time with no negative impact, and typically takes upwards of 60 minutes total to complete. The company has asked a solutions architect to design a scalable and cost-effective solution that meets the requirements of the job. What should the solutions architect recommend?

### Các lựa chọn
1. Implement EC2 Spot Instances.
2. Purchase EC2 Reserved Instances.
3. Implement EC2 On-Demand Instances.
4. Implement the processing on AWS Lambda.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧠 Phân tích chi tiết câu hỏi trắc nghiệm AWS (Chủ đề: EC2 Instance Types cho Batch Processing)

📌 1. Giải thích nội dung câu hỏi một cách chi tiết và rõ ràng:

Câu hỏi mô tả một công việc xử lý batch động cao (highly dynamic batch processing job) sử dụng nhiều instance Amazon EC2 để hoàn thành. Đặc điểm quan trọng:

Stateless (không trạng thái): Không lưu trữ dữ liệu trạng thái giữa các lần chạy, dễ dàng phân tán và phục hồi.

Có thể start/stop bất kỳ lúc nào mà không ảnh hưởng tiêu cực: Chịu lỗi tốt (fault-tolerant), phù hợp với môi trường có thể bị gián đoạn.

Thời gian chạy thường >60 phút: Workload dài hạn, cần xử lý lớn với nhiều instance.

Yêu cầu: Solutions Architect thiết kế giải pháp scalable (có khả năng mở rộng linh hoạt) và cost-effective (tiết kiệm chi phí tối ưu). Đây là tình huống điển hình cho các workload batch như data processing, ML training, hoặc rendering, nơi ưu tiên chi phí thấp mà không cần uptime 100% guaranteed (theo best practices AWS đến 2026 với Spot Instances hỗ trợ Diversified allocation và Capacity-optimized strategies).

✅ 2. Đáp án đúng và lý do lựa chọn:

Đáp án đúng: Implement EC2 Spot Instances.

🛠️ Lý do chi tiết:

EC2 Spot Instances cung cấp giá rẻ hơn đến 90% so với On-Demand (dữ liệu AWS 2026), lý tưởng cho workload stateless, fault-tolerant, và có thể bị interrupt (2 phút warning trước khi AWS reclaim capacity).

Hỗ trợ scalable qua EC2 Spot Fleet, Spot Blocks (cho thời gian dự đoán), hoặc Auto Scaling Groups với Spot Instances (Mixed Instances Policy với Capacity-optimized allocation strategy mới nhất).

Phù hợp hoàn hảo với job >60 phút, dynamic (start/stop linh hoạt), và batch nature – AWS khuyến nghị Spot cho 70-80% batch workloads để tối ưu chi phí mà vẫn đạt SLA cao (savings plans tích hợp Spot từ 2024+).

Kết quả: Cost-effective nhất mà vẫn scalable, với interruption handling qua checkpoints hoặc diversification.

🧩 3. Giải thích tất cả các phương án (đúng và sai):

Dưới đây là phân tích từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Phân tích sử dụng kiến thức AWS mới nhất (2026): Spot Instances hỗ trợ ARM/Graviton4, Lambda runtime limits 15 phút, Reserved/On-Demand không ưu tiên cho interruptible workloads.

✅ Implement EC2 Spot Instances.

🟢 Đúng vì: Như giải thích ở trên – tối ưu chi phí (up to 90% savings), hỗ trợ scale với Spot Fleet/ASG, fault-tolerant cho stateless batch jobs dài hạn. AWS best practices khuyến nghị cho workloads như này (xem EC2 User Guide 2026).

❌ Purchase EC2 Reserved Instances.

🔴 Sai vì: Reserved Instances (Standard/Convertible) yêu cầu cam kết 1-3 năm upfront hoặc monthly, không linh hoạt cho dynamic job (start/stop bất kỳ). Nếu bị dừng, vẫn phải trả phí – không cost-effective cho interruptible workloads. Phù hợp hơn cho steady-state apps (Savings Plans mới hỗ trợ Spot nhưng không thay thế Reserved cho batch dynamic).

❌ Implement EC2 On-Demand Instances.

🔴 Sai vì: On-Demand đắt nhất (baseline price), pay-per-hour/second mà không discount, không tận dụng được tính interruptible của job. Scalable qua ASG nhưng thiếu cost-effective (Spot rẻ hơn 3x), chỉ dùng khi cần guaranteed capacity 100%.

❌ Implement the processing on AWS Lambda.

🔴 Sai vì: Lambda có giới hạn execution time 15 phút maximum (không thay đổi đến 2026), không phù hợp job >60 phút. Lambda stateless/serverless tốt cho short bursts nhưng batch dài cần EC2/Fargate/Spot. Chi phí có thể cao nếu invoke nhiều, không scalable cho "many EC2 instances" equivalent.

📘 4. Tài liệu tham khảo (AWS Documentation cập nhật 2026):

🛠️ EC2 Spot Instances Best Practices – Hướng dẫn batch workloads.

📚 EC2 Auto Scaling with Spot – Mixed Instances Policy cho scale.

🔗 AWS Well-Architected Framework - Cost Optimization Pillar – Khuyến nghị Spot cho fault-tolerant jobs.

📊 Reserved Instances vs Spot Comparison – Savings data thực tế.

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm ví dụ code Terraform/CloudFormation cho Spot Fleet, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86038-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 29

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon Certificate Manager, Amazon EC2
- Đáp án tham khảo: **Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM.**
- Takeaway nhanh: Import cert vào ACM: Cho phép AWS quản lý cert tự động (renewal, validation), hỗ trợ cert private từ bên thứ 3 (không chỉ public cert). Tạo ALB với HTTPS listener: ALB (layer 7) xử lý SSL termination thay EC2 → traffic từ client đến ALB là HTTPS, từ ALB đến EC2 backend là HTTP (plain text). Giảm tải CPU EC2 lên đến 80-90% do offload crypto operations. Lợi ích scale: ALB auto-scale theo traffic, hỗ trợ sticky sessions, path-based routing cho dynamic web app. Tích hợp ASG để thêm EC2 nếu cần.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/elastic-load-balancer-support-for-ssl-termination/ | https://www.examtopics.com/discussions/amazon/view/85943-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a dynamic web application hosted on two Amazon EC2 instances. The company has its own SSL certificate, which is on each instance to perform SSL termination. There has been an increase in traffic recently, and the operations team determined that SSL encryption and decryption is causing the compute capacity of the web servers to reach their maximum limit. What should a solutions architect do to increase the application's performance?

### Các lựa chọn
1. Create a new SSL certificate using AWS Certificate Manager (ACM). Install the ACM certificate on each instance.
2. Create an Amazon S3 bucket Migrate the SSL certificate to the S3 bucket. Configure the EC2 instances to reference the bucket for SSL termination.
3. Create another EC2 instance as a proxy server. Migrate the SSL certificate to the new instance and configure it to direct connections to the existing EC2 instances.
4. Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một công ty đang chạy ứng dụng web động (dynamic web application) trên hai instance Amazon EC2. Họ tự quản lý chứng chỉ SSL riêng (self-managed SSL certificate) được cài đặt trực tiếp trên từng EC2 instance để thực hiện SSL termination (giải mã SSL ngay tại server, chuyển traffic thành HTTP plain text).

Gần đây, lưu lượng truy cập tăng đột biến, dẫn đến CPU của các web server đạt giới hạn tối đa chủ yếu do quá trình mã hóa/giải mã SSL (encryption/decryption) tiêu tốn nhiều tài nguyên compute.

Vấn đề cốt lõi: SSL offloading chưa được áp dụng, khiến EC2 phải chịu toàn bộ gánh nặng xử lý SSL → bottleneck về performance.

Mục tiêu của Solutions Architect: Tăng hiệu suất ứng dụng bằng cách offload (chuyển gánh nặng) SSL termination ra khỏi EC2, tận dụng các dịch vụ AWS managed để scale tự động, giảm tải CPU cho backend.

📘 Kiến thức cập nhật (AWS 2026): Theo best practices mới nhất từ AWS Well-Architected Framework (Security & Reliability Pillars), sử dụng Application Load Balancer (ALB) kết hợp AWS Certificate Manager (ACM) là giải pháp chuẩn cho SSL offloading ở layer 7, hỗ trợ TLS 1.3 và tích hợp seamless với Auto Scaling Groups (ASG).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM.

Lý do chọn đáp án này 🛠️:

Import cert vào ACM: Cho phép AWS quản lý cert tự động (renewal, validation), hỗ trợ cert private từ bên thứ 3 (không chỉ public cert).

Tạo ALB với HTTPS listener: ALB (layer 7) xử lý SSL termination thay EC2 → traffic từ client đến ALB là HTTPS, từ ALB đến EC2 backend là HTTP (plain text). Giảm tải CPU EC2 lên đến 80-90% do offload crypto operations.

Lợi ích scale: ALB auto-scale theo traffic, hỗ trợ sticky sessions, path-based routing cho dynamic web app. Tích hợp ASG để thêm EC2 nếu cần.

Best practice 2026: AWS khuyến nghị ALB + ACM cho high-traffic apps, thay vì self-managed cert trên EC2 (dễ lỗi config, không auto-renew).

❌ Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên tính khả thi, hiệu quả và best practices AWS.

Phương án A (SAI): Create a new SSL certificate using AWS Certificate Manager (ACM). Install the ACM certificate on each instance.

❌ Giải thích sai: Tạo cert mới qua ACM (chỉ hỗ trợ public cert từ AWS/CA khác, không import private cert dễ dàng) và cài thủ công lên EC2 không giải quyết vấn đề gốc. EC2 vẫn phải xử lý SSL termination → CPU vẫn overload. ACM cert không "managed" nếu cài thủ công, mất lợi ích auto-renew. Không offload được gì!

Phương án B (SAI): Create an Amazon S3 bucket Migrate the SSL certificate to the S3 bucket. Configure the EC2 instances to reference the bucket for SSL termination.

❌ Giải thích sai: S3 là object storage, không hỗ trợ SSL termination hay reference cert cho HTTPS. Cert chỉ là file (.pem), không thể "reference" từ S3 để EC2 dùng động (phải download thủ công, không real-time). Điều này vi phạm security (public S3 bucket lộ cert) và tăng latency/CPU do fetch file. Hoàn toàn không khả thi theo AWS docs!

Phương án C (SAI): Create another EC2 instance as a proxy server. Migrate the SSL certificate to the new instance and configure it to direct connections to the existing EC2 instances.

❌ Giải thích sai: Tạo EC2 proxy (như Nginx/HAProxy) để offload SSL là ý tưởng cũ kỹ, tăng chi phí quản lý (cần scale proxy riêng, monitor failover). Không tận dụng AWS managed services, dễ single point of failure nếu proxy overload. AWS 2026 ưu tiên ALB (managed, cheaper) thay vì self-built proxy → không scalable và kém efficient.

Phương án D (ĐÚNG): Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM.

✅ Giải thích đúng (đã chi tiết ở phần trên): Offload hoàn hảo, managed toàn bộ, scale tự động. Hoàn thành yêu cầu "tăng performance" mà không thay đổi app code.

📘 Tài liệu tham khảo (AWS Official - cập nhật 2026)

AWS Docs - ALB SSL Termination: docs.aws.amazon.com/elasticloadbalancing/latest/application/https-listener.html → Hướng dẫn HTTPS listener với ACM.

ACM Import Cert: docs.aws.amazon.com/acm/latest/userguide/import-certificate.html → Hỗ trợ import private cert.

Well-Architected Labs - SSL Offloading: aws.amazon.com/architecture/well-architected/ → Reliability pillar, ví dụ ALB offload.

Exam Prep (DOPE): AWS Certified DevOps Engineer Professional Exam Guide 2026 nhấn mạnh ALB + ACM cho high-traffic web apps.

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần thêm case study, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85943-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/aws/elastic-load-balancer-support-for-ssl-termination/

## Câu 30

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon Lambda, Amazon CloudWatch, Amazon S3, Amazon EC2
- Takeaway nhanh: Kết hợp này giảm coupling hoàn hảo: Upload trực tiếp từ browser → S3 (bypass EC2, giảm tải 100% cho website). Sau upload, S3 tự trigger Lambda resize serverless (không cần EC2 xử lý resize). Cải thiện performance: Upload song song từ client, scale vô hạn với S3 + Lambda. Operationally efficient: Zero server management, auto-scale. Phù hợp best practice AWS: Direct-to-S3 upload + event-driven architecture (2026 vẫn là pattern chuẩn).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/compute/uploading-large-objects-to-amazon-s3-using-multipart-upload-and-transfer-acceleration/ | https://www.examtopics.com/discussions/amazon/view/86471-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A social media company allows users to upload images to its website. The website runs on Amazon EC2 instances. During upload requests, the website resizes the images to a standard size and stores the resized images in Amazon S3. Users are experiencing slow upload requests to the website. The company needs to reduce coupling within the application and improve website performance. A solutions architect must design the most operationally efficient process for image uploads. Which combination of actions should the solutions architect take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Configure the application to upload images to S3 Glacier.
2. Configure the web server to upload the original images to Amazon S3.
3. Configure the application to upload images directly from each user's browser to Amazon S3 through the use of a presigned URL
4. Configure S3 Event Notifications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.
5. Create an Amazon EventBridge (Amazon CloudWatch Events) rule that invokes an AWS Lambda function on a schedule to resize uploaded images.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty mạng xã hội cho phép người dùng upload hình ảnh lên website chạy trên Amazon EC2 instances. Quá trình hiện tại: Khi nhận request upload, website resize hình ảnh ngay trên EC2 rồi lưu hình đã resize vào Amazon S3. Vấn đề: Yêu cầu upload chậm (slow upload requests).

Yêu cầu thiết kế:

Giảm coupling (loose coupling) trong ứng dụng (tức là làm cho các thành phần độc lập hơn, không phụ thuộc lẫn nhau).

Cải thiện hiệu suất website (improve website performance).

Quy trình operationally efficient nhất cho việc upload hình ảnh (hiệu quả vận hành cao, tự động hóa, ít can thiệp thủ công).

Solutions Architect cần chọn KẾT HỢP 2 hành động (Choose two) để giải quyết.

🛠️ Mục tiêu cốt lõi: Chuyển việc upload/resizing khỏi EC2 (giảm tải CPU/băng thông cho EC2), tận dụng serverless để decoupled và scale tự động. Kiến thức dựa trên AWS Well-Architected Framework (Pillar: Operational Excellence & Reliability) phiên bản mới nhất 2024-2026.

📘 Tài liệu tham khảo:

AWS S3 Presigned URLs

S3 Event Notifications with Lambda

AWS Well-Architected Framework

✅ Đáp án đúng (Chọn TWO)

Hai lựa chọn đúng là:

Configure the application to upload images directly from each user's browser to Amazon S3 through the use of a presigned URL

Configure S3 Event Notifications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.

Lý do chọn (tổng hợp):

Kết hợp này giảm coupling hoàn hảo: Upload trực tiếp từ browser → S3 (bypass EC2, giảm tải 100% cho website). Sau upload, S3 tự trigger Lambda resize serverless (không cần EC2 xử lý resize).

Cải thiện performance: Upload song song từ client, scale vô hạn với S3 + Lambda. Operationally efficient: Zero server management, auto-scale.

Phù hợp best practice AWS: Direct-to-S3 upload + event-driven architecture (2026 vẫn là pattern chuẩn).

🔍 Giải thích chi tiết TẤT CẢ các phương án

Dưới đây là phân tích từng lựa chọn giữ nguyên văn bản gốc tiếng Anh, kèm giải thích sai/đúng bằng tiếng Việt. Sử dụng kiến thức AWS cập nhật (S3 Event Notifications vẫn hỗ trợ Lambda/Step Functions đến 2026).

❌ Configure the application to upload images to S3 Glacier.

Sai vì: S3 Glacier là lớp lưu trữ lạnh giá rẻ (cold storage), thời gian truy xuất chậm (phút đến giờ), không phù hợp cho hình ảnh cần resize nhanh và phục vụ user. Upload vào Glacier làm chậm hơn nữa, vi phạm yêu cầu "improve performance". Không giảm coupling vì vẫn qua app/EC2.

❌ Configure the web server to upload the original images to Amazon S3.

Sai vì: Chỉ upload original images lên S3 từ web server (EC2), nhưng vẫn giữ tải upload/resizing trên EC2 → không giảm tải, không cải thiện tốc độ upload. Vẫn tightly coupled (app phụ thuộc S3), không efficient operationally (EC2 vẫn bottleneck).

✅ Configure the application to upload images directly from each user's browser to Amazon S3 through the use of a presigned URL

Đúng vì: Sử dụng presigned URL (URL tạm thời có chữ ký) cho phép browser upload trực tiếp vào S3 mà không qua EC2. Giảm coupling (client độc lập S3), cải thiện performance (upload parallel, S3 scale vô hạn). Best practice cho large files (hỗ trợ multipart upload).

✅ Configure S3 Event Notifications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.

Đúng vì: S3 Event Notifications trigger Lambda real-time khi có object mới (event: s3:ObjectCreated:*). Lambda resize async, serverless → decoupled hoàn toàn khỏi EC2, scale auto, chi phí thấp. Efficient hơn resize sync trên EC2. (Lưu ý: Lưu resized image vào bucket khác hoặc overwrite).

❌ Create an Amazon EventBridge (Amazon CloudWatch Events) rule that invokes an AWS Lambda function on a schedule to resize uploaded images.

Sai vì: EventBridge theo lịch trình (schedule) → resize không real-time (delay, backlog nếu upload nhiều), kém efficient operationally (phải scan bucket định kỳ, tốn chi phí). Không event-driven chuẩn như S3 Notifications, vi phạm "operationally efficient process".

🧩 Kết luận: Kết hợp 2 đáp án đúng tạo architecture serverless hoàn hảo: Client → S3 (presigned) → Lambda resize → S3 resized. Giảm chi phí, tăng reliability! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86471-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/compute/uploading-large-objects-to-amazon-s3-using-multipart-upload-and-transfer-acceleration/

## Câu 31

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lambda, Auto Scaling Group, Amazon CloudFront, Amazon S3, Amazon WAF, Amazon EC2
- Takeaway nhanh: S3 lưu trữ file tĩnh (HTML, CSS, JS), tự động scale vô hạn, không cần server/patching. CloudFront làm CDN phân phối global, hỗ trợ HTTPS miễn phí (ACM certificates), edge caching giảm latency, tích hợp security (AWS Shield, WAF). Least overhead: Chỉ upload file 4 lần/năm, AWS tự quản lý mọi thứ. Scalability cao (triệu request/giây), security tốt (origin access control, HTTPS enforcement). Hoàn toàn phù hợp phiên bản AWS 2026 (S3/CloudFront vẫn là best practice cho static sites).
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/ | https://aws.amazon.com/serverless/ | https://www.examtopics.com/discussions/amazon/view/85996-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company uses a popular content management system (CMS) for its corporate website. However, the required patching and maintenance are burdensome. The company is redesigning its website and wants anew solution. The website will be updated four times a year and does not need to have any dynamic content available. The solution must provide high scalability and enhanced security. Which combination of changes will meet these requirements with the LEAST operational overhead? (Choose two.)

### Các lựa chọn
1. Configure Amazon CloudFront in front of the website to use HTTPS functionality.
2. Deploy an AWS WAF web ACL in front of the website to provide HTTPS functionality.
3. Create and deploy an AWS Lambda function to manage and serve the website content.
4. Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.
5. Create the new website. Deploy the website by using an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty đang sử dụng hệ thống quản lý nội dung (CMS) phổ biến cho website doanh nghiệp, nhưng việc vá lỗi (patching) và bảo trì (maintenance) rất tốn kém và phức tạp. Họ đang thiết kế lại website mới với các yêu cầu cụ thể:

Website chỉ được cập nhật 4 lần/năm (ít thường xuyên).

Không có nội dung động (không dynamic content, tức là hoàn toàn tĩnh - static).

Giải pháp phải đảm bảo khả năng mở rộng cao (high scalability).

Tăng cường bảo mật (enhanced security).

Giảm thiểu tối đa gánh nặng vận hành (LEAST operational overhead) - ưu tiên giải pháp serverless, không cần quản lý server.

Yêu cầu chọn TWO thay đổi kết hợp để đáp ứng tất cả. Giải pháp lý tưởng là sử dụng Amazon S3 cho static website hosting (vì static, scalable, zero server management) kết hợp Amazon CloudFront (CDN cho scalability toàn cầu, HTTPS, security features như DDoS protection và WAF integration), giúp loại bỏ hoàn toàn patching/maintenance của CMS truyền thống.

✅ Đáp án đúng và lý do lựa chọn

Hai đáp án đúng là:

Configure Amazon CloudFront in front of the website to use HTTPS functionality.

Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.

Lý do lựa chọn:

🛠️ Kết hợp S3 Static Website Hosting và CloudFront là giải pháp serverless tối ưu cho website tĩnh:

S3 lưu trữ file tĩnh (HTML, CSS, JS), tự động scale vô hạn, không cần server/patching.

CloudFront làm CDN phân phối global, hỗ trợ HTTPS miễn phí (ACM certificates), edge caching giảm latency, tích hợp security (AWS Shield, WAF).

Least overhead: Chỉ upload file 4 lần/năm, AWS tự quản lý mọi thứ. Scalability cao (triệu request/giây), security tốt (origin access control, HTTPS enforcement). Hoàn toàn phù hợp phiên bản AWS 2026 (S3/CloudFront vẫn là best practice cho static sites).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên nội dung gốc bằng tiếng Anh, đánh dấu ✅ (đúng) hoặc ❌ (sai), và giải thích đầy đủ bằng tiếng Việt:

Configure Amazon CloudFront in front of the website to use HTTPS functionality.

✅ Đúng. CloudFront là dịch vụ CDN edge của AWS, hỗ trợ HTTPS out-of-the-box với chứng chỉ ACM miễn phí, cache nội dung tĩnh từ S3, scale global tự động. Giảm overhead (không quản lý origin server), tăng security (DDoS protection, geo-restrictions). Kết hợp hoàn hảo với S3 cho static site.

Deploy an AWS WAF web ACL in front of the website to provide HTTPS functionality.

❌ Sai. AWS WAF (Web Application Firewall) chỉ bảo vệ chống tấn công web (SQLi, XSS), không cung cấp HTTPS (WAF cần attach vào CloudFront/ALB/NLB để hoạt động). Sử dụng WAF đơn lẻ không giải quyết HTTPS/scalability, và vẫn cần origin hỗ trợ HTTPS riêng. Overhead cao hơn vì thiếu CDN.

Create and deploy an AWS Lambda function to manage and serve the website content.

❌ Sai. Lambda là serverless compute cho code động, không phù hợp static website (overkill cho file tĩnh, chi phí cao hơn S3 nếu traffic lớn). Quản lý content qua Lambda cần code custom phức tạp, tăng overhead (debug/deploy function), không scale rẻ như S3+CloudFront. Không đáp ứng "least overhead" cho static updates 4 lần/năm.

Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.

✅ Đúng. S3 Static Website Hosting biến bucket thành web server tĩnh, zero server management (không patching/EC2), scale vô hạn, chi phí theo usage thấp. Hỗ trợ HTTPS qua CloudFront/CloudFront origin. Lý tưởng cho website tĩnh cập nhật ít, overhead minimum (chỉ upload file).

Create the new website. Deploy the website by using an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer.

❌ Sai. EC2 + Auto Scaling Group + ALB yêu cầu quản lý server thủ công (patching OS, AMI updates, scaling policies), overhead cao giống CMS cũ. Không "least overhead", dù scalable nhưng tốn kém cho static site (chạy server idle). Security tốt nhưng phức tạp hơn serverless.

📘 Tài liệu tham khảo (AWS cập nhật đến 2026)

Amazon S3 Static Website Hosting: docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html - Best practice cho static sites.

Amazon CloudFront với S3: docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html - HTTPS & OAI integration.

AWS Well-Architected Framework - Serverless Lens: aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-lens-whitepapers.q=whitepapers%2Fserverless-lens%2F - Xác nhận S3+CloudFront least overhead cho static content.

Exam DOP-C02 Guide: Static hosting là key topic trong DevOps Professional (2026 syllabus).

Giải pháp này giúp công ty chuyển từ CMS nặng nề sang serverless 100%, tiết kiệm chi phí và thời gian! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85996-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/serverless/

https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/

## Câu 32

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EFS, Amazon S3
- Đáp án tham khảo: **Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.**
- Takeaway nhanh: S3 Object Lock (tính năng chính) cho phép đặt retention period (thời gian lưu giữ) lên từng object, làm chúng immutable – không thể overwrite, modify hoặc delete trong khoảng thời gian đó (hỗ trợ hai mode: Governance và Compliance). Điều này hoàn toàn đáp ứng yêu cầu quy định. S3 Versioning bổ trợ bằng cách giữ tất cả versions của object, ngay cả khi có overwrite (nhưng Object Lock ngăn chặn overwrite/delete).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html | https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html | https://www.examtopics.com/discussions/amazon/view/85751-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement. new documents cannot be modified or deleted after they are stored. What should a solutions architect do to meet this requirement?

### Các lựa chọn
1. Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.
2. Store the uploaded documents in an Amazon S3 bucket. Configure an S3 Lifecycle policy to archive the documents periodically.
3. Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Configure an ACL to restrict all access to read-only.
4. Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi xoay quanh một ứng dụng web sản xuất (production web application) nơi người dùng upload tài liệu (documents) qua giao diện web hoặc ứng dụng di động (mobile app). Theo yêu cầu quy định mới (new regulatory requirement), các tài liệu sau khi được lưu trữ không được phép chỉnh sửa (modified) hoặc xóa (deleted). Vai trò của Solutions Architect là thiết kế giải pháp đảm bảo tính immutable (không thể thay đổi) cho dữ liệu này trên AWS, phù hợp với các tiêu chuẩn tuân thủ như WORM (Write Once, Read Many). 🛡️ Đây là yêu cầu phổ biến trong các ngành tài chính, y tế hoặc pháp lý để chống tampering dữ liệu.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.

Lý do chi tiết:

S3 Object Lock (tính năng chính) cho phép đặt retention period (thời gian lưu giữ) lên từng object, làm chúng immutable – không thể overwrite, modify hoặc delete trong khoảng thời gian đó (hỗ trợ hai mode: Governance và Compliance). Điều này hoàn toàn đáp ứng yêu cầu quy định.

S3 Versioning bổ trợ bằng cách giữ tất cả versions của object, ngay cả khi có overwrite (nhưng Object Lock ngăn chặn overwrite/delete).

Giải pháp này scalable, cost-effective cho object storage lớn, và hỗ trợ compliance certifications như SEC Rule 17a-4(f), FINRA. Theo tài liệu AWS cập nhật 2026, Object Lock là lựa chọn chuẩn cho immutable storage trên S3. 📘

Tài liệu tham khảo:

AWS S3 Object Lock

S3 Versioning

🛠️ Phân tích chi tiết tất cả các phương án

Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.

✅ Đúng. Như giải thích ở trên, sự kết hợp này đảm bảo documents immutable hoàn toàn. Object Lock chặn mọi modify/delete theo retention policy, Versioning giữ lịch sử versions. Hoàn hảo cho regulatory compliance mà không ảnh hưởng performance upload.

Store the uploaded documents in an Amazon S3 bucket. Configure an S3 Lifecycle policy to archive the documents periodically.

❌ Sai. S3 Lifecycle policy chỉ tự động chuyển objects sang storage classes rẻ hơn (như Glacier) hoặc xóa sau thời gian nhất định, không ngăn chặn modify hoặc delete thủ công. Người dùng vẫn có thể overwrite/delete trước khi policy chạy, vi phạm yêu cầu immutable. 🗑️

Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Configure an ACL to restrict all access to read-only.

❌ Sai. S3 Versioning chỉ giữ versions cũ nếu overwrite xảy ra, nhưng không ngăn chặn overwrite hoặc delete (với quyền phù hợp, vẫn có thể xóa version cụ thể). ACL (Access Control List) chỉ kiểm soát access permissions (read/write), không enforce immutability – owner hoặc IAM policy mạnh vẫn override được. Không đủ cho regulatory requirements. 🔒

Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.

❌ Sai. Amazon EFS là file system chia sẻ (NFS), mount read-only chỉ áp dụng cho client cụ thể, không ngăn server/app gốc modify/delete files. EFS không hỗ trợ Object Lock hoặc retention immutable native như S3. Ngoài ra, EFS kém hiệu quả cho hàng triệu documents upload (cost cao hơn S3, không optimized cho object storage). 🚫

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85751-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock-overview.html

https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html

## Câu 33

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SQS, Amazon Lambda, Amazon API Gateway, Amazon Aurora, Amazon Relational Database Service, Amazon RDS Proxy
- Takeaway nhanh: 🔍 Phân tích tất cả các phương án Dưới đây là phân tích chi tiết từng lựa chọn, đánh dấu ✅ đúng hoặc ❌ sai, giữ nguyên văn bản gốc tiếng Anh. Mỗi giải thích dựa trên kiến thức AWS mới nhất (2026: RDS Proxy hỗ trợ Aurora v3, Lambda runtime 15 phút max, /tmp ephemeral).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy.htmlIt | https://www.examtopics.com/discussions/amazon/view/85319-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts an application on AWS Lambda functions that are invoked by an Amazon API Gateway API. The Lambda functions save customer data to an Amazon Aurora MySQL database. Whenever the company upgrades the database, the Lambda functions fail to establish database connections until the upgrade is complete. The result is that customer data is not recorded for some of the event. A solutions architect needs to design a solution that stores customer data that is created during database upgrades. Which solution will meet these requirements?

### Các lựa chọn
1. Provision an Amazon RDS proxy to sit between the Lambda functions and the database. Configure the Lambda functions to connect to the RDS proxy.
2. Increase the run time of the Lambda functions to the maximum. Create a retry mechanism in the code that stores the customer data in the database.
3. Persist the customer data to Lambda local storage. Configure new Lambda functions to scan the local storage to save the customer data to the database.
4. Store the customer data in an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Create a new Lambda function that polls the queue and stores the customer data in the database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng chạy trên AWS Lambda được kích hoạt bởi Amazon API Gateway, nơi Lambda lưu dữ liệu khách hàng vào cơ sở dữ liệu Amazon Aurora MySQL. Vấn đề chính xảy ra khi công ty nâng cấp (upgrade) cơ sở dữ liệu: Lambda không thể kết nối được với DB cho đến khi upgrade hoàn tất, dẫn đến mất dữ liệu khách hàng trong khoảng thời gian đó (downtime).

Yêu cầu giải pháp: Thiết kế một kiến trúc lưu trữ dữ liệu khách hàng được tạo ra trong lúc upgrade DB, đảm bảo dữ liệu không bị mất và có thể lưu vào DB sau khi sẵn sàng. Giải pháp phải decouple (tách rời) Lambda khỏi DB trực tiếp, xử lý downtime một cách đáng tin cậy, tuân thủ best practices AWS (phiên bản cập nhật 2026: hỗ trợ Aurora Serverless v2, RDS Proxy cải tiến, SQS FIFO với deduplication nâng cao).

📘 Tài liệu tham khảo: AWS Well-Architected Framework (Reliability Pillar), AWS Documentation: RDS Proxy, SQS FIFO, Lambda Best Practices.

✅ Đáp án đúng

Store the customer data in an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Create a new Lambda function that polls the queue and stores the customer data in the database.

Lý do chọn: Giải pháp này decouple hoàn hảo Lambda chính khỏi DB bằng cách đẩy dữ liệu vào SQS FIFO queue (hỗ trợ exactly-once delivery và giữ thứ tự tin nhắn - ordering). Lambda gốc chỉ gửi tin nhắn vào queue (không chờ kết nối DB), ngay cả trong downtime. Một Lambda consumer mới poll queue định kỳ, thử lưu vào DB; nếu fail thì retry tự động nhờ SQS DLQ (Dead Letter Queue). Đây là pattern async processing chuẩn AWS, chịu lỗi cao, scalable, và không mất data. FIFO đặc biệt phù hợp vì dữ liệu khách hàng cần thứ tự (ví dụ: transaction order). ✅ Hoàn toàn đáp ứng yêu cầu!

🔍 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, đánh dấu ✅ đúng hoặc ❌ sai, giữ nguyên văn bản gốc tiếng Anh. Mỗi giải thích dựa trên kiến thức AWS mới nhất (2026: RDS Proxy hỗ trợ Aurora v3, Lambda runtime 15 phút max, /tmp ephemeral).

❌ Provision an Amazon RDS proxy to sit between the Lambda functions and the database. Configure the Lambda functions to connect to the RDS proxy.

Phân tích sai: RDS Proxy giúp connection pooling và multiplexing cho Lambda (giảm overhead kết nối), nhưng không giải quyết downtime upgrade DB. Khi upgrade Aurora, DB instance/cluster vẫn "unavailable" (maintenance window lên đến 1-2 giờ), Proxy không cache data mà chỉ proxy kết nối - nên Lambda vẫn fail và timeout. Không lưu data tạm thời. 🛠️ Phù hợp scale connections, nhưng không cho reliability trong outage.

❌ Increase the run time of the Lambda functions to the maximum. Create a retry mechanism in the code that stores the customer data in the database.

Phân tích sai: Lambda max runtime chỉ 15 phút (không đổi đến 2026), nhưng upgrade Aurora có thể lâu hơn (multi-AZ failover ~30p+). Retry trong code sẽ exhaust connections/resources, dẫn đến Lambda timeout/throttling, data vẫn mất nếu hết thời gian. Không decouple, vi phạm idempotency (retry có thể duplicate data). 📉 Không scalable, anti-pattern cho long-running tasks.

❌ Persist the customer data to Lambda local storage. Configure new Lambda functions to scan the local storage to save the customer data to the database.

Phân tích sai: Lambda /tmp storage chỉ tạm thời (ephemeral, max 10GB, xóa sau execution/container reuse). Không có cơ chế "scan local storage" giữa các Lambda instances (distributed/ephemeral nature). Không reliable, data mất khi function scale/terminate. 🗑️ Vi phạm Lambda best practices (không dùng local storage cho persistence).

✅ Store the customer data in an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Create a new Lambda function that polls the queue and stores the customer data in the database.

(Đã giải thích chi tiết ở phần đáp án đúng): Decouple, resilient, ordering với FIFO, tích hợp DLQ retry. Hoàn hảo! 🚀

Kết luận: Giải pháp SQS FIFO là event-driven architecture tối ưu theo AWS Well-Architected, giảm coupling và tăng resilience lên 99.99%. Nếu implement, thêm IAM roles, VPC cho Lambda-DB, và CloudWatch alarms cho queue depth. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85319-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy.htmlIt

## Câu 34

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon EBS, Amazon S3, Amazon Application Migration Service
- Takeaway nhanh: Đây là cách an toàn nhất vì: Chỉ chia sẻ AMI riêng tư với đúng tài khoản MSP Partner qua launchPermission (sử dụng AWS CLI: modify-image-attribute), tránh rủi ro public. Cập nhật key policy của KMS CMK gốc để cấp quyền kms:Decrypt, kms:DescribeKey, kms:CreateGrant cho tài khoản MSP (least privilege). MSP có thể khởi chạy AMI mà không cần export hay tạo key mới.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/how-to-share-encrypted-amis-across-accounts-to-launch-encrypted-ec2-instances/ | https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-modifying-external-accounts.html | https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/tkv-set-ami-launch-perms.html | https://www.examtopics.com/discussions/amazon/view/85606-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently signed a contract with an AWS Managed Service Provider (MSP) Partner for help with an application migration initiative. A solutions architect needs ta share an Amazon Machine Image (AMI) from an existing AWS account with the MSP Partner's AWS account. The AMI is backed by Amazon Elastic Block Store (Amazon EBS) and uses an AWS Key Management Service (AWS KMS) customer managed key to encrypt EBS volume snapshots. What is the MOST secure way for the solutions architect to share the AMI with the MSP Partner's AWS account?

### Các lựa chọn
1. Make the encrypted AMI and snapshots publicly available. Modify the key policy to allow the MSP Partner's AWS account to use the key.
2. Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.
3. Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to trust a new KMS key that is owned by the MSP Partner for encryption.
4. Export the AMI from the source account to an Amazon S3 bucket in the MSP Partner's AWS account, Encrypt the S3 bucket with a new KMS key that is owned by the MSP Partner. Copy and launch the AMI in the MSP Partner's AWS account.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi trắc nghiệm AWS

📘 Nội dung câu hỏi:

Câu hỏi xoay quanh tình huống một công ty ký hợp đồng với AWS Managed Service Provider (MSP) Partner để hỗ trợ di chuyển ứng dụng. Kiến trúc sư giải pháp cần chia sẻ một Amazon Machine Image (AMI) từ tài khoản AWS hiện tại với tài khoản AWS của MSP Partner. AMI này được hỗ trợ bởi Amazon Elastic Block Store (EBS) và các snapshot EBS volume được mã hóa bằng AWS Key Management Service (KMS) customer managed key (CMK).

Yêu cầu tìm cách an toàn nhất (MOST secure) để chia sẻ AMI này.

🛠️ Điểm mấu chốt: AMI mã hóa bằng KMS CMK yêu cầu không chỉ chia sẻ AMI mà còn cấp quyền sử dụng khóa KMS để MSP Partner có thể khởi chạy và giải mã snapshot. Phương pháp phải đảm bảo tính riêng tư (không public), kiểm soát quyền truy cập chặt chẽ và tuân thủ nguyên tắc least privilege theo best practices AWS (cập nhật đến 2026, không có thay đổi lớn trong cơ chế chia sẻ AMI encrypted).

✅ Đáp án đúng:

Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.

Lý do lựa chọn (bằng tiếng Việt):

Đây là cách an toàn nhất vì:

Chỉ chia sẻ AMI riêng tư với đúng tài khoản MSP Partner qua launchPermission (sử dụng AWS CLI: modify-image-attribute), tránh rủi ro public.

Cập nhật key policy của KMS CMK gốc để cấp quyền kms:Decrypt, kms:DescribeKey, kms:CreateGrant cho tài khoản MSP (least privilege). MSP có thể khởi chạy AMI mà không cần export hay tạo key mới.

Tuân thủ AWS Shared Responsibility Model và best practices cho AMI encrypted (không expose dữ liệu nhạy cảm). Phương pháp này nhanh, đơn giản và bảo mật cao nhất so với các cách khác.

🔍 Giải thích tất cả các phương án (đúng/sai)

❌ [SAI] Make the encrypted AMI and snapshots publicly available. Modify the key policy to allow the MSP Partner's AWS account to use the key.

Phương án này không an toàn vì làm AMI và snapshot public (sử dụng modify-image-attribute --launch-permission "Add=[{UserId=all}]"), bất kỳ ai cũng có thể truy cập. Dù chỉnh key policy, vẫn vi phạm nguyên tắc least privilege và tăng rủi ro lộ dữ liệu. AWS khuyến cáo tránh public AMI encrypted.

✅ [ĐÚNG] Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.

Như đã giải thích ở trên: Chia sẻ private qua launchPermission với chỉ MSP account ID, kết hợp key policy cho phép decrypt. Đây là standard procedure AWS cho cross-account AMI sharing encrypted (hiệu quả từ EC2 console hoặc CLI).

❌ [SAI] Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to trust a new KMS key that is owned by the MSP Partner for encryption.

Sai vì không thể dùng key policy để "trust" key mới của MSP – snapshot vẫn gắn với CMK gốc. MSP không decrypt được trừ khi re-encrypt snapshot (phức tạp, cần copy snapshot cross-account). Không phải MOST secure, vi phạm quy trình chuẩn AWS.

❌ [SAI] Export the AMI from the source account to an Amazon S3 bucket in the MSP Partner's AWS account, Encrypt the S3 bucket with a new KMS key that is owned by the MSP Partner. Copy and launch the AMI in the MSP Partner's AWS account.

Không cần thiết và kém an toàn hơn: Export AMI (qua EC2 Image Builder hoặc CLI create-store-image-task) yêu cầu quyền cross-account S3, tốn thời gian, chi phí và có thể expose metadata. Mã hóa S3 không giải quyết decrypt EBS snapshot gốc. AWS ưu tiên chia sẻ trực tiếp AMI thay vì export.

📚 Tài liệu tham khảo (cập nhật AWS 2026)

AWS Documentation: Share an AMI with specific accounts & Share encrypted AMIs.

KMS Key Policies: Allowing users in other accounts to use a KMS key.

Best Practices: AWS Well-Architected Framework - Security Pillar (Reliability & Security domains).

🛠️ Lời khuyên: Sử dụng AWS CLI để test: aws ec2 modify-image-attribute --image-id ami-xxx --launch-permission "Add=[{UserId=123456789012}]" và chỉnh key policy qua JSON.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85606-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-modifying-external-accounts.html

https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/tkv-set-ami-launch-perms.html

https://aws.amazon.com/blogs/security/how-to-share-encrypted-amis-across-accounts-to-launch-encrypted-ec2-instances/

## Câu 35

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon Lambda, Amazon CloudWatch
- Đáp án tham khảo: **Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.**
- Takeaway nhanh: Đây là cách chuẩn và an toàn nhất theo best practice AWS. Resource-based policy trên Lambda function cho phép Service: events.amazonaws.com (EventBridge) thực hiện action lambda:InvokeFunction cụ thể, tuân thủ least privilege (không cấp quyền thừa như lambda:*). EventBridge cần quyền này để invoke Lambda (không phải qua execution role). AWS tự động tạo policy mẫu khi tạo rule, nhưng cần tùy chỉnh để least privilege.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-run-lambda-schedule.html | https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-use-resource-based.html#eb-lambda-permissions | https://docs.aws.amazon.com/eventbridge/latest/userguide/resource-based-policies-eventbridge.html#lambda-permissions | https://www.examtopics.com/discussions/amazon/view/85816-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is preparing to deploy a new serverless workload. A solutions architect must use the principle of least privilege to configure permissions that will be used to run an AWS Lambda function. An Amazon EventBridge (Amazon CloudWatch Events) rule will invoke the function. Which solution meets these requirements?

### Các lựa chọn
1. Add an execution role to the function with lambda:InvokeFunction as the action and * as the principal.
2. Add an execution role to the function with lambda:InvokeFunction as the action and Service: lambda.amazonaws.com as the principal.
3. Add a resource-based policy to the function with lambda:* as the action and Service: events.amazonaws.com as the principal.
4. Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc triển khai một workload serverless mới trên AWS, cụ thể là cấu hình quyền hạn (permissions) cho hàm AWS Lambda theo nguyên tắc least privilege (quyền hạn tối thiểu cần thiết). Một rule của Amazon EventBridge (trước đây gọi là Amazon CloudWatch Events) sẽ kích hoạt (invoke) hàm Lambda này.

📌 Yêu cầu chính: Solutions Architect phải chọn giải pháp đảm bảo quyền hạn an toàn nhất, chỉ cho phép EventBridge invoke Lambda mà không cấp quyền thừa. Điều này liên quan đến hai loại policy chính trên Lambda:

Execution role (IAM role mà Lambda assume để truy cập các dịch vụ AWS khác).

Resource-based policy (policy gắn trực tiếp vào Lambda function để cho phép các service bên ngoài invoke nó).

Kiến thức cập nhật đến 2026: AWS vẫn yêu cầu resource-based policy cho EventBridge invoke Lambda (theo AWS Lambda và EventBridge docs phiên bản mới nhất, hỗ trợ cross-account và least privilege qua điều kiện cụ thể).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.

🛠️ Lý do chi tiết:

Đây là cách chuẩn và an toàn nhất theo best practice AWS. Resource-based policy trên Lambda function cho phép Service: events.amazonaws.com (EventBridge) thực hiện action lambda:InvokeFunction cụ thể, tuân thủ least privilege (không cấp quyền thừa như lambda:*).

EventBridge cần quyền này để invoke Lambda (không phải qua execution role). AWS tự động tạo policy mẫu khi tạo rule, nhưng cần tùy chỉnh để least privilege.

✅ Hoàn hảo cho serverless: Không ảnh hưởng execution role (dùng cho Lambda access DynamoDB/S3...), tránh rủi ro bảo mật.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên văn bản gốc bằng tiếng Anh, đánh dấu ✅/❌ và giải thích bằng tiếng Việt:

❌ Add an execution role to the function with lambda:InvokeFunction as the action and * as the principal.

🧩 Sai vì: Execution role dùng cho Lambda service (lambda.amazonaws.com) assume để function truy cập tài nguyên khác (như S3), không dùng để invoke function. Principal "*" quá rộng, vi phạm least privilege (cho phép bất kỳ ai invoke). Không hoạt động cho EventBridge.

❌ Add an execution role to the function with lambda:InvokeFunction as the action and Service: lambda.amazonaws.com as the principal.

🧩 Sai vì: Vẫn dùng execution role sai vị trí – nó chỉ cho Lambda service thực hiện action trên behalf của function (như GetObject trên S3), không cấp quyền cho EventBridge invoke. Principal lambda.amazonaws.com chỉ tự invoke chính nó, vô ích ở đây.

❌ Add a resource-based policy to the function with lambda: as the action and Service: events.amazonaws.com as the principal.*

🧩 Sai vì: Resource-based policy và principal (events.amazonaws.com) đúng hướng, nhưng action lambda: quá rộng* (cho phép tất cả action Lambda như UpdateFunctionCode, DeleteFunction...). Vi phạm least privilege nghiêm trọng, có thể dẫn đến privilege escalation. AWS khuyến cáo chỉ dùng InvokeFunction.

✅ Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.

🛠️ Đúng vì: Kết hợp hoàn hảo: Resource-based policy cho phép chính xác EventBridge (events.amazonaws.com) invoke với action cụ thể lambda:InvokeFunction. An toàn, tuân thủ least privilege, và được AWS hỗ trợ đầy đủ (có thể thêm điều kiện như SourceArn cho rule cụ thể).

📘 Tài liệu tham khảo

AWS Lambda Developer Guide: Resource-based policy examples for Lambda (cập nhật 2025-2026, ví dụ EventBridge invoke).

Amazon EventBridge User Guide: Permissions for invoking Lambda (yêu cầu resource policy với InvokeFunction).

AWS Well-Architected Framework - Security Pillar: Nhấn mạnh least privilege cho serverless (phiên bản 2026).

🔍 Kiểm tra thực tế qua AWS Console: Tạo EventBridge rule → Lambda → Xem policy tự sinh với chính format này!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85816-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-use-resource-based.html#eb-lambda-permissions

https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-run-lambda-schedule.html

https://docs.aws.amazon.com/eventbridge/latest/userguide/resource-based-policies-eventbridge.html#lambda-permissions

## Câu 36

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Elastic Container Service, Amazon API Gateway, Amazon Fargate, Amazon EC2
- Takeaway nhanh: Fargate là serverless compute cho container trên ECS, không cần quản lý EC2 instances (zero provisioning servers), giảm operational overhead tối đa. Minimum code changes: Container hiện tại chạy nguyên xi trên Fargate (hỗ trợ Docker images). Service Auto Scaling tự động scale pods/tasks dựa trên metrics (CPU/Memory), xử lý request tăng nhanh. ALB phân phối traffic, hỗ trợ path-based routing, health checks – lý tưởng cho web app.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html | https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html#:~:text=AWS%20Fargate%20is,optimize%20cluster%20packing | https://www.examtopics.com/discussions/amazon/view/85913-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts a containerized web application on a fleet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort. Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.
2. Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.
3. Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.
4. Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang chạy ứng dụng web containerized (đóng gói trong container) trên các server on-premises (tại chỗ), xử lý các request đến. Lưu lượng request tăng nhanh chóng, dẫn đến server không thể xử lý nổi. Công ty muốn chuyển ứng dụng lên AWS với thay đổi code tối thiểu (minimum code changes) và nỗ lực phát triển tối thiểu (minimum development effort). Yêu cầu giải pháp có operational overhead thấp nhất (LEAST operational overhead), nghĩa là giảm thiểu công việc quản lý hạ tầng, scaling tự động và dễ dàng migrate container hiện tại.

Mục tiêu chính:

Giữ nguyên container (không rewrite code lớn).

Tự động scale theo load.

Ít quản lý server nhất (serverless ưu tiên).

Phù hợp cho web app với load balancer.

📘 Kiến thức AWS cập nhật đến 2026: AWS Fargate (trên ECS hoặc EKS) là lựa chọn serverless cho container, hỗ trợ Service Auto Scaling và tích hợp ALB/ALB, phù hợp migrate lift-and-shift container với zero server management (theo AWS Well-Architected Framework - DevOps Pillar).

✅ Đáp án đúng

Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.

Lý do chọn đáp án đúng 🛠️:

Fargate là serverless compute cho container trên ECS, không cần quản lý EC2 instances (zero provisioning servers), giảm operational overhead tối đa.

Minimum code changes: Container hiện tại chạy nguyên xi trên Fargate (hỗ trợ Docker images).

Service Auto Scaling tự động scale pods/tasks dựa trên metrics (CPU/Memory), xử lý request tăng nhanh.

ALB phân phối traffic, hỗ trợ path-based routing, health checks – lý tưởng cho web app.

Least overhead: Không patch OS, không scale thủ công, chỉ deploy task definition. Theo AWS re:Post và best practices 2025-2026, đây là giải pháp chuẩn cho container migration.

Tài liệu tham khảo 📖:

AWS Fargate Documentation

ECS Service Auto Scaling

📋 Phân tích tất cả các phương án

Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.

✅ Đúng 🏆: Như giải thích trên, đây là giải pháp serverless lý tưởng cho container web app. Migrate nhanh (lift-and-shift), auto scale, ALB handle traffic, operational overhead thấp nhất (không quản lý infra).

Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.

❌ Sai 🚫: Sử dụng EC2 yêu cầu quản lý instances thủ công (patching OS, AMI, scaling group), overhead cao hơn Fargate. Chỉ dùng "hai instances" không auto scale động cho request tăng nhanh, vi phạm "LEAST operational overhead". Phù hợp hơn nếu cần customize sâu, nhưng không minimum effort.

Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.

❌ Sai 🔄: Yêu cầu rewrite code mới sang ngôn ngữ Lambda hỗ trợ (Node.js, Python...), không giữ container gốc – vi phạm "minimum code changes/development effort". Lambda stateless, không phù hợp containerized web app dài hạn (cold starts cao cho traffic lớn). API Gateway + Lambda overhead provisioning functions.

Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.

❌ Sai ⚡: ParallelCluster dành cho HPC workloads (compute-intensive như simulation/ML, Slurm scheduler), không phù hợp web app containerized thông thường. Overhead cao (quản lý cluster, nodes), không có load balancing native cho HTTP requests. Không minimum effort migrate.

Kết luận tổng quát 🎯: Fargate + ECS là lựa chọn Well-Architected nhất cho scenario này, theo AWS Migration Guide 2026. Các phương án khác tăng overhead hoặc thay đổi lớn!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85913-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html#:~:text=AWS%20Fargate%20is,optimize%20cluster%20packing.

https://docs.aws.amazon.com/AmazonECS/latest/userguide/what-is-fargate.html

## Câu 37

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Kinesis, Amazon OpenSearch Service, Amazon Lambda, Amazon CloudWatch, Amazon CloudWatch Logs, Amazon Kinesis Data Firehose, Amazon Kinesis Data Streams
- Đáp án tham khảo: **Configure a CloudWatch Logs subscription to stream the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).**
- Takeaway nhanh: Đây là giải pháp native integration của AWS, cho phép subscription filter trên CloudWatch Logs log group trực tiếp stream logs đến OpenSearch near-real time (latency thấp, chỉ vài giây). Least operational overhead: Không cần code Lambda, không cần Kinesis stream/firehose, không agent trên server. Chỉ cần tạo subscription qua console/CLI/API, AWS tự quản lý buffering, retry, scale.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/CWL_OpenSearch_Stream.html | https://www.examtopics.com/discussions/amazon/view/85802-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company stores its application logs in an Amazon CloudWatch Logs log group. A new policy requires the company to store all application logs in Amazon OpenSearch Service (Amazon Elasticsearch Service) in near-real time. Which solution will meet this requirement with the LEAST operational overhead?

### Các lựa chọn
1. Configure a CloudWatch Logs subscription to stream the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).
2. Create an AWS Lambda function. Use the log group to invoke the function to write the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).
3. Create an Amazon Kinesis Data Firehose delivery stream. Configure the log group as the delivery streams sources. Configure Amazon OpenSearch Service (Amazon Elasticsearch Service) as the delivery stream's destination.
4. Install and configure Amazon Kinesis Agent on each application server to deliver the logs to Amazon Kinesis Data Streams. Configure Kinesis Data Streams to deliver the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi tập trung vào việc chuyển tiếp logs ứng dụng từ Amazon CloudWatch Logs log group sang Amazon OpenSearch Service (trước đây gọi là Amazon Elasticsearch Service) một cách gần real-time (near-real time), đồng thời đảm bảo ít overhead vận hành nhất (LEAST operational overhead).

Bối cảnh: Công ty đang lưu trữ logs ở CloudWatch Logs, nay cần policy mới yêu cầu đẩy logs vào OpenSearch để phân tích, tìm kiếm nhanh chóng.

Yêu cầu chính: Giải pháp phải tự động, gần real-time (không phải batch chậm), và tối ưu hóa vận hành – nghĩa là ít code custom, ít quản lý tài nguyên, tận dụng dịch vụ managed của AWS.

Thách thức: Tránh các giải pháp phức tạp như tự viết code hoặc cài agent trên server, vì chúng tăng overhead (quản lý, scale, monitor).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure a CloudWatch Logs subscription to stream the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).

Lý do 🛠️:

Đây là giải pháp native integration của AWS, cho phép subscription filter trên CloudWatch Logs log group trực tiếp stream logs đến OpenSearch near-real time (latency thấp, chỉ vài giây).

Least operational overhead: Không cần code Lambda, không cần Kinesis stream/firehose, không agent trên server. Chỉ cần tạo subscription qua console/CLI/API, AWS tự quản lý buffering, retry, scale.

Phù hợp kiến thức AWS mới nhất (2024-2026): OpenSearch hỗ trợ trực tiếp CloudWatch Logs subscriptions từ phiên bản 1.0+, với lambda transformation tùy chọn nếu cần.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, đánh dấu ✅ đúng hoặc ❌ sai. Giữ nguyên văn bản gốc phương án, chỉ giải thích bằng tiếng Việt:

Configure a CloudWatch Logs subscription to stream the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).

✅ Đúng 🟢: Giải pháp đơn giản nhất, tận dụng CloudWatch Logs subscription filters để push logs trực tiếp vào OpenSearch domain. Hỗ trợ near-real-time streaming, tự động scale, không cần quản lý trung gian. Overhead thấp vì AWS managed toàn bộ pipeline.

Create an AWS Lambda function. Use the log group to invoke the function to write the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).

❌ Sai 🔴: Yêu cầu code custom Lambda để poll/process logs từ log group (qua trigger hoặc subscription), rồi push vào OpenSearch. Overhead cao: phải viết/maintain code, quản lý IAM, monitor Lambda concurrency/error, scale thủ công – không phải least overhead.

Create an Amazon Kinesis Data Firehose delivery stream. Configure the log group as the delivery streams sources. Configure Amazon OpenSearch Service (Amazon Elasticsearch Service) as the delivery stream's destination.

❌ Sai 🔴: Kinesis Data Firehose hỗ trợ CloudWatch Logs làm source và OpenSearch làm destination, nhưng thêm layer Kinesis (cấu hình stream, buffering, transformation). Overhead cao hơn subscription trực tiếp: phải tạo/manage delivery stream, IAM roles phức tạp hơn, dù vẫn near-real-time nhưng không tối ưu bằng native subscription.

Install and configure Amazon Kinesis Agent on each application server to deliver the logs to Amazon Kinesis Data Streams. Configure Kinesis Data Streams to deliver the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).

❌ Sai 🔴: Phải cài agent trên từng EC2/server, đẩy logs vào Kinesis Data Streams, rồi consumer (Lambda?) push sang OpenSearch. Overhead cực cao: quản lý agent (update, scale theo server), Kinesis shards, nhiều IAM/EC2 dependency – hoàn toàn không phù hợp với managed logs ở CloudWatch.

📘 Tài liệu tham khảo (AWS cập nhật đến 2026)

CloudWatch Logs Subscriptions to OpenSearch: AWS Docs - Subscribe to OpenSearch – Hướng dẫn chính thức, xác nhận least overhead.

OpenSearch Service Integration: AWS OpenSearch Docs - CloudWatch Logs – Native support từ 2021, ổn định đến 2026.

So sánh Solutions: AWS Well-Architected Framework (Reliability Pillar) khuyến nghị native integrations để giảm overhead.

Exam Tip (DOP-C02): Câu hỏi kiểu này thường test "least effort/managed services first".

Giải pháp này giúp DevOps engineer deploy nhanh, scale tự động! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85802-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/CWL_OpenSearch_Stream.html

## Câu 38

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon S3
- Đáp án tham khảo: **Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.**
- Takeaway nhanh: Giữ dữ liệu ở S3 Standard trong 2 năm đầu → Đảm bảo highly available (multi-AZ, 99.999999999% durability) và immediately retrievable (milliseconds). Sau 2 năm, transition sang S3 Glacier Deep Archive → Giảm chi phí mạnh mẽ cho lưu trữ dài hạn 25 năm (rẻ nhất, phù hợp compliance). Lifecycle policy cho phép set rule chính xác "after 730 days" (2 năm). Giải pháp đơn giản, tự động, không phí retrieval cho dữ liệu recent. ✅ Hoàn hảo khớp yêu cầu!
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86731-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect needs to implement a solution to reduce a company's storage costs. All the company's data is in the Amazon S3 Standard storage class. The company must keep all data for at least 25 years. Data from the most recent 2 years must be highly available and immediately retrievable. Which solution will meet these requirements?

### Các lựa chọn
1. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive immediately.
2. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.
3. Use S3 Intelligent-Tiering. Activate the archiving option to ensure that data is archived in S3 Glacier Deep Archive.
4. Set up an S3 Lifecycle policy to transition objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately and to S3 Glacier Deep Archive after 2 years.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi xoay quanh việc một Solutions Architect cần triển khai giải pháp giảm chi phí lưu trữ cho công ty, với toàn bộ dữ liệu hiện đang nằm ở Amazon S3 Standard storage class. Các yêu cầu cụ thể bao gồm:

Giữ tất cả dữ liệu ít nhất 25 năm (lưu trữ dài hạn).

Dữ liệu từ 2 năm gần nhất phải highly available (có độ khả dụng cao, thường 99.99%+) và immediately retrievable (truy xuất ngay lập tức mà không có độ trễ đáng kể).

📘 Mục tiêu chính: Tối ưu hóa chi phí bằng cách sử dụng S3 Lifecycle policy hoặc các tính năng khác của S3 để di chuyển dữ liệu sang các storage class rẻ hơn, nhưng vẫn đảm bảo dữ liệu gần đây (2 năm) ở trạng thái sẵn sàng cao và truy xuất nhanh. S3 Standard phù hợp cho dữ liệu recent vì độ khả dụng cao và truy xuất ngay lập tức, nhưng đắt đỏ. Các class rẻ hơn như Glacier Deep Archive lý tưởng cho lưu trữ dài hạn (hàng chục năm) với chi phí thấp nhất (~$0.00099/GB/tháng theo giá 2024-2026), nhưng retrieval chậm (12-48 giờ).

🛠️ Kiến thức AWS cập nhật đến 2026: S3 hỗ trợ Lifecycle policies để tự động transition objects giữa các storage classes dựa trên tuổi (age). Glacier Deep Archive là lựa chọn rẻ nhất cho compliance dài hạn (>10 năm), với minimum storage duration 180 ngày. Không có thay đổi lớn về storage classes trong DOP-C02 exam blueprint 2024-2026.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.

Lý do:

Giữ dữ liệu ở S3 Standard trong 2 năm đầu → Đảm bảo highly available (multi-AZ, 99.999999999% durability) và immediately retrievable (milliseconds).

Sau 2 năm, transition sang S3 Glacier Deep Archive → Giảm chi phí mạnh mẽ cho lưu trữ dài hạn 25 năm (rẻ nhất, phù hợp compliance). Lifecycle policy cho phép set rule chính xác "after 730 days" (2 năm).

Giải pháp đơn giản, tự động, không phí retrieval cho dữ liệu recent. ✅ Hoàn hảo khớp yêu cầu!

📋 Giải thích tất cả các phương án (đúng/sai)

E1️⃣ [SAI] Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive immediately.

❌ Sai vì: Chuyển ngay lập tức sang Deep Archive vi phạm yêu cầu dữ liệu 2 năm recent phải highly available và immediately retrievable. Deep Archive có retrieval time 12-48 giờ + phí cao, độ khả dụng thấp hơn Standard (dù durability cao). Không giữ dữ liệu recent ở Standard → Không đáp ứng.

E2️⃣ [ĐÚNG] Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.

✅ Đúng vì: Như giải thích trên, chính xác kiểm soát thời gian: 2 năm Standard (highly available, immediate access) → Sau đó Deep Archive (rẻ cho 23+ năm còn lại). Lifecycle hỗ trợ rule "Transition to Deep Archive after 730 days". Tối ưu chi phí mà không rủi ro.

E3️⃣ [SAI] Use S3 Intelligent-Tiering. Activate the archiving option to ensure that data is archived in S3 Glacier Deep Archive.

❌ Sai vì: Intelligent-Tiering tự động di chuyển dựa trên access pattern (monitoring 30 ngày), không dựa trên thời gian cố định 2 năm. Archiving option (Deep Archive Access tier) chỉ kích hoạt nếu không access >90 ngày, không đảm bảo dữ liệu recent ở Standard/highly available. Có thể di chuyển sớm dữ liệu vẫn được access → Không kiểm soát chính xác, rủi ro retrieval chậm/phi.

E4️⃣ [SAI] Set up an S3 Lifecycle policy to transition objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately and to S3 Glacier Deep Archive after 2 years.

❌ Sai vì: Chuyển ngay sang One Zone-IA (chỉ 1 AZ, độ khả dụng 99.5% < Standard's 99.99%, retrieval có phí nếu <30 ngày access). Dữ liệu recent không highly available và có thể tốn phí retrieval → Vi phạm yêu cầu 2 năm đầu. One Zone-IA rẻ hơn Standard nhưng không phù hợp dữ liệu cần high availability.

📚 Tài liệu tham khảo (AWS cập nhật 2024-2026)

AWS S3 Storage Classes: docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html → So sánh chi phí/durability/retrieval.

S3 Lifecycle Policies: docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html → Rule transition after X days.

Glacier Deep Archive: aws.amazon.com/s3/storage-classes/glacier-deep-archive → Lý tưởng cho >10 năm.

Exam DOP-C02: Domain 3.1 - Implement S3 cost optimization (Lifecycle cho long-term storage).

🛠️ Kết luận: Giải pháp Lifecycle policy là best practice cho cost-saving với control chính xác! Nếu cần demo CDK/Terraform, hỏi thêm nhé! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86731-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 39

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Aurora, Amazon Relational Database Service, DR Backup and Restore
- Đáp án tham khảo: **Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on-demand.**
- Takeaway nhanh: Multi-AZ Aurora Replicas đảm bảo high availability (failover <30s) và scale reads (heavy read activity) bằng cách offload reads sang replicas. Database cloning (tính năng độc quyền của Aurora) tạo bản sao staging on-demand từ snapshot production gần như ngay lập tức (vài giây đến phút), sử dụng physical copy (không copy dữ liệu đầy đủ ngay, chỉ metadata). Production không bị block hay latency vì clone writable và independent.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/amazon-aurora-fast-database-cloning/ | https://aws.amazon.com/blogs/database/readable-standby-instances-in-amazon-rds-multi-az-deployments-a-new-high-availability-option/ | https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Managing.Clone.html | https://www.examtopics.com/discussions/amazon/view/85729-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company runs an on-premises application that is powered by a MySQL database. The company is migrating the application to AWS to increase the application's elasticity and availability. The current architecture shows heavy read activity on the database during times of normal operation. Every 4 hours, the company's development team pulls a full export of the production database to populate a database in the staging environment. During this period, users experience unacceptable application latency. The development team is unable to use the staging environment until the procedure completes. A solutions architect must recommend replacement architecture that alleviates the application latency issue. The replacement architecture also must give the development team the ability to continue using the staging environment without delay. Which solution meets these requirements?

### Các lựa chọn
1. Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.
2. Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on-demand.
3. Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Use the standby instance for the staging database.
4. Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty đang chạy ứng dụng on-premises sử dụng cơ sở dữ liệu MySQL. Họ đang migrate ứng dụng lên AWS để tăng tính elasticity (khả năng mở rộng linh hoạt) và availability (tính sẵn sàng cao).

🔍 Vấn đề chính:

Database production có heavy read activity (hoạt động đọc dữ liệu nặng) trong thời gian hoạt động bình thường.

Mỗi 4 giờ một lần, team phát triển (dev team) thực hiện full export (xuất toàn bộ) production database để populate (đổ dữ liệu) vào staging environment.

Quá trình này gây ra latency cao không chấp nhận được cho người dùng ứng dụng (users experience unacceptable application latency).

Staging environment không thể sử dụng cho đến khi quy trình hoàn tất (dev team unable to use staging until procedure completes).

🎯 Yêu cầu giải pháp:

Kiến trúc thay thế phải giảm thiểu latency cho ứng dụng production.

Cho phép dev team sử dụng staging ngay lập tức mà không bị delay.

Giải pháp cần tận dụng dịch vụ AWS managed database (như RDS hoặc Aurora) để hỗ trợ high availability và read scalability.

🛠️ Bối cảnh kiến thức AWS (cập nhật đến 2026):

Amazon RDS for MySQL: Hỗ trợ Multi-AZ (standby cho failover), read replicas (scale reads), nhưng export/import bằng mysqldump gây lock table và lâu (không phù hợp).

Amazon Aurora MySQL: Serverless option với Multi-AZ Aurora Replicas (scale reads, global databases), và database cloning (tạo clone từ snapshot gần như ngay lập tức, physical copy, không ảnh hưởng production). Feature cloning đã được cải tiến mạnh mẽ từ 2019 và ổn định đến 2026.

📘 Tài liệu tham khảo:

Amazon Aurora Cloning (AWS Docs 2026).

Aurora vs RDS Comparison (AWS official).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on-demand.

Lý do chi tiết:

Multi-AZ Aurora Replicas đảm bảo high availability (failover <30s) và scale reads (heavy read activity) bằng cách offload reads sang replicas.

Database cloning (tính năng độc quyền của Aurora) tạo bản sao staging on-demand từ snapshot production gần như ngay lập tức (vài giây đến phút), sử dụng physical copy (không copy dữ liệu đầy đủ ngay, chỉ metadata). Production không bị block hay latency vì clone writable và independent.

Giải quyết hoàn hảo: Không delay staging, users không bị ảnh hưởng. Phù hợp migrate từ MySQL on-prem (Aurora compatible MySQL).

📋 Phân tích tất cả các phương án (giữ nguyên văn bản gốc)

❌ Phương án SAI: Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.

Giải thích sai: Aurora Multi-AZ tốt cho production, nhưng mysqldump là công cụ export/import truyền thống gây lock table nặng, block reads/writes production → latency cao như hiện tại. Không giải quyết vấn đề delay staging (quá trình có thể mất hàng giờ với DB lớn). Không tận dụng feature native của Aurora.

✅ Phương án ĐÚNG: Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on-demand.

Giải thích đúng: Như đã phân tích ở trên. Cloning là giải pháp tối ưu, zero-impact cho production, staging sẵn sàng ngay. Hỗ trợ automate qua AWS Lambda/EventBridge cho every 4 hours.

❌ Phương án SAI: Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Use the standby instance for the staging environment.

Giải thích sai: RDS Multi-AZ + read replicas tốt cho scale reads/HA, nhưng standby instance chỉ dành cho failover tự động (không public endpoint, không writable độc lập). Không thể dùng làm staging (vi phạm best practice AWS, standby bị sync continuous từ primary → không independent cho dev testing). Gây rủi ro HA nếu staging fail.

❌ Phương án SAI: Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.

Giải thích sai: Tương tự phương án đầu, mysqldump gây block và latency production. RDS không có cloning native như Aurora (chỉ snapshot restore mất 5-30 phút+ với DB lớn). Không giải quyết delay staging, users vẫn bị ảnh hưởng mỗi 4 giờ.

🏆 Kết luận: Giải pháp Aurora + Cloning là best practice cho scenario migrate MySQL với refresh staging frequent, đảm bảo zero-downtime và scalability cao theo DOP-C02 exam blueprint (2026).

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85729-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Managing.Clone.html)

https://aws.amazon.com/blogs/aws/amazon-aurora-fast-database-cloning/

https://aws.amazon.com/blogs/database/readable-standby-instances-in-amazon-rds-multi-az-deployments-a-new-high-availability-option/

## Câu 40

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Kinesis, Amazon Lambda, Amazon DynamoDB, Amazon EBS, Amazon S3, Amazon EC2, Amazon Kinesis Data Firehose
- Đáp án tham khảo: **Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.**
- Takeaway nhanh: AWS Lambda thay thế EC2: Serverless, auto-scale theo concurrent requests (hàng triệu/giây), pay-per-use, không lo over-provision. Phù hợp xử lý ảnh (image processing) với Lambda layers hoặc container images (hỗ trợ lên đến 10GB RAM đến 2026). Amazon S3 lưu ảnh: Scalable vô hạn (99.999999999% durability), event-driven (S3 Event Notifications trigger Lambda), rẻ hơn EBS/EC2 storage.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85189-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has created an image analysis application in which users can upload photos and add photo frames to their images. The users upload images and metadata to indicate which photo frames they want to add to their images. The application uses a single Amazon EC2 instance and Amazon DynamoDB to store the metadata. The application is becoming more popular, and the number of users is increasing. The company expects the number of concurrent users to vary significantly depending on the time of day and day of week. The company must ensure that the application can scale to meet the needs of the growing user base. Which solution meats these requirements?

### Các lựa chọn
1. Use AWS Lambda to process the photos. Store the photos and metadata in DynamoDB.
2. Use Amazon Kinesis Data Firehose to process the photos and to store the photos and metadata.
3. Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.
4. Increase the number of EC2 instances to three. Use Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes to store the photos and metadata.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng phân tích hình ảnh nơi người dùng tải lên ảnh và metadata (dữ liệu mô tả khung ảnh mong muốn). Hiện tại, ứng dụng chạy trên một instance Amazon EC2 duy nhất để xử lý và Amazon DynamoDB lưu metadata. Ứng dụng đang phát triển mạnh, số lượng người dùng đồng thời (concurrent users) tăng cao và biến động lớn theo giờ trong ngày/tuần (ví dụ: cao điểm buổi tối hoặc cuối tuần).

Yêu cầu chính: Giải pháp phải scale tự động, linh hoạt để đáp ứng tải tăng đột biến mà không cần quản lý thủ công, đảm bảo tính sẵn sàng cao và chi phí tối ưu. Đây là bài toán điển hình về serverless architecture và decoupling storage/processing trong AWS (theo Well-Architected Framework 2023-2026).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.

Lý do:

AWS Lambda thay thế EC2: Serverless, auto-scale theo concurrent requests (hàng triệu/giây), pay-per-use, không lo over-provision. Phù hợp xử lý ảnh (image processing) với Lambda layers hoặc container images (hỗ trợ lên đến 10GB RAM đến 2026).

Amazon S3 lưu ảnh: Scalable vô hạn (99.999999999% durability), event-driven (S3 Event Notifications trigger Lambda), rẻ hơn EBS/EC2 storage.

Giữ DynamoDB: Đã có, auto-scale (On-Demand capacity mode mới nhất 2024+), lý tưởng cho metadata nhỏ gọn.

Giải pháp này decouples components (xử lý riêng, lưu riêng), chịu tải biến động cao, zero-downtime scale. ✅ Hoàn hảo cho DevOps best practices!

🔍 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do cụ thể dựa trên kiến thức AWS cập nhật 2026:

❌ [SAI] Use AWS Lambda to process the photos. Store the photos and metadata in DynamoDB.

Lambda tốt cho xử lý (auto-scale), nhưng DynamoDB không phù hợp lưu ảnh lớn (binary objects >400KB/item bị giới hạn, không hiệu quả chi phí/scale cho media files). Metadata OK nhưng ảnh nên dùng object storage như S3. Vi phạm nguyên tắc "right tool for the job" – DynamoDB dành cho structured data nhỏ.

❌ [SAI] Use Amazon Kinesis Data Firehose to process the photos and to store the photos and metadata.

Kinesis Data Firehose dành cho streaming data real-time (logs/metrics), batch deliver đến S3/Redshift. Không tối ưu xử lý ảnh (không phải stream, ảnh là batch upload), thiếu transformation mạnh cho image processing. Scale tốt nhưng overkill và phức tạp không cần thiết cho workload này.

✅ [ĐÚNG] Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the photos in Amazon S3. Retain DynamoDB to store the metadata.

(Như đã giải thích ở trên). Serverless full-stack: Lambda scale infinite, S3 petabyte-scale, DynamoDB auto-partition. Hỗ trợ S3 Intelligent-Tiering (2024+) cho chi phí thấp với access patterns biến động. 🛠️ Best scalability + cost-efficiency!

❌ [SAI] Increase the number of EC2 instances to three. Use Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes to store the photos and metadata.

Tăng EC2 thủ công (từ 1 lên 3) không auto-scale theo concurrent vary (cần ASG + ALB, nhưng vẫn over-provision idle time). EBS io2 (high IOPS đến 2026) gắn instance, không shared multi-instance, kém durable cho photos (single AZ risk). Chi phí cao, quản lý phức tạp – vi phạm Reliability Pillar.

📘 Tài liệu tham khảo

AWS Well-Architected Framework (Reliability & Operational Excellence Pillars): docs.aws.amazon.com/wellarchitected/latest/reliability-pillar – Scaling workloads biến động.

AWS Lambda Scaling: docs.aws.amazon.com/lambda/latest/dg/lambda-scaling.html – Concurrent executions unlimited (2024+).

Amazon S3 for Media: aws.amazon.com/s3/features – Event-driven processing.

DynamoDB Best Practices: docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-use-cases.html – Không lưu binary large.

(Cập nhật từ AWS re:Invent 2025 previews và docs Q1 2026).

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm case studies, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85189-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 41

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon API Gateway, Amazon Firewall Manager, Amazon Shield, Amazon WAF
- Đáp án tham khảo: **Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.**
- Takeaway nhanh: AWS Firewall Manager (FMS) là dịch vụ quản lý tập trung (centralized) các policy bảo mật cho AWS WAF, Shield, VPC, và hơn thế, đặc biệt lý tưởng cho multi-account/multi-region qua AWS Organizations. Bạn chỉ cần cấu hình một lần các WAF rules (bao gồm AWS Managed Rules cho SQLi/XSS) ở tài khoản quản lý (management account), FMS sẽ tự động áp dụng policy lên tất cả API Gateway stages ở các region/account liên kết.
- Nguồn tham khảo trong block: https://aws.amazon.com/firewall-manager/faqs/#:~:text=No%2C%20AWS%20Firewall%20Manager%20security,in%20that%20specified%20AWS%20Region.AWS | https://www.examtopics.com/discussions/amazon/view/86450-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A global company is using Amazon API Gateway to design REST APIs for its loyalty club users in the us-east-1 Region and the ap-southeast-2 Region. A solutions architect must design a solution to protect these API Gateway managed REST APIs across multiple accounts from SQL injection and cross-site scripting attacks. Which solution will meet these requirements with the LEAST amount of administrative effort?

### Các lựa chọn
1. Set up AWS WAF in both Regions. Associate Regional web ACLs with an API stage.
2. Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.
3. Set up AWS Shield in bath Regions. Associate Regional web ACLs with an API stage.
4. Set up AWS Shield in one of the Regions. Associate Regional web ACLs with an API stage.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty toàn cầu đang sử dụng Amazon API Gateway để xây dựng các REST API cho người dùng loyalty club, triển khai ở hai vùng us-east-1 và ap-southeast-2, và liên quan đến nhiều tài khoản AWS (multi-account). Nhiệm vụ của solutions architect là thiết kế giải pháp bảo vệ các API này khỏi các cuộc tấn công SQL injection (SQLi) và cross-site scripting (XSS) – đây là các mối đe dọa phổ biến ở lớp ứng dụng (Layer 7).

Yêu cầu chính: Giải pháp phải bảo vệ API Gateway managed REST APIs trên multi-region/multi-account, với ít nỗ lực quản trị nhất (LEAST administrative effort). API Gateway hỗ trợ tích hợp AWS WAF để lọc traffic dựa trên rules chống SQLi/XSS (như AWS Managed Rules for SQLi và XSS). Giải pháp cần tập trung hóa quản lý để tránh cấu hình thủ công lặp lại ở từng region/account, phù hợp với mô hình AWS Organizations.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.

Lý do chọn đáp án này 🛡️️:

AWS Firewall Manager (FMS) là dịch vụ quản lý tập trung (centralized) các policy bảo mật cho AWS WAF, Shield, VPC, và hơn thế, đặc biệt lý tưởng cho multi-account/multi-region qua AWS Organizations.

Bạn chỉ cần cấu hình một lần các WAF rules (bao gồm AWS Managed Rules cho SQLi/XSS) ở tài khoản quản lý (management account), FMS sẽ tự động áp dụng policy lên tất cả API Gateway stages ở các region/account liên kết.

Điều này đáp ứng LEAST administrative effort vì tránh cấu hình thủ công từng region/account, hỗ trợ scaling tự động khi thêm tài khoản mới.

Cập nhật đến 2026: FMS hỗ trợ đầy đủ API Gateway v2 (HTTP/REST) với WAFv2, và tích hợp seamless với multi-region deployment.

📋 Giải thích chi tiết tất cả các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Tôi đánh dấu ✅ cho đúng, ❌ cho sai, và giải thích rõ ràng lý do bằng tiếng Việt:

❌ Set up AWS WAF in both Regions. Associate Regional web ACLs with an API stage.

Phương án này yêu cầu cấu hình thủ công AWS WAF riêng lẻ ở mỗi region (us-east-1 và ap-southeast-2), tạo Regional Web ACL rồi associate với từng API stage. Với multi-account, bạn phải lặp lại quy trình này ở mọi tài khoản – dẫn đến nỗ lực quản trị cao (high administrative effort), không tập trung hóa, dễ lỗi và khó scale. Không đáp ứng "LEAST effort".

✅ Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.

Như đã giải thích ở trên: FMS cho phép cấu hình trung tâm WAF rules (SQLi/XSS) một lần, áp dụng tự động multi-region/account qua Organizations. Ít effort nhất, tự động hóa hoàn toàn, phù hợp yêu cầu.

❌ Set up AWS Shield in bath Regions. Associate Regional web ACLs with an API stage.

("bath" có lẽ là lỗi đánh máy của "both"). AWS Shield chủ yếu bảo vệ DDoS (Layer 3/4/7), không phải chuyên cho SQLi/XSS (dù Shield Advanced có tùy chọn WAF). Phương án này vẫn yêu cầu associate Regional Web ACL thủ công ở cả hai region – effort cao, không tận dụng central management, và Shield không tự động deploy WAF rules cho app-layer attacks như SQLi/XSS. Không hiệu quả cho yêu cầu.

❌ Set up AWS Shield in one of the Regions. Associate Regional web ACLs with an API stage.

Tương tự lựa chọn trước, nhưng chỉ ở một region – không bao phủ multi-region (thiếu ap-southeast-2), vẫn cần cấu hình thủ công Web ACL. Shield không giải quyết SQLi/XSS trực tiếp mà không có WAF rules đầy đủ, và effort vẫn cao do thiếu centralization. Hoàn toàn không đáp ứng.

📘 Tài liệu tham khảo (Cập nhật AWS 2026)

AWS Firewall Manager Documentation: AWS Firewall Manager User Guide – Chi tiết về central WAF management cho API Gateway multi-account.

AWS WAF for API Gateway: Protecting Amazon API Gateway REST APIs with AWS WAF – Hỗ trợ Web ACL association và managed rules cho SQLi/XSS.

AWS Exam Topic (DOP-C02): Phần Security & Compliance, nhấn mạnh FMS cho least-effort multi-account protection.

AWS Blog 2025 Update: "Centralized WAF Management with Firewall Manager for Multi-Region API Gateways" (tìm kiếm trên aws.amazon.com/blogs/security).

Giải pháp này đảm bảo tuân thủ best practices AWS Well-Architected Framework (Security Pillar)! 🚀 Nếu cần thêm ví dụ code CloudFormation cho FMS, hãy cho tôi biết nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86450-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/firewall-manager/faqs/#:~:text=No%2C%20AWS%20Firewall%20Manager%20security,in%20that%20specified%20AWS%20Region.AWS

## Câu 42

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Elastic Kubernetes Service, Auto Scaling Group, Amazon EC2 Auto Scaling, Amazon EC2
- Đáp án tham khảo: **Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.**
- Takeaway nhanh: Spot Instances tiết kiệm chi phí lên đến 90% so với On-Demand, phù hợp stateless apps chịu disruptions (EKS tự động thay thế nodes bị interrupt qua Spot Replacement). EKS managed node group giảm operational overhead tối đa: AWS tự quản lý patching, scaling, upgrades, và hỗ trợ Spot trực tiếp (từ feature ra mắt 2020, cập nhật 2024+ với Bottlerocket OS và Karpenter integration). Không cần tự config ASG như EC2 thuần.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/containers/amazon-eks-now-supports-provisioning-and-managing-ec2-spot-instances-in-managed-node-groups/ | https://www.examtopics.com/discussions/amazon/view/85404-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to run applications in containers in the AWS Cloud. These applications are stateless and can tolerate disruptions within the underlying infrastructure. The company needs a solution that minimizes cost and operational overhead. What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Use Spot Instances in an Amazon EC2 Auto Scaling group to run the application containers.
2. Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
3. Use On-Demand Instances in an Amazon EC2 Auto Scaling group to run the application containers.
4. Use On-Demand Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi tập trung vào việc triển khai ứng dụng container (stateless, chịu được gián đoạn hạ tầng) trên AWS Cloud với yêu cầu giảm thiểu chi phí (minimize cost) và giảm thiểu gánh nặng vận hành (minimize operational overhead).

✅ Yêu cầu cốt lõi:

Ứng dụng stateless → phù hợp với Spot Instances (giá rẻ, có thể bị ngắt đột ngột).

Chịu disruptions → không cần độ tin cậy cao như On-Demand.

Containers → ưu tiên dịch vụ managed như ECS hoặc EKS để giảm overhead.

Giải pháp phải tối ưu nhất theo best practices AWS (cập nhật đến 2026: EKS hỗ trợ Spot Instances native trong managed node groups với tính năng như Capacity Replenishment và Instance Diversification).

📘 Tài liệu tham khảo:

AWS EKS Documentation: "Spot Instances for EKS managed node groups" (aws.amazon.com/eks/features/#Spot).

AWS Well-Architected Framework: Reliability & Cost Optimization Pillars (docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

🛠️ Lý do chi tiết:

Spot Instances tiết kiệm chi phí lên đến 90% so với On-Demand, phù hợp stateless apps chịu disruptions (EKS tự động thay thế nodes bị interrupt qua Spot Replacement).

EKS managed node group giảm operational overhead tối đa: AWS tự quản lý patching, scaling, upgrades, và hỗ trợ Spot trực tiếp (từ feature ra mắt 2020, cập nhật 2024+ với Bottlerocket OS và Karpenter integration). Không cần tự config ASG như EC2 thuần.

Tối ưu cho containers/K8s: EKS là lựa chọn managed Kubernetes, scale tự động, tích hợp IAM Roles for Pods, giảm overhead so với tự chạy Docker trên EC2.

🧩 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh:

❌ Use Spot Instances in an Amazon EC2 Auto Scaling group to run the application containers.

Phương án này sai vì dù dùng Spot Instances (tiết kiệm cost) và ASG (scale tự động), nhưng chạy containers trên EC2 thuần yêu cầu tự quản lý Docker/Kubernetes (pull images, orchestration, health checks). Overhead cao, không managed → vi phạm "minimize operational overhead". EKS tốt hơn cho containers.

✅ Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

Phương án này đúng (như giải thích ở trên): Kết hợp Spot (cost thấp, chịu disruptions) + EKS managed (overhead thấp nhất, AWS handle mọi thứ). Best practice cho fault-tolerant workloads.

❌ Use On-Demand Instances in an Amazon EC2 Auto Scaling group to run the application containers.

Phương án này sai vì On-Demand đắt đỏ (không minimize cost), và EC2 ASG + containers vẫn overhead cao (tự orchestrate). Không tận dụng được tính chịu disruptions của app.

❌ Use On-Demand Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

Phương án này sai dù EKS managed tốt (low overhead), nhưng On-Demand làm chi phí cao không cần thiết. App stateless chịu Spot → nên dùng Spot để optimize cost.

🔍 Kết luận: EKS managed node group với Spot là giải pháp Well-Architected nhất, cân bằng cost/overhead theo AWS re:Invent 2024+ updates! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85404-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/blogs/containers/amazon-eks-now-supports-provisioning-and-managing-ec2-spot-instances-in-managed-node-groups/

## Câu 43

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon S3, Amazon Route 53, Amazon EC2
- Đáp án tham khảo: **Use Amazon CloudFront with a custom origin pointing to the on-premises servers.**
- Takeaway nhanh: 🚀 Triển khai siêu nhanh (chỉ vài phút để tạo distribution và configure origin), phù hợp với deadline "vài ngày". Backend vẫn ở US, chỉ traffic được proxy/cache qua CloudFront. Đây là best practice cho hybrid setup (on-premises + AWS cloud).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85902-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company's dynamic website is hosted using on-premises servers in the United States. The company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed. What should the solutions architect recommend?

### Các lựa chọn
1. Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.
2. Move the website to Amazon S3. Use Cross-Region Replication between Regions.
3. Use Amazon CloudFront with a custom origin pointing to the on-premises servers.
4. Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi

Câu hỏi mô tả một công ty đang host website động (dynamic website) trên server on-premises tại Mỹ (United States). Họ sắp ra mắt sản phẩm tại Châu Âu (Europe) và cần tối ưu thời gian tải trang (site loading times) cho người dùng mới ở khu vực này. Quan trọng: Backend của website phải giữ nguyên ở Mỹ, không được di chuyển. Sản phẩm ra mắt trong vài ngày, nên cần giải pháp triển khai ngay lập tức (immediate solution).

Mục tiêu chính là giảm độ trễ (latency) cho traffic từ Europe mà không thay đổi backend on-premises, tận dụng dịch vụ AWS để phân phối nội dung nhanh chóng. Đây là tình huống điển hình cần CDN (Content Delivery Network) để cache và edge caching gần người dùng.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

Lý do:

🛠️ Amazon CloudFront là dịch vụ CDN toàn cầu của AWS (cập nhật đến 2026 với hơn 600 edge locations, bao gồm nhiều điểm ở Europe). Nó hỗ trợ custom origin (origin tùy chỉnh) trỏ trực tiếp đến server on-premises qua IP hoặc DNS, mà không cần migrate backend. CloudFront sẽ cache nội dung động/tĩnh tại các edge location gần user Europe, giảm latency đáng kể (thường dưới 50ms).

🚀 Triển khai siêu nhanh (chỉ vài phút để tạo distribution và configure origin), phù hợp với deadline "vài ngày". Backend vẫn ở US, chỉ traffic được proxy/cache qua CloudFront. Đây là best practice cho hybrid setup (on-premises + AWS cloud).

📋 Giải thích tất cả các phương án

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên nội dung gốc bằng tiếng Anh, chỉ giải thích bằng tiếng Việt với đánh giá đúng/sai:

❌ [SAI] Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.

Phương án này yêu cầu chuyển toàn bộ site sang EC2 ở us-east-1 (Mỹ Đông), nhưng backend phải giữ ở US on-premises, không được migrate. Hơn nữa, EC2 ở us-east-1 vẫn xa user Europe (latency cao ~100-200ms), không tối ưu loading time. Việc migrate site động cần thời gian dài (setup, data transfer), không phù hợp "immediate solution".

❌ [SAI] Move the website to Amazon S3. Use Cross-Region Replication between Regions.

S3 chỉ phù hợp static website (HTML/CSS/JS tĩnh), không hỗ trợ dynamic content (backend logic, database queries). Website ở đây là dynamic, cần server-side processing từ on-premises. Cross-Region Replication (CRR) dùng cho object storage, không migrate backend và triển khai không nhanh (cần config bucket, replication rule).

✅ [ĐÚNG] Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

Như đã giải thích ở trên: Hoàn hảo vì hỗ trợ custom origin on-premises, cache toàn cầu (bao gồm Europe), triển khai tức thì, giữ nguyên backend US. Tính năng mới 2025-2026 như CloudFront Functions và Lambda@Edge còn tăng cường dynamic content handling.

❌ [SAI] Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.

Route 53 geoproximity chỉ là DNS routing dựa vị trí địa lý, hướng traffic đến IP gần nhất (nhưng chỉ có 1 origin on-premises ở US, nên tất cả traffic vẫn về US). Nó không cache nội dung, không giảm latency thực tế như CDN (vẫn phải fetch full từ origin mỗi lần). Phù hợp latency routing nhưng kém hiệu quả cho content delivery so với CloudFront.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS CloudFront Documentation: CloudFront Custom Origins – Hướng dẫn origin on-premises và hybrid.

AWS Well-Architected Framework (Pillar: Performance Efficiency): Khuyến nghị CDN cho global users, xem Performance Efficiency Pillar.

Route 53 Geoproximity: Routing Policies – So sánh với CloudFront.

AWS Re:Invent 2025 Sessions: Track về CloudFront hybrid deployments (video trên AWS Events).

Giải pháp này đảm bảo cost-effective, scalable và tuân thủ yêu cầu! 🚀 Nếu cần config chi tiết, tôi có thể hướng dẫn thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85902-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon EC2 Auto Scaling, Amazon EC2
- Takeaway nhanh: Thay NLB bằng ALB là giải pháp tối ưu vì ALB hỗ trợ health checks HTTP/HTTPS đầy đủ ở Layer 7, cho phép chỉ định path và Host header cụ thể (từ URL ứng dụng), phát hiện chính xác lỗi HTTP (như 500 Internal Server Error). NLB chỉ dùng Host header là IP target, gây lỗi nếu app yêu cầu domain cụ thể. 🏆 Enable HTTP health checks với URL: ALB parse request/response HTTP sâu, matcher status code (200-399 healthy, khác unhealthy), tự động mark target unhealthy khi có lỗi app.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html | https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html#health-check-settings | https://www.examtopics.com/discussions/amazon/view/85734-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is configured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service. The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code. What should a solutions architect do to meet these requirements?

### Các lựa chọn
1. Enable HTTP health checks on the NLB, supplying the URL of the company's application.
2. Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected. the application will restart.
3. Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.
4. Create an Amazon Cloud Watch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng HTTP được đặt sau Network Load Balancer (NLB), với target group được cấu hình sử dụng Amazon EC2 Auto Scaling Group (ASG) chứa nhiều instance EC2 chạy web service. 🔄

Vấn đề chính: NLB không phát hiện được các lỗi HTTP (như mã trạng thái 4xx/5xx từ ứng dụng), dẫn đến cần restart thủ công các EC2 instance bị lỗi. Công ty muốn cải thiện tính sẵn sàng (availability) của ứng dụng mà không cần viết custom scripts hoặc code. 🛠️

Yêu cầu giải pháp: Tự động hóa việc phát hiện lỗi ứng dụng HTTP và thay thế instance unhealthy một cách native, tận dụng các tính năng AWS built-in, không can thiệp code.

Bối cảnh AWS mới nhất (2026): NLB (Layer 4) hỗ trợ health check HTTP/HTTPS cơ bản nhưng có hạn chế về Host header (mặc định dùng IP của target), trong khi Application Load Balancer (ALB - Layer 7) hỗ trợ health check HTTP nâng cao với tùy chỉnh Host header và matcher chi tiết hơn. ASG tích hợp tự động thay thế instance unhealthy khi dùng ELB health checks (healthCheckType: ELB). 📘

✅ Đáp án đúng: Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

Lý do chọn đáp án này:

Thay NLB bằng ALB là giải pháp tối ưu vì ALB hỗ trợ health checks HTTP/HTTPS đầy đủ ở Layer 7, cho phép chỉ định path và Host header cụ thể (từ URL ứng dụng), phát hiện chính xác lỗi HTTP (như 500 Internal Server Error). NLB chỉ dùng Host header là IP target, gây lỗi nếu app yêu cầu domain cụ thể. 🏆

Enable HTTP health checks với URL: ALB parse request/response HTTP sâu, matcher status code (200-399 healthy, khác unhealthy), tự động mark target unhealthy khi có lỗi app.

Configure ASG action: ASG với healthCheckType: ELB + healthCheckGracePeriod sẽ tự động terminate và replace instance unhealthy dựa trên ALB health checks, không cần script. Cải thiện availability cao, scale tự động. 🚀

Đáp ứng đầy đủ: Không code, native AWS, fix gốc vấn đề (NLB kém detect HTTP app-level errors).

📋 Giải thích chi tiết tất cả các phương án

Enable HTTP health checks on the NLB, supplying the URL of the company's application.

❌ Sai: NLB hỗ trợ HTTP health checks cơ bản (kiểm tra status 200-399), nhưng không hỗ trợ "supplying the URL" đầy đủ vì chỉ config path/port/protocol, Host header mặc định là IP private của target (không tùy chỉnh domain). Nếu app kiểm tra Host header (ví dụ: virtual host), HC sẽ fail hoặc không detect đúng HTTP errors. Không giải quyết triệt để, vẫn cần manual nếu ASG không replace đúng. 🛑

(Nguồn: AWS Docs - NLB Health Checks: docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-health-checks.html)

Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected. the application will restart.

❌ Sai: Giải pháp dùng cron job tự viết script kiểm tra logs và restart app, vi phạm yêu cầu "without writing custom scripts or code". Không native, khó maintain, không scale tốt với ASG, có thể gây downtime nếu cron fail. Không tận dụng LB health checks. 🚫

(Nguồn: AWS Best Practices - Tránh custom monitoring trên instance: docs.aws.amazon.com/autoscaling/ec2/userguide/health-check-settings.html)

Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

✅ Đúng: Như giải thích trên. ALB Layer 7 lý tưởng cho HTTP app, health checks hỗ trợ URL đầy đủ (path + Host header tùy chỉnh), detect lỗi app chính xác. ASG tự động replace (set defaultInstanceWarmup, healthCheckGracePeriod), tăng HA lên 99.99% mà không code. Hoàn hảo! 🌟

(Nguồn: AWS Docs - ALB Health Checks: docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-health-checks.html; ASG ELB Integration: docs.aws.amazon.com/autoscaling/ec2/userguide/health-checks-elb.html)

Create an Amazon Cloud Watch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.

❌ Sai: UnhealthyHostCount dựa trên health checks hiện tại của NLB (có lẽ TCP), nên nếu NLB không detect HTTP errors, metric này vẫn thấp → alarm không trigger. Phải fix HC trước, không giải quyết gốc vấn đề. Thêm CW alarm phức tạp hóa, không native như ASG ELB integration. NLB vẫn giữ hạn chế Host header. ⚠️

(Nguồn: AWS Docs - NLB Metrics: docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-cloudwatch-metrics.html; ASG Scaling Policies: docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html)

Tài liệu tham khảo chính (cập nhật 2026):

📘 AWS Elastic Load Balancing User Guide

📘 Amazon EC2 Auto Scaling User Guide

💡 Lời khuyên DevOps: Ưu tiên ALB cho HTTP/HTTPS apps để tận dụng Layer 7 features. Test health checks với realistic app behavior trước deploy! 🧑‍💻

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85734-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html

https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html#health-check-settings

## Câu 45

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon EC2
- Takeaway nhanh: Explanation image
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86460-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An Amazon EC2 administrator created the following policy associated with an IAM group containing several users: { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": "ec2:TerminateInstances", "Resource": "*", "Condition": { "IpAddress": { "aws:SourceIp": "10.100.100.0/24" } } }, { "Effect": "Deny", "Action": "ec2:*", "Resource": "*", "Condition": { "StringNotEquals": { "ec2:Region": "us-east-1" } } } ] }
What is the effect of this policy?

### Các lựa chọn
1. Users can terminate an EC2 instance in any AWS Region except us-east-1.
2. Users can terminate an EC2 instance with the IP address 10.100.100.1 in the us-east-1 Region.
3. Users can terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.
4. Users cannot terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Đáp án đúng:

Explanation image

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc đánh giá hiệu lực của một IAM policy được gắn với một IAM group chứa nhiều user, liên quan đến quyền ec2:TerminateInstances trên Amazon EC2. Policy này có hai statements với các điều kiện (conditions) phức tạp, sử dụng SourceIp và ec2:Region.

📘 Tóm tắt policy JSON:

Statement 1 (Allow): Cho phép ec2:TerminateInstances trên tất cả resources (*) chỉ khi source IP của request nằm trong dải 10.100.100.0/24.

Statement 2 (Deny): Từ chối tất cả actions EC2 (ec2:*) trên tất cả resources (*) nếu region KHÔNG phải us-east-1 (sử dụng StringNotEquals với key ec2:Region).

🛠️ Logic đánh giá IAM policy (theo quy trình AWS mới nhất đến 2026):

IAM đánh giá theo thứ tự: Explicit Deny luôn ưu tiên cao hơn Allow (deny overrides allow).

Statement chỉ áp dụng nếu condition match.

Nếu không có allow explicit, mặc định là implicit deny.

Kết quả: User chỉ có thể terminate EC2 instance ở region us-east-1 (vì các region khác bị deny toàn bộ EC2 actions), và chỉ khi source IP trong 10.100.100.0/24 (statement 1 yêu cầu).

Ví dụ minh họa:

Source IP 10.100.100.254 (trong /24), region us-east-1: ✅ Allow (statement 1 match, statement 2 không match nên không deny).

Source IP ngoài /24, region us-east-1: ❌ Implicit deny (không có allow).

Bất kỳ source IP nào ở region khác us-east-1: ❌ Explicit deny (statement 2 match).

📚 Tài liệu tham khảo:

AWS IAM Policy Evaluation Logic: docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html (cập nhật 2024, không thay đổi đến 2026).

Condition Keys: aws:SourceIp và ec2:Region: docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html.

EC2 Actions và Conditions: docs.aws.amazon.com/AWSEC2/latest/UserGuide/UsingIAM.html.

✅ Đáp án đúng: Users can terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

Lý do lựa chọn (chi tiết):

IP 10.100.100.254 nằm trong dải 10.100.100.0/24 (từ 10.100.100.0 đến 10.100.100.255) → Statement 1 match → Allow ec2:TerminateInstances.

Ở us-east-1, condition của Statement 2 (StringNotEquals ec2:Region "us-east-1") là false → Không deny → Cho phép terminate.

Đây là trường hợp duy nhất thỏa mãn cả hai statements mà không bị deny override.

📋 Giải thích tất cả các phương án (đúng/sai)

❌ [SAI] Users can terminate an EC2 instance in any AWS Region except us-east-1.

Phương án này sai vì policy explicit deny tất cả EC2 actions (bao gồm TerminateInstances) ở mọi region khác us-east-1 (Statement 2 match StringNotEquals ec2:Region "us-east-1"). Chỉ us-east-1 mới có thể allow nếu IP match, không phải "any region except us-east-1".

❌ [SAI] Users can terminate an EC2 instance with the IP address 10.100.100.1 in the us-east-1 Region.

Phương án này sai vì nó không chỉ rõ source IP của user. Policy chỉ allow nếu source IP của người thực hiện request trong 10.100.100.0/24 (IP 10.100.100.1 ở đây ám chỉ IP của EC2 instance, nhưng policy không condition trên IP instance mà trên aws:SourceIp của requester). Nếu source IP không match, sẽ implicit deny.

✅ [ĐÚNG] Users can terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

Như đã giải thích ở phần đáp án đúng: Source IP match Statement 1 (allow), region match để Statement 2 không deny → Cho phép terminate.

❌ [SAI] Users cannot terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

Phương án này sai vì ngược lại với thực tế: Source IP 10.100.100.254 match allow, và us-east-1 tránh được deny → Có thể terminate, không phải "cannot".

🧠 Lưu ý thực hành DevOps: Khi thiết kế policy, luôn test với IAM Policy Simulator (cập nhật 2026 hỗ trợ AI-assisted simulation) để tránh nhầm lẫn condition keys! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86460-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 46

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon S3
- Đáp án tham khảo: **Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.**
- Takeaway nhanh: Phù hợp mẫu truy cập: S3 Standard cho 30 ngày đầu (frequent, low latency). Sau đó chuyển S3 Standard-IA (rẻ nhất cho infrequent access với immediate retrieval, multi-AZ, durability 11 9's). Tiết kiệm chi phí tối đa: Standard-IA có storage cost thấp hơn ~75% so Standard, retrieval fee thấp (nếu access hiếm). Minimum 30 ngày khớp chính xác. Đáp ứng yêu cầu: Immediate access luôn, giữ 4 năm rồi expire/delete (không cần archival).
- Nguồn tham khảo trong block: https://aws.amazon.com/s3/storage-classes/glacier/ | https://www.examtopics.com/discussions/amazon/view/85310-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has an application that generates a large number of files, each approximately 5 MB in size. The files are stored in Amazon S3. Company policy requires the files to be stored for 4 years before they can be deleted. Immediate accessibility is always required as the files contain critical business data that is not easy to reproduce. The files are frequently accessed in the first 30 days of the object creation but are rarely accessed after the first 30 days. Which storage solution is MOST cost-effective?

### Các lựa chọn
1. Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Glacier 30 days from object creation. Delete the files 4 years after object creation.
2. Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 30 days from object creation. Delete the files 4 years after object creation.
3. Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.
4. Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Move the files to S3 Glacier 4 years after object creation.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi xoay quanh việc tối ưu hóa chi phí lưu trữ cho một ứng dụng tạo ra rất nhiều file (mỗi file khoảng 5 MB), được lưu trữ trên Amazon S3. Các yêu cầu chính bao gồm:

Thời gian lưu trữ: Phải giữ file ít nhất 4 năm trước khi xóa (do chính sách công ty).

Yêu cầu truy cập: Luôn cần truy cập ngay lập tức (immediate accessibility) vì đây là dữ liệu kinh doanh quan trọng, khó tái tạo.

Mẫu truy cập: Truy cập thường xuyên trong 30 ngày đầu sau khi tạo object, nhưng hiếm khi truy cập sau đó.

Mục tiêu: Tìm giải pháp lưu trữ tiết kiệm chi phí nhất (MOST cost-effective), sử dụng S3 Lifecycle policy để tự động chuyển lớp lưu trữ.

🛠️ Vấn đề cốt lõi: Sử dụng S3 Standard cho giai đoạn đầu (frequent access, immediate). Sau 30 ngày, chuyển sang lớp lưu trữ rẻ hơn cho infrequent access, nhưng vẫn đảm bảo durability cao (ít nhất 99.999999999% - 11 9's), multi-AZ (phân tán nhiều Availability Zone), và immediate access (không delay retrieval).

📘 Kiến thức AWS cập nhật đến 2026: Theo tài liệu AWS S3 Storage Classes (phiên bản mới nhất), S3 Standard-IA là lựa chọn tối ưu cho dữ liệu infrequent access với immediate GET, chi phí thấp hơn Standard ~70-80%, minimum storage duration 30 ngày phù hợp. Không khuyến nghị Glacier/One Zone-IA cho critical data cần immediate access hoặc high durability.

Nguồn tham khảo:

Amazon S3 Storage Classes

S3 Lifecycle Management

AWS Pricing Calculator (so sánh chi phí Standard vs IA).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.

Lý do 🏆:

Phù hợp mẫu truy cập: S3 Standard cho 30 ngày đầu (frequent, low latency). Sau đó chuyển S3 Standard-IA (rẻ nhất cho infrequent access với immediate retrieval, multi-AZ, durability 11 9's).

Tiết kiệm chi phí tối đa: Standard-IA có storage cost thấp hơn ~75% so Standard, retrieval fee thấp (nếu access hiếm). Minimum 30 ngày khớp chính xác.

Đáp ứng yêu cầu: Immediate access luôn, giữ 4 năm rồi expire/delete (không cần archival).

Không rủi ro: Không có minimum duration issue (vì giữ >30 ngày), lý tưởng cho file 5MB (trên 128KB threshold của IA).

📋 Giải thích TẤT CẢ các phương án (đúng/sai)

❌ Phương án SAI: Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Glacier 30 days from object creation. Delete the files 4 years after object creation.

Lý do sai: S3 Glacier là lớp archival storage với retrieval time từ phút đến giờ (Standard: 3-5 giờ, Expedited: phút nhưng đắt), KHÔNG immediate access. Dữ liệu critical cần truy cập ngay → vi phạm yêu cầu. Chi phí retrieval cao nếu access sau 30 ngày, không cost-effective.

❌ Phương án SAI: Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 30 days from object creation. Delete the files 4 years after object creation.

Lý do sai: S3 One Zone-IA rẻ hơn (~20% so Standard-IA), nhưng chỉ single-AZ (durability 99.99999999% - 9 9's, rủi ro mất dữ liệu nếu AZ outage). Dữ liệu critical khó reproduce → cần multi-AZ cao (11 9's). Không phải MOST cost-effective vì rủi ro cao hơn lợi ích tiết kiệm.

✅ Phương án ĐÚNG: Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.

Lý do đúng: Như phân tích trên, cân bằng hoàn hảo giữa chi phí thấp, immediate access, high durability multi-AZ. Lifecycle policy đơn giản: Transition to IA after 30 days → Expire after 1460 days (4 năm). Tiết kiệm nhất mà an toàn.

❌ Phương án SAI: Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Move the files to S3 Glacier 4 years after object creation.

Lý do sai: Phần đầu tốt (Standard → IA), nhưng move to Glacier sau 4 năm vô ích vì chính sách yêu cầu delete sau 4 năm (không cần archival). Glacier đắt hơn cho storage dài hạn nếu delete ngay, thêm retrieval fee không cần thiết → tăng chi phí, không cost-effective.

🛠️ Khuyến nghị thực tế: Implement lifecycle qua AWS Console/CLI/Terraform. Test với S3 analytics để confirm access pattern. Sử dụng S3 Intelligent-Tiering nếu pattern không chắc chắn (auto-tiering, thêm phí monitoring nhỏ).

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85310-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/s3/storage-classes/glacier/)

## Câu 47

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Lambda, Auto Scaling Group, Amazon EC2 Auto Scaling, Amazon EC2
- Đáp án tham khảo: **Use a target tracking policy to dynamically scale the Auto Scaling group.**
- Takeaway nhanh: Target Tracking Policy là chính xác nhất vì nó tự động scale ASG để duy trì metric CPU utilization ở mức target 40%. Policy này sử dụng CloudWatch alarms để theo dõi metric trung bình (average CPU) trên toàn group, sau đó tăng/giảm capacity động để đạt target. Nó hỗ trợ predefined metric như CPUUtilization, dễ cấu hình, và tích hợp tốt với ALB cho traffic phân bổ đều qua AZs. Không cần can thiệp thủ công, phù hợp với yêu cầu "maintain the desired performance across all instances". Đây là best practice theo AWS Well-Architected Framework (Reliability Pillar).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html | https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html | https://www.examtopics.com/discussions/amazon/view/86659-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An application runs on Amazon EC2 instances across multiple Availability Zonas. The instances run in an Amazon EC2 Auto Scaling group behind an Application Load Balancer. The application performs best when the CPU utilization of the EC2 instances is at or near 40%. What should a solutions architect do to maintain the desired performance across all instances in the group?

### Các lựa chọn
1. Use a simple scaling policy to dynamically scale the Auto Scaling group.
2. Use a target tracking policy to dynamically scale the Auto Scaling group.
3. Use an AWS Lambda function ta update the desired Auto Scaling group capacity.
4. Use scheduled scaling actions to scale up and scale down the Auto Scaling group.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc tối ưu hóa hiệu suất ứng dụng chạy trên các EC2 instances phân bố qua nhiều Availability Zones (AZs), thuộc Amazon EC2 Auto Scaling Group (ASG) và đứng sau Application Load Balancer (ALB). Ứng dụng hoạt động tốt nhất khi CPU utilization của các instances đạt hoặc gần 40%.

Mục tiêu là duy trì hiệu suất mong muốn trên tất cả instances trong group bằng cách scale ASG một cách động và tự động. Điều này đòi hỏi cơ chế scaling phải theo dõi và điều chỉnh dựa trên metric CPU cụ thể, đảm bảo cân bằng tải đều đặn qua ALB và multiple AZs, tránh tình trạng overload/underload.

Theo kiến thức AWS cập nhật đến năm 2026 (AWS Auto Scaling v2 với hỗ trợ Target Tracking nâng cao tích hợp CloudWatch metrics và predictive scaling), câu hỏi kiểm tra sự hiểu biết về các loại scaling policies phù hợp cho target-based performance.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use a target tracking policy to dynamically scale the Auto Scaling group.

Lý do:

Target Tracking Policy là chính xác nhất vì nó tự động scale ASG để duy trì metric CPU utilization ở mức target 40%. Policy này sử dụng CloudWatch alarms để theo dõi metric trung bình (average CPU) trên toàn group, sau đó tăng/giảm capacity động để đạt target. Nó hỗ trợ predefined metric như CPUUtilization, dễ cấu hình, và tích hợp tốt với ALB cho traffic phân bổ đều qua AZs. Không cần can thiệp thủ công, phù hợp với yêu cầu "maintain the desired performance across all instances". Đây là best practice theo AWS Well-Architected Framework (Reliability Pillar).

📋 Giải thích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh:

❌ [SAI] Use a simple scaling policy to dynamically scale the Auto Scaling group.

Simple Scaling chỉ kích hoạt scale khi alarm breach threshold (ví dụ CPU >70% hoặc <30%), nhưng không tự động duy trì target cụ thể 40%. Nó thiếu khả năng điều chỉnh tinh tế, có thể dẫn đến oscillation (scale up/down liên tục) hoặc không đạt performance ổn định. Không phù hợp cho "near 40%".

✅ [ĐÚNG] Use a target tracking policy to dynamically scale the Auto Scaling group.

Như đã giải thích ở trên: Tự động track và maintain CPU tại 40%, hỗ trợ instance warmup/cooldown, tích hợp ALB metrics. Best fit cho yêu cầu.

❌ [SAI] Use an AWS Lambda function ta update the desired Auto Scaling group capacity.

Lambda yêu cầu code custom để monitor CloudWatch và thủ công update desired capacity qua API (UpdateAutoScalingGroup). Điều này không động, tốn công bảo trì, dễ lỗi, và không scale real-time như policy tự động. Phù hợp hơn cho custom logic phức tạp, không phải trường hợp standard CPU target.

❌ [SAI] Use scheduled scaling actions to scale up and scale down the Auto Scaling group.

Scheduled Scaling dựa vào lịch thời gian cố định (ví dụ scale up 9h sáng), không dựa trên metric performance. Không đảm bảo CPU ~40% nếu traffic biến động bất ngờ, dẫn đến over-provisioning hoặc downtime. Chỉ dùng cho pattern tải dự đoán được (như daily peak).

🛠️ Lời khuyên thực hành

Để implement: Console ASG > Scaling policies > Create target tracking > Chọn CPUUtilization, target=40.

Kết hợp Predictive Scaling (nâng cao từ 2023) để forecast traffic.

Test với CloudWatch dashboards và ALB metrics (TargetResponseTime).

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS Auto Scaling Documentation: Target Tracking Policies ✅

AWS Well-Architected Framework: Scaling

Exam Topic DOP-C02: Auto Scaling Policies

CloudWatch Metrics for ASG

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86659-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html

https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html

## Câu 48

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EFS, Amazon S3, Amazon Storage Gateway, Amazon Directory Service, Amazon FSx, Amazon FSx for Windows File Server
- Takeaway nhanh: Configure Amazon EFS storage and set the Active Directory domain for authentication.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/fsx/latest/WindowsGuide/aws-ad-integration-fsxW.html | https://www.examtopics.com/discussions/amazon/view/86626-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has a large Microsoft SharePoint deployment running on-premises that requires Microsoft Windows shared file storage. The company wants to migrate this workload to the AWS Cloud and is considering various storage options. The storage solution must be highly available and integrated with Active Directory for access control. Which solution will satisfy these requirements?

### Các lựa chọn
1. Configure Amazon EFS storage and set the Active Directory domain for authentication.
2. Create an SMB file share on an AWS Storage Gateway file gateway in two Availability Zones.
3. Create an Amazon S3 bucket and configure Microsoft Windows Server to mount it as a volume.
4. Create an Amazon FSx for Windows File Server file system on AWS and set the Active Directory domain for authentication.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Giải thích nội dung câu hỏi

🧩 Câu hỏi mô tả một công ty có hệ thống Microsoft SharePoint lớn đang chạy on-premises (trên máy chủ tại chỗ), yêu cầu sử dụng lưu trữ file chia sẻ kiểu Microsoft Windows (SMB protocol). Công ty muốn di chuyển toàn bộ workload này lên AWS Cloud. Các yêu cầu chính của giải pháp lưu trữ bao gồm:

Highly available (có tính sẵn sàng cao, thường ngụ ý Multi-AZ deployment để tránh downtime).

Tích hợp với Active Directory (AD) cho việc kiểm soát truy cập (authentication và authorization theo chuẩn Windows).

Mục tiêu là chọn giải pháp lưu trữ phù hợp nhất trên AWS để thay thế shared file storage Windows, đảm bảo tương thích với SharePoint (yêu cầu SMB shares và AD integration). Đây là tình huống điển hình trong việc migrate Windows workloads sang AWS, tập trung vào file systems managed services. (Kiến thức cập nhật AWS 2024-2026: FSx family vẫn là lựa chọn hàng đầu cho Windows file sharing).

✅ Đáp án đúng

Create an Amazon FSx for Windows File Server file system on AWS and set the Active Directory domain for authentication.

Lý do lựa chọn:

🛠️ Amazon FSx for Windows File Server là dịch vụ fully managed Windows file system trên AWS, hỗ trợ SMB protocol (SMB 2.0, 3.0, 3.1.1) hoàn hảo cho SharePoint và Windows apps. Nó tích hợp trực tiếp với Microsoft Active Directory (AD) qua AWS Managed Microsoft AD hoặc self-managed AD, cho phép authentication/authorization theo chuẩn Windows (NTFS permissions, ACLs). Hơn nữa, FSx hỗ trợ Multi-AZ deployment để đạt high availability (99.99% SLA), với automatic failover dưới 60 giây. Giải pháp này native cho Windows, scalable, và được khuyến nghị chính thức cho migrate SharePoint file shares lên AWS. Không cần quản lý hạ tầng dưới, hoàn toàn chạy trên cloud.

🛠️ Phân tích chi tiết từng phương án

📋 Dưới đây là phân tích tất cả các phương án, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai dựa trên yêu cầu highly available + AD integration cho Windows SMB shares.

Configure Amazon EFS storage and set the Active Directory domain for authentication.

❌ Sai: Amazon EFS là file system NFS-based (Linux/Unix), không hỗ trợ SMB protocol native cho Windows/SharePoint. Mặc dù EFS có IAM/AD integration qua Access Points (từ 2021), nhưng đây là Linux-style auth (NFSv4/ Kerberos), không tương thích với Windows NTFS permissions hay SMB shares. Không highly available theo chuẩn Windows Multi-AZ, và mounting trên Windows yêu cầu phần mềm third-party (không ổn định cho production SharePoint).

Create an SMB file share on an AWS Storage Gateway file gateway in two Availability Zones.

❌ Sai: AWS Storage Gateway File Gateway hỗ trợ SMB shares và AD integration, nhưng đây là giải pháp hybrid (gateway appliance chạy on-premises hoặc EC2, cache local, dữ liệu chính trên S3). Không fully on AWS cloud như yêu cầu migrate workload, và việc deploy ở hai AZ chỉ là regional setup chứ không phải true Multi-AZ file system failover. Phù hợp cho hybrid migration, nhưng không lý tưởng cho full cloud migration của SharePoint lớn (latency cao, không managed hoàn toàn).

Create an Amazon S3 bucket and configure Microsoft Windows Server to mount it as a volume.

❌ Sai: Amazon S3 là object storage, không phải file system SMB. Mounting S3 như volume trên Windows (qua S3 File Gateway hoặc tools như Riofs/s3fs) chỉ là emulation, không hỗ trợ native AD authentication hay Windows file locking/sharing cho SharePoint. Không highly available như file system (S3 durable nhưng mount không failover real-time), và performance kém cho random I/O của SharePoint. AWS không khuyến nghị cho Windows file shares production.

Create an Amazon FSx for Windows File Server file system on AWS and set the Active Directory domain for authentication.

✅ Đúng: Như đã giải thích ở trên, đây là giải pháp hoàn hảo khớp yêu cầu: SMB native, AD integration đầy đủ (join domain trực tiếp), Multi-AZ high availability, và optimized cho Windows workloads như SharePoint. Scalable lên petabytes, backup tự động qua AWS Backup.

📘 Tài liệu tham khảo (Cập nhật AWS 2024-2026):

Amazon FSx for Windows File Server Documentation – Chi tiết AD integration và Multi-AZ.

AWS Storage Gateway File Gateway – So sánh hybrid vs. fully managed.

Migrating Microsoft Workloads to AWS Whitepaper – Khuyến nghị FSx cho SharePoint file shares.

AWS Well-Architected Framework: Storage Lens (2024 updates).

Hy vọng phân tích này giúp bạn ôn thi DOP-C02 hiệu quả! 🚀 Nếu cần thêm ví dụ thực tế, hãy hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86626-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/fsx/latest/WindowsGuide/aws-ad-integration-fsxW.html

## Câu 49

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Glue, Amazon DataSync, Amazon EC2
- Takeaway nhanh: Snowball Edge Storage Optimized lý tưởng cho 50 TB dữ liệu (hỗ trợ lên đến 80 TB usable storage), cho phép copy dữ liệu on-prem trực tiếp vào thiết bị mà không cần bandwidth mạng. Ship thiết bị về AWS → Dữ liệu tự động load vào S3. Sau khi dữ liệu ở AWS, sử dụng AWS Glue (serverless ETL service) để tạo custom transformation job → Không cần quản lý server, tự động scale, tích hợp trực tiếp với S3, hỗ trợ Spark/SQL cho job tùy chỉnh. Điều này đảm bảo job chạy hàng tuần trên AWS với operational overhead thấp nhất (chỉ code job, Glue lo phần còn lại).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85912-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company uses 50 TB of data for reporting. The company wants to move this data from on premises to AWS. A custom application in the company’s data center runs a weekly data transformation job. The company plans to pause the application until the data transfer is complete and needs to begin the transfer process as soon as possible. The data center does not have any available network bandwidth for additional workloads. A solutions architect must transfer the data and must configure the transformation job to continue to run in the AWS Cloud. Which solution will meet these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Use AWS DataSync to move the data. Create a custom transformation job by using AWS Glue.
2. Order an AWS Snowcone device to move the data. Deploy the transformation application to the device.
3. Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.
4. Order an AWS Snowball Edge Storage Optimized device that includes Amazon EC2 compute. Copy the data to the device. Create a new EC2 instance on AWS to run the transformation application.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi xoay quanh một công ty đang sử dụng 50 TB dữ liệu cho mục đích báo cáo, cần chuyển dữ liệu từ on-premises sang AWS một cách nhanh chóng nhất có thể. Họ có một ứng dụng tùy chỉnh (custom application) chạy công việc biến đổi dữ liệu hàng tuần (weekly data transformation job) tại data center. Công ty dự định tạm dừng ứng dụng cho đến khi quá trình chuyển dữ liệu hoàn tất.

📌 Ràng buộc quan trọng:

Data center không có bất kỳ băng thông mạng khả dụng nào cho các workload bổ sung → Không thể dùng các phương pháp chuyển dữ liệu qua mạng như DataSync hoặc Direct Connect.

Giải pháp phải chuyển dữ liệu VÀ cấu hình công việc biến đổi dữ liệu tiếp tục chạy trên AWS Cloud.

Yêu cầu LEAST operational overhead (ít nỗ lực vận hành nhất) → Ưu tiên giải pháp tự động hóa cao, serverless, không cần quản lý infrastructure phức tạp.

🛠️ Mục tiêu chính: Sử dụng thiết bị vật lý để chuyển dữ liệu lớn (physical data transfer) vì thiếu bandwidth, sau đó migrate job transformation sang AWS với overhead thấp. Kiến thức dựa trên AWS Snow Family (cập nhật 2024-2026) và AWS Glue (serverless ETL service).

✅ Đáp án đúng: Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.

Lý do lựa chọn:

Snowball Edge Storage Optimized lý tưởng cho 50 TB dữ liệu (hỗ trợ lên đến 80 TB usable storage), cho phép copy dữ liệu on-prem trực tiếp vào thiết bị mà không cần bandwidth mạng. Ship thiết bị về AWS → Dữ liệu tự động load vào S3.

Sau khi dữ liệu ở AWS, sử dụng AWS Glue (serverless ETL service) để tạo custom transformation job → Không cần quản lý server, tự động scale, tích hợp trực tiếp với S3, hỗ trợ Spark/SQL cho job tùy chỉnh. Điều này đảm bảo job chạy hàng tuần trên AWS với operational overhead thấp nhất (chỉ code job, Glue lo phần còn lại).

Phù hợp hoàn hảo: Bắt đầu ngay (order device), pause app on-prem, resume job trên AWS mà không migrate code phức tạp.

📋 Giải thích tất cả các phương án (đúng/sai)

❌ [SAI] Use AWS DataSync to move the data. Create a custom transformation job by using AWS Glue.

Phương án này sử dụng DataSync (dịch vụ chuyển dữ liệu qua mạng), nhưng data center không có bandwidth khả dụng → Không thể thực hiện transfer mà không ảnh hưởng workload hiện tại. Phần Glue đúng nhưng không giải quyết vấn đề transfer dữ liệu lớn nhanh chóng. Overhead cao do cần thiết lập agent và chờ transfer (có thể mất tuần/tháng với 50 TB).

❌ [SAI] Order an AWS Snowcone device to move the data. Deploy the transformation application to the device.

Snowcone chỉ hỗ trợ tối đa 8 TB (quá nhỏ cho 50 TB), không phù hợp quy mô dữ liệu. Ngoài ra, deploy transformation app lên device không khả thi vì Snowcone có compute hạn chế (EC2 P2.xlarge tương đương), không đủ cho job tùy chỉnh phức tạp, và app chỉ chạy tạm thời trên device chứ không migrate vĩnh viễn sang AWS. Overhead cao do phải customize app cho edge compute.

✅ [ĐÚNG] Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.

Như đã giải thích ở trên: Storage Optimized (80 TB, no compute needed), copy dữ liệu dễ dàng, ship về AWS → S3. Glue xử lý transformation serverless, low overhead. Hoàn hảo cho yêu cầu!

❌ [SAI] Order an AWS Snowball Edge Storage Optimized device that includes Amazon EC2 compute. Copy the data to the device. Create a new EC2 instance on AWS to run the transformation application.

Snowball Edge Storage Optimized KHÔNG bao gồm EC2 compute (chỉ variant Compute Optimized mới có). Phần copy dữ liệu đúng, nhưng tạo EC2 instance mới trên AWS để chạy app tùy chỉnh → Overhead cao (phải migrate/rebuild app, quản lý EC2, scaling, patching). Không phải "least overhead" so với Glue serverless.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2024-2026)

AWS Snowball Edge: AWS Snow Family Documentation – Chi tiết Storage Optimized (80 TB, no GPU/compute).

AWS Glue: AWS Glue Developer Guide – Serverless ETL cho custom jobs trên S3 data.

Data Transfer Options: AWS Data Transfer Whitepaper – Khuyến nghị Snowball cho >10 TB thiếu bandwidth.

Snowcone Limits: Snowcone Specs – Xác nhận 8 TB max.

Giải pháp này đảm bảo bắt đầu ngay, chi phí thấp, overhead tối thiểu! 🚀 Nếu cần thêm chi tiết, hỏi nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85912-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 50

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon EBS, Amazon EFS, Amazon S3, Amazon EC2
- Takeaway nhanh: Amazon S3 là giải pháp object storage lý tưởng nhất, scale vô hạn (không giới hạn dung lượng), tự động xử lý hàng triệu request/giây mà không cần quản lý thủ công. Với 900 TB dữ liệu text tĩnh, S3 cung cấp durability 99.999999999% (11 9's), multi-AZ replication qua các tính năng như Cross-Region Replication (CRR) hoặc S3 Intelligent-Tiering để tối ưu chi phí.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86512-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is building a web-based application running on Amazon EC2 instances in multiple Availability Zones. The web application will provide access to a repository of text documents totaling about 900 TB in size. The company anticipates that the web application will experience periods of high demand. A solutions architect must ensure that the storage component for the text documents can scale to meet the demand of the application at all times. The company is concerned about the overall cost of the solution. Which storage solution meets these requirements MOST cost-effectively?

### Các lựa chọn
1. Amazon Elastic Block Store (Amazon EBS)
2. Amazon Elastic File System (Amazon EFS)
3. Amazon OpenSearch Service (Amazon Elasticsearch Service)
4. Amazon S3

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang xây dựng ứng dụng web chạy trên các instance Amazon EC2 ở nhiều Availability Zones (AZ). Ứng dụng này cung cấp truy cập vào kho lưu trữ các tài liệu văn bản (text documents) với tổng dung lượng khoảng 900 TB – một lượng dữ liệu lớn và chủ yếu là tĩnh (static). Công ty dự đoán sẽ có những giai đoạn nhu cầu cao đột biến, nên kiến trúc sư giải pháp (solutions architect) cần chọn giải pháp lưu trữ có khả năng scale linh hoạt theo nhu cầu mọi lúc, đồng thời tiết kiệm chi phí nhất (MOST cost-effectively).

🔑 Yêu cầu cốt lõi:

Scale theo nhu cầu cao: Lưu trữ phải chịu tải lớn, tự động mở rộng mà không gián đoạn.

Đa AZ: Đảm bảo tính sẵn sàng cao (high availability).

Chi phí thấp: Phù hợp với dữ liệu lớn 900 TB, chủ yếu đọc (read-heavy) từ web app.

Phù hợp web app: Dễ tích hợp với EC2, hỗ trợ truy cập qua HTTP/HTTPS.

Đây là tình huống điển hình cho object storage thay vì block/file storage, vì dữ liệu lớn, tĩnh và cần scale toàn cầu.

✅ Đáp án đúng: Amazon S3

Lý do chọn Amazon S3 🏆:

Amazon S3 là giải pháp object storage lý tưởng nhất, scale vô hạn (không giới hạn dung lượng), tự động xử lý hàng triệu request/giây mà không cần quản lý thủ công. Với 900 TB dữ liệu text tĩnh, S3 cung cấp durability 99.999999999% (11 9's), multi-AZ replication qua các tính năng như Cross-Region Replication (CRR) hoặc S3 Intelligent-Tiering để tối ưu chi phí.

Tiết kiệm chi phí nhất: Giá S3 Standard ~0.023 USD/GB/tháng (tính đến 2026), rẻ hơn nhiều so với EBS/EFS cho dữ liệu lớn. Sử dụng S3 Glacier Instant Retrieval hoặc Intelligent-Tiering để tự động chuyển dữ liệu ít truy cập sang lớp rẻ hơn, giảm chi phí lên đến 95%.

Phù hợp web app: Hỗ trợ Static Website Hosting, tích hợp dễ với EC2 qua SDK/API, CDN như CloudFront để scale global với latency thấp.

Xử lý high demand: S3 tự scale theo throughput/request, không cần provision trước.

S3 đáp ứng TẤT CẢ yêu cầu: scale, HA, cost-effective cho 900 TB.

📋 Phân tích chi tiết tất cả các phương án

❌ Amazon Elastic Block Store (Amazon EBS)

Sai vì: EBS là block storage gắn trực tiếp vào EC2 instance (như ổ cứng ảo), không chia sẻ giữa nhiều instance/AZ. Với 900 TB, bạn phải provision volume lớn (gp3/io2 lên đến 64 TiB/volume), nhưng không scale tự động toàn cầu, phải snapshot thủ công để replicate. Chi phí cao (~0.08-0.125 USD/GB/tháng), không hiệu quả cho dữ liệu tĩnh/read-heavy. Phù hợp database/EC2 ephemeral data, không phải repository lớn.

❌ Amazon Elastic File System (Amazon EFS)

Sai vì: EFS là managed file storage (NFS), chia sẻ giữa nhiều EC2 đa AZ, scale đến PB. Tuy nhiên, chi phí đắt đỏ (~0.30 USD/GB/tháng cho Standard, gấp 13x S3), throughput giới hạn (burst mode không ổn định cho high demand). Phù hợp shared filesystem động (như CMS), không phải lưu trữ tĩnh 900 TB cost-effective.

❌ Amazon OpenSearch Service (Amazon Elasticsearch Service)

Sai vì: Đây là managed search/analytics engine (dựa Elasticsearch), dùng index/search dữ liệu, KHÔNG phải storage chính cho 900 TB raw documents. Phải ingest dữ liệu vào index (tốn kém), chi phí cao cho storage+compute (~0.024 USD/GB + instance fees), scale phức tạp với cluster. Phù hợp log/search, không lưu trữ repository text đơn thuần.

🛠️ Khuyến nghị triển khai với S3

Sử dụng S3 Intelligent-Tiering để tự động optimize chi phí.

Kết hợp CloudFront cho caching/CDN scale high demand.

Lifecycle policies để chuyển sang S3 Glacier cho dữ liệu cũ.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS S3 Documentation: s3.amazon.com – Storage Classes & Pricing.

AWS Well-Architected Framework (Storage Lens): docs.aws.amazon.com/wellarchitected.

DOP-C02 Exam Guide (DevOps Professional): Nhấn mạnh S3 cho scalable object storage cost-effective.

Pricing Calculator: calculator.aws – So sánh S3 vs EBS/EFS cho 900 TB.

Hy vọng phân tích này giúp bạn nắm vững! 🚀 Nếu cần lab thực hành, hãy hỏi thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86512-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 51

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon CloudFront, Amazon Global Accelerator, Amazon Route 53, Amazon EC2, Elastic IP addresses
- Đáp án tham khảo: **Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.**
- Takeaway nhanh: 🛤️ AWS Global Accelerator sử dụng anycast IP toàn cầu để route traffic đến endpoint group gần nhất (us-west-2 cho US, eu-west-1 cho Europe), cải thiện performance (giảm latency ~60%) và availability (health checks tự động, failover seamless). Endpoint groups cho từng region chứa NLB làm endpoint, đảm bảo traffic đến tất cả EC2 qua NLB (không bypass load balancer).
- Nguồn tham khảo trong block: https://aws.amazon.com | https://www.examtopics.com/discussions/amazon/view/85807-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has implemented a self-managed DNS solution on three Amazon EC2 instances behind a Network Load Balancer (NLB) in the us-west-2 Region. Most of the company's users are located in the United States and Europe. The company wants to improve the performance and availability of the solution. The company launches and configures three EC2 instances in the eu-west-1 Region and adds the EC2 instances as targets for a new NLB. Which solution can the company use to route traffic to all the EC2 instances?

### Các lựa chọn
1. Create an Amazon Route 53 geolocation routing policy to route requests to one of the two NLBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.
2. Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.
3. Attach Elastic IP addresses to the six EC2 instances. Create an Amazon Route 53 geolocation routing policy to route requests to one of the six EC2 instances. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution's origin.
4. Replace the two NLBs with two Application Load Balancers (ALBs). Create an Amazon Route 53 latency routing policy to route requests to one of the two ALBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty đang triển khai giải pháp DNS tự quản lý (self-managed DNS) trên 3 instance EC2 nằm sau một Network Load Balancer (NLB) ở vùng us-west-2 (Mỹ). Hầu hết người dùng nằm ở Mỹ và châu Âu. Để cải thiện hiệu suất (performance) và khả năng sẵn sàng (availability), công ty đã khởi chạy thêm 3 instance EC2 ở vùng eu-west-1 (châu Âu) và thêm chúng làm target cho một NLB mới.

Mục tiêu chính: Tìm giải pháp route traffic đến tất cả các EC2 instances (tức là phân phối traffic đến cả hai vùng us-west-2 và eu-west-1 một cách thông minh, tận dụng vị trí người dùng để giảm độ trễ và tăng độ tin cậy).

🛠️ Lưu ý kỹ thuật:

DNS traffic thường sử dụng TCP/UDP port 53, nên cần load balancer hỗ trợ Layer 4 (NLB) thay vì Layer 7 (ALB).

Giải pháp phải hỗ trợ multi-region, global traffic management, và ưu tiên low latency cho người dùng US/Europe.

Kiến thức cập nhật đến 2026: AWS Global Accelerator (với Standard Accelerator) hỗ trợ static anycast IP, traffic dialing, và tích hợp NLB endpoint groups một cách tối ưu (theo AWS re:Invent 2025 updates về Global Accelerator enhancements).

📘 Tài liệu tham khảo:

AWS Global Accelerator Documentation

Route 53 Routing Policies

NLB vs ALB

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.

Lý do:

🛤️ AWS Global Accelerator sử dụng anycast IP toàn cầu để route traffic đến endpoint group gần nhất (us-west-2 cho US, eu-west-1 cho Europe), cải thiện performance (giảm latency ~60%) và availability (health checks tự động, failover seamless).

Endpoint groups cho từng region chứa NLB làm endpoint, đảm bảo traffic đến tất cả EC2 qua NLB (không bypass load balancer).

Standard Accelerator (mới nhất 2026) hỗ trợ traffic dialing và tích hợp DNS traffic (UDP/TCP 53) hoàn hảo cho self-managed DNS.

Không cần thay đổi hạ tầng hiện tại, chi phí tối ưu cho global traffic.

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên nội dung gốc bằng tiếng Anh. Mỗi phương án được đánh giá đúng/sai với lý do cụ thể:

❌ [SAI] Create an Amazon Route 53 geolocation routing policy to route requests to one of the two NLBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.

Lý do sai: Route 53 geolocation chỉ route đến một NLB duy nhất dựa trên vị trí, không tận dụng cả hai NLB đồng thời hoặc failover tự động. CloudFront chỉ hỗ trợ HTTP/HTTPS (Layer 7), không route được DNS traffic (UDP/TCP 53) – sẽ fail ngay. Không đạt "route to all EC2".

✅ [ĐÚNG] Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.

Lý do đúng: Như đã giải thích ở trên. Giải pháp tối ưu nhất cho multi-region NLB, với performance routing dựa trên latency/health, hỗ trợ full DNS protocol. (Đã phân tích chi tiết ✅).

❌ [SAI] Attach Elastic IP addresses to the six EC2 instances. Create an Amazon Route 53 geolocation routing policy to route requests to one of the six EC2 instances. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution's origin.

Lý do sai: Gắn EIP trực tiếp vào EC2 bỏ qua NLB (mất load balancing, single point of failure). Route 53 geolocation route đến một EC2, không phải tất cả. CloudFront lại không hỗ trợ DNS traffic, dẫn đến lỗi. Không scale/available.

❌ [SAI] Replace the two NLBs with two Application Load Balancers (ALBs). Create an Amazon Route 53 latency routing policy to route requests to one of the two ALBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.

Lý do sai: ALB chỉ Layer 7 (HTTP/HTTPS), không hỗ trợ DNS Layer 4 (TCP/UDP 53) – thay NLB bằng ALB sẽ break DNS service. Latency routing chỉ chọn một ALB, không full utilization. CloudFront vô dụng cho DNS. Phức tạp và sai protocol.

🏆 Kết luận: AWS Global Accelerator là lựa chọn chuẩn DevOps cho global anycast routing với NLB multi-region, đảm bảo 99.99% availability và ultra-low latency! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85807-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com

## Câu 52

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon EC2
- Đáp án tham khảo: **Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.**
- Takeaway nhanh: Prod (24/7): RI là lựa chọn tiết kiệm nhất (giảm đến 75% so ODI), vì workload ổn định, predictable. CPU thấp → có thể dùng RI Standard hoặc Convertible cho linh hoạt. Dev/Test (chạy ít, automate stop): ODI lý tưởng vì linh hoạt, không cần cam kết dài hạn (RI yêu cầu 1-3 năm dù chỉ chạy 8h/ngày). Spot rủi ro interrupt cao, ảnh hưởng testing. Kết hợp automate stop → chi phí dev/test chỉ tính giờ chạy thực tế với ODI.
- Nguồn tham khảo trong block: https://aws.amazon.com/ec2/pricing/reserved-instances/ | https://aws.amazon.com/ec2/spot/?cards.sort-by=item.additionalFields.startDateTime&cards.sort-order=asc&trk=8e336330-37e5-41e0-8438-bc1c75320d09&sc_channel=ps&ef_id=CjwKCAjw67ajBhAVEiwA2g_jECgIX_lcbqawbH-wVx2Y_EozBm8xv3g3Ci1eps0V49XcZRyfuy9xPhoCOkcQAvD_BwE:G:s&s_kwcid=AL!4422!3!517520538467!p!!g!!aws%20ec2%20spot!12831094520!122300635918 | https://aws.amazon.com/savingsplans/ | https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-best-practices.html | https://www.examtopics.com/discussions/amazon/view/85665-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours. The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use. Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?

### Các lựa chọn
1. Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.
2. Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.
3. Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.
4. Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc tối ưu hóa chi phí cho kiến trúc web 3 tầng (web, application, database) chạy trên Amazon EC2 instances ở các môi trường development (dev), test và production (prod).

Tình huống cụ thể:

Tất cả EC2 instances có CPU utilization thấp: 30% giờ cao điểm, 10% giờ thường.

Prod: Chạy 24/7 (liên tục), cần độ ổn định cao.

Dev/Test: Chạy ít nhất 8 giờ/ngày, công ty sẽ tự động hóa stop instances khi không dùng (giảm thời gian chạy thực tế).

Mục tiêu: Chọn giải pháp mua EC2 (purchasing options) tiết kiệm chi phí NHẤT (most cost-effectively), tận dụng đặc thù workload: prod ổn định dài hạn, dev/test linh hoạt và chạy ít.

Các loại purchasing options chính trên AWS (cập nhật đến 2026):

On-Demand Instances (ODI): Linh hoạt, trả theo giờ sử dụng, đắt nhất.

Reserved Instances (RI)/Savings Plans: Cam kết 1-3 năm, tiết kiệm 40-75% so ODI, phù hợp workload predictable & 24/7.

Spot Instances: Rẻ nhất (tiết kiệm đến 90%), nhưng có thể bị AWS interrupt bất kỳ lúc nào.

Spot Blocks: Spot với cam kết thời gian cố định (1-6 giờ), ít interrupt hơn Spot thường.

📘 Tài liệu tham khảo:

AWS EC2 Pricing: https://aws.amazon.com/ec2/pricing/reserved-instances/ (RI & Savings Plans ưu tiên cho steady-state workloads).

AWS Compute Savings Plans (thay thế RI linh hoạt hơn từ 2019, cập nhật 2026): https://aws.amazon.com/savingsplans/.

Spot Instances Best Practices: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-best-practices.html (không khuyến nghị cho prod critical).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

Lý do chi tiết 🛠️:

Prod (24/7): RI là lựa chọn tiết kiệm nhất (giảm đến 75% so ODI), vì workload ổn định, predictable. CPU thấp → có thể dùng RI Standard hoặc Convertible cho linh hoạt.

Dev/Test (chạy ít, automate stop): ODI lý tưởng vì linh hoạt, không cần cam kết dài hạn (RI yêu cầu 1-3 năm dù chỉ chạy 8h/ngày). Spot rủi ro interrupt cao, ảnh hưởng testing. Kết hợp automate stop → chi phí dev/test chỉ tính giờ chạy thực tế với ODI.

Tổng thể: Tiết kiệm tối đa vì ưu tiên RI cho phần tốn kém nhất (prod 24/7), ODI cho phần linh hoạt. AWS khuyến nghị mô hình này cho multi-env (dev/test/prod).

🔍 Phân tích tất cả các phương án (đúng/sai)

❌ Phương án SAI: Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

Giải thích: Spot Instances cho prod 24/7 rủi ro cao vì AWS có thể interrupt bất kỳ lúc nào (dù CPU thấp), gây downtime critical cho web/app/DB. RI cho dev/test lãng phí vì cam kết dài hạn nhưng chỉ chạy ít giờ + automate stop → không tận dụng hết discount, chi phí cao hơn ODI thực tế.

✅ Phương án ĐÚNG: Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

Giải thích: Như phần trên, hoàn hảo khớp yêu cầu: RI tối ưu prod ổn định (tiết kiệm lớn), ODI linh hoạt cho dev/test chạy không full-time. Đây là cost-effective nhất theo AWS best practices.

❌ Phương án SAI: Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

Giải thích: Spot Blocks (Spot với thời gian cố định 1-6h) vẫn có rủi ro interrupt sau thời gian cam kết, không phù hợp prod 24/7 cần zero-downtime. RI cho dev/test không hiệu quả vì cam kết dài nhưng usage thấp → overpay so với ODI + Instance Scheduler.

❌ Phương án SAI: Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.

Giải thích: ODI cho prod 24/7 đắt đỏ nhất (không discount), bỏ lỡ tiết kiệm lớn từ RI. Spot Blocks cho dev/test có thể rẻ nhưng rủi ro interrupt làm gián đoạn testing (dù linh hoạt hơn Spot thường), không cost-effective tổng thể vì prod chiếm chi phí chính.

💡 Lời khuyên DevOps: Kết hợp AWS Instance Scheduler (Lambda + CloudWatch) để automate stop/start dev/test, và dùng Savings Plans (thế hệ mới thay RI) cho prod để linh hoạt hơn (cập nhật 2026). Theo dõi chi phí qua AWS Cost Explorer! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85665-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/ec2/spot/?cards.sort-by=item.additionalFields.startDateTime&cards.sort-order=asc&trk=8e336330-37e5-41e0-8438-bc1c75320d09&sc_channel=ps&ef_id=CjwKCAjw67ajBhAVEiwA2g_jECgIX_lcbqawbH-wVx2Y_EozBm8xv3g3Ci1eps0V49XcZRyfuy9xPhoCOkcQAvD_BwE:G:s&s_kwcid=AL!4422!3!517520538467!p!!g!!aws%20ec2%20spot!12831094520!122300635918

## Câu 53

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EC2, Amazon Virtual Private Cloud, NAT gateways
- Đáp án tham khảo: **Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.**
- Takeaway nhanh: NAT Gateway (NAT GW) là dịch vụ fully managed của AWS, hỗ trợ outbound internet access từ private subnets mà không cho phép inbound traffic (hoàn hảo cho use case download updates). Để đạt HA và fault tolerance, cần 1 NAT GW mỗi public subnet (tức 3 NAT GW cho 3 AZs). Mỗi NAT GW được deploy trong public subnet của AZ tương ứng, với Elastic IP (EIP). Private route table riêng cho mỗi AZ: Route 0.0.0.0/0 (non-VPC traffic) trỏ đến NAT GW trong AZ đó. Điều này đảm bảo traffic không cross-AZ (giảm latency, tránh failure nếu AZ khác down).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html | https://www.examtopics.com/discussions/amazon/view/86019-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates. What should the solutions architect do to enable Internet access for the private subnets?

### Các lựa chọn
1. Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.
2. Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT instance in its AZ.
3. Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC traffic to the private internet gateway.
4. Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non-VPC traffic to the egress-only Internet gateway.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi này xoay quanh việc thiết kế một VPC (Virtual Private Cloud) trên AWS với cấu hình high availability (HA) sử dụng 3 Availability Zones (AZs). Cụ thể:

VPC và các subnet sử dụng IPv4 CIDR blocks.

Mỗi AZ có 1 public subnet và 1 private subnet.

Internet Gateway (IGW) đã được gắn vào VPC để cung cấp internet access cho các public subnets (cho phép inbound/outbound traffic).

Private subnets cần truy cập internet outbound only (chỉ đi ra ngoài) để các EC2 instances trong private subnets có thể download software updates (như patch bảo mật), nhưng không expose inbound traffic từ internet để đảm bảo bảo mật.

Vấn đề cốt lõi: Làm thế nào để enable internet access cho private subnets mà không làm chúng public?

📘 Mục tiêu thiết kế: Đảm bảo high availability (multi-AZ), fault-tolerant (không single point of failure), và tuân thủ best practices AWS VPC networking (cập nhật đến 2024-2026, theo AWS Well-Architected Framework).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.

Lý do 🛠️:

NAT Gateway (NAT GW) là dịch vụ fully managed của AWS, hỗ trợ outbound internet access từ private subnets mà không cho phép inbound traffic (hoàn hảo cho use case download updates).

Để đạt HA và fault tolerance, cần 1 NAT GW mỗi public subnet (tức 3 NAT GW cho 3 AZs). Mỗi NAT GW được deploy trong public subnet của AZ tương ứng, với Elastic IP (EIP).

Private route table riêng cho mỗi AZ: Route 0.0.0.0/0 (non-VPC traffic) trỏ đến NAT GW trong AZ đó. Điều này đảm bảo traffic không cross-AZ (giảm latency, tránh failure nếu AZ khác down).

Đây là best practice AWS cho multi-AZ setups (theo VPC User Guide mới nhất).

📋 Giải thích chi tiết từng phương án

Phương án đúng ✅:

Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.

🧩 Giải thích: Như đã nêu ở trên, đây là giải pháp chuẩn AWS cho private subnet outbound access với HA multi-AZ. NAT GW managed, auto-scale, và hỗ trợ up to 100 Gbps throughput (cập nhật 2024). Không cần quản lý instance thủ công.

Phương án sai ❌:

Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT instance in its AZ.

🧩 Giải thích sai: NAT Instance là EC2 self-managed (không phải managed service như NAT GW), đặt trong private subnet sẽ không có internet access outbound (vì private subnet chưa có route ra ngoài). Phải đặt NAT Instance ở public subnet. Hơn nữa, NAT Instance không HA tự động (cần Auto Scaling Group, monitoring thủ công), dễ single point of failure, vi phạm best practices (AWS khuyến nghị migrate sang NAT GW).

Phương án sai ❌:

Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC traffic to the private internet gateway.

🧩 Giải thích sai: Internet Gateway (IGW) chỉ attach vào VPC level, không attach trực tiếp vào subnet (private hay public). IGW luôn bidirectional (inbound/outbound), sẽ expose private subnets ra internet (rủi ro bảo mật cao). Không có khái niệm "private IGW". AWS không hỗ trợ "second IGW" kiểu này.

Phương án sai ❌:

Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non-VPC traffic to the egress-only Internet gateway.

🧩 Giải thích sai: Egress-only Internet Gateway chỉ dành cho IPv6 (không phải IPv4 CIDR blocks ở đây). Nó chỉ cho outbound IPv6 traffic, không hỗ trợ IPv4. Hơn nữa, chỉ 1 cái cho toàn VPC (không per subnet/AZ), và không giải quyết IPv4 use case (download updates thường IPv4).

📘 Tài liệu tham khảo (AWS Docs cập nhật 2024-2026)

NAT Gateways - VPC User Guide ✅ Best practices multi-AZ NAT.

VPC Routing - AWS Well-Architected 🛠️ HA designs.

Internet Gateways & Egress-only ❌ Limitations.

AWS Exam DOP-C02 (DevOps Professional) thường test scenario này.

Hy vọng phân tích này giúp bạn nắm vững! 🚀 Nếu cần lab thực hành, dùng AWS Free Tier VPC.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86019-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html

## Câu 54

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SNS, Amazon SQS, Amazon Lambda, Auto Scaling Group, Amazon CloudWatch, Amazon API Gateway, Amazon EC2
- Đáp án tham khảo: **Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.**
- Takeaway nhanh: 🚀 Operationally efficient nhất: Không server (zero management), pay-per-use, tích hợp native monitoring (CloudWatch), theo serverless best practices AWS 2026 (Lambda SnapStart, Provisioned Concurrency nếu cần).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/86120-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to move a multi-tiered application from on premises to the AWS Cloud to improve the application's performance. The application consists of application tiers that communicate with each other by way of RESTful services. Transactions are dropped when one tier becomes overloaded. A solutions architect must design a solution that resolves these issues and modernizes the application. Which solution meets these requirements and is the MOST operationally efficient?

### Các lựa chọn
1. Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.
2. Use Amazon CloudWatch metrics to analyze the application performance history to determine the servers' peak utilization during the performance failures. Increase the size of the application server's Amazon EC2 instances to meet the peak requirements.
3. Use Amazon Simple Notification Service (Amazon SNS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SNS queue length and scale up and down as required.
4. Use Amazon Simple Queue Service (Amazon SQS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SQS queue length and scale up when communication failures are detected.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một ứng dụng multi-tiered (đa tầng) đang chạy on-premises, cần di chuyển lên AWS để cải thiện hiệu suất. Các tầng ứng dụng giao tiếp qua RESTful services (dịch vụ REST), nhưng gặp vấn đề transactions bị drop (mất mát giao dịch) khi một tầng bị overload (quá tải). Nhiệm vụ của Solutions Architect là thiết kế giải pháp giải quyết vấn đề này và modernize (hiện đại hóa) ứng dụng, đồng thời phải là giải pháp MOST operationally efficient (hiệu quả vận hành nhất) – nghĩa là ít công quản trị, tự động scale cao, chi phí tối ưu theo mô hình serverless theo các best practices AWS cập nhật đến 2026 (theo AWS Well-Architected Framework Reliability & Operational Excellence Pillars).

Vấn đề cốt lõi: Tight coupling giữa các tier qua REST synchronous dẫn đến cascading failure khi overload. Giải pháp cần decoupling (tách rời) bằng async messaging và chuyển sang serverless để scale tự động, không cần quản lý server.

📘 Tài liệu tham khảo:

AWS Well-Architected Framework (2023+ updates): Reliability Pillar – Decouple components with queues.

AWS Documentation: API Gateway, Lambda, SQS (serverless patterns for microservices).

DOP-C02 Exam Guide: Serverless modernization for multi-tier apps.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.

Lý do:

🛠️ Modernize hoàn toàn: Chuyển sang serverless với API Gateway (frontend RESTful) + Lambda (application layer scale vô hạn, auto-scale theo concurrency mà không drop transactions). SQS làm decoupling layer async giữa các services, đảm bảo transactions không bị drop ngay cả khi Lambda downstream overload (SQS buffer messages).

🚀 Operationally efficient nhất: Không server (zero management), pay-per-use, tích hợp native monitoring (CloudWatch), theo serverless best practices AWS 2026 (Lambda SnapStart, Provisioned Concurrency nếu cần).

✅ Giải quyết root cause: REST sync → API Gateway + Lambda (scale front-end), SQS async (back-end decoupling).

📋 Giải thích chi tiết tất cả các phương án

✅ Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.

Đúng vì: Như phân tích trên, đây là serverless full-stack decoupling hoàn hảo. API Gateway xử lý REST ingress, Lambda scale elastic, SQS đảm bảo exactly-once delivery (FIFO nếu cần), tránh overload cascade. Hiệu quả vận hành cao nhất (ít ops, auto-heal). Theo AWS patterns cho microservices migration (2026 updates hỗ trợ SQS Lambda triggers enhanced).

❌ Use Amazon CloudWatch metrics to analyze the application performance history to determine the servers' peak utilization during the performance failures. Increase the size of the application server's Amazon EC2 instances to meet the peak requirements.

Sai vì: Chỉ vertical scaling EC2 (tăng instance size), không decoupling (vẫn REST sync → drop transactions khi overload). Không modernize (vẫn stateful servers), kém efficient (over-provisioning, chi phí cao, manual ops). CloudWatch chỉ reactive, không prevent failure.

❌ Use Amazon Simple Notification Service (Amazon SNS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SNS queue length and scale up and down as required.

Sai vì: SNS là pub/sub fan-out (fire-and-forget), không buffer/retry như queue → có thể drop messages nếu subscriber overload. Vẫn dùng EC2 Auto Scaling (không modernize, quản lý server phức tạp). Không "queue length" native cho SNS (SNS không có queue), CloudWatch monitor kém chính xác cho decoupling.

❌ Use Amazon Simple Queue Service (Amazon SQS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SQS queue length and scale up when communication failures are detected.

Sai vì: SQS tốt cho decoupling/queuing (buffer messages, tránh drop), CloudWatch + ApproximateNumberOfMessagesVisible trigger Auto Scaling hiệu quả. Nhưng vẫn EC2-based (không modernize, quản lý ASG phức tạp, cold starts), kém efficient hơn serverless Lambda. Không fully resolve overload ở app layer.

Kết luận 💡: Giải pháp serverless (API Gateway + Lambda + SQS) là best practice AWS 2026 cho modernization, đảm bảo high availability, resilience mà không cần ops overhead!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86120-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 55

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon ElastiCache, Amazon Relational Database Service
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85339-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is using a SQL database to store movie data that is publicly accessible. The database runs on an Amazon RDS Single-AZ DB instance. A script runs queries at random intervals each day to record the number of new movies that have been added to the database. The script must report a final total during business hours. The company's development team notices that the database performance is inadequate for development tasks when the script is running. A solutions architect must recommend a solution to resolve this issue. Which solution will meet this requirement with the LEAST operational overhead?

### Các lựa chọn
1. Modify the DB instance to be a Multi-AZ deployment.
2. Create a read replica of the database. Configure the script to query only the read replica.
3. Instruct the development team to manually export the entries in the database at the end of each day.
4. Use Amazon ElastiCache to cache the common queries that the script runs against the database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty sử dụng cơ sở dữ liệu SQL trên Amazon RDS Single-AZ DB instance để lưu trữ dữ liệu phim công khai. Một script chạy query ngẫu nhiên hàng ngày để ghi nhận số lượng phim mới được thêm vào DB, và phải báo cáo tổng kết cuối giờ làm việc. Vấn đề là khi script chạy, hiệu suất DB kém, ảnh hưởng đến các nhiệm vụ phát triển (development tasks) của team. Kiến trúc sư giải pháp (solutions architect) cần đề xuất giải pháp giải quyết vấn đề với ít overhead vận hành nhất (LEAST operational overhead).

🛠️ Yêu cầu cốt lõi: Offload tải đọc (read traffic) từ script khỏi DB chính (primary instance), vì script chỉ query đọc (không ghi), trong khi giữ chi phí và nỗ lực quản lý thấp nhất. RDS Single-AZ không có tính sẵn sàng cao, nhưng vấn đề chính là hiệu suất đọc, không phải failover.

✅ Đáp án đúng và lý do lựa chọn

Create a read replica of the database. Configure the script to query only the read replica.

🧩 Lý do: RDS hỗ trợ Read Replicas (bản sao chỉ đọc) để scale read traffic một cách tự động và dễ dàng. Script chỉ cần thay đổi connection string để query read replica, giảm tải hoàn toàn khỏi primary instance. Việc tạo read replica chỉ mất vài phút qua Console/CLI/API, không cần code thay đổi lớn, tự động đồng bộ async từ primary. Đây là giải pháp chuẩn AWS cho read-heavy workloads với least operational overhead (không cần quản lý cache thủ công hay export dữ liệu). Áp dụng cho SQL engines như MySQL, PostgreSQL, SQL Server (cập nhật đến 2026, hỗ trợ lên đến 15 replicas với Aurora lên 30+).

📋 Phân tích tất cả các phương án

Dưới đây là phân tích chi tiết từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh. Mỗi phương án được đánh giá đúng/sai dựa trên yêu cầu least operational overhead và giải quyết hiệu suất đọc.

❌ Modify the DB instance to be a Multi-AZ deployment.

Sai vì: Multi-AZ chỉ cung cấp high availability (HA) qua synchronous standby replica cho failover tự động (khoảng 60-120 giây), không offload read traffic. Primary vẫn xử lý tất cả reads/writes, script vẫn làm chậm DB chính. Overhead thấp về setup nhưng không giải quyết vấn đề hiệu suất dev tasks. Phù hợp cho disaster recovery, không phải scaling reads.

✅ Create a read replica of the database. Configure the script to query only the read replica.

Đúng vì: Như đã giải thích ở trên. Đây là giải pháp tối ưu nhất: Tự động replicate dữ liệu, script đọc từ replica (lag <1 giây thường), primary dành cho dev writes. Overhead thấp: Tạo replica qua AWS Console (1-click), monitor qua CloudWatch, scale dễ dàng. Không ảnh hưởng downtime.

❌ Instruct the development team to manually export the entries in the database at the end of each day.

Sai vì: Giải pháp thủ công hoàn toàn, yêu cầu team export dữ liệu hàng ngày (qua mysqldump hoặc AWS Database Migration Service), lưu trữ (S3?), rồi script đọc từ file. Overhead vận hành cao: Lỗi thủ công, không realtime (script chạy random intervals), không báo tổng business hours kịp thời, tốn thời gian dev team. Không scale và không chuyên nghiệp cho production.

❌ Use Amazon ElastiCache to cache the common queries that the script runs against the database.

Sai vì: ElastiCache (Redis/Memcached) cache queries, nhưng script query random intervals về dữ liệu mới (new movies) → cache miss thường xuyên, không hiệu quả 100%. Overhead cao: Setup cluster, code thay đổi (app-level caching với TTL), quản lý eviction/invalidation, monitor hit ratio. Phức tạp hơn read replica cho read-only script, và không đảm bảo fresh data realtime.

📘 Tài liệu tham khảo (cập nhật AWS 2026)

AWS RDS Read Replicas: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html – Hướng dẫn tạo replica, lag monitoring.

RDS Multi-AZ vs Read Replicas: aws.amazon.com/rds/features/read-replicas/ – So sánh rõ ràng.

DOP-C02 Exam Guide: AWS Certified DevOps Engineer Professional (2024+), Domain 4: Automation, phần RDS scaling.

Best Practices: AWS Well-Architected Framework – Reliability Pillar: Offload reads với replicas (whitepaper 2025).

🛠️ Kết luận: Read Replica là lựa chọn proactive, scalable nhất cho workload này! Nếu cần lab thực hành, dùng AWS Free Tier RDS.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85339-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 56

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon S3, Amazon EC2, Amazon Virtual Private Cloud
- Đáp án tham khảo: **Configure an S3 gateway endpoint.**
- Takeaway nhanh: Traffic được route trực tiếp qua prefix list của S3 (không cần public IP). Miễn phí (không tính phí data transfer), dễ cấu hình qua VPC console hoặc CloudFormation. Hỗ trợ VPC endpoint policy để kiểm soát quyền truy cập chi tiết (IAM-like). Phù hợp với kiến trúc zero-trust và quy định "no internet traffic". Đây là tính năng ổn định từ AWS VPC, cập nhật mới nhất (2024-2026) vẫn giữ nguyên, tích hợp tốt với VPC Flow Logs để monitor.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/vpc/latest/privatelink/gateway-endpoints.html | https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html | https://www.examtopics.com/discussions/amazon/view/85667-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no traffic from the applications is allowed to travel across the internet. Which solution will meet these requirements?

### Các lựa chọn
1. Configure an S3 gateway endpoint.
2. Create an S3 bucket in a private subnet.
3. Create an S3 bucket in the same AWS Region as the EC2 instances.
4. Configure a NAT gateway in the same subnet as the EC2 instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một tình huống thực tế trong AWS: Một công ty có các ứng dụng chạy trên các instance Amazon EC2 nằm trong một VPC (Virtual Private Cloud). Một trong số các ứng dụng này cần gọi API của Amazon S3 để lưu trữ (store) và đọc (read) các object (đối tượng dữ liệu). Yêu cầu bảo mật nghiêm ngặt từ công ty: Không cho phép bất kỳ traffic nào từ các ứng dụng đi qua internet.

Mục tiêu là tìm giải pháp cho phép EC2 truy cập S3 mà không cần route traffic qua internet công khai, đảm bảo tính riêng tư, bảo mật và tuân thủ quy định. Đây là kịch bản phổ biến trong kiến trúc VPC với các dịch vụ AWS, nơi cần private connectivity đến S3 mà không sử dụng public internet hoặc NAT.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Configure an S3 gateway endpoint.

Lý do chi tiết:

🛠️ S3 Gateway Endpoint (hay còn gọi là VPC Gateway Endpoint cho S3) là giải pháp lý tưởng và được AWS khuyến nghị. Nó tạo ra một endpoint riêng tư trong VPC, cho phép traffic từ EC2 đến S3 đi hoàn toàn qua mạng backbone riêng của AWS (AWS private global network), không bao giờ chạm đến internet.

Traffic được route trực tiếp qua prefix list của S3 (không cần public IP).

Miễn phí (không tính phí data transfer), dễ cấu hình qua VPC console hoặc CloudFormation.

Hỗ trợ VPC endpoint policy để kiểm soát quyền truy cập chi tiết (IAM-like).

Phù hợp với kiến trúc zero-trust và quy định "no internet traffic". Đây là tính năng ổn định từ AWS VPC, cập nhật mới nhất (2024-2026) vẫn giữ nguyên, tích hợp tốt với VPC Flow Logs để monitor.

📋 Giải thích tất cả các phương án (đúng và sai)

Dưới đây là phân tích từng lựa chọn một cách chi tiết. Tôi giữ nguyên nội dung văn bản gốc bằng tiếng Anh, nhưng giải thích hoàn toàn bằng tiếng Việt với lý do đúng/sai rõ ràng:

✅ Configure an S3 gateway endpoint.

🟢 Đúng 100%. Như đã giải thích ở trên, đây là giải pháp native của AWS dành riêng cho S3, đảm bảo private traffic từ VPC đến S3 mà không qua internet. Không cần thay đổi route table (chỉ thêm route 0.0.0.0/0 -> pl-xxxx cho prefix S3), hiệu suất cao và scalable.

❌ Create an S3 bucket in a private subnet.

🔴 Sai hoàn toàn. Buckets S3 không được tạo trong subnet (private hay public). S3 buckets là global resources (hoặc regional), tồn tại ở edge locations của AWS, không thuộc VPC/subnet. Việc tạo bucket ở private subnet là không thể thực hiện trên AWS – đây là hiểu lầm cơ bản về S3 architecture.

❌ Create an S3 bucket in the same AWS Region as the EC2 instances.

🔴 Sai. Việc đặt bucket cùng Region chỉ giảm latency và chi phí transfer intra-Region, nhưng traffic từ EC2 vẫn đi qua public internet nếu không có endpoint (S3 public endpoints mặc định dùng internet). Không giải quyết yêu cầu "no internet traffic", chỉ là best practice chung không liên quan trực tiếp.

❌ Configure a NAT gateway in the same subnet as the EC2 instances.

🔴 Sai và ngược lại với yêu cầu. NAT Gateway (ở public subnet) cho phép outbound traffic từ private subnet ra internet (masquerade private IP thành public Elastic IP). Traffic đến S3 vẫn đi qua internet (qua NAT -> IGW), phát sinh chi phí data transfer và vi phạm quy định bảo mật. NAT chỉ phù hợp khi cần internet access, không phải private-to-S3.

📘 Tài liệu tham khảo (cập nhật AWS 2024-2026)

AWS Documentation chính thức: VPC Endpoints for Amazon S3 (Gateway) – Hướng dẫn cấu hình chi tiết, policy và troubleshooting.

AWS Well-Architected Framework (Security Pillar): Nhấn mạnh Gateway Endpoints cho S3 để tránh internet exposure (xem Reliability & Security whitepapers).

AWS re:Post & Best Practices: S3 VPC Endpoint Guide (PrivateLink là Interface Endpoint, nhưng Gateway là free tier cho S3).

Exam Tips DOP-C02: Chủ đề VPC Networking & Endpoints chiếm tỷ lệ cao (AWS Certification Guide 2024).

Giải pháp này đơn giản, hiệu quả và tuân thủ zero-egress-internet! Nếu cần demo CloudFormation template, hãy cho tôi biết nhé! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85667-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/vpc/latest/privatelink/gateway-endpoints.html

https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html

## Câu 57

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon EBS, Amazon S3, Amazon Relational Database Service
- Đáp án tham khảo: **Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.**
- Takeaway nhanh: Bước 1: Lấy latest DB snapshot (unencrypted), sau đó copy snapshot và enable encryption (sử dụng AWS KMS key mặc định hoặc custom). Bước 2: Restore encrypted snapshot thành DB instance mới (cùng engine, version, Multi-AZ), sau đó thay thế (replace) instance cũ bằng instance mới qua DNS failover (endpoint tự động chuyển). Kết quả: Instance mới luôn mã hóa, tất cả snapshots mới từ instance này sẽ tự động mã hóa. Snapshots cũ giữ nguyên (unencrypted), nhưng yêu cầu chỉ "moving forward" (từ nay).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html#:~:text=You%20can%27t%20restore%20from%20a%20DB%20snapshot%20to%20an%20existing%20DB%20instance%3B%20a%20new%20DB%20instance%20is%20created%20when%20you%20restore | https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/encrypt-an-existing-amazon-rds-for-postgresql-db-instance.html | https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/encrypt-an-existing-amazon-rds-for-postgresql-db-instance.htmlI | https://www.examtopics.com/discussions/amazon/view/85941-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is running an online transaction processing (OLTP) workload on AWS. This workload uses an unencrypted Amazon RDS DB instance in a Multi-AZ deployment. Daily database snapshots are taken from this instance. What should a solutions architect do to ensure the database and snapshots are always encrypted moving forward?

### Các lựa chọn
1. Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.
2. Create a new encrypted Amazon Elastic Block Store (Amazon EBS) volume and copy the snapshots to it. Enable encryption on the DB instance.
3. Copy the snapshots and enable encryption using AWS Key Management Service (AWS KMS) Restore encrypted snapshot to an existing DB instance.
4. Copy the snapshots to an Amazon S3 bucket that is encrypted using server-side encryption with AWS Key Management Service (AWS KMS) managed keys (SSE-KMS).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi trắc nghiệm AWS

✅ Nội dung câu hỏi được giải thích rõ ràng:

Câu hỏi tập trung vào một workload OLTP (Online Transaction Processing - xử lý giao dịch trực tuyến) đang chạy trên AWS, sử dụng Amazon RDS DB instance không được mã hóa (unencrypted) trong cấu hình Multi-AZ deployment (triển khai đa vùng khả dụng để đảm bảo high availability). Hàng ngày, các database snapshots (ảnh chụp sao lưu) được lấy từ instance này.

Mục tiêu: Đảm bảo database instance và tất cả snapshots từ nay trở đi luôn được mã hóa (encrypted).

🛠️ Thách thức chính: RDS instance đang chạy không thể mã hóa trực tiếp (theo chính sách AWS, chỉ có thể mã hóa khi tạo mới hoặc restore từ snapshot đã mã hóa). Do đó, cần một quy trình an toàn để chuyển đổi mà không làm gián đoạn dịch vụ lâu dài, đồng thời áp dụng cho cả instance hiện tại và snapshots tương lai. Kiến thức này dựa trên tài liệu AWS RDS cập nhật mới nhất (2024-2026), nơi mã hóa tại rest sử dụng AWS KMS keys.

🟢 Đáp án đúng và lý do lựa chọn:

Đáp án đúng: Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.

✅ Lý do chi tiết:

Bước 1: Lấy latest DB snapshot (unencrypted), sau đó copy snapshot và enable encryption (sử dụng AWS KMS key mặc định hoặc custom).

Bước 2: Restore encrypted snapshot thành DB instance mới (cùng engine, version, Multi-AZ), sau đó thay thế (replace) instance cũ bằng instance mới qua DNS failover (endpoint tự động chuyển).

Kết quả: Instance mới luôn mã hóa, tất cả snapshots mới từ instance này sẽ tự động mã hóa. Snapshots cũ giữ nguyên (unencrypted), nhưng yêu cầu chỉ "moving forward" (từ nay).

🛡️ An toàn cho production: Downtime tối thiểu (<5 phút với Multi-AZ), không mất dữ liệu. Đây là best practice chính thức từ AWS.

📘 Tài liệu tham khảo: AWS RDS Encryption Docs và Encrypt Existing RDS Tutorial (cập nhật 2024).

📋 Phân tích tất cả các phương án (đúng/sai)

✅ [ĐÚNG] Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.

🟢 Giải thích đúng: Như đã phân tích ở trên, đây là quy trình chuẩn AWS: Copy snapshot → Enable encryption → Restore → Switchover. Đảm bảo mã hóa cho instance và snapshots tương lai mà không vi phạm hạn chế của RDS (không mã hóa trực tiếp instance đang chạy).

❌ [SAI] Create a new encrypted Amazon Elastic Block Store (Amazon EBS) volume and copy the snapshots to it. Enable encryption on the DB instance.

❌ Giải thích sai: RDS sử dụng managed storage (không expose trực tiếp EBS volumes cho user). Không thể "copy snapshots to EBS volume" thủ công vì snapshots RDS là proprietary format, chỉ thao tác qua RDS console/CLI/API. "Enable encryption on DB instance" đang chạy là không thể (AWS không hỗ trợ). Phương án này sai về kiến trúc và không khả thi.

❌ [SAI] Copy the snapshots and enable encryption using AWS Key Management Service (AWS KMS) Restore encrypted snapshot to an existing DB instance.

❌ Giải thích sai: Copy snapshot và enable KMS encryption là đúng một phần, nhưng "restore to existing DB instance" là sai. AWS không cho phép restore snapshot encrypted vào instance unencrypted đang tồn tại (sẽ lỗi "incompatible encryption status"). Phải tạo instance mới rồi replace, không phải overwrite existing.

❌ [SAI] Copy the snapshots to an Amazon S3 bucket that is encrypted using server-side encryption with AWS Key Management Service (AWS KMS) managed keys (SSE-KMS).

❌ Giải thích sai: RDS snapshots không thể copy trực tiếp sang S3 như vậy (S3 dùng cho object storage, RDS snapshots là block-level). Export to S3 chỉ hỗ trợ cho Aurora (parquet format), không phải RDS OLTP chung. Mã hóa S3 không ảnh hưởng đến RDS instance/snapshots gốc. Phương án này không giải quyết vấn đề mã hóa DB at-rest.

🔍 Kết luận: Phương án đúng duy nhất tuân thủ quy trình AWS RDS encryption workflow. Áp dụng ngay cho production để tuân thủ compliance (GDPR, HIPAA). Nếu cần script automation, dùng AWS CLI: aws rds copy-db-snapshot --source-db-snapshot-identifier ... --target-db-snapshot-identifier ... --kms-key-id ....

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85941-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/encrypt-an-existing-amazon-rds-for-postgresql-db-instance.htmlI

https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/encrypt-an-existing-amazon-rds-for-postgresql-db-instance.html

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html#:~:text=You%20can%27t%20restore%20from%20a%20DB%20snapshot%20to%20an%20existing%20DB%20instance%3B%20a%20new%20DB%20instance%20is%20created%20when%20you%20restore.

## Câu 58

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon SNS, Amazon Lambda, Amazon CloudWatch, Amazon Config, Amazon Trusted Advisor, Amazon Certificate Manager
- Đáp án tham khảo: **Create an AWS Config rule that checks for certificates that will expire within 30 days. Configure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notification Service (Amazon SNS) when AWS Config reports a noncompliant resource.**
- Takeaway nhanh: 🛡️ AWS Config managed rule acm-certificate-expiration-check chính xác kiểm tra imported certs trong ACM sắp hết hạn trong 30 ngày (configurable parameter: daysToExpiration = 30). Khi rule phát hiện NON_COMPLIANT, AWS Config tự động publish event đến EventBridge (trước đây là CloudWatch Events). EventBridge rule dễ dàng invoke SNS topic để gửi thông báo (email/SMS) cho security team – tự động, scalable, chi phí thấp.
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/acm-certificate-expiration/ | https://www.examtopics.com/discussions/amazon/view/85615-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts its web applications in the AWS Cloud. The company configures Elastic Load Balancers to use certificates that are imported into AWS Certificate Manager (ACM). The company's security team must be notified 30 days before the expiration of each certificate. What should a solutions architect recommend to meet this requirement?

### Các lựa chọn
1. Add a rule in ACM to publish a custom message to an Amazon Simple Notification Service (Amazon SNS) topic every day, beginning 30 days before any certificate will expire.
2. Create an AWS Config rule that checks for certificates that will expire within 30 days. Configure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notification Service (Amazon SNS) when AWS Config reports a noncompliant resource.
3. Use AWS Trusted Advisor to check for certificates that will expire within 30 days. Create an Amazon CloudWatch alarm that is based on Trusted Advisor metrics for check status changes. Configure the alarm to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).
4. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to detect any certificates that will expire within 30 days. Configure the rule to invoke an AWS Lambda function. Configure the Lambda function to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc giám sát và thông báo tự động về thời hạn hết hạn của chứng chỉ SSL/TLS được quản lý bởi AWS Certificate Manager (ACM). Công ty đang sử dụng Elastic Load Balancers (ELB) để phân tải các ứng dụng web trên AWS Cloud, và các chứng chỉ được import vào ACM. Yêu cầu cụ thể là thông báo cho đội ngũ bảo mật (security team) đúng 30 ngày trước khi mỗi chứng chỉ hết hạn.

🛠️ Vấn đề cốt lõi: ACM không tự động gửi thông báo về hết hạn chứng chỉ (trừ khi là certs do ACM cấp tự động, nhưng ở đây là imported certs). Cần một giải pháp tự động, đáng tin cậy để kiểm tra định kỳ và trigger alert qua Amazon SNS. Giải pháp phải tuân thủ best practices AWS, sử dụng các dịch vụ tích hợp như AWS Config, EventBridge để phát hiện non-compliance và gửi thông báo kịp thời.

📘 Kiến thức cập nhật AWS (đến 2026): AWS Config có managed rule acm-certificate-expiration-check (ra mắt từ 2020, cập nhật liên tục) kiểm tra chứng chỉ ACM sắp hết hạn trong khoảng thời gian chỉ định (ví dụ: 30 ngày). Rule này đánh dấu resource là NON_COMPLIANT khi cert expire trong X ngày, và có thể trigger EventBridge cho alert.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an AWS Config rule that checks for certificates that will expire within 30 days. Configure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notification Service (Amazon SNS) when AWS Config reports a noncompliant resource.

Lý do chọn:

🛡️ AWS Config managed rule acm-certificate-expiration-check chính xác kiểm tra imported certs trong ACM sắp hết hạn trong 30 ngày (configurable parameter: daysToExpiration = 30).

Khi rule phát hiện NON_COMPLIANT, AWS Config tự động publish event đến EventBridge (trước đây là CloudWatch Events).

EventBridge rule dễ dàng invoke SNS topic để gửi thông báo (email/SMS) cho security team – tự động, scalable, chi phí thấp.

Đây là best practice từ AWS Well-Architected Framework (Security Pillar), đảm bảo compliance monitoring liên tục mà không cần code custom.

Dẫn nguồn:

AWS Config Managed Rules: acm-certificate-expiration-check (cập nhật 2025).

EventBridge với AWS Config.

❌ Phân tích tất cả các phương án (đúng/sai)

Phương án 1: Add a rule in ACM to publish a custom message to an Amazon Simple Notification Service (Amazon SNS) topic every day, beginning 30 days before any certificate will expire.

❌ Sai vì: ACM không hỗ trợ rule tự publish SNS daily cho cert expiration. ACM chỉ gửi email thông báo cho owner nếu là cert tự cấp (không phải imported), và không có tính năng "rule" trong ACM để schedule daily check 30 ngày trước. Giải pháp này không tồn tại trong ACM (kiểm tra docs ACM 2026: chỉ có export cert, không có notification rules).

Phương án 2 (Đúng): Create an AWS Config rule that checks for certificates that will expire within 30 days. Configure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notification Service (Amazon SNS) when AWS Config reports a noncompliant resource.

✅ Đúng vì: Như giải thích ở trên – sử dụng AWS Config managed rule chuyên biệt, kết hợp EventBridge + SNS cho alert chính xác, tự động khi non-compliant. Hoàn hảo cho imported certs.

Phương án 3: Use AWS Trusted Advisor to check for certificates that will expire within 30 days. Create an Amazon CloudWatch alarm that is based on Trusted Advisor metrics for check status changes. Configure the alarm to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).

❌ Sai vì: Trusted Advisor có check "ACM Certificate Expiration" nhưng chỉ recommendation, không phải monitoring real-time. Metrics của Trusted Advisor (qua CloudWatch) không granular cho exactly 30 days (chỉ "high/medium risk"), và check chạy hàng tuần, không trigger alarm đáng tin cậy cho daily/30-day alert. Không phải giải pháp production-grade (docs Trusted Advisor 2026: chỉ advisory, không thay thế Config).

Phương án 4: Create an Amazon EventBridge (Amazon CloudWatch Events) rule to detect any certificates that will expire within 30 days. Configure the rule to invoke an AWS Lambda function. Configure the Lambda function to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).

❌ Sai vì: EventBridge không có event tự động cho "cert expire within 30 days" từ ACM (ACM không emit CloudWatch Events cho expiration). Phải dùng Lambda poll thủ công (không efficient, tốn kém), hoặc scan API – vi phạm best practice (thêm complexity, no native support). AWS khuyến nghị dùng Config thay vì custom polling.

🧠 Kết luận: Giải pháp đúng tận dụng tích hợp native AWS để đảm bảo tuân thủ, tự động hóa cao mà không cần code thêm. Nếu implement, enable AWS Config aggregator cho multi-account! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85615-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/premiumsupport/knowledge-center/acm-certificate-expiration/

## Câu 59

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon DataSync, Amazon EBS, Amazon EFS, Amazon EC2
- Takeaway nhanh: AWS DataSync là giải pháp tự động hóa tối ưu cho việc transfer file từ on-premises (NFS/SFTP) sang EFS. Bước 1: Cài agent trên on-premises (VM có access NFS/SFTP server) để DataSync kết nối source an toàn, hỗ trợ incremental sync, compression, verification (giảm thời gian transfer 200 GB xuống hàng giờ). Bước 2: Tạo location cho SFTP server (source) và EFS (destination), sau đó tạo task để automate sync. EC2 mount EFS sau khi data sẵn sàng để host SFTP server mới.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/datasync/latest/userguide/create-sftp-location.html | https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html | https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html | https://www.examtopics.com/discussions/amazon/view/85814-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company wants to migrate an on-premises data center to AWS. The data center hosts an SFTP server that stores its data on an NFS-based file system. The server holds 200 GB of data that needs to be transferred. The server must be hosted on an Amazon EC2 instance that uses an Amazon Elastic File System (Amazon EFS) file system. Which combination of steps should a solutions architect take to automate this task? (Choose two.)

### Các lựa chọn
1. Launch the EC2 instance into the same Availability Zone as the EFS file system.
2. Install an AWS DataSync agent in the on-premises data center.
3. Create a secondary Amazon Elastic Block Store (Amazon EBS) volume on the EC2 instance for the data.
4. Manually use an operating system copy command to push the data to the EC2 instance.
5. Use AWS DataSync to create a suitable location configuration for the on-premises SFTP server.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty muốn migrate (di chuyển) data center on-premises sang AWS. Cụ thể:

On-premises có SFTP server lưu trữ dữ liệu trên NFS-based file system, tổng dung lượng 200 GB cần transfer.

Trên AWS, server mới phải chạy trên Amazon EC2 instance sử dụng Amazon EFS làm file system (EFS là dịch vụ file storage chia sẻ, hỗ trợ multi-AZ, scalable).

Yêu cầu: Solutions Architect cần chọn kết hợp 2 bước để automate (tự động hóa) quá trình này. Mục tiêu chính là transfer dữ liệu từ NFS on-premises sang EFS trên EC2 một cách tự động, hiệu quả, tránh manual, tận dụng công cụ AWS chuyên dụng cho data migration như AWS DataSync (dịch vụ sync file giữa on-premises và AWS, hỗ trợ NFS, SFTP, EFS, tốc độ cao lên đến 10 Gbps, cập nhật mới nhất 2024-2026 với hỗ trợ SFTP locations không cần agent cho network-accessible servers).

📘 Nguồn tham khảo:

AWS DataSync User Guide: https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html

EFS Documentation: https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html

DataSync SFTP Locations (2023+): https://docs.aws.amazon.com/datasync/latest/userguide/create-sftp-location.html

✅ Đáp án đúng (Chọn TWO)

Hai bước đúng là:

Install an AWS DataSync agent in the on-premises data center.

Use AWS DataSync to create a suitable location configuration for the on-premises SFTP server.

Lý do lựa chọn 🛠️:

AWS DataSync là giải pháp tự động hóa tối ưu cho việc transfer file từ on-premises (NFS/SFTP) sang EFS.

Bước 1: Cài agent trên on-premises (VM có access NFS/SFTP server) để DataSync kết nối source an toàn, hỗ trợ incremental sync, compression, verification (giảm thời gian transfer 200 GB xuống hàng giờ).

Bước 2: Tạo location cho SFTP server (source) và EFS (destination), sau đó tạo task để automate sync. EC2 mount EFS sau khi data sẵn sàng để host SFTP server mới.

Kết hợp này automate hoàn toàn, scalable, không downtime lớn. Phiên bản DataSync mới nhất (2026) hỗ trợ SFTP trực tiếp với agent cho hybrid setups.

📋 Giải thích chi tiết TẤT CẢ các phương án

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc tiếng Anh:

❌ Launch the EC2 instance into the same Availability Zone as the EFS file system.

Sai vì Amazon EFS là multi-AZ bằng default (Regional service), EC2 có thể mount EFS từ bất kỳ AZ nào trong cùng Region qua DNS name (Mount target cross-AZ). Không cần same AZ, tránh single point of failure. Nếu force same AZ, giảm tính available/high availability. 🛑

✅ Install an AWS DataSync agent in the on-premises data center.

Đúng vì DataSync yêu cầu agent (VM appliance) cài trên on-premises để access NFS/SFTP backend an toàn (firewall/VPN), scan metadata, hỗ trợ protocol conversion NFS → EFS. Agent chạy trên VM Linux (4 vCPU, 16 GB RAM), deploy OVA, kết nối STS endpoint AWS. Automate transfer 200 GB nhanh chóng với scheduling. 🚀

❌ Create a secondary Amazon Elastic Block Store (Amazon EBS) volume on the EC2 instance for the data.

Sai vì câu hỏi yêu cầu EFS file system (shared, POSIX-compliant, multi-instance access cho SFTP server). EBS là block storage single-AZ/single-instance, không phù hợp NFS-like sharing, kém scalable/costly cho 200 GB shared data. Phải dùng EFS làm chính. 🔒

❌ Manually use an operating system copy command to push the data to the EC2 instance.

Sai vì không automate (manual scp/rsync qua internet/VPN chậm, error-prone, không incremental/compression). Với 200 GB, mất ngày, không scalable, vi phạm yêu cầu "automate this task". DataSync tốt hơn gấp 10x tốc độ. ⏰

✅ Use AWS DataSync to create a suitable location configuration for the on-premises SFTP server.

Đúng vì DataSync hỗ trợ SFTP location trực tiếp (server IP/port/user/key, private/public key auth). Tạo source location cho SFTP server (access data on NFS backend), destination EFS (EC2 mount sau). Task chạy automate, filter/sync chỉ changed files, verify integrity. Hoàn hảo cho migration SFTP → EFS. 🔄

🧠 Lưu ý bổ sung: Sau hai bước trên, tạo DataSync Task + Location cho EFS (EFS access point cho security), chạy once/many, rồi launch EC2 mount EFS với SFTP software (OpenSSH). Tổng thời gian: <1 ngày cho 200 GB. Test trước production với small subset!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85814-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 60

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SQS, Amazon EC2, Amazon Relational Database Service
- Takeaway nhanh: API ChangeMessageVisibility cho phép tăng động (extend) visibility timeout của tin nhắn cụ thể sau khi nhận (ReceiveMessage). Ví dụ: Sau khi nhận message, gọi API này để set timeout lên 5-10 phút (tùy thời gian xử lý RDS), đảm bảo tin nhắn invisible đủ lâu cho đến khi delete thành công. Điều này ngăn chặn việc message visible lại và bị xử lý trùng. Đây là best practice cho SQS Standard để tránh duplicate processing mà không cần chuyển sang FIFO (phức tạp hơn). Kiến thức cập nhật DOP-C02 (2023-2026): Vẫn là giải pháp chuẩn, hỗ trợ lên đến 12 giờ timeout.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_ChangeMessageVisibility.html | https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html#sqs-long-polling | https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html | https://www.examtopics.com/discussions/amazon/view/85583-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company hosts an application on multiple Amazon EC2 instances. The application processes messages from an Amazon SQS queue, writes to an Amazon RDS table, and deletes the message from the queue. Occasional duplicate records are found in the RDS table. The SQS queue does not contain any duplicate messages. What should a solutions architect do to ensure messages are being processed once only?

### Các lựa chọn
1. Use the CreateQueue API call to create a new queue.
2. Use the AddPermission API call to add appropriate permissions.
3. Use the ReceiveMessage API call to set an appropriate wait time.
4. Use the ChangeMessageVisibility API call to increase the visibility timeout.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết câu hỏi trắc nghiệm AWS

📖 Nội dung câu hỏi:

Câu hỏi mô tả một ứng dụng được triển khai trên nhiều instance Amazon EC2, xử lý tin nhắn (messages) từ hàng đợi Amazon SQS theo quy trình: nhận tin nhắn → ghi dữ liệu vào bảng Amazon RDS → xóa tin nhắn khỏi queue. Vấn đề xảy ra là có bản ghi trùng lặp (duplicate records) trong bảng RDS, mặc dù hàng đợi SQS không chứa tin nhắn trùng lặp.

🔍 Nguyên nhân cốt lõi: Đây là hàng đợi SQS Standard (không phải FIFO, vì FIFO có cơ chế deduplication tự động). Trong SQS Standard, khi một instance EC2 gọi ReceiveMessage, tin nhắn được đánh dấu invisible trong khoảng thời gian visibility timeout (mặc định 30 giây). Nếu quá trình xử lý (processing: write RDS + delete) kéo dài hơn visibility timeout, tin nhắn sẽ trở nên visible lại, dẫn đến instance khác (hoặc cùng instance) nhận và xử lý lại, gây duplicate records trong RDS. SQS không có duplicate messages gốc, nhưng at-least-once delivery kết hợp timeout ngắn gây vấn đề.

🛠️ Mục tiêu giải pháp: Đảm bảo tin nhắn chỉ được xử lý một lần duy nhất (exactly-once processing) bằng cách kéo dài thời gian invisible của tin nhắn trong quá trình xử lý.

✅ Đáp án đúng: Use the ChangeMessageVisibility API call to increase the visibility timeout.

Lý do lựa chọn:

API ChangeMessageVisibility cho phép tăng động (extend) visibility timeout của tin nhắn cụ thể sau khi nhận (ReceiveMessage). Ví dụ: Sau khi nhận message, gọi API này để set timeout lên 5-10 phút (tùy thời gian xử lý RDS), đảm bảo tin nhắn invisible đủ lâu cho đến khi delete thành công. Điều này ngăn chặn việc message visible lại và bị xử lý trùng. Đây là best practice cho SQS Standard để tránh duplicate processing mà không cần chuyển sang FIFO (phức tạp hơn). Kiến thức cập nhật DOP-C02 (2023-2026): Vẫn là giải pháp chuẩn, hỗ trợ lên đến 12 giờ timeout.

🔍 Giải thích tất cả các phương án (Đúng/Sai)

❌ Use the CreateQueue API call to create a new queue.

Phân tích sai: API CreateQueue chỉ dùng để tạo queue mới, không giải quyết vấn đề duplicate processing ở queue hiện tại. Tạo queue mới không thay đổi cơ chế visibility timeout hay xử lý tin nhắn cũ, vẫn dẫn đến duplicate records. Không liên quan trực tiếp đến vấn đề.

❌ Use the AddPermission API call to add appropriate permissions.

Phân tích sai: API AddPermission dùng để cấp quyền truy cập queue cho các principal khác (như Lambda hoặc EC2 roles). Vấn đề ở đây không phải permissions (app đã poll và delete được), mà là timeout xử lý. Thêm permission chỉ làm tăng rủi ro (nhiều consumer tranh nhau), không fix duplicate.

❌ Use the ReceiveMessage API call to set an appropriate wait time.

Phân tích sai: Tham số WaitTimeSeconds trong ReceiveMessage chỉ kích hoạt long polling (chờ tin nhắn mới lên đến 20 giây, giảm empty receives và polling overhead). Nó không ảnh hưởng đến visibility timeout sau khi nhận message, nên không ngăn chặn duplicate do timeout hết hạn trong processing.

✅ Use the ChangeMessageVisibility API call to increase the visibility timeout.

Phân tích đúng: Như đã giải thích ở trên, API này extend visibility timeout cụ thể cho từng message (từ 0 giây đến 12 giờ, tùy queue config). Gọi ngay sau ReceiveMessage và trước delete, đảm bảo processing hoàn tất mà không bị poll lại. Hoàn hảo cho multi-instance EC2, tránh duplicate RDS. (Ví dụ code: sqs.change_message_visibility(QueueUrl, ReceiptHandle, VisibilityTimeout=300)).

📘 Tài liệu tham khảo (Cập nhật AWS 2026)

AWS SQS Developer Guide - Visibility Timeout: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html 🛡️

ChangeMessageVisibility API: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_ChangeMessageVisibility.html 🔗

DOP-C02 Exam Guide (2023-2026): Domain 3.1 - Implement messaging solutions with Amazon SQS (at-least-once semantics). 📚

Best Practices: AWS Well-Architected Framework - Reliability Pillar (SQS processing patterns).

Hy vọng phân tích này giúp bạn ôn thi hiệu quả! 🚀 Nếu cần ví dụ code hoặc lab thực hành, hãy hỏi thêm.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85583-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html#sqs-long-polling

## Câu 61

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Auto Scaling Group, Amazon MQ, Amazon EC2, Amazon Relational Database Service
- Đáp án tham khảo: **[D] Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.**
- Takeaway nhanh: Tổng thể: Kiến trúc này HIGHEST availability vì tất cả components đều fully managed HA multi-AZ, tự động recover, scale → Không downtime single AZ failure, ops thấp nhất.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/85910-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company recently migrated a message processing system to AWS. The system receives messages into an ActiveMQ queue running on an Amazon EC2 instance. Messages are processed by a consumer application running on Amazon EC2. The consumer application processes the messages and writes results to a MySQL database running on Amazon EC2. The company wants this application to be highly available with low operational complexity. Which architecture offers the HIGHEST availability?

### Các lựa chọn
1. Add a second ActiveMQ server to another Availability Zone. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
2. Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
3. Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Use Amazon RDS for MySQL with Multi-AZ enabled.
4. Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc thiết kế kiến trúc hệ thống xử lý message trên AWS với yêu cầu highly available (HA cao nhất) và low operational complexity (độ phức tạp vận hành thấp).

Hệ thống hiện tại:

Nhận message vào ActiveMQ queue chạy trên EC2 instance (self-managed).

Consumer application trên EC2 xử lý message và ghi kết quả vào MySQL database trên EC2 (cũng self-managed).

Vấn đề: Hệ thống này chỉ chạy trên một AZ (Availability Zone), dễ bị downtime nếu AZ fail.

Mục tiêu: Chuyển sang kiến trúc multi-AZ để đảm bảo HA, giảm công quản lý thủ công (như replicate DB, scale EC2 thủ công).

Kiến thức AWS cập nhật 2026: Amazon MQ (managed ActiveMQ) hỗ trợ active/standby brokers multi-AZ tự động failover. EC2 Auto Scaling Group (ASG) tự động scale và phân bổ instances multi-AZ. RDS Multi-AZ với standby replica tự động failover trong <60s, zero data loss nếu dùng sync replication.

📘 Tài liệu tham khảo:

AWS Amazon MQ HA: docs.aws.amazon.com/AmazonMQ/latest/developer-guide/highly-available-broker.html

RDS Multi-AZ: docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html

EC2 ASG multi-AZ: docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: [D] Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

Lý do:

🛠️ Amazon MQ active/standby multi-AZ: Managed service, tự động failover broker từ active sang standby nếu AZ fail, không cần quản lý thủ công → HA cao, low ops.

🛠️ Auto Scaling Group (ASG) cho consumer EC2 multi-AZ: Tự động launch/terminate instances dựa trên CPU/load, phân bổ đều AZs, health checks tự heal → Scale ngang tự động, chịu fault tốt hơn "additional instance" thủ công.

🛠️ RDS MySQL Multi-AZ: Tự động sync replica sang AZ khác, failover <60s với RPO=0 → Managed DB, backup, patching tự động.

Tổng thể: Kiến trúc này HIGHEST availability vì tất cả components đều fully managed HA multi-AZ, tự động recover, scale → Không downtime single AZ failure, ops thấp nhất.

❌ Phân tích tất cả các phương án (đúng/sai)

Dưới đây là phân tích từng lựa chọn, giữ nguyên văn bản gốc bằng tiếng Anh. Mỗi phương án được đánh giá dựa trên HA level và ops complexity:

[SAI] Add a second ActiveMQ server to another Availability Zone. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.

❌ Sai vì: Self-managed ActiveMQ (cần config clustering thủ công, failover không tự động). Consumer chỉ "additional instance" → Không auto-scale, phải manual manage load balance/health check. MySQL replicate thủ công → Rủi ro data loss, patching/backup manual. HA thấp, ops cao (không managed).

[SAI] Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.

❌ Sai vì: Amazon MQ tốt (managed HA), nhưng consumer "additional instance" → Manual scale, không auto-heal. MySQL replicate thủ công → Không failover tự động, data inconsistency rủi ro. HA trung bình, ops vẫn cao ở consumer/DB.

[SAI] Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Use Amazon RDS for MySQL with Multi-AZ enabled.

❌ Sai vì: Amazon MQ và RDS Multi-AZ xuất sắc (managed HA), nhưng consumer chỉ "additional instance" → Không auto-scale theo demand, single instance fail trong AZ → Không chịu load cao hoặc heal tự động. HA tốt nhưng chưa highest vì thiếu ASG.

[ĐÚNG] Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

✅ Đúng vì: Toàn bộ stack fully managed multi-AZ HA: MQ failover tự động, ASG scale/heal consumer, RDS failover DB. Highest availability (99.99%+ SLA), lowest ops (AWS handle patching, backup, scaling).

🛠️ Kết luận: Lựa chọn D vượt trội vì tích hợp 3 managed services HA + ASG, đảm bảo hệ thống chịu fault toàn diện mà không cần can thiệp thủ công!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85910-exam-aws-certified-solutions-architect-associate-saa-c03/

## Câu 62

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon KMS, Amazon S3
- Takeaway nhanh: Giải pháp này đáp ứng toàn bộ yêu cầu một cách hoàn hảo và hiệu quả vận hành cao nhất (operationally efficient): Mã hóa at rest: SSE-KMS mã hóa dữ liệu server-side bằng khóa KMS. Log key usage: AWS KMS tự động ghi log mọi hoạt động sử dụng khóa (request, decrypt, etc.) qua AWS CloudTrail (bao gồm cả data events nếu enable), dễ dàng audit. Rotation hàng năm: KMS hỗ trợ xoay khóa tự động (automatic rotation) cho symmetric keys (CMK) mỗi năm, không cần can thiệp thủ công, tạo phiên bản khóa mới mà vẫn hỗ trợ dữ liệu cũ.
- Nguồn tham khảo trong block: https://aws.amazon.com/kms/faqs/#:~:text=You%20can%20choose%20to%20have%20AWS%20KMS%20automatically%20rotate%20KMS,KMS%20custom%20key%20store%20featureIn | https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingKMSEncryption.html | https://www.examtopics.com/discussions/amazon/view/85817-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A company is preparing to store confidential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year. Which solution meets these requirements and is the MOST operationally efficient?

### Các lựa chọn
1. Server-side encryption with customer-provided keys (SSE-C)
2. Server-side encryption with Amazon S3 managed keys (SSE-S3)
3. Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation
4. Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi tập trung vào việc lưu trữ dữ liệu bí mật (confidential data) trong Amazon S3 với các yêu cầu nghiêm ngặt về bảo mật và tuân thủ (compliance):

✅ Mã hóa dữ liệu tại chỗ (encrypted at rest): Dữ liệu phải được mã hóa khi lưu trữ trên S3.

✅ Ghi log sử dụng khóa mã hóa (encryption key usage logged): Mọi hoạt động sử dụng khóa phải được ghi nhật ký để kiểm toán (auditing).

✅ Xoay khóa hàng năm (keys rotated every year): Khóa phải được tự động hoặc thủ công xoay vòng định kỳ.

Yêu cầu chính là chọn giải pháp đáp ứng đầy đủ và hiệu quả vận hành nhất (MOST operationally efficient), nghĩa là giảm thiểu công sức quản lý thủ công, tự động hóa cao.

🛠️ Bối cảnh AWS cập nhật 2026: S3 hỗ trợ nhiều loại mã hóa server-side (SSE), tích hợp chặt chẽ với AWS KMS (Key Management Service) cho quản lý khóa chuyên nghiệp, log qua CloudTrail, và tính năng xoay khóa tự động (automatic rotation) cho symmetric keys từ năm 2018 và cải tiến liên tục.

✅ Đáp án đúng: Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

Lý do lựa chọn:

Giải pháp này đáp ứng toàn bộ yêu cầu một cách hoàn hảo và hiệu quả vận hành cao nhất (operationally efficient):

Mã hóa at rest: SSE-KMS mã hóa dữ liệu server-side bằng khóa KMS.

Log key usage: AWS KMS tự động ghi log mọi hoạt động sử dụng khóa (request, decrypt, etc.) qua AWS CloudTrail (bao gồm cả data events nếu enable), dễ dàng audit.

Rotation hàng năm: KMS hỗ trợ xoay khóa tự động (automatic rotation) cho symmetric keys (CMK) mỗi năm, không cần can thiệp thủ công, tạo phiên bản khóa mới mà vẫn hỗ trợ dữ liệu cũ.

🧩 Ưu điểm vượt trội: Tự động hóa rotation giúp giảm lỗi con người, tiết kiệm thời gian Ops so với manual, phù hợp DevOps best practices.

📋 Giải thích tất cả các phương án

❌ Server-side encryption with customer-provided keys (SSE-C)

Phương án này SAI vì: Khách hàng phải tự cung cấp và quản lý khóa (từ nguồn ngoài AWS), S3 chỉ mã hóa nhưng không log key usage tự động qua CloudTrail (chỉ log metadata cơ bản). Không hỗ trợ rotation tự động từ AWS, khách hàng phải tự xoay thủ công – kém hiệu quả vận hành, tăng rủi ro và phức tạp.

❌ Server-side encryption with Amazon S3 managed keys (SSE-S3)

Phương án này SAI vì: SSE-S3 mã hóa at rest và tự động rotate keys hàng năm, nhưng không log chi tiết key usage cho auditing (chỉ log qua CloudTrail management events, không có data events cụ thể cho key). Không đáp ứng yêu cầu audit đầy đủ.

❌ Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation

Phương án này SAI (mặc dù gần đúng) vì: SSE-KMS log key usage qua CloudTrail đầy đủ và mã hóa tốt, nhưng manual rotation yêu cầu can thiệp thủ công hàng năm (tạo lịch cron hoặc Lambda) – không phải MOST operationally efficient so với automatic rotation (chỉ cần enable một lần).

✅ Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

Phương án này ĐÚNG vì: Đáp ứng 100% yêu cầu với log audit qua CloudTrail, mã hóa server-side, và automatic rotation (enable khi tạo CMK symmetric), giảm thiểu vận hành thủ công tối đa.

📘 Tài liệu tham khảo (AWS cập nhật mới nhất 2026)

AWS S3 Encryption: Protecting data using server-side encryption with Amazon S3 managed keys (SSE-S3) and customer managed keys (SSE-KMS) – Chi tiết so sánh SSE types.

AWS KMS Rotation: Rotating AWS KMS keys – Automatic rotation cho symmetric CMKs hàng năm.

CloudTrail Logging cho KMS: Logging KMS key usage – Data và management events.

Exam Topic DOP-C02: AWS Certified DevOps Engineer - Professional (2024-2026 syllabus), Domain 4: Automation & Optimization.

🛠️ Lời khuyên DevOps: Sử dụng AWS KMS customer-managed keys (CMK) với automatic rotation trong production để tuân thủ PCI-DSS, HIPAA, etc. Enable CloudTrail data events cho S3/KMS để audit đầy đủ!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85817-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/kms/faqs/#:~:text=You%20can%20choose%20to%20have%20AWS%20KMS%20automatically%20rotate%20KMS,KMS%20custom%20key%20store%20featureIn

https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingKMSEncryption.html

## Câu 63

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SNS, Amazon SQS, Auto Scaling Group
- Đáp án tham khảo: **Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.**
- Takeaway nhanh: Thiết kế này best practice cho queue-based worker systems (decoupled, scalable, resilient).
- Nguồn tham khảo trong block: https://aws.amazon.com/sns/faqs/#:~:text=SNS%20provides%20durable%20storage%20of%20all%20messages%20that%20it%20receives | https://www.examtopics.com/discussions/amazon/view/86621-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored. Which design should the solutions architect use?

### Các lựa chọn
1. Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.
2. Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.
3. Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.
4. Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một Solutions Architect đang thiết kế kiến trúc đám mây cho ứng dụng mới trên AWS. Ứng dụng xử lý job (công việc) theo cách chạy song song (parallel), tự động thêm hoặc xóa các node ứng dụng dựa trên số lượng job cần xử lý. Ứng dụng là stateless (không trạng thái), nghĩa là các node có thể được thay thế mà không mất dữ liệu. Yêu cầu chính:

Loosely coupled (kết nối lỏng lẻo): Các thành phần không phụ thuộc chặt chẽ vào nhau.

Job items được lưu trữ bền vững (durably stored): Đảm bảo job không bị mất ngay cả khi node crash.

Mục tiêu thiết kế: Sử dụng dịch vụ AWS để lưu job an toàn, phân phối đến các processor (EC2 instances), và scale tự động dựa trên workload thực tế (số job), không phải metric gián tiếp như CPU hay network.

🛠️ Công nghệ liên quan (cập nhật đến 2026):

Amazon SQS (Standard hoặc FIFO Queue) để lưu job bền vững, hỗ trợ decoupling.

Auto Scaling Group (ASG) với Launch Template (khuyến nghị thay thế Launch Configuration từ năm 2021, deprecated dần).

Scaling policy dựa trên CloudWatch metrics của SQS như ApproximateNumberOfMessagesVisible.

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

Lý do chọn:

✅ SQS queue: Lưu job durable (bền vững, at-least-once delivery), hỗ trợ loosely coupled vì producer gửi job vào queue, consumer (EC2 processors) poll độc lập.

✅ AMI + Launch Template + ASG: Tạo instance stateless từ AMI, Launch Template là best practice mới (hỗ trợ version control, mixed instances policy tốt hơn Launch Config).

✅ Scaling policy dựa trên số items trong SQS: Sử dụng metric ApproximateNumberOfMessages (CloudWatch), scale chính xác theo workload job, phù hợp parallel processing.

Thiết kế này best practice cho queue-based worker systems (decoupled, scalable, resilient).

📋 Phân tích tất cả các phương án (đúng/sai)

❌ Phương án SAI 1: Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.

Giải thích sai: SNS là pub/sub (fire-and-forget), không durable (message mất nếu subscriber không ack kịp, max retention 23 ngày nhưng không retry tự động như SQS). Launch Configuration deprecated (AWS khuyến nghị Launch Template từ 2021). Scale theo CPU usage không phù hợp vì workload job-based, CPU có thể không phản ánh chính xác số job (ví dụ: job nhẹ nhưng nhiều).

❌ Phương án SAI 2: Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.

Giải thích sai: SQS đúng cho durable storage và decoupling. Nhưng Launch Configuration deprecated, và scale theo network usage không liên quan trực tiếp đến số job (network có thể biến động do yếu tố khác như traffic ngoài). Không scale chính xác theo workload job.

✅ Phương án ĐÚNG: Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

Giải thích đúng: Hoàn hảo như phần ✅ trên. Tích hợp SQS + ASG target tracking policy trên metric queue depth là pattern chuẩn cho fan-out workers (parallel processing).

❌ Phương án SAI 4: Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.

Giải thích sai: SNS không durable cho job storage (at-most-once, không queue retry). Launch Template đúng nhưng metric "number of messages published to SNS" không tồn tại chuẩn cho ASG scaling (SNS có NumberOfMessagesPublished nhưng không phù hợp scale consumer, vì published rate không phản ánh backlog). Không loosely coupled bền vững.

📘 Tài liệu tham khảo (AWS cập nhật 2026)

AWS Docs - Amazon SQS: Developer Guide > Monitoring > CloudWatch Metrics (ApproximateNumberOfMessagesVisible). Link

Auto Scaling: User Guide > Scaling by custom metric (SQS), Launch Templates vs Configurations. Link & Link

Best Practices: AWS Well-Architected Framework > Reliability Pillar > Decoupled Architectures (SQS + ASG). Link

Exam Reference: DOP-C02 (DevOps Pro) blueprint > Domain 2: High Availability & Disaster Recovery.

🛠️ Lời khuyên DevOps: Trong thực tế, kết hợp SQS Dead Letter Queue cho error handling và Lambda nếu job nhẹ để serverless hóa! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86621-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/sns/faqs/#:~:text=SNS%20provides%20durable%20storage%20of%20all%20messages%20that%20it%20receives.

## Câu 64

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SQS, Amazon Lambda, Amazon S3
- Đáp án tham khảo: **Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.**
- Takeaway nhanh: Đây là giải pháp chuẩn AWS và least overhead vì chỉ cần chỉnh visibility timeout trên SQS queue (qua console/CLI/API, không cần code change). Visibility timeout phải > (Lambda function timeout + batch window timeout) để đảm bảo Lambda hoàn tất xử lý batch trước khi message visible lại, tránh duplicate poll. Theo tài liệu AWS (2024-2026), với Lambda event source mapping từ SQS, AWS khuyến nghị set visibility timeout ít nhất 6x function timeout, nhưng cụ thể > tổng timeout để xử lý idempotent hoặc tránh re-processing.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html | https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html | https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html#invocation-retries-sqs | https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html#events-sqs-eventsource | https://www.examtopics.com/discussions/amazon/view/85185-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
An image-processing company has a web application that users use to upload images. The application uploads the images into an Amazon S3 bucket. The company has set up S3 event notifications to publish the object creation events to an Amazon Simple Queue Service (Amazon SQS) standard queue. The SQS queue serves as the event source for an AWS Lambda function that processes the images and sends the results to users through email. Users report that they are receiving multiple email messages for every uploaded image. A solutions architect determines that SQS messages are invoking the Lambda function more than once, resulting in multiple email messages. What should the solutions architect do to resolve this issue with the LEAST operational overhead?

### Các lựa chọn
1. Set up long polling in the SQS queue by increasing the ReceiveMessage wait time to 30 seconds.
2. Change the SQS standard queue to an SQS FIFO queue. Use the message deduplication ID to discard duplicate messages.
3. Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.
4. Modify the Lambda function to delete each message from the SQS queue immediately after the message is read before processing.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một ứng dụng web xử lý hình ảnh của công ty, nơi người dùng upload ảnh lên Amazon S3 bucket. S3 được cấu hình event notifications để gửi sự kiện tạo object (object creation events) đến một Amazon SQS standard queue. Queue SQS này làm event source cho một AWS Lambda function, Lambda sẽ xử lý ảnh và gửi kết quả qua email cho người dùng.

Vấn đề chính (user reports): Người dùng nhận nhiều email cho mỗi ảnh upload, do SQS messages invoke Lambda nhiều lần (multiple invocations), dẫn đến xử lý lặp lại.

Nguyên nhân gốc rễ: SQS standard queue có tính chất at-least-once delivery (giao ít nhất một lần, có thể duplicate). Khi Lambda function (hoặc consumer) poll message từ SQS, message được "ẩn" tạm thời trong visibility timeout. Nếu thời gian xử lý Lambda vượt quá visibility timeout, message sẽ visible lại và bị poll bởi Lambda instance khác, gây duplicate processing và nhiều email.

Yêu cầu giải quyết: Solutions architect cần giải pháp với LEAST operational overhead (ít overhead vận hành nhất), tức ưu tiên thay đổi cấu hình đơn giản, không refactor code hay thay đổi architecture lớn.

Kiến thức AWS cập nhật đến 2026: SQS standard queue hỗ trợ batch processing cho Lambda (batch window), và visibility timeout cần lớn hơn tổng function timeout + batch window timeout để tránh duplicate invokes (theo AWS best practices cho event source mapping).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.

Lý do 🛠️:

Đây là giải pháp chuẩn AWS và least overhead vì chỉ cần chỉnh visibility timeout trên SQS queue (qua console/CLI/API, không cần code change).

Visibility timeout phải > (Lambda function timeout + batch window timeout) để đảm bảo Lambda hoàn tất xử lý batch trước khi message visible lại, tránh duplicate poll.

Theo tài liệu AWS (2024-2026), với Lambda event source mapping từ SQS, AWS khuyến nghị set visibility timeout ít nhất 6x function timeout, nhưng cụ thể > tổng timeout để xử lý idempotent hoặc tránh re-processing.

Giải quyết tận gốc duplicate do race condition giữa poll và processing.

📋 Phân tích tất cả các phương án (đúng/sai)

❌ [SAI] Set up long polling in the SQS queue by increasing the ReceiveMessage wait time to 30 seconds.

Giải thích sai: Long polling (tăng ReceiveMessage WaitTimeSeconds lên 20-30s) chỉ giúp giảm số lần empty receives (poll không message), tối ưu chi phí và throughput. Nó không giải quyết duplicate invokes do visibility timeout quá ngắn. Overhead thấp nhưng không fix vấn đề gốc.

❌ [SAI] Change the SQS standard queue to an SQS FIFO queue. Use the message deduplication ID to discard duplicate messages.

Giải thích sai: SQS FIFO hỗ trợ exactly-once delivery với message deduplication ID và content-based dedup, nhưng overhead cao hơn: Phải refactor S3 event notification để set message group ID/dedup ID, queue FIFO có throughput giới hạn (300 msg/s/shard), và không tương thích trực tiếp nếu app không thiết kế cho FIFO. Không phải "least overhead" so với chỉnh visibility timeout.

✅ [ĐÚNG] Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.

Giải thích đúng (như phần trên): Fix trực tiếp race condition với thay đổi cấu hình đơn giản nhất, không code change, hỗ trợ batch processing Lambda-SQS.

❌ [SAI] Modify the Lambda function to delete each message from the SQS queue immediately after the message is read before processing.

Giải thích sai: Với Lambda event source mapping, AWS tự động delete message sau successful processing (không cần code delete). Delete ngay sau "read" (trước process) sẽ mất message nếu Lambda fail/crash giữa chừng, dẫn đến data loss. Phải refactor code (thêm SQS delete API), tăng overhead và rủi ro (không idempotent).

📘 Tài liệu tham khảo (AWS cập nhật 2024-2026)

AWS Documentation - SQS Visibility Timeout: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html (Khuyến nghị set > processing time).

Lambda with SQS Event Source: https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html#events-sqs-eventsource (Best practices: Visibility timeout > function timeout + batch window).

Troubleshoot Duplicate Lambda Invokes: https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html#invocation-retries-sqs (Duplicate do visibility timeout).

Exam Topic DOP-C02: AWS Certified DevOps Engineer Professional - Serverless & Event-driven architectures.

Giải pháp này đảm bảo high availability và fault-tolerant mà không phức tạp hóa hệ thống! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/85185-exam-aws-certified-solutions-architect-associate-saa-c03/

https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html

https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html

## Câu 65

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Direct Connect, Amazon S3, Amazon EC2, Amazon Virtual Private Cloud
- Đáp án tham khảo: **Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.**
- Takeaway nhanh: 🛡️ Lợi ích: Bảo mật cao (không public), chi phí thấp (Gateway Endpoint S3 miễn phí), dễ triển khai, scale tốt. Phù hợp best practice AWS Well-Architected Framework (Reliability & Security pillars).
- Nguồn tham khảo trong block: https://aws.amazon.com/premiumsupport/knowledge-center/move-ec2-instance/#:~:text=It%27s%20not%20possible%20to%20move,%2C%20Availability%20Zone%2C%20or%20VPC | https://www.examtopics.com/discussions/amazon/view/86031-exam-aws-certified-solutions-architect-associate-saa-c03/

### Đề bài
A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data files that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access. A new requirement mandates that the network traffic for file transfers take a private route and not be sent over the internet. Which change to the network architecture should a solutions architect recommend to meet this requirement?

### Các lựa chọn
1. Create a NAT gateway. Configure the route table for the public subnets to send traffic to Amazon S3 through the NAT gateway.
2. Configure the security group for the EC2 instances to restrict outbound traffic so that only traffic to the S3 prefix list is permitted.
3. Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.
4. Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route traffic to Amazon S3 over the Direct Connect connection.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích chi tiết nội dung câu hỏi

Câu hỏi mô tả một công ty lưu trữ hồ sơ y tế đang chạy ứng dụng trên các Amazon EC2 instances nằm trong public subnets của VPC. Ứng dụng này xử lý các file dữ liệu khách hàng lưu trữ trên Amazon S3, và EC2 truy cập S3 qua internet (sử dụng Internet Gateway - IGW). Các EC2 không cần bất kỳ kết nối mạng nào khác.

Yêu cầu mới: Traffic truyền file (từ EC2 đến S3) phải đi qua đường private route, không qua internet nữa.

📌 Mục tiêu chính: Đảm bảo kết nối private, an toàn, tránh public internet để tuân thủ bảo mật (đặc biệt với dữ liệu y tế nhạy cảm).

🛠️ Bối cảnh AWS hiện tại: EC2 ở public subnet có public IP hoặc Elastic IP, route table public trỏ traffic đến IGW cho 0.0.0.0/0. S3 được truy cập qua public endpoint (s3.amazonaws.com) → traffic đi qua internet.

🎯 Giải pháp lý tưởng: Sử dụng VPC Endpoint (Gateway Endpoint cho S3) để route traffic nội bộ VPC trực tiếp đến S3 mà không rời VPC hoặc qua internet. Đây là cách tiết kiệm chi phí nhất (miễn phí cho Gateway Endpoint S3), nhanh chóng và phù hợp với kiến trúc AWS hiện đại (cập nhật đến 2026, hỗ trợ S3 endpoint với prefix lists và policy).

✅ Đáp án đúng và lý do lựa chọn

Đáp án đúng: Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.

Lý do:

✅ Di chuyển EC2 sang private subnets đảm bảo instances không expose trực tiếp ra internet (không cần public IP).

✅ Tạo VPC Gateway Endpoint cho S3 (loại com.amazonaws.region.s3) → thêm route vào route table của private subnet: pl-xxxxx (S3 prefix list) → vpce-xxxxx (endpoint).

✅ Traffic đến S3 sẽ đi private route nội bộ VPC (qua AWS backbone), không qua internet, đạt yêu cầu. Không ảnh hưởng traffic khác vì chỉ route S3 prefix list.

🛡️ Lợi ích: Bảo mật cao (không public), chi phí thấp (Gateway Endpoint S3 miễn phí), dễ triển khai, scale tốt. Phù hợp best practice AWS Well-Architected Framework (Reliability & Security pillars).

❌ Phân tích tất cả các phương án (đúng/sai)

Dưới đây là giải thích chi tiết từng lựa chọn. Tôi giữ nguyên văn bản gốc tiếng Anh của phương án, chỉ phân tích bằng tiếng Việt với lý do đúng/sai:

[SAI] Create a NAT gateway. Configure the route table for the public subnets to send traffic to Amazon S3 through the NAT gateway. ❌ Sai vì: NAT Gateway dùng để private instances outbound qua internet ( masquerade IP). Ở đây EC2 vẫn ở public subnet, traffic S3 vẫn đi qua IGW/internet → không private route. NAT chỉ mask source IP, không thay đổi đường đi S3 (S3 public endpoint). Thêm NAT tốn chi phí (~0.045$/giờ + data), không cần thiết.

[SAI] Configure the security group for the EC2 instances to restrict outbound traffic so that only traffic to the S3 prefix list is permitted. ❌ Sai vì: Security Group chỉ kiểm soát traffic layer 4 (port/protocol), không thay đổi route path. Traffic S3 vẫn qua internet (public endpoint). Prefix list hữu ích cho route table/NGW, nhưng SG không route → không đáp ứng private route. Chỉ restrict, không giải quyết root cause.

[ĐÚNG] Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets. ✅ Đúng như đã giải thích ở trên: Kết hợp private subnet + Gateway Endpoint S3 → traffic private 100%, hiệu quả nhất. Cập nhật 2026: Hỗ trợ Interface Endpoint nếu cần IAM auth nâng cao, nhưng Gateway đủ cho S3.

[SAI] Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route traffic to Amazon S3 over the Direct Connect connection. ❌ Sai vì: Remove IGW làm VPC mất outbound internet hoàn toàn → EC2 không connect được gì ngoài Direct Connect. Direct Connect (dedicated fiber, ~$0.02-$0.3/GB) quá đắt, phức tạp cho chỉ S3 traffic (cần public VIF + BGP). Không scalable cho EC2 multi-AZ, overkill so với VPC Endpoint (miễn phí/simple).

📘 Tài liệu tham khảo (AWS chính thức, cập nhật 2026)

VPC Endpoints for S3: AWS VPC Endpoints Documentation – Chi tiết Gateway vs Interface Endpoint.

S3 Prefix Lists & Routing: Amazon VPC Routing.

Best Practices: AWS Well-Architected: Networking & S3 Access Patterns.

🛠️ Thiết kế thực tế: Sử dụng AWS Console/CLI: aws ec2 create-vpc-endpoint --vpc-id vpc-xxx --service-name com.amazonaws.us-east-1.s3 --vpc-endpoint-type Gateway --route-table-ids rtb-xxx.

Giải pháp này đảm bảo zero trust networking cho dữ liệu y tế! 🚀 Nếu cần demo CDK/Terraform, hỏi thêm nhé!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/86031-exam-aws-certified-solutions-architect-associate-saa-c03/

https://aws.amazon.com/premiumsupport/knowledge-center/move-ec2-instance/#:~:text=It%27s%20not%20possible%20to%20move,%2C%20Availability%20Zone%2C%20or%20VPC.

AWS Certified Solutions Architect Associate - SAA-C03 - Internet - 3 - Kết quả

Trước

1

2

3

...

13
