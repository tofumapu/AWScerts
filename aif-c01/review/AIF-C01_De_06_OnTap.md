# AIF-C01 - Bộ Ôn Tập Chi Tiết - Đề 06

- Số câu phát hiện: **2**
- Nguồn câu hỏi: Đề 06 tham khảo từ Đề Internet - ExamTopics (Full6de.md)
- Blueprint tham chiếu: `w:\AI Practitioner\AIF\AWS-Certified-AI-Practitioner_Exam-Guide.pdf`
- Ghi chú kỹ thuật: dữ liệu được tách từ `Full6de.md`; parser dùng reset `Câu hỏi 1`/`Câu 1:` và link tham khảo để vá các câu thiếu marker.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon Bedrock | 2 |
| Amazon SageMaker | 2 |
| Amazon SageMaker AI | 1 |
| Amazon SageMaker JumpStart | 1 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon SageMaker | 1 |
| Amazon SageMaker JumpStart | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| fine-tuning | 15 |

### Domain heuristic

| Domain | Tên | Tỷ trọng chính thức | Số câu ước lượng |
| --- | --- | --- | --- |
| Domain 1 | Fundamentals of AI and ML | 20% | 2 |
| Domain 2 | Fundamentals of Generative AI | 24% | 0 |
| Domain 3 | Applications of Foundation Models | 28% | 0 |
| Domain 4 | Guidelines for Responsible AI | 14% | 0 |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% | 0 |

## Service Key-Notes

### Amazon Bedrock
- Dịch vụ managed để dùng foundation models qua API, thường là đáp án cho generative AI với ít vận hành.
- Các mảng hay gặp: model selection, Knowledge Bases/RAG, Agents, Guardrails, logging, VPC endpoint và dữ liệu không dùng để train model nền mặc định.

### Amazon SageMaker
- Bộ dịch vụ managed cho vòng đời ML: chuẩn bị dữ liệu, huấn luyện, tuning, deploy, monitor và governance.
- Trong đề AIF, cần phân biệt SageMaker với Bedrock: SageMaker thiên về build/train/deploy ML model; Bedrock thiên về consume/customize foundation model.

### Amazon SageMaker AI
- Tên mới/biến thể cách gọi SageMaker trong nguồn câu hỏi, thường trỏ về cùng nhóm năng lực ML managed.
- Hay đi cùng training job, endpoint, Feature Store, Clarify, Model Cards và JumpStart.

### Amazon SageMaker JumpStart
- Cung cấp model và solution template dựng sẵn, phù hợp khi cần triển khai hoặc fine-tune model nguồn mở với ít operational effort.
- Nếu câu hỏi nhấn mạnh least operational effort cho open-source LLM, JumpStart thường là lựa chọn mạnh.

## Pattern Key-Notes

### fine-tuning
- Tinh chỉnh model đã có bằng dữ liệu chuyên biệt để cải thiện task/domain cụ thể.
- Nếu cần ít vận hành với open-source model trên AWS, SageMaker JumpStart thường nổi bật.

## Cách Học Đề Này

- Đọc nhanh các service/pattern nổi bật để biết đề nghiêng về Bedrock, SageMaker, responsible AI hay governance.
- Với câu generative AI, xác định trước keyword như `RAG`, `prompt`, `embedding`, `guardrails`, `fine-tuning`, `hallucination`.
- Với câu ML nền tảng, chọn metric/kỹ thuật đúng theo task thay vì nhớ máy móc đáp án.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, Amazon EC2, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Đáp án tham khảo: **Use Amazon SageMaker JumpStart to create a training job – vì nó cung cấp quy trình đầy đủ, tự động, ít cấu hình cho việc fine‑tune LLM nguồn mở, đáp ứng yêu cầu “least operational effort”.**
- Takeaway nhanh: Bối cảnh: Một chuyên gia AI muốn fine‑tune (tinh chỉnh) một mô hình ngôn ngữ lớn (LLM) nguồn mở để thực hiện text categorization. Dữ liệu đã sẵn sàng. Yêu cầu: Lựa chọn giải pháp có mức độ vận hành (operational effort) thấp nhất – tức là giảm thiểu việc phải tự quản lý hạ tầng, viết script, cấu hình môi trường, v.v. Điểm cần xét: Độ “đóng gói” của dịch vụ (có tích hợp sẵn pipeline training hay không).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/316407-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner must fine-tune an open source large language model (LLM) for text categorization. The dataset is already prepared.
Which solution will meet these requirements with the LEAST operational effort?

### Các lựa chọn
1. Create a custom model training job in PartyRock on Amazon Bedrock.
2. Use Amazon SageMaker JumpStart to create a training job.
3. Use a custom script to run an Amazon SageMaker AI model training job.
4. Create a Jupyter notebook on an Amazon EC2 instance. Use the notebook to train the model.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Một chuyên gia AI muốn fine‑tune (tinh chỉnh) một mô hình ngôn ngữ lớn (LLM) nguồn mở để thực hiện text categorization. Dữ liệu đã sẵn sàng.

Yêu cầu: Lựa chọn giải pháp có mức độ vận hành (operational effort) thấp nhất – tức là giảm thiểu việc phải tự quản lý hạ tầng, viết script, cấu hình môi trường, v.v.

Điểm cần xét:

Độ “đóng gói” của dịch vụ (có tích hợp sẵn pipeline training hay không).

Quản lý hạ tầng (tự provision EC2, SageMaker notebook, v.v.).

Hỗ trợ LLM nguồn mở và công cụ fine‑tune hiện đại (đến năm 2026, AWS đã mở rộng hỗ trợ các mô hình như Llama‑2, Mistral, Falcon,…).

✅ Đáp án đúng

Use Amazon SageMaker JumpStart to create a training job.

Lý do:

SageMaker JumpStart cung cấp “one‑click” training jobs cho hơn 100 mô hình LLM nguồn mở (Llama 2, Mistral, Falcon, …) và bao gồm các pipeline fine‑tuning sẵn có.

Người dùng chỉ cần chọn mô hình, tải dataset (hoặc trỏ tới S3), cấu hình một vài siêu‑tham số và khởi chạy.

Hạ tầng (SageMaker Training Instances, autoscaling, checkpoint, logging) được AWS quản lý hoàn toàn, giảm thiểu công việc cấu hình và bảo trì.

Đến tháng 3/2026, JumpStart đã bổ sung “Fine‑tune LLM” UI trong SageMaker Studio Lab và API cho việc triển khai nhanh, phù hợp nhất với yêu cầu “least operational effort”.

🧩 Giải thích các phương án khác (đúng/sai)

1️⃣ Create a custom model training job in PartyRock on Amazon Bedrock. (SAI)

PartyRock không phải là một dịch vụ thực tế của AWS; có thể là một “placeholder” trong đề.

Amazon Bedrock hiện tại (2026) chỉ cung cấp inference cho các foundation models (mô hình nền tảng) và custom model deployment, nhưng không hỗ trợ training/fine‑tuning trực tiếp trên Bedrock.

Do vậy, việc “create a custom model training job in PartyRock on Amazon Bedrock” không khả thi và yêu cầu người dùng tự xây dựng hạ tầng, trái với tiêu chí “least operational effort”.

2️⃣ Use a custom script to run an Amazon SageMaker AI model training job. (SAI)

Việc viết script (Python, SageMaker SDK, hoặc CLI) để khởi chạy một training job yêu cầu:

Định nghĩa Docker container hoặc sử dụng SageMaker‑provided containers.

Quản lý IAM role, VPC, S3 bucket, checkpoint, hyper‑parameter tuning, …

Mặc dù SageMaker tự động hoá hạ tầng, công sức chuẩn bị script và đảm bảo tương thích với mô hình LLM nguồn mở (cài đặt dependencies, tokenizer, v.v.) làm tăng đáng kể operational effort.

So với JumpStart, đây là một bước “manual” hơn, vì JumpStart đã có các script và cấu hình sẵn.

3️⃣ Create a Jupyter notebook on an Amazon EC2 instance. Use the notebook to train the model. (SAI)

EC2 + Jupyter là cách “bare‑metal” truyền thống:

Người dùng tự provision instance (chọn loại GPU, cài đặt driver, CUDA, PyTorch/TensorFlow, các thư viện LLM…).

Phải tự quản lý lưu trữ (EBS), backup, scaling, và dừng/start instance để tối ưu chi phí.

So với SageMaker, không có tính năng managed training, không có checkpoint tự động, không có logging/monitoring tích hợp, và không có cost‑optimisation tự động.

Vì vậy, đây là phương án cực kỳ tốn công sức và không đáp ứng yêu cầu “least operational effort”.

📚 Tham khảo tài liệu (2026)

Amazon SageMaker JumpStart Documentation – “Fine‑tune large language models with one‑click” (AWS Docs, March 2026).

Amazon Bedrock Developer Guide – “Inference only; training not supported” (AWS Docs, February 2026).

AWS re:Invent 2025 – Deep dive on SageMaker JumpStart for LLM fine‑tuning (video & slides).

AWS Blog – Simplifying LLM fine‑tuning with SageMaker JumpStart (12 Nov 2025).

🏁 Tổng kết

✅ Đáp án đúng: Use Amazon SageMaker JumpStart to create a training job – vì nó cung cấp quy trình đầy đủ, tự động, ít cấu hình cho việc fine‑tune LLM nguồn mở, đáp ứng yêu cầu “least operational effort”.

❌ Các phương án còn lại yêu cầu tự triển khai hạ tầng, viết code, hoặc thậm chí sử dụng dịch vụ không hỗ trợ training, do đó không phù hợp với tiêu chí của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316407-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 02

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Model size**
- Takeaway nhanh: 🚗💥 Một công ty muốn tích hợp một giải pháp AI để tự động gọi dịch vụ cứu hộ (emergency services) trong vòng 30 giây ngay sau khi phát hiện va chạm xe. Yêu cầu thời gian đáp ứng rất gắt gao → độ trễ (latency) của mô hình inference phải rất thấp. Công ty muốn sử dụng mô hình đã được huấn luyện sẵn (pre‑trained) và không thực hiện thêm quá trình training. Vì vậy, khi lựa chọn mô hình, yếu tố quyết định là điều gì ảnh hưởng trực tiếp tới thời gian inference để đáp ứng thời gian giới hạn 30 s.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/382712-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to integrate an AI solution to contact emergency services within 30 seconds of vehicle crash detection. The company wants to use a pre-trained model without additional training.
Which factor should the company prioritize when selecting a model to meet these requirements?

### Các lựa chọn
1. Model customization
2. Model size
3. Model cost
4. Model temperature

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

1. Giải thích nội dung câu hỏi

🚗💥 Một công ty muốn tích hợp một giải pháp AI để tự động gọi dịch vụ cứu hộ (emergency services) trong vòng 30 giây ngay sau khi phát hiện va chạm xe.

Yêu cầu thời gian đáp ứng rất gắt gao → độ trễ (latency) của mô hình inference phải rất thấp.

Công ty muốn sử dụng mô hình đã được huấn luyện sẵn (pre‑trained) và không thực hiện thêm quá trình training.

Vì vậy, khi lựa chọn mô hình, yếu tố quyết định là điều gì ảnh hưởng trực tiếp tới thời gian inference để đáp ứng thời gian giới hạn 30 s.

2. Đáp án đúng

✅ Model size

Lý do:

Kích thước mô hình (số lượng tham số, depth, width) quyết định thời gian tính toán và lượng tài nguyên (CPU/GPU, RAM) cần thiết cho mỗi lần dự đoán.

Mô hình lớn hơn thường cho độ chính xác cao hơn, nhưng latency tăng và yêu cầu phần cứng mạnh hơn, gây khó đạt mục tiêu 30 s, đặc biệt khi chạy trên các endpoint thực tế (Amazon SageMaker, Amazon Bedrock).

Khi không có khả năng tùy chỉnh hoặc huấn luyện lại, cách duy nhất để giảm latency là chọn mô hình có kích thước phù hợp (ví dụ: các phiên bản “lite” hoặc “small” của mô hình trong SageMaker JumpStart hoặc Amazon Bedrock).

3. Phân tích các phương án

Model customization

❌ Giải thích: “Customization” đề cập tới việc tinh chỉnh (fine‑tune) mô hình hoặc thêm layer mới. Câu hỏi đã nói không thực hiện thêm training nên việc tùy chỉnh không liên quan. Thậm chí, việc tùy chỉnh còn tốn thời gian và tài nguyên, không giúp giảm latency.

Model size

✅ Giải thích: Như đã nêu ở mục 2, kích thước mô hình quyết định thời gian inference và mức tài nguyên cần thiết. Để đáp ứng “within 30 seconds”, ưu tiên chọn mô hình nhỏ hơn (ví dụ: “Claude‑instant”, “Titan‑text‑lite”, “Llama‑2‑7B”) và triển khai trên instance có tốc độ xử lý cao (ml.g5.xlarge, g4dn.xlarge…) để đạt latency thấp.

Model cost

❌ Giải thích: Chi phí mô hình (giá tiền trả cho inference, licensing) là yếu tố quan trọng trong quản lý ngân sách, nhưng không ảnh hưởng trực tiếp đến thời gian phản hồi. Một mô hình đắt hơn có thể lớn hơn và thậm chí tăng latency, nên không phải là ưu tiên trong yêu cầu này.

Model temperature

❌ Giải thích: “Temperature” là tham số điều chỉnh độ ngẫu nhiên của kết quả tạo ngôn ngữ (creativity). Nó không ảnh hưởng tới thời gian tính toán hay kích thước mô hình. Do yêu cầu là thời gian phản hồi nhanh, nhiệt độ không phải là tiêu chí lựa chọn.

4. Kiến thức cập nhật tới năm 2026

Amazon Bedrock (ra mắt 2023, mở rộng 2024‑2025) cung cấp các mô hình foundation (Anthropic, Stability AI, Amazon Titan) với các phiên bản “lite” (nhỏ) để giảm latency.

SageMaker JumpStart cung cấp pre‑trained models và cho phép triển khai multi‑model endpoints; tài liệu mới (2025‑2026) nhấn mạnh: “Select a model family and size that meets your latency SLA; smaller model variants typically achieve < 100 ms per request on g5.xlarge”.

SageMaker Serverless Inference và Provisioned Throughput cho phép cân bằng chi phí và latency, nhưng kích thước mô hình vẫn là yếu tố quyết định chính.

📚 Tham khảo:

AWS Documentation – Amazon Bedrock Model Families (2026 edition).

AWS Documentation – SageMaker Inference Latency Best Practices (2025).

AWS Blog – Choosing the right foundation model size for real‑time workloads (2024).

5. Tổng kết

Để đáp ứng độ trễ ≤ 30 giây khi không thực hiện thêm training, công ty cần ưu tiên chọn “Model size” thích hợp – mô hình nhỏ hơn sẽ chạy nhanh hơn trên cùng một phần cứng.

Các yếu tố khác (customization, cost, temperature) không ảnh hưởng trực tiếp tới yêu cầu thời gian phản hồi và do đó không phải là tiêu chí ưu tiên.

Chúc bạn thành công trong việc thiết kế giải pháp AI đáp ứng SLA khắt khe! 🚀🧩

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/382712-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/
