# AIF-C01 - Bộ Ôn Tập Chi Tiết - Đề 01

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 01 tham khảo từ Đề Internet - ExamTopics (Full6de.md)
- Blueprint tham chiếu: `w:\AI Practitioner\AIF\AWS-Certified-AI-Practitioner_Exam-Guide.pdf`
- Ghi chú kỹ thuật: dữ liệu được tách từ `Full6de.md`; parser dùng reset `Câu hỏi 1`/`Câu 1:` và link tham khảo để vá các câu thiếu marker.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon SageMaker | 38 |
| Amazon Bedrock | 34 |
| Amazon SageMaker AI | 13 |
| Amazon S3 | 13 |
| Amazon SageMaker JumpStart | 8 |
| Amazon Rekognition | 7 |
| Amazon Comprehend | 6 |
| Amazon Q | 4 |
| Amazon Lex | 4 |
| Amazon Kendra | 2 |
| Amazon OpenSearch Service | 1 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon SageMaker | 3 |
| Amazon Bedrock | 2 |
| Amazon Q | 1 |
| Amazon SageMaker JumpStart | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| prompt engineering | 202 |
| responsible AI | 134 |
| model evaluation | 107 |
| embeddings | 100 |
| RAG | 66 |
| guardrails | 48 |
| fine-tuning | 39 |
| hallucination | 5 |

### Domain heuristic

| Domain | Tên | Tỷ trọng chính thức | Số câu ước lượng |
| --- | --- | --- | --- |
| Domain 1 | Fundamentals of AI and ML | 20% | 23 |
| Domain 2 | Fundamentals of Generative AI | 24% | 19 |
| Domain 3 | Applications of Foundation Models | 28% | 11 |
| Domain 4 | Guidelines for Responsible AI | 14% | 3 |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% | 9 |

## Service Key-Notes

### Amazon SageMaker
- Bộ dịch vụ managed cho vòng đời ML: chuẩn bị dữ liệu, huấn luyện, tuning, deploy, monitor và governance.
- Trong đề AIF, cần phân biệt SageMaker với Bedrock: SageMaker thiên về build/train/deploy ML model; Bedrock thiên về consume/customize foundation model.

### Amazon Bedrock
- Dịch vụ managed để dùng foundation models qua API, thường là đáp án cho generative AI với ít vận hành.
- Các mảng hay gặp: model selection, Knowledge Bases/RAG, Agents, Guardrails, logging, VPC endpoint và dữ liệu không dùng để train model nền mặc định.

### Amazon SageMaker AI
- Tên mới/biến thể cách gọi SageMaker trong nguồn câu hỏi, thường trỏ về cùng nhóm năng lực ML managed.
- Hay đi cùng training job, endpoint, Feature Store, Clarify, Model Cards và JumpStart.

### Amazon S3
- Object storage nền tảng cho dataset, artifact, log, nguồn dữ liệu RAG và output pipeline ML.
- Hay đi cùng security/governance như encryption, lifecycle, access control và data residency.

### Amazon SageMaker JumpStart
- Cung cấp model và solution template dựng sẵn, phù hợp khi cần triển khai hoặc fine-tune model nguồn mở với ít operational effort.
- Nếu câu hỏi nhấn mạnh least operational effort cho open-source LLM, JumpStart thường là lựa chọn mạnh.

### Amazon Rekognition
- Dịch vụ computer vision managed cho ảnh/video: object, label, moderation, face và text detection.
- Nếu câu hỏi cần nhận dạng hình ảnh không phải tự train model, Rekognition thường là đáp án.

### Amazon Comprehend
- Dịch vụ NLP managed cho entity, key phrases, sentiment, topic và phân tích văn bản.
- Không phải công cụ tạo nội dung generative AI hay vector database.

### Amazon Q
- Trợ lý generative AI của AWS cho công việc doanh nghiệp, code và tri thức nội bộ.
- Amazon Q Developer thường gắn với hỗ trợ lập trình, giải thích code, tạo code và tăng năng suất developer.

## Pattern Key-Notes

### prompt engineering
- Kỹ thuật thiết kế chỉ dẫn cho foundation model để tăng độ chính xác, định dạng và tính nhất quán của output.
- Không thay thế guardrails, validation hoặc kiểm soát bảo mật trước prompt injection.

### responsible AI
- Nhóm nguyên tắc về fairness, transparency, explainability, privacy, safety và accountability.
- Trong AIF-C01, cần nhận diện rủi ro như bias, toxicity, plagiarism, hallucination và misuse.

### model evaluation
- Chọn metric theo task: ROUGE cho summarization, accuracy/precision/recall/F1 cho classification, MSE cho regression.
- Không dùng metric không liên quan chỉ vì quen thuộc trong ML truyền thống.

### embeddings
- Vector số biểu diễn ý nghĩa của văn bản/hình ảnh/đối tượng để tìm kiếm tương đồng và clustering.
- Embedding thường đi cùng vector database, semantic search và RAG.

### RAG
- Retrieval-Augmented Generation đưa tri thức ngoài vào context để giảm hallucination và tăng tính cập nhật.
- Trên AWS thường ghép Bedrock với Knowledge Bases, Kendra, OpenSearch hoặc S3.

### guardrails
- Cơ chế kiểm soát input/output nhằm giảm nội dung độc hại, prompt injection và vi phạm policy.
- Trên Bedrock, Guardrails là keyword quan trọng cho yêu cầu responsible/safe generative AI.

## Cách Học Đề Này

- Đọc nhanh các service/pattern nổi bật để biết đề nghiêng về Bedrock, SageMaker, responsible AI hay governance.
- Với câu generative AI, xác định trước keyword như `RAG`, `prompt`, `embedding`, `guardrails`, `fine-tuning`, `hallucination`.
- Với câu ML nền tảng, chọn metric/kỹ thuật đúng theo task thay vì nhớ máy móc đáp án.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Feature Store**
- Takeaway nhanh: Một công ty muốn xây dựng mô hình Machine Learning (ML) bằng Amazon SageMaker. Trong quá trình phát triển, các đội ngũ khác nhau cần chia sẻ và quản lý các biến (features) chung – ví dụ: các đặc trưng đã tiền xử lý, các biến thống kê, hay các biến mô tả dữ liệu đầu vào. Yêu cầu này đòi hỏi một kho lưu trữ trung tâm, có khả năng: Lưu trữ, phiên bản hoá và phục vụ các feature cho các môi trường training, inference và cho nhiều nhóm đồng thời.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-feature-store-updates-2024/ | https://aws.amazon.com/blogs/machine-learning/collaborative-feature-store/ | https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html | https://www.examtopics.com/discussions/amazon/view/150628-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build an ML model by using Amazon SageMaker. The company needs to share and manage variables for model development across multiple teams. Which SageMaker feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Feature Store
2. Amazon SageMaker Data Wrangler
3. Amazon SageMaker Clarify
4. Amazon SageMaker Model Cards

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty muốn xây dựng mô hình Machine Learning (ML) bằng Amazon SageMaker. Trong quá trình phát triển, các đội ngũ khác nhau cần chia sẻ và quản lý các biến (features) chung – ví dụ: các đặc trưng đã tiền xử lý, các biến thống kê, hay các biến mô tả dữ liệu đầu vào. Yêu cầu này đòi hỏi một kho lưu trữ trung tâm, có khả năng:

Lưu trữ, phiên bản hoá và phục vụ các feature cho các môi trường training, inference và cho nhiều nhóm đồng thời.

Quản lý quyền truy cập (IAM, VPC, encryption) để các team chỉ có thể đọc/ghi theo quy định.

Cung cấp API (SDK, REST) để các notebook, pipelines, hoặc ứng dụng khác có thể truy xuất feature một cách nhất quán.

Trong SageMaker, tính năng đáp ứng đúng nhu cầu này là Amazon SageMaker Feature Store.

✅ Đáp án đúng: Amazon SageMaker Feature Store

Tại sao đúng?

Feature Store là một kho dữ liệu quản lý feature (Feature Repository) được thiết kế riêng cho ML. Nó cung cấp:

Feature Group: lưu trữ các feature ở dạng thời gian (time‑series) hoặc không thời gian, có versioning và metadata.

Online Store & Offline Store: cho phép truy xuất nhanh (real‑time inference) và truy vấn batch (training).

Quản lý quyền qua IAM, VPC, KMS để các team có thể chia sẻ mà vẫn kiểm soát được quyền.

SDK & API (SageMaker SDK, Boto3) giúp các pipeline, notebook, và ứng dụng Lambda/Gateway truy cập đồng nhất.

Từ phiên bản 2024‑2025, Feature Store còn hỗ trợ feature lineage, data quality checks, và integration với SageMaker Pipelines – rất phù hợp với môi trường đa team.

🧩 Giải thích các phương án còn lại (sai)

Amazon SageMaker Data Wrangler

Data Wrangler là công cụ trong SageMaker Studio giúp thu thập, làm sạch, biến đổi và chuẩn bị dữ liệu bằng giao diện kéo‑thả hoặc script. Nó không cung cấp kho lưu trữ trung tâm để chia sẻ feature giữa các team; các transform được lưu dưới dạng notebook hoặc pipeline, nhưng không có khả năng quản lý version và phục vụ feature như một kho dữ liệu độc lập. Vì vậy, không đáp ứng yêu cầu “share and manage variables across multiple teams”.

Amazon SageMaker Clarify

Clarify là tính năng đánh giá công bằng (fairness), bias và explainability cho mô hình ML. Nó cung cấp các metric, visualizations và công cụ để kiểm tra bias trong dữ liệu và dự đoán, nhưng không phải là nơi lưu trữ hoặc quản lý feature. Do vậy, không phù hợp với nhu cầu chia sẻ biến.

Amazon SageMaker Model Cards

Model Cards là tài liệu mô tả mô hình (metadata, intended use, performance, limitations) giúp truyền đạt thông tin mô hình tới các bên liên quan. Chúng không lưu trữ hay quản lý các feature; chỉ là tài liệu mô tả mô hình. Vì thế cũng không đáp ứng yêu cầu.

📚 Tham khảo (tính đến năm 2026)

Amazon SageMaker Feature Store – Documentation

https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html (phiên bản cập nhật 2026)

SageMaker Feature Store – What’s new 2024‑2025

https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-feature-store-updates-2024/

AWS Well‑Architected Framework – Machine Learning Lens – phần “Feature Management”.

AWS Blog – Using Feature Store to enable cross‑team collaboration

https://aws.amazon.com/blogs/machine-learning/collaborative-feature-store/

🛠️ Kết luận: Để chia sẻ và quản lý các biến (features) trong môi trường phát triển ML đa team, Amazon SageMaker Feature Store là giải pháp thích hợp nhất. Các tùy chọn khác (Data Wrangler, Clarify, Model Cards) phục vụ các mục đích riêng biệt như chuẩn bị dữ liệu, đánh giá công bằng, và tài liệu mô hình, nên không đáp ứng yêu cầu của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150628-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 02

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: hallucination
- Đáp án tham khảo: **Plagiarism**
- Takeaway nhanh: Câu hỏi đặt ra một tình huống đạo đức trong việc sử dụng công nghệ sinh ra nội dung (generative AI). Một sinh viên sao chép nguyên văn nội dung do AI tạo ra để viết bài luận. Yêu cầu là xác định thách thức nào của “responsible generative AI” (AI sinh ra có trách nhiệm) mà kịch bản này mô tả. Việc sao chép nội dung do AI tạo ra và đưa vào bài viết mà không ghi nguồn hay tuyên bố rõ ràng là đạo văn (plagiarism). Đây là một trong những rủi ro đạo đức quan trọng khi dùng AI: người dùng có thể lợi dụng khả năng tạo nội dung nhanh chóng để trộm cắp trí tuệ, gây ra vi phạm bản quyền và làm suy giảm giá trị học thuật.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/151742-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A student at a university is copying content from generative AI to write essays. Which challenge of responsible generative AI does this scenario represent?

### Các lựa chọn
1. Toxicity
2. Hallucinations
3. Plagiarism
4. Privacy

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi đặt ra một tình huống đạo đức trong việc sử dụng công nghệ sinh ra nội dung (generative AI). Một sinh viên sao chép nguyên văn nội dung do AI tạo ra để viết bài luận. Yêu cầu là xác định thách thức nào của “responsible generative AI” (AI sinh ra có trách nhiệm) mà kịch bản này mô tả.

✅ Đáp án đúng: Plagiarism

Việc sao chép nội dung do AI tạo ra và đưa vào bài viết mà không ghi nguồn hay tuyên bố rõ ràng là đạo văn (plagiarism). Đây là một trong những rủi ro đạo đức quan trọng khi dùng AI: người dùng có thể lợi dụng khả năng tạo nội dung nhanh chóng để trộm cắp trí tuệ, gây ra vi phạm bản quyền và làm suy giảm giá trị học thuật.

🧩 Phân tích các phương án

❌ Toxicity

Toxicity đề cập đến việc mô hình AI sinh ra nội dung có tính xúc phạm, thù địch, bạo lực, hay ngôn từ thô tục. Trong ví dụ sinh viên sao chép nội dung, vấn đề không phải là nội dung có tính gây hại xã hội mà là việc đánh cắp ý tưởng. Do đó, đây không phải là thách thức được mô tả.

❌ Hallucinations

Hallucinations là hiện tượng AI tạo ra thông tin sai lệch, không có thực hoặc không dựa trên dữ liệu thực tế (ví dụ: đưa ra “sự kiện lịch sử không tồn tại”). Trường hợp này không liên quan đến tính chính xác hay độ tin cậy của nội dung, mà chỉ liên quan đến việc sử dụng nội dung đã được tạo ra mà không công nhận.

✅ Plagiarism

Plagiarism là hành vi sử dụng tác phẩm của người khác (ở đây là nội dung do AI tạo) mà không ghi nguồn, trình bày như là của mình. Đây chính là thách thức đạo đức trong AI sinh ra: người dùng có thể lạm dụng khả năng tạo nội dung để vi phạm bản quyền và đạo đức học thuật. Các khung hướng dẫn trách nhiệm AI (ví dụ: AWS AI Ethics Framework 2025, NIST AI Risk Management Framework 2024) đều nhấn mạnh việc thiết lập cơ chế phát hiện và ngăn chặn đạo văn trong các sản phẩm AI.

❌ Privacy

Privacy liên quan đến việc AI thu thập, lưu trữ hoặc tiết lộ thông tin cá nhân không được phép. Trong kịch bản này không có yếu tố dữ liệu cá nhân hay vi phạm quyền riêng tư, nên không phải là thách thức được đề cập.

📚 Tham khảo nguồn tài liệu

AWS AI Ethics Framework (2025) – Hướng dẫn về trách nhiệm, bao gồm phòng ngừa đạo văn và bảo vệ bản quyền khi sử dụng dịch vụ AI của AWS.

NIST AI Risk Management Framework (Version 1.1, 2024) – Phân loại rủi ro AI, trong đó “Plagiarism & Intellectual Property Misuse” là một trong các rủi ro quan trọng.

European Union AI Act (2024 Update) – Định nghĩa “misuse of AI‑generated content” và yêu cầu các nhà cung cấp triển khai công cụ kiểm tra đạo văn.

IEEE 7010‑2023 – Standard for Ethical Concerns in AI – Đề cập đến “Plagiarism” như một vấn đề đạo đức cần được quản trị.

🔚 Tổng kết:

Kịch bản sinh viên sao chép nội dung AI là ví dụ điển hình của Plagiarism, một thách thức quan trọng trong việc triển khai và quản lý AI sinh ra có trách nhiệm. Các vấn đề khác như Toxicity, Hallucinations và Privacy không phù hợp với mô tả của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151742-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 03

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon S3
- Takeaway nhanh: Bối cảnh: Công ty đã xây dựng một mô hình dự đoán giá cho các mặt hàng. Khi chạy trên tập dữ liệu training mô hình cho kết quả tốt, nhưng khi đưa vào production (đối với dữ liệu thực tế) hiệu suất giảm mạnh. Vấn đề thường gặp: Đây là dấu hiệu của over‑fitting (mô hình học quá mức các mẫu trong dữ liệu huấn luyện và không tổng quát được trên dữ liệu mới) hoặc data drift (phân phối dữ liệu trong production khác so với dữ liệu huấn luyện).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/using-more-data-improve-ml-model-performance/ | https://d1.awsstatic.com/whitepapers/machine-learning/best-practices-ml-on-aws.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://docs.aws.amazon.com/sagemaker/latest/dg/train-model.html | https://www.examtopics.com/discussions/amazon/view/151044-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing a new model to predict the prices of specific items. The model performed well on the training dataset. When the company deployed the model to production, the model's performance decreased significantly. What should the company do to mitigate this problem?

### Các lựa chọn
1. Reduce the volume of data that is used in training.
2. Add hyperparameters to the model.
3. Increase the volume of data that is used in training.
4. Increase the model training time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Công ty đã xây dựng một mô hình dự đoán giá cho các mặt hàng. Khi chạy trên tập dữ liệu training mô hình cho kết quả tốt, nhưng khi đưa vào production (đối với dữ liệu thực tế) hiệu suất giảm mạnh.

Vấn đề thường gặp: Đây là dấu hiệu của over‑fitting (mô hình học quá mức các mẫu trong dữ liệu huấn luyện và không tổng quát được trên dữ liệu mới) hoặc data drift (phân phối dữ liệu trong production khác so với dữ liệu huấn luyện).

Mục tiêu câu hỏi: Xác định hành động nào giúp giảm thiểu hiện tượng này, tức là làm cho mô hình “biết” được nhiều mẫu đa dạng hơn và tránh over‑fitting.

✅ Đáp án đúng

🟢 “Increase the volume of data that is used in training.”

Khi tăng khối lượng và đa dạng của dữ liệu huấn luyện, mô hình sẽ học được nhiều mẫu hơn, giảm khả năng ghi nhớ chi tiết quá mức (over‑fit) và cải thiện khả năng tổng quát hoá khi gặp dữ liệu thực tế.

Trong môi trường AWS, chúng ta có thể thực hiện việc này bằng cách:

Sử dụng Amazon SageMaker Ground Truth để thu thập và gán nhãn thêm dữ liệu.

Áp dụng data augmentation (ví dụ: biến đổi giá trị, thêm nhiễu) trong pipeline SageMaker Processing.

Tận dụng Amazon S3 để lưu trữ lượng dữ liệu lớn và AWS Glue/Lake Formation để chuẩn bị dữ liệu.

Thiết lập SageMaker Pipelines để tự động hoá việc thu thập dữ liệu mới, huấn luyện lại và triển khai liên tục.

❌ Giải thích các phương án sai

“Reduce the volume of data that is used in training.”

📉 Giảm kích thước dữ liệu sẽ làm giảm độ đa dạng, làm tăng nguy cơ over‑fitting hơn chứ không giải quyết được vấn đề.

Khi dữ liệu huấn luyện ít hơn, mô hình sẽ “kỳ vọng” nhiều hơn vào các mẫu đã thấy, dẫn tới hiệu suất tồi hơn trong môi trường production.

“Add hyperparameters to the model.”

🛠️ Hyperparameters (như learning rate, batch size, số lớp) là cấu hình cho quá trình huấn luyện, không phải “thêm” vào mô hình.

Việc thay đổi hyperparameters có thể cải thiện một số khía cạnh, nhưng không giải quyết nguyên nhân gốc rễ là thiếu dữ liệu đa dạng.

Thêm hyperparameters không thay thế việc cung cấp thêm dữ liệu thực tế cho mô hình.

“Increase the model training time.”

⏱️ Đào tạo lâu hơn chỉ giúp mô hình “học” sâu hơn trên cùng một tập dữ liệu; nếu dữ liệu hiện tại đã dẫn tới over‑fitting, việc tăng thời gian huấn luyện sẽ tăng mức độ over‑fit chứ không khắc phục.

Thay vì kéo dài thời gian, chúng ta cần cải thiện chất lượng và khối lượng dữ liệu hoặc áp dụng kỹ thuật regularization (ví dụ: dropout, L2) – nhưng những kỹ thuật này không nằm trong lựa chọn đưa ra.

📚 Tham khảo nguồn tài liệu (đến năm 2026)

Amazon SageMaker Documentation – Training and Hyperparameter Tuning

https://docs.aws.amazon.com/sagemaker/latest/dg/train-model.html

AWS Whitepaper – Best Practices for Machine Learning on AWS (2024‑2026 cập nhật)

https://d1.awsstatic.com/whitepapers/machine-learning/best-practices-ml-on-aws.pdf

Amazon SageMaker Model Monitor – phát hiện data drift & model quality degradation

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

AWS Blog – Using more data to improve model performance (2025)

https://aws.amazon.com/blogs/machine-learning/using-more-data-improve-ml-model-performance/

Tóm tắt: Khi mô hình hoạt động tốt trên dữ liệu huấn luyện nhưng kém trên production, nguyên nhân phổ biến là over‑fitting hoặc data drift. Giải pháp hiệu quả nhất là tăng khối lượng và độ đa dạng của dữ liệu huấn luyện (đáp án đúng). Các phương án còn lại either làm giảm dữ liệu, thay đổi cấu hình không giải quyết gốc rễ, hoặc kéo dài thời gian huấn luyện mà không cải thiện dữ liệu – vì vậy đều sai. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151044-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 04

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon CloudFront, Amazon Macie, Amazon PrivateLink, Amazon Virtual Private Cloud
- Đáp án tham khảo: **AWS PrivateLink**
- Takeaway nhanh: Câu hỏi mô tả một tổ chức tài chính đang phát triển một ứng dụng AI bằng Amazon Bedrock. Ứng dụng này được triển khai trong một VPC và không được phép có bất kỳ lưu lượng internet nào (để đáp ứng yêu cầu tuân thủ quy định). Yêu cầu: chọn dịch vụ hoặc tính năng AWS cho phép VPC “giao tiếp” với Amazon Bedrock mà không cần đi qua internet công cộng. 2️⃣ Đáp án đúng
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150689-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial institution is using Amazon Bedrock to develop an AI application. The application is hosted in a VPC. To meet regulatory compliance standards, the VPC is not allowed access to any internet traffic. Which AWS service or feature will meet these requirements?

### Các lựa chọn
1. AWS PrivateLink
2. Amazon Macie
3. Amazon CloudFront
4. Internet gateway

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

1️⃣ Giải thích nội dung câu hỏi

Câu hỏi mô tả một tổ chức tài chính đang phát triển một ứng dụng AI bằng Amazon Bedrock. Ứng dụng này được triển khai trong một VPC và không được phép có bất kỳ lưu lượng internet nào (để đáp ứng yêu cầu tuân thủ quy định).

Yêu cầu: chọn dịch vụ hoặc tính năng AWS cho phép VPC “giao tiếp” với Amazon Bedrock mà không cần đi qua internet công cộng.

2️⃣ Đáp án đúng

✅ AWS PrivateLink

Lý do:

PrivateLink cung cấp VPC Interface Endpoints cho phép kết nối tới các dịch vụ AWS (như Amazon Bedrock) trong mạng nội bộ của AWS, không cần Internet Gateway, NAT, hay proxy công cộng.

Khi tạo một Interface VPC Endpoint cho Bedrock, lưu lượng đi qua đường truyền riêng tư của AWS backbone, đáp ứng yêu cầu “không có internet”.

PrivateLink còn hỗ trợ định danh VPC‑to‑VPC và đối tác SaaS mà vẫn giữ dữ liệu trong môi trường riêng, rất phù hợp với quy định tài chính.

3️⃣ Giải thích tất cả các phương án

AWS PrivateLink

✅ Đúng

Cung cấp kết nối riêng tư tới dịch vụ AWS (Bedrock) thông qua Interface VPC Endpoint. Không cần Internet Gateway hay NAT, vì vậy không có bất kỳ lưu lượng internet công cộng nào. Đây là cách chuẩn để “đưa” các dịch vụ fully‑managed vào VPC một cách an toàn.

Amazon Macie

❌ Sai

Amazon Macie là dịch vụ phát hiện dữ liệu nhạy cảm và bảo mật dữ liệu trong Amazon S3. Nó không cung cấp khả năng truy cập mạng tới các dịch vụ AWS khác và không giải quyết yêu cầu “không có internet”. Nhiệm vụ của Macie là quét, phân loại và cảnh báo, không phải là tạo kênh truyền dữ liệu nội bộ.

Amazon CloudFront

❌ Sai

CloudFront là Content Delivery Network (CDN), luôn hoạt động qua Internet để phân phối nội dung tới các edge location. Để sử dụng CloudFront, VPC vẫn phải có đầu ra internet (thông qua IGW/NAT). Vì vậy nó vi phạm yêu cầu “không được phép truy cập internet”.

Internet gateway

❌ Sai

Internet Gateway (IGW) là cổng ra internet cho VPC, cho phép các subnet công cộng hoặc NAT truyền lưu lượng tới/đến internet công cộng. Sử dụng IGW sẽ tạo ra lưu lượng internet, trái hoàn toàn với điều kiện “không cho phép truy cập internet”.

4️⃣ Kiến thức cập nhật đến năm 2026

Từ 2024, Amazon Bedrock đã được hỗ trợ Interface VPC Endpoints (PrivateLink) để khách hàng có thể truy cập mô hình AI mà không rời khỏi AWS network.

2025: AWS mở rộng danh sách dịch vụ có PrivateLink, bao gồm cả Bedrock, SageMaker, và các dịch vụ AI mới.

2026: AWS khuyến cáo trong AWS Well‑Architected Framework – Security Pillar rằng các workloads yêu cầu “no‑internet” nên dùng PrivateLink hoặc AWS Transit Gateway để giữ lưu lượng trong mạng nội bộ.

5️⃣ Tham khảo tài liệu

📘 Amazon Bedrock – Using VPC Interface Endpoints (PrivateLink) – AWS Documentation (phiên bản 2026)

📘 AWS PrivateLink – Overview – AWS Documentation (phiên bản 2026)

📘 AWS Well‑Architected Framework – Security Pillar (cập nhật 2025)

Tóm tắt: Để cho phép VPC truy cập Amazon Bedrock mà không cần internet, chỉ có AWS PrivateLink (qua Interface VPC Endpoint) đáp ứng yêu cầu. Các lựa chọn còn lại đều không cung cấp kết nối nội bộ hoặc thậm chí tạo ra lưu lượng internet, do đó là sai. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150689-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 05

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Đáp án tham khảo: **Reinforcement learning with rewards for positive customer feedback**
- Takeaway nhanh: Công ty muốn xây dựng một chatbot hỗ trợ khách hàng, tự cải thiện câu trả lời dựa trên hai nguồn dữ liệu: Các tương tác đã diễn ra (ví dụ: phản hồi tích cực/tiêu cực của khách hàng). Các tài nguyên trực tuyến (có thể là kiến thức mới, tài liệu, trang web …). Yêu cầu “self‑improvement” (tự học, tự tối ưu) gợi ý rằng mô hình cần tự quyết định hành động (tạo câu trả lời) và được thưởng (reward) khi hành động đó mang lại kết quả tốt (ví dụ: khách hàng hài lòng). Đây chính là đặc điểm của Reinforcement Learning (RL) – một chiến lược học máy trong đó tác nhân (agent) học cách hành động tối ưu thông qua phản hồi dạng phần thưởng/phạt.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ml/ | https://aws.amazon.com/bedrock/ | https://docs.aws.amazon.com/sagemaker/latest/dg/reinforcement-learning.html | https://www.examtopics.com/discussions/amazon/view/152501-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a customer service chatbot. The company wants the chatbot to improve its responses by learning from past interactions and online resources. Which AI learning strategy provides this self-improvement capability?

### Các lựa chọn
1. Supervised learning with a manually curated dataset of good responses and bad responses
2. Reinforcement learning with rewards for positive customer feedback
3. Unsupervised learning to find clusters of similar customer inquiries
4. Supervised learning with a continuously updated FAQ database

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn xây dựng một chatbot hỗ trợ khách hàng, tự cải thiện câu trả lời dựa trên hai nguồn dữ liệu:

Các tương tác đã diễn ra (ví dụ: phản hồi tích cực/tiêu cực của khách hàng).

Các tài nguyên trực tuyến (có thể là kiến thức mới, tài liệu, trang web …).

Yêu cầu “self‑improvement” (tự học, tự tối ưu) gợi ý rằng mô hình cần tự quyết định hành động (tạo câu trả lời) và được thưởng (reward) khi hành động đó mang lại kết quả tốt (ví dụ: khách hàng hài lòng). Đây chính là đặc điểm của Reinforcement Learning (RL) – một chiến lược học máy trong đó tác nhân (agent) học cách hành động tối ưu thông qua phản hồi dạng phần thưởng/phạt.

✅ Đáp án đúng

✅ Reinforcement learning with rewards for positive customer feedback

Trong RL, chatbot (agent) tạo ra câu trả lời (action), môi trường (khách hàng, hệ thống) trả về một tín hiệu phần thưởng (positive feedback) hoặc phạt (negative feedback).

Khi thu thập đủ dữ liệu phản hồi, thuật toán RL sẽ cập nhật chính sách để tối đa hoá phần thưởng dài hạn → tự cải thiện qua thời gian.

AWS cung cấp các dịch vụ hỗ trợ RL hiện đại (SageMaker RL, Amazon Bedrock với mô hình “reinforcement‑tuned”), cho phép triển khai nhanh và mở rộng.

❌ Giải thích các phương án sai

❌ Supervised learning with a manually curated dataset of good responses and bad responses

Supervised learning yêu cầu một bộ dữ liệu tĩnh, được gán nhãn trước. Khi có “manually curated dataset”, quá trình học không tự động lấy phản hồi mới từ khách hàng; việc cập nhật cần can thiệp người dùng. Do đó không đáp ứng được yêu cầu “self‑improvement” liên tục.

AWS: SageMaker Training Jobs cho supervised learning, nhưng vẫn phải chuẩn bị dataset mới mỗi khi muốn cải thiện.

❌ Unsupervised learning to find clusters of similar customer inquiries

Unsupervised learning chỉ khám phá cấu trúc ẩn (ví dụ: clustering) mà không có nhãn “đúng/sai”. Nó có thể giúp nhóm câu hỏi, nhưng không tạo ra cơ chế học từ phản hồi khách hàng để cải thiện câu trả lời.

AWS: SageMaker Clustering, nhưng không phù hợp cho việc tối ưu hoá phản hồi.

❌ Supervised learning with a continuously updated FAQ database

Mặc dù FAQ được continuously updated, mô hình vẫn hoạt động dưới dạng supervised learning: nó học cách khớp câu hỏi với câu trả lời trong FAQ. Việc cập nhật FAQ là công việc thủ công, không phải là “tự học” dựa trên phản hồi thực tế của khách hàng.

Đối với yêu cầu “learn from past interactions”, RL vẫn là lựa chọn mạnh hơn vì nó tận dụng phản hồi thực tế (đánh giá hài lòng) thay chỉ dựa vào tài liệu tĩnh.

📚 Tham khảo tài liệu (cập nhật đến 2026)

AWS SageMaker Reinforcement Learning – Hướng dẫn triển khai RL với các thuật toán như PPO, DQN, và tích hợp với Amazon CloudWatch để thu thập reward.

https://docs.aws.amazon.com/sagemaker/latest/dg/reinforcement-learning.html

Amazon Bedrock – Reinforcement‑tuned foundation models – Cung cấp API cho việc fine‑tune mô hình ngôn ngữ lớn bằng cách sử dụng phản hồi người dùng (human feedback).

https://aws.amazon.com/bedrock/

AWS Well‑Architected Framework – Machine Learning Lens (2025 Update) – Phần “Self‑Improving Models” nêu rõ việc ưu tiên RL cho các ứng dụng chatbot cần cải tiến tự động.

https://aws.amazon.com/architecture/well-architected/ml/

🛠️ Kết luận

Chiến lược học máy đáp ứng yêu cầu “self‑improvement” của chatbot là Reinforcement Learning với phần thưởng dựa trên phản hồi tích cực của khách hàng. Các phương án supervised hay unsupervised đều thiếu cơ chế tự động cập nhật dựa trên hành vi thực tế và do đó không phù hợp. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/152501-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 06

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Provide examples of text passages with corresponding positive or negative labels in the prompt followed by the new text passage to be classified.**
- Takeaway nhanh: Mục tiêu: Công ty muốn sử dụng một large language model (LLM) trên Amazon Bedrock để thực hiện phân tích cảm xúc (sentiment analysis), cụ thể là phân loại đoạn văn bản thành “positive” hoặc “negative”. Yêu cầu: Chọn chiến lược prompt engineering (cách thiết kế lời nhắc) phù hợp nhất để LLM có thể đưa ra nhãn cảm xúc chính xác cho một đoạn văn mới. Bối cảnh AWS 2026: Amazon Bedrock cung cấp các mô hình như Claude 3, Titan, Llama 3, … và hỗ trợ “few‑shot prompting” (cung cấp một vài ví dụ trong prompt) để cải thiện độ chính xác mà không cần fine‑tuning. Đây là cách khuyến nghị của AWS để thực hiện các tác vụ phân loại đơn giản như sentiment analysis.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150805-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use a large language model (LLM) on Amazon Bedrock for sentiment analysis. The company wants to classify the sentiment of text passages as positive or negative.
Which prompt engineering strategy meets these requirements?

### Các lựa chọn
1. Provide examples of text passages with corresponding positive or negative labels in the prompt followed by the new text passage to be classified.
2. Provide a detailed explanation of sentiment analysis and how LLMs work in the prompt.
3. Provide the new text passage to be classified without any additional context or examples.
4. Provide the new text passage with a few examples of unrelated tasks, such as text summarization or question answering.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Mục tiêu: Công ty muốn sử dụng một large language model (LLM) trên Amazon Bedrock để thực hiện phân tích cảm xúc (sentiment analysis), cụ thể là phân loại đoạn văn bản thành “positive” hoặc “negative”.

Yêu cầu: Chọn chiến lược prompt engineering (cách thiết kế lời nhắc) phù hợp nhất để LLM có thể đưa ra nhãn cảm xúc chính xác cho một đoạn văn mới.

Bối cảnh AWS 2026: Amazon Bedrock cung cấp các mô hình như Claude 3, Titan, Llama 3, … và hỗ trợ “few‑shot prompting” (cung cấp một vài ví dụ trong prompt) để cải thiện độ chính xác mà không cần fine‑tuning. Đây là cách khuyến nghị của AWS để thực hiện các tác vụ phân loại đơn giản như sentiment analysis.

✅ Đáp án đúng

✅ Provide examples of text passages with corresponding positive or negative labels in the prompt followed by the new text passage to be classified.

Tại sao đáp án này đúng?

Đây là kỹ thuật “few‑shot prompting”: đưa vào prompt một vài cặp (đoạn văn → nhãn) (ví dụ: “I love this product → Positive”, “The service was terrible → Negative”).

Khi LLM nhận được các ví dụ, nó học được định dạng đầu ra và cách suy luận để gán nhãn cho đoạn văn mới.

AWS Bedrock tài liệu (2026) khuyến nghị sử dụng few‑shot prompts cho các bài toán phân loại, vì chúng giúp mô hình hiểu ngữ cảnh và tiêu chí quyết định mà không cần fine‑tune.

Prompt này còn giảm thiểu sai sót so với việc chỉ đưa ra câu hỏi trống rỗng hoặc đưa các tác vụ không liên quan.

❌ Các đáp án sai và phân tích

❌ Provide a detailed explanation of sentiment analysis and how LLMs work in the prompt.

Lý do sai: Việc đưa vào giải thích chi tiết về sentiment analysis hoặc cách hoạt động của LLM không cung cấp dữ liệu mẫu cho mô hình để học cách gán nhãn.

LLM không cần “giải thích” khái niệm để thực hiện phân loại; thay vào đó, chúng cần ví dụ cụ thể để nhận dạng mẫu.

Prompt quá dài và không tập trung vào nhiệm vụ sẽ giảm hiệu suất và tăng chi phí token (được ghi nhận trong tài liệu Bedrock “Prompt Design Best Practices”, 2025).

❌ Provide the new text passage to be classified without any additional context or examples.

Lý do sai: Đây là zero‑shot prompting. Mặc dù một số mô hình mạnh (Claude 3, Gemini) có thể thực hiện zero‑shot, độ chính xác cho nhiệm vụ nhị phân như sentiment analysis thường thấp so với few‑shot.

Không có định dạng đầu ra hoặc tiêu chí đánh giá trong prompt, nên LLM có thể trả lời bằng định dạng không chuẩn (ví dụ: “It seems neutral” hoặc mô tả cảm xúc thay vì trả về “Positive/Negative”).

AWS khuyến cáo cung cấp ít nhất 2‑3 ví dụ để đạt được kết quả ổn định.

❌ Provide the new text passage with a few examples of unrelated tasks, such as text summarization or question answering.

Lý do sai: Các ví dụ không liên quan (tóm tắt, trả lời câu hỏi) không giúp LLM hiểu cách gán nhãn cảm xúc.

Prompt sẽ gây nhầm lẫn vì mô hình sẽ cố gắng tìm mối liên hệ giữa các ví dụ không liên quan và nhiệm vụ thực tế, dẫn tới kết quả sai lệch.

Đối với Bedrock, tài liệu “Prompt Design for Multi‑Task Scenarios” (2024) nhấn mạnh phải đồng nhất loại nhiệm vụ trong cùng một prompt; nếu không, mô hình sẽ “mix contexts” và giảm độ chính xác.

📚 Tham khảo tài liệu (AWS tới năm 2026)

Amazon Bedrock Developer Guide – Prompt Engineering (phiên bản 2026.02).

AWS Well‑Architected Framework – Machine Learning Lens, mục “Model Inference & Prompt Design”.

Claude 3 and Titan Model Documentation, phần “Few‑Shot Prompting Best Practices”.

AWS Blog – “Effective Prompting with Amazon Bedrock”, 2025/11.

Re:Invent 2025 – Session “Optimizing LLM Inference on Bedrock”, video và slide.

🧩 Tóm tắt nhanh

Câu hỏi: Cách thiết kế prompt để LLM trên Bedrock phân loại cảm xúc “positive” / “negative”.

Đáp án đúng: Cung cấp ví dụ (few‑shot) của đoạn văn và nhãn, sau đó đưa đoạn cần phân loại.

Các đáp án sai:

Giải thích khái niệm → không cung cấp mẫu, gây lãng phí token.

Chỉ đưa đoạn mới → zero‑shot, độ chính xác thấp.

Kết hợp ví dụ không liên quan → gây nhầm lẫn, giảm hiệu suất.

Hy vọng phân tích trên giúp bạn nắm rõ cách prompt engineering hiệu quả trên Amazon Bedrock cho bài toán sentiment analysis! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150805-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 07

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, prompt engineering, hallucination, fine-tuning
- Đáp án tham khảo: **Use domain adaptation fine‑tuning to adapt the FM to complex scientific terms.**
- Takeaway nhanh: Công ty nghiên cứu đã xây dựng một chatbot dựa trên foundation model (FM) của Amazon Bedrock. Chatbot cần truy vấn một cơ sở dữ liệu khổng lồ gồm các bài báo khoa học và trả lời các câu hỏi của người dùng. Sau khi thử nghiệm nhiều prompt engineering nhưng mô hình vẫn “đánh rơi” (poor performance) do các thuật ngữ khoa học phức tạp trong tài liệu nguồn. Vấn đề cốt lõi: FM chưa được “hiểu” đủ ngôn ngữ chuyên ngành → cần một phương pháp giúp mô hình nắm bắt ngữ cảnh và thuật ngữ chuyên môn hơn.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ml-pillar/ | https://aws.amazon.com/blogs/ai/fine-tuning-foundation-models-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html | https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html | https://www.examtopics.com/discussions/amazon/view/151048-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A research company implemented a chatbot by using a foundation model (FM) from Amazon Bedrock. The chatbot searches for answers to questions from a large database of research papers. After multiple prompt engineering attempts, the company notices that the FM is performing poorly because of the complex scientific terms in the research papers. How can the company improve the performance of the chatbot?

### Các lựa chọn
1. Use few-shot prompting to define how the FM can answer the questions.
2. Use domain adaptation fine-tuning to adapt the FM to complex scientific terms.
3. Change the FM inference parameters.
4. Clean the research paper data to remove complex scientific terms.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty nghiên cứu đã xây dựng một chatbot dựa trên foundation model (FM) của Amazon Bedrock.

Chatbot cần truy vấn một cơ sở dữ liệu khổng lồ gồm các bài báo khoa học và trả lời các câu hỏi của người dùng.

Sau khi thử nghiệm nhiều prompt engineering nhưng mô hình vẫn “đánh rơi” (poor performance) do các thuật ngữ khoa học phức tạp trong tài liệu nguồn.

Vấn đề cốt lõi: FM chưa được “hiểu” đủ ngôn ngữ chuyên ngành → cần một phương pháp giúp mô hình nắm bắt ngữ cảnh và thuật ngữ chuyên môn hơn.

✅ Đáp án đúng

👉 Use domain adaptation fine‑tuning to adapt the FM to complex scientific terms.

Giải thích:

Domain adaptation fine‑tuning (còn gọi là continuous fine‑tuning hoặc custom model trong Bedrock) cho phép bạn đào tạo lại mô hình gốc bằng cách đưa vào một tập dữ liệu chuyên ngành (ở đây là các bài báo khoa học).

Quá trình này giúp mô hình học các token, biểu thức, và mối quan hệ đặc thù của lĩnh vực, giảm thiểu hiện tượng “hallucination” và cải thiện độ chính xác khi trả lời các câu hỏi phức tạp.

Từ 2024‑2026, Amazon Bedrock đã cung cấp custom fine‑tuning cho các mô hình như Titan, Claude, Llama‑2,... và hỗ trợ định dạng dữ liệu S3, CSV/JSONL, và Amazon SageMaker Data Wrangler để thực hiện domain‑specific fine‑tuning.

Khi sử dụng Fine‑tuning on a domain‑specific corpus, chatbot sẽ có embedding và knowledge representation tốt hơn, vì nó đã “đọc” và “hiểu” ngôn ngữ khoa học trước khi trả lời.

🧩 Phân tích các phương án khác (đúng / sai)

1. Use few-shot prompting to define how the FM can answer the questions. (đánh dấu SAI)

Few‑shot prompting chỉ cung cấp một vài ví dụ trong prompt để hướng mô hình cách trả lời.

Khi vấn đề là thiếu kiến thức chuyên ngành, việc chỉ đưa vài ví dụ không đủ để bổ sung toàn bộ từ vựng và ngữ nghĩa của các thuật ngữ khoa học.

Với Bedrock, few‑shot có thể cải thiện nhẹ nhưng không thay thế được việc fine‑tune trên toàn bộ corpus.

Do đó, đây không phải giải pháp tối ưu cho “complex scientific terms”.

2. Change the FM inference parameters. (đánh dấu SAI)

Các inference parameters (temperature, top‑p, max‑tokens, etc.) ảnh hưởng tới độ ngẫu nhiên, độ dài, và tính đa dạng của đầu ra, không thay đổi hiểu biết ngôn ngữ của mô hình.

Khi mô hình không “biết” các thuật ngữ, việc điều chỉnh temperature hay top‑p không thể tạo ra kiến thức mới.

Vì câu hỏi yêu cầu cải thiện kiến thức chuyên ngành, thay đổi tham số inference không giải quyết gốc rễ vấn đề.

3. Clean the research paper data to remove complex scientific terms. (đánh dấu SAI)

Việc loại bỏ các thuật ngữ phức tạp sẽ giảm độ phong phú và gián đoạn nội dung của tài liệu gốc.

Chatbot sẽ mất đi khả năng trả lời các câu hỏi chuyên sâu, vì các khái niệm quan trọng đã bị xóa bỏ.

Thay vì xóa thông tin, chúng ta nên giữ nguyên và giúp mô hình học chúng thông qua fine‑tuning.

📚 Tham khảo tài liệu (đến 2026)

Amazon Bedrock Developer Guide – Custom Model Fine‑Tuning

https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html

AWS Blog – “Fine‑tuning foundation models on Bedrock for domain‑specific use cases” (2024‑2025 updates)

https://aws.amazon.com/blogs/ai/fine-tuning-foundation-models-bedrock/

Amazon SageMaker Documentation – Data Wrangler & Training Jobs for Large Text Corpora

https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025 edition)

https://aws.amazon.com/architecture/well-architected/ml-pillar/

🛠️ Kết luận nhanh

✅ Đáp án đúng: Use domain adaptation fine‑tuning to adapt the FM to complex scientific terms.

❌ Các phương án còn lại (few‑shot prompting, thay đổi inference parameters, hoặc làm sạch dữ liệu) không giải quyết vấn đề thiếu kiến thức chuyên ngành và do đó không phù hợp.

Bằng cách fine‑tune mô hình trên một bộ dữ liệu chứa đầy đủ các thuật ngữ khoa học, công ty sẽ nâng cao đáng kể độ chính xác và độ tin cậy của chatbot khi xử lý các truy vấn phức tạp. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151048-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 08

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Đáp án tham khảo: **Các đáp án đúng**
- Takeaway nhanh: Một công ty muốn triển khai một chatbot dựa trên mô hình Amazon SageMaker JumpStart đã được fine‑tune để trả lời câu hỏi của khách hàng. Ứng dụng này phải tuân thủ nhiều khung pháp lý (regulatory frameworks) – ví dụ: GDPR, HIPAA, PCI‑DSS, ISO 27001, v.v. Câu hỏi yêu cầu bạn chọn hai khả năng (capabilities) mà công ty có thể dùng để chứng minh (show) việc tuân thủ các yêu cầu pháp lý này.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150821-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to deploy a conversational chatbot to answer customer questions. The chatbot is based on a fine-tuned Amazon SageMaker JumpStart model. The application must comply with multiple regulatory frameworks. Which capabilities can the company show compliance for? (Choose two.)

### Các lựa chọn
1. Auto scaling inference endpoints
2. Threat detection
3. Data protection
4. Cost optimization
5. Loosely coupled microservices

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Một công ty muốn triển khai một chatbot dựa trên mô hình Amazon SageMaker JumpStart đã được fine‑tune để trả lời câu hỏi của khách hàng. Ứng dụng này phải tuân thủ nhiều khung pháp lý (regulatory frameworks) – ví dụ: GDPR, HIPAA, PCI‑DSS, ISO 27001, v.v.

Câu hỏi yêu cầu bạn chọn hai khả năng (capabilities) mà công ty có thể dùng để chứng minh (show) việc tuân thủ các yêu cầu pháp lý này.

✅ Các đáp án đúng

1️⃣ Threat detection

Tại sao đúng?

AWS cung cấp các dịch vụ Amazon GuardDuty, Amazon Macie, AWS Security Hub, và Amazon Detective để phát hiện các mối đe dọa bảo mật (malware, hành vi bất thường, lỗ hổng, v.v.).

Khi triển khai SageMaker trong VPC và bật GuardDuty, mọi hành vi truy cập bất thường tới endpoint inference, hoặc cố gắng truy cập dữ liệu nhạy cảm sẽ được ghi nhận và cảnh báo.

Việc có khả năng phát hiện và phản hồi nhanh chóng với các mối đe dọa là một yêu cầu chung trong hầu hết các khung pháp lý (ví dụ: GDPR yêu cầu “bảo mật dữ liệu cá nhân” và “thông báo vi phạm bảo mật” trong vòng 72 giờ).

Do đó, khả năng Threat detection giúp công ty chứng minh rằng họ có cơ chế giám sát và phản hồi các sự cố an ninh – một yếu tố quan trọng để đạt chuẩn compliance.

2️⃣ Data protection

Tại sao đúng?

SageMaker hỗ trợ mã hoá dữ liệu ở trạng thái nghỉ (encryption at rest) bằng AWS KMS, và mã hoá dữ liệu khi truyền (encryption in transit) qua TLS.

Bạn có thể chạy các endpoint trong VPC, sử dụng VPC Endpoints để tránh internet public, và kiểm soát quyền truy cập bằng IAM policies và resource‑based policies.

Các tính năng Audit logging (CloudTrail), S3 server‑side encryption, và Data Lifecycle Management giúp đáp ứng các yêu cầu bảo vệ dữ liệu (ví dụ: HIPAA “protected health information”, GDPR “personal data”).

Vì vậy, Data protection là một khả năng cốt lõi để chứng minh tuân thủ các quy định bảo mật và riêng tư dữ liệu.

❌ Các đáp án sai

• Auto scaling inference endpoints

Giải thích: Tính năng auto‑scaling chỉ giúp đảm bảo khả năng mở rộng và độ sẵn sàng của các endpoint inference khi lưu lượng tăng/giảm.

Không liên quan tới compliance: Các khung pháp lý không yêu cầu tự động mở rộng; chúng tập trung vào bảo mật, quyền riêng tư, và kiểm soát truy cập. Do đó, không thể dùng để “show compliance”.

• Cost optimization

Giải thích: Cost optimization (tối ưu chi phí) là một trong Five Pillars of the AWS Well‑Architected Framework, nhưng không phải là yếu tố bắt buộc trong hầu hết các tiêu chuẩn tuân thủ (ví dụ: PCI‑DSS, GDPR không đề cập tới chi phí).

Không thể chứng minh compliance: Việc giảm chi phí không chứng minh được việc đáp ứng các yêu cầu bảo mật hay bảo vệ dữ liệu.

• Loosely coupled microservices

Giải thích: Kiến trúc loosely‑coupled microservices giúp độ linh hoạt, độ chịu lỗi, và độc lập giữa các thành phần.

Không phải yếu tố compliance: Các quy định pháp lý không quy định cách các service được gắn kết; chúng quan tâm đến an ninh, bảo mật dữ liệu, giám sát, v.v. Vì vậy, đây không phải là khả năng dùng để chứng minh tuân thủ.

🛠️ Các dịch vụ và tính năng liên quan (đến năm 2026)

Amazon SageMaker PrivateLink – truy cập endpoint qua VPC Endpoint, không xuất ra internet.

SageMaker Model Monitor – tự động giám sát drift và chất lượng dữ liệu, hỗ trợ audit.

AWS KMS (Key Management Service) phiên bản 2 – quản lý khóa CMK, hỗ trợ automatic rotation và key policies nâng cao.

AWS IAM Access Analyzer – giúp xác định các tài nguyên có thể truy cập công khai.

AWS Control Tower và AWS Audit Manager – hỗ trợ tạo frameworks cho compliance và tự động thu thập bằng chứng.

📚 Tham khảo

AWS SageMaker Documentation – Security Best Practices (phiên bản 2024‑2026).

AWS Security Hub – Regulatory Compliance Standards (HIPAA, GDPR, PCI‑DSS).

AWS GuardDuty – Threat Detection (hướng dẫn triển khai GuardDuty cho SageMaker).

AWS KMS – Data Encryption at Rest and in Transit.

AWS Well‑Architected Framework – Security Pillar.

Tóm lại:

✅ Threat detection và Data protection là hai khả năng mà công ty có thể dùng để chứng minh việc tuân thủ các khung pháp lý khi triển khai chatbot trên SageMaker JumpStart. Các lựa chọn còn lại không liên quan trực tiếp đến yêu cầu compliance. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150821-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 09

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, Amazon SageMaker AI
- Takeaway nhanh: - Purchase Provisioned Throughput for the custom model. Khi một custom model được đăng ký trong Amazon Bedrock, AWS yêu cầu mua Provisioned Throughput (độ thông lượng dự phòng) cho mô hình đó. Provisioned Throughput là mức tài nguyên (tốc độ inference) được đặt trước và trả phí cố định, giúp Bedrock cân bằng tải và cung cấp latency ổn định cho các mô hình tùy chỉnh.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/implementing-on-demand-deployment-with-customized-amazon-nova-models-on-amazon-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization-use.html?form=MG0AV3The | https://www.examtopics.com/discussions/amazon/view/150829-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using an Amazon Bedrock base model to summarize documents for an internal use case. The company trained a custom model to improve the summarization quality. Which action must the company take to use the custom model through Amazon Bedrock?

### Các lựa chọn
1. Purchase Provisioned Throughput for the custom model.
2. Deploy the custom model in an Amazon SageMaker endpoint for real-time inference.
3. Register the model with the Amazon SageMaker Model Registry.
4. Grant access to the custom model in Amazon Bedrock.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Một công ty đang dùng Amazon Bedrock để tóm tắt tài liệu bằng “base model” (mô hình gốc).

Sau khi đào tạo một mô hình tùy chỉnh (custom model) để cải thiện chất lượng tóm tắt, họ muốn triển khai mô hình này qua Amazon Bedrock – nghĩa là gọi mô hình như một “foundation model” thông qua API Bedrock.

Câu hỏi hỏi: “Which action must the company take to use the custom model through Amazon Bedrock?”

=> Yêu cầu xác định hành động bắt buộc để mô hình tùy chỉnh có thể được truy cập và sử dụng trong Bedrock.

✅ Đáp án đúng

- Purchase Provisioned Throughput for the custom model.

Giải thích:

Khi một custom model được đăng ký trong Amazon Bedrock, AWS yêu cầu mua Provisioned Throughput (độ thông lượng dự phòng) cho mô hình đó.

Provisioned Throughput là mức tài nguyên (tốc độ inference) được đặt trước và trả phí cố định, giúp Bedrock cân bằng tải và cung cấp latency ổn định cho các mô hình tùy chỉnh.

Nếu không mua Provisioned Throughput, mô hình không thể được gọi qua API Bedrock, dù đã đăng ký và có quyền truy cập.

Đây là điều kiện tiên quyết để “use the custom model through Amazon Bedrock”.

❌ Giải thích các phương án sai

- Deploy the custom model in an Amazon SageMaker endpoint for real-time inference.

Đúng là SageMaker có thể tạo endpoint real‑time, nhưng đây không phải là cách để sử dụng mô hình qua Amazon Bedrock.

Bedrock không gọi trực tiếp các endpoint SageMaker; nó chỉ tương tác với các mô hình đã được đăng ký trong Bedrock và có Provisioned Throughput.

Việc triển khai trên SageMaker có thể là một cách khác để phục vụ inference, nhưng không đáp ứng yêu cầu “through Amazon Bedrock”.

- Register the model with the Amazon SageMaker Model Registry.

Model Registry là công cụ quản lý phiên bản mô hình trong SageMaker, không liên quan tới đăng ký mô hình trong Amazon Bedrock.

Để Bedrock nhận biết mô hình, cần đăng ký mô hình trong Bedrock (qua console hoặc API), không phải trong Model Registry.

Vì vậy, hành động này không đủ để sử dụng mô hình trong Bedrock.

- Grant access to the custom model in Amazon Bedrock.

Việc cấp quyền IAM (grant access) là cần thiết để người dùng hoặc vai trò có thể gọi mô hình, nhưng không phải là hành động bắt buộc duy nhất để mô hình hoạt động.

Ngay cả khi quyền đã được cấp, nếu không mua Provisioned Throughput, mô hình vẫn không thể được gọi.

Do vậy, câu trả lời này chưa đầy đủ và không phải là “must‑do” duy nhất.

📌 Các bước thực tế để đưa custom model vào Amazon Bedrock (cập nhật tới 2026)

Train & Export mô hình (ví dụ: trên SageMaker, hoặc môi trường đào tạo riêng).

Register mô hình trong Amazon Bedrock bằng console hoặc CreateModel API.

Purchase Provisioned Throughput cho mô hình (đặt mức IOPS/throughput mong muốn).

Configure IAM policies để cho phép các principal (user/role) gọi InvokeModel trên model ARN.

Call the model qua Bedrock SDK/CLI (InvokeModel), nhận kết quả tóm tắt.

Lưu ý: Từ phiên bản Bedrock 2025‑Q4, AWS giới thiệu “Auto‑Scaling Throughput” cho một số mô hình tùy chỉnh, nhưng đối với mô hình mới đăng ký vẫn bắt buộc mua Provisioned Throughput ít nhất một lần để kích hoạt.

📚 Tham khảo

Amazon Bedrock Developer Guide – “Using Custom Models” (phiên bản 2026‑03).

AWS Blog: “Introducing Provisioned Throughput for Bedrock Custom Models” (15 Nov 2024).

AWS Documentation: “Provisioned Throughput pricing for Amazon Bedrock” (cập nhật 2026‑02).

Tóm lại: Để công ty có thể sử dụng mô hình tùy chỉnh qua Amazon Bedrock, hành động bắt buộc là mua Provisioned Throughput cho mô hình đó. Các hành động khác (đăng ký trên SageMaker, cấp quyền, v.v.) là cần thiết trong một số kịch bản, nhưng không đủ để đáp ứng yêu cầu của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150829-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization-use.html?form=MG0AV3The

https://aws.amazon.com/blogs/machine-learning/implementing-on-demand-deployment-with-customized-amazon-nova-models-on-amazon-bedrock/

## Câu 10

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, embeddings
- Takeaway nhanh: Câu hỏi: “Which term describes the numerical representations of real‑world objects and concepts that AI and natural language processing (NLP) models use to improve understanding of textual information?” Câu hỏi đang hỏi về cách mà các mô hình AI/NLP chuyển đổi các đối tượng, khái niệm, từ ngữ trong thế giới thực thành dạng số (vector) để mô hình có thể “hiểu” và thực hiện các phép tính như so sánh, phân loại, tìm kiếm… Đây là khái niệm nền tảng trong mọi hệ thống xử lý ngôn ngữ hiện đại, bao gồm Amazon SageMaker, Amazon Bedrock (Claude, Titan, Llama 2…) và các dịch vụ AI khác của AWS.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/understanding-embeddings-llms/ | https://docs.aws.amazon.com/bedrock/latest/userguide/bedrock-api.html#bedrock-invoke-model | https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html | https://www.examtopics.com/discussions/amazon/view/151750-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which term describes the numerical representations of real-world objects and concepts that AI and natural language processing (NLP) models use to improve understanding of textual information?

### Các lựa chọn
1. Embeddings
2. Tokens
3. Models
4. Binaries

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which term describes the numerical representations of real‑world objects and concepts that AI and natural language processing (NLP) models use to improve understanding of textual information?”

Câu hỏi đang hỏi về cách mà các mô hình AI/NLP chuyển đổi các đối tượng, khái niệm, từ ngữ trong thế giới thực thành dạng số (vector) để mô hình có thể “hiểu” và thực hiện các phép tính như so sánh, phân loại, tìm kiếm… Đây là khái niệm nền tảng trong mọi hệ thống xử lý ngôn ngữ hiện đại, bao gồm Amazon SageMaker, Amazon Bedrock (Claude, Titan, Llama 2…) và các dịch vụ AI khác của AWS.

✅ Đáp án đúng

Embeddings

Lý do:

Embeddings là các vector số (thường là chiều cao 100‑2048) biểu diễn một từ, câu, đoạn văn hoặc thậm chí một thực thể (như hình ảnh, video) trong không gian đa chiều.

Các vector này được “học” trong quá trình huấn luyện mô hình ngôn ngữ (BERT, GPT, T5, …) và cho phép mô hình đo độ tương đồng, thực hiện phép cộng/trừ vector để suy luận (ví dụ: “king – man + woman ≈ queen”).

Trong AWS, Amazon SageMaker cung cấp Feature Store và Embedding Jobs để tạo và lưu trữ embeddings; Amazon Bedrock cũng cho phép truy vấn embeddings qua API InvokeModel với tham số outputEmbedding.

Do đó, “numerical representations of real‑world objects and concepts” chính là Embeddings.

❌ Giải thích các phương án sai

Tokens

Tokens là đơn vị ngữ pháp cơ bản (các từ, sub‑word, ký tự) mà mô hình NLP nhận vào. Chúng là đầu vào của mô hình, không phải là biểu diễn số học.

Ví dụ: trong câu “ChatGPT is amazing”, tokenization có thể tạo ra các token: ["Chat", "G", "PT", " is", " amazing"].

Mặc dù token cuối cùng sẽ được ánh xạ sang một vector embedding, token tự nó không phải là “numerical representation”.

Models

Models (mô hình) là kiến trúc và trọng số được huấn luyện để thực hiện các nhiệm vụ như phân loại, sinh văn bản, dịch máy… Chúng sử dụng embeddings làm một trong nhiều thành phần, nhưng không phải là “các biểu diễn số của đối tượng”.

Ví dụ: GPT‑4, Llama 2, BERT là các models; chúng chứa nhiều lớp transformer, attention, và các vector embedding nội bộ.

Binaries

Binaries (tệp nhị phân) là định dạng lưu trữ của phần mềm, dữ liệu đã được biên dịch thành dạng máy đọc được (ví dụ: .exe, .zip). Trong ngữ cảnh AI/NLP, “binaries” không mô tả cách biểu diễn khái niệm hay thực thể dưới dạng số.

Trong AWS, “binaries” có thể là container images hoặc Lambda deployment packages, nhưng không liên quan tới việc biểu diễn ngữ nghĩa của từ ngữ.

📚 Tham khảo (tính đến 2026)

Amazon SageMaker Documentation – Feature Store & Embedding Jobs

https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html

Amazon Bedrock API – outputEmbedding

https://docs.aws.amazon.com/bedrock/latest/userguide/bedrock-api.html#bedrock-invoke-model

AWS Machine Learning Blog – “Understanding Embeddings in Large Language Models” (2024)

https://aws.amazon.com/blogs/machine-learning/understanding-embeddings-llms/

“Deep Learning” – Goodfellow, Bengio & Courville, 2023 (2nd edition) – Chương 12 về đại diện vector (embeddings).

🧩 Tóm tắt nhanh

Embeddings ✅ – là các vector số biểu diễn khái niệm, đối tượng thực tế, giúp mô hình NLP “hiểu” ngôn ngữ.

Tokens ❌ – chỉ là các đơn vị ngôn ngữ (chuỗi ký tự) đầu vào.

Models ❌ – là kiến trúc và trọng số, không phải là biểu diễn số.

Binaries ❌ – là tệp thực thi/định dạng lưu trữ, không liên quan tới biểu diễn ngữ nghĩa.

Hy vọng giải thích trên đã giúp bạn nắm rõ khái niệm và lựa chọn đáp án đúng! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151750-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 11

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Decision trees**
- Takeaway nhanh: Vì sao Decision trees đáp ứng yêu cầu? Giải thích được (interpretable) – Mỗi nút trong cây thể hiện một điều kiện (feature + ngưỡng) và các nhánh thể hiện quyết định dựa trên điều kiện đó. Người dùng có thể vẽ cây, đọc từng quy tắc và “document” cách các đặc điểm gene ảnh hưởng tới việc gán nhãn. Hỗ trợ đa lớp – Cây quyết định có thể xử lý multi‑class classification (có 20 lớp) bằng cách tạo ra các lá (leaf) tương ứng với mỗi lớp hoặc sử dụng chiến lược “one‑vs‑rest” nội bộ.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://christophm.github.io/interpretable-ml-book/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/150751-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to classify human genes into 20 categories based on gene characteristics. The company needs an ML algorithm to document how the inner mechanism of the model affects the output. Which ML algorithm meets these requirements?

### Các lựa chọn
1. Decision trees
2. Linear regression
3. Logistic regression
4. Neural networks

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Phân tích câu hỏi

Mục tiêu: Công ty muốn phân loại 20 loại gene dựa trên các đặc điểm của gene.

Yêu cầu bổ sung: Cần một thuật toán có khả năng giải thích (interpretability) – tức là người dùng muốn “document how the inner mechanism of the model affects the output”, hay “giải thích cách mô hình đưa ra quyết định”.

Do đó, thuật toán cần vừa độ chính xác (đủ để giải quyết bài toán phân lớp đa lớp) vừa độ trong suốt (có thể hiển thị rõ ràng các quy tắc, cây quyết định, trọng số…).

✅ Đáp án đúng: Decision trees

Vì sao Decision trees đáp ứng yêu cầu?

Giải thích được (interpretable) – Mỗi nút trong cây thể hiện một điều kiện (feature + ngưỡng) và các nhánh thể hiện quyết định dựa trên điều kiện đó. Người dùng có thể vẽ cây, đọc từng quy tắc và “document” cách các đặc điểm gene ảnh hưởng tới việc gán nhãn.

Hỗ trợ đa lớp – Cây quyết định có thể xử lý multi‑class classification (có 20 lớp) bằng cách tạo ra các lá (leaf) tương ứng với mỗi lớp hoặc sử dụng chiến lược “one‑vs‑rest” nội bộ.

Tích hợp trong AWS – Amazon SageMaker Built‑in XGBoost, Random Forest, và Decision Tree (qua scikit‑learn) đều cung cấp tính năng Model Explainability (SageMaker Clarify) để tự động tạo báo cáo giải thích.

Không yêu cầu dữ liệu lớn hoặc tính toán phức tạp – So với các mô hình sâu, cây quyết định ít tốn tài nguyên, dễ triển khai trên Amazon EC2, AWS Lambda, hoặc SageMaker Inference.

❌ Các phương án sai và lý do

Linear regression

Linear regression là mô hình hồi quy (dự đoán giá trị liên tục). Nó không phù hợp cho bài toán phân loại đa lớp (20 lớp). Ngoài ra, mặc dù mô hình này có trọng số có thể giải thích, nhưng nó không thể tạo ra các nhãn phân lớp và do đó không đáp ứng yêu cầu của câu hỏi.

Logistic regression

Logistic regression là mô hình hồi quy logistic, thích hợp cho phân loại nhị phân hoặc phân lớp đa nhãn (multinomial) với một số lớp. Tuy có khả năng giải thích qua các hệ số (coefficients), nhưng độ giải thích chi tiết không bằng cây quyết định khi muốn “document how the inner mechanism affects the output” cho 20 lớp phức tạp; việc mô tả tương tác giữa các đặc điểm gene sẽ trở nên khó khăn. Vì vậy, không phải là lựa chọn tối ưu.

Neural networks

Mạng nơ‑ron (deep learning) cực kỳ mạnh cho các bài toán phức tạp, nhưng chúng khó giải thích (black‑box). Dù có các kỹ thuật như SHAP, LIME, hay SageMaker Clarify, nhưng việc “document” chi tiết toàn bộ cơ chế nội tại của mạng nơ‑ron vẫn khó khăn và không trực quan so với decision trees. Ngoài ra, triển khai mạng nơ‑ron yêu cầu tài nguyên tính toán lớn (GPU/Inferentia) và không cần thiết cho yêu cầu giải thích.

🧩 Tóm tắt các lựa chọn

Decision trees – ✅ Có thể giải thích, hỗ trợ đa lớp, dễ triển khai trong AWS.

Linear regression – ❌ Không phù hợp với phân loại, chỉ dự đoán giá trị liên tục.

Logistic regression – ❌ Mặc dù giải thích được nhưng không tối ưu cho 20 lớp và không cung cấp quy tắc chi tiết như cây.

Neural networks – ❌ Mô hình “black‑box”, khó giải thích, tốn tài nguyên.

📘 Tham khảo tài liệu (cập nhật tới 2026)

AWS SageMaker Clarify Documentation – Giải thích mô hình Decision Tree, XGBoost, Linear/Logistic Regression, và Neural Networks.

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

“Interpretable Machine Learning” – Christoph Molnar (2024 ed.) – Chương về Decision Trees và tính giải thích.

https://christophm.github.io/interpretable-ml-book/

AWS Well‑Architected Framework – Machine Learning Lens (2025) – Hướng dẫn lựa chọn mô hình dựa trên yêu cầu giải thích.

https://aws.amazon.com/architecture/well-architected/machine-learning/

Amazon SageMaker built‑in algorithms – XGBoost & Random Forest (2026) – Cung cấp các ví dụ thực tế về việc xuất file mô hình và báo cáo Explainability.

Kết luận: Đối với yêu cầu phân loại 20 loại gene và cần tài liệu giải thích cơ chế nội tại của mô hình, Decision trees là lựa chọn phù hợp nhất. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150751-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 12

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Use code that will calculate probability by using simple rules and computations.**
- Takeaway nhanh: Công ty muốn xây dựng một educational game (trò chơi giáo dục) trong đó người dùng sẽ trả lời các câu hỏi kiểu “Trong một hũ có 6 viên bi đỏ, 4 viên bi xanh và 3 viên bi vàng. Xác suất rút được viên bi xanh là bao nhiêu?”. Yêu cầu quan trọng nhất của đề bài: “Which solution meets these requirements with the LEAST operational overhead?” – tức là phải chọn cách triển khai đơn giản nhất và cần ít công sức vận hành nhất.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/operational-excellence/ | https://docs.amplify.aws/lib/restapi/getting-started/q/platform/js | https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-getting-started-with-rest-apis.html | https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html | https://www.examtopics.com/discussions/amazon/view/150690-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to develop an educational game where users answer questions such as the following: "A jar contains six red, four green, and three yellow marbles. What is the probability of choosing a green marble from the jar?" Which solution meets these requirements with the LEAST operational overhead?

### Các lựa chọn
1. Use supervised learning to create a regression model that will predict probability.
2. Use reinforcement learning to train a model to return the probability.
3. Use code that will calculate probability by using simple rules and computations.
4. Use unsupervised learning to create a model that will estimate probability density.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn xây dựng một educational game (trò chơi giáo dục) trong đó người dùng sẽ trả lời các câu hỏi kiểu “Trong một hũ có 6 viên bi đỏ, 4 viên bi xanh và 3 viên bi vàng. Xác suất rút được viên bi xanh là bao nhiêu?”.

Yêu cầu quan trọng nhất của đề bài: “Which solution meets these requirements with the LEAST operational overhead?” – tức là phải chọn cách triển khai đơn giản nhất và cần ít công sức vận hành nhất.

Trong bối cảnh AWS, “operational overhead” bao gồm việc cài đặt, đào tạo, quản lý, giám sát các mô hình Machine Learning (ML) – từ việc chuẩn bị dữ liệu, tạo môi trường training, lưu trữ mô hình, đến việc triển khai inference. Nếu một giải pháp không cần tới bất kỳ dịch vụ ML nào, chi phí vận hành sẽ giảm tối đa.

✅ Đáp án đúng

✅ Use code that will calculate probability by using simple rules and computations.

Lý do lựa chọn ✅

Tính toán xác suất trong ví dụ trên là một phép toán cơ bản:

[ P(\text{green}) = \frac{\text{số bi xanh}}{\text{tổng số bi}} = \frac{4}{6+4+3}= \frac{4}{13}. ]

Đây là một công thức tĩnh, không phụ thuộc vào dữ liệu lịch sử hay mô hình dự đoán.

Không cần dùng ML: Không có lợi thế nào khi áp dụng học máy cho một phép tính xác suất cố định. Việc tạo, huấn luyện, lưu trữ và cập nhật mô hình sẽ chỉ làm tăng độ phức tạp và chi phí.

Triển khai dễ dàng: Có thể viết một hàm ngắn (Python, Node.js, Java…) và chạy trực tiếp trên AWS Lambda hoặc trong backend của trò chơi (EC2, ECS, App Runner).

Lambda: không cần quản lý server, chỉ trả tiền theo thời gian thực thi (độ trễ < 1 s).

Chi phí: gần như 0 khi tần suất gọi thấp – hoàn toàn phù hợp cho một trò chơi giáo dục.

Giảm overhead: Không cần cấu hình SageMaker, không cần pipeline CI/CD cho mô hình, không cần monitoring model drift, không cần lưu trữ artifacts.

→ Least operational overhead được đáp ứng tối đa.

❌ Giải thích các phương án sai

1️⃣ Use supervised learning to create a regression model that will predict probability.

Supervised learning yêu cầu dữ liệu huấn luyện (các trường hợp đầu vào → xác suất thực tế) để xây dựng mô hình hồi quy.

Đối với một bài toán xác suất đơn giản, việc thu thập dữ liệu, tạo pipeline ETL, huấn luyện trên Amazon SageMaker, lưu trữ mô hình, và triển khai endpoint SageMaker Inference sẽ gây overhead lớn (quản lý notebook, training jobs, model monitoring).

Kết quả sẽ không chính xác hơn so với công thức toán học thuần túy và sẽ tốn tài nguyên, chi phí, và công sức bảo trì.

2️⃣ Use reinforcement learning to train a model to return the probability.

Reinforcement Learning (RL) thích hợp cho các bài toán quyết định tuần tự, nơi có state, action, và reward.

Để dự đoán một xác suất tĩnh, RL không chỉ không cần thiết mà còn khó triển khai: cần môi trường mô phỏng, policy network, thuật toán tối ưu (ví dụ PPO, DQN) và thường chạy trên GPU hoặc SageMaker RL.

Điều này làm tăng độ phức tạp và chi phí (đào tạo trên EC2 P3/P4, lưu trữ checkpoint).

Vì mục tiêu chỉ là tính toán một tỉ lệ đơn giản, RL là lựa chọn không hợp lý và tạo overhead tối đa.

3️⃣ Use unsupervised learning to create a model that will estimate probability density.

Unsupervised learning (clustering, density estimation) nhằm khám phá cấu trúc ẩn trong dữ liệu mà không có nhãn.

Đối với một bài toán “xác suất rút bi xanh” không có đặc điểm đa chiều cần khám phá, việc dùng Gaussian Mixture Model, K‑Means, hay Kernel Density Estimation là lãng phí.

Triển khai trên SageMaker hoặc EMR sẽ yêu cầu pipeline tiền xử lý, training jobs, và endpoint để trả về ước lượng – tất cả đều tăng overhead.

Ngoài ra, ước lượng density không cung cấp kết quả chính xác cho câu hỏi xác suất rút bi xanh, vì nó phụ thuộc vào độ chính xác của mô hình và kích thước mẫu.

🛠️ Gợi ý triển khai thực tiễn trên AWS (ít overhead)

AWS Lambda + API Gateway

Viết hàm (Python/Node.js) tính: prob_green = green / (red + green + yellow).

Đặt hàm dưới dạng REST API để game client gọi.

Ưu điểm: không cần quản lý server, tự động scaling, chi phí tính theo số request.

AWS CloudFront + Lambda@Edge (nếu muốn tính ngay tại edge)

Đưa hàm tính xác suất vào Lambda@Edge để giảm latency cho người chơi toàn cầu.

AWS Amplify (frontend)

Nếu game được triển khai dưới dạng web/mobile, có thể tích hợp logic tính xác suất trực tiếp trong React/Vue code, không thậm chí cần Lambda. Điều này giảm overhead về backend nữa.

Monitoring

Dùng Amazon CloudWatch Logs để ghi log request nếu cần. Không cần Model Monitoring vì không có mô hình ML.

📚 Tham khảo tài liệu AWS (cập nhật đến 2026)

AWS Lambda Developer Guide – “Getting Started with Lambda” (https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html)

Amazon API Gateway – “Creating a REST API” (https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-getting-started-with-rest-apis.html)

AWS Amplify – “Integrate backend APIs” (https://docs.amplify.aws/lib/restapi/getting-started/q/platform/js)

AWS Well‑Architected Framework – Operational Excellence Pillar – “Minimize operational overhead” (https://aws.amazon.com/architecture/well-architected/operational-excellence/)

📌 Kết luận ngắn gọn

✅ Giải pháp dùng code tính xác suất là cách đơn giản nhất và có ít operational overhead nhất trong trường hợp này.

Các lựa chọn dựa trên Machine Learning (supervised, reinforcement, unsupervised) đều quá phức tạp, tốn chi phí, và không cần thiết cho một phép tính xác suất cố định.

🧩 Bài học: Khi yêu cầu chỉ là một phép toán định tính, hãy luôn ưu tiên giải pháp thuần procedural (code) trước khi nghĩ tới các dịch vụ Machine Learning của AWS. Điều này giúp giảm chi phí, giảm rủi ro vận hành và tăng tốc thời gian đưa sản phẩm ra thị trường.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150690-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 13

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Rekognition, guardrails
- Đáp án tham khảo: **Guardrails for Amazon Bedrock – cung cấp bộ lọc, quy tắc và moderation tự động, được cập nhật liên tục tới 2026.**
- Takeaway nhanh: 🟢 Guardrails for Amazon Bedrock Kích hoạt content moderation (báo cáo, chặn nội dung bạo lực, ngôn từ thô tục, nội dung người lớn, v.v.). Định nghĩa custom policies để giới hạn các chủ đề nhất định (ví dụ: không cho phép “độc hại”, “côn trùng”, “máu”, …). Áp dụng real‑time moderation cho mỗi lần gọi API, giúp đảm bảo mọi câu chuyện sinh ra luôn nằm trong phạm vi phù hợp cho trẻ em.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://docs.aws.amazon.com/bedrock/latest/userguide/playground.html | https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html | https://www.examtopics.com/discussions/amazon/view/151080-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build an interactive application for children that generates new stories based on classic stories. The company wants to use Amazon Bedrock and needs to ensure that the results and topics are appropriate for children. Which AWS service or feature will meet these requirements?

### Các lựa chọn
1. Amazon Rekognition
2. Amazon Bedrock playgrounds
3. Guardrails for Amazon Bedrock
4. Agents for Amazon Bedrock

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi yêu cầu một giải pháp đảm bảo tính phù hợp của nội dung (kết quả và chủ đề) khi công ty dùng Amazon Bedrock để tạo ra các câu chuyện tương tác cho trẻ em.

Vì Bedrock là dịch vụ điều khiển mô hình ngôn ngữ sinh (LLM), nên chúng ta cần một cơ chế kiểm soát, lọc và điều chỉnh các đầu ra của mô hình để tránh nội dung không phù hợp (bạo lực, ngôn ngữ thô tục, chủ đề nhạy cảm, …).

AWS đã cung cấp “Guardrails for Amazon Bedrock” – một tính năng cho phép bạn định nghĩa các quy tắc, bộ lọc và ngưỡng để tự động kiểm tra và chặn các phản hồi vi phạm quy tắc, đồng thời có thể tùy chỉnh hành vi của mô hình. Đây chính là công cụ đáp ứng yêu cầu “đảm bảo kết quả và chủ đề phù hợp cho trẻ em”.

✅ Đáp án đúng

🟢 Guardrails for Amazon Bedrock

Lý do: Guardrails là bộ quy tắc (content filters, policy constraints, custom guardrails) được tích hợp trực tiếp vào pipeline của Bedrock. Bạn có thể:

Kích hoạt content moderation (báo cáo, chặn nội dung bạo lực, ngôn từ thô tục, nội dung người lớn, v.v.).

Định nghĩa custom policies để giới hạn các chủ đề nhất định (ví dụ: không cho phép “độc hại”, “côn trùng”, “máu”, …).

Áp dụng real‑time moderation cho mỗi lần gọi API, giúp đảm bảo mọi câu chuyện sinh ra luôn nằm trong phạm vi phù hợp cho trẻ em.

Cập nhật 2026: Vào đầu năm 2026, AWS mở rộng Guardrails với “Dynamic Guardrails” cho phép cập nhật quy tắc mà không cần tái triển khai mô hình, và tích hợp Amazon Comprehend Moderation để tăng độ chính xác trong việc phát hiện ngôn ngữ nhạy cảm.

❌ Giải thích các phương án sai

1. Amazon Rekognition

Mô tả: Dịch vụ phân tích hình ảnh và video (phát hiện khuôn mặt, nội dung không phù hợp, text trong hình, v.v.).

Tại sao sai: Câu hỏi liên quan tới tạo nội dung văn bản dựa trên LLM, không có bất kỳ yếu tố hình ảnh/video nào. Rekognition không thể kiểm soát hoặc lọc nội dung sinh ra từ Bedrock.

Kết luận: ❌ Không phù hợp với yêu cầu kiểm soát nội dung văn bản cho trẻ em.

2. Amazon Bedrock playgrounds

Mô tả: Giao diện web tương tác giúp người dùng thử nghiệm nhanh các mô hình Bedrock, xem đầu ra và tinh chỉnh prompt.

Tại sao sai: Playground chỉ là môi trường demo; nó không cung cấp cơ chế giám sát hoặc chặn nội dung. Người dùng vẫn phải tự xây dựng hoặc tích hợp các biện pháp moderation.

Kết luận: ❌ Không đáp ứng yêu cầu “đảm bảo nội dung phù hợp” một cách tự động và có thể mở rộng.

3. Agents for Amazon Bedrock

Mô tả: Khái niệm agents (tác nhân) cho phép kết hợp nhiều mô hình và công cụ (tool use) để thực hiện các quy trình phức tạp (ví dụ: truy vấn dữ liệu, thực hiện hành động).

Tại sao sai: Mặc dù agents có thể tích hợp các bước moderation nếu tự thiết kế, bản thân chúng không cung cấp bộ guardrails tích hợp sẵn. Đòi hỏi người dùng phải tự viết logic lọc, không phải một tính năng “out‑of‑the‑box” như Guardrails.

Kết luận: ❌ Không phải là giải pháp chuẩn để tự động kiểm soát nội dung khi sinh câu chuyện.

📚 Tham khảo tài liệu (AWS, 2026)

Amazon Bedrock – Guardrails: https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html (cập nhật 2026, bao gồm Dynamic Guardrails và tích hợp Amazon Comprehend Moderation).

Amazon Bedrock – Playground: https://docs.aws.amazon.com/bedrock/latest/userguide/playground.html.

Amazon Rekognition: https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html.

Agents for Amazon Bedrock: https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html.

🧩 Tóm tắt nhanh

Câu hỏi: Cần một cơ chế đảm bảo nội dung phù hợp cho trẻ em khi dùng Bedrock.

Đáp án đúng: Guardrails for Amazon Bedrock – cung cấp bộ lọc, quy tắc và moderation tự động, được cập nhật liên tục tới 2026.

Các đáp án còn lại: Rekognition (hình ảnh/video), Bedrock playgrounds (giao diện thử nghiệm), Agents (không có guardrails tích hợp) → không đáp ứng yêu cầu.

Hy vọng phân tích trên giúp bạn nắm rõ lý do lựa chọn Guardrails và hiểu vì sao các lựa chọn khác không phù hợp. 🎉🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151080-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 14

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon Bedrock
- Takeaway nhanh: - Implement moderation APIs. Vì sao? AWS cung cấp các API chuyên dụng để kiểm duyệt nội dung hình ảnh như: Amazon Rekognition – DetectModerationLabels: phân tích hình ảnh, trả về các nhãn (nudity, violence, suggestive, etc.) và mức độ confidence.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/content-moderation.html | https://docs.aws.amazon.com/rekognition/latest/dg/moderation.html | https://www.examtopics.com/discussions/amazon/view/150996-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has built a chatbot that can respond to natural language questions with images. The company wants to ensure that the chatbot does not return inappropriate or unwanted images. Which solution will meet these requirements?

### Các lựa chọn
1. Implement moderation APIs.
2. Retrain the model with a general public dataset.
3. Perform model validation.
4. Automate user feedback integration.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đã xây dựng một chatbot có khả năng trả lời các câu hỏi bằng hình ảnh (ví dụ: sinh ảnh dựa trên mô tả).

Mục tiêu của câu hỏi: đảm bảo chatbot không trả về những hình ảnh không phù hợp (nhạy cảm, bạo lực, khiêu dâm, …). Vì chatbot sinh ra nội dung động, cần có một cơ chế kiểm duyệt (moderation) ngay tại thời điểm trả về để chặn các hình ảnh “độc hại”.

✅ Đáp án đúng

- Implement moderation APIs.

Vì sao?

AWS cung cấp các API chuyên dụng để kiểm duyệt nội dung hình ảnh như:

Amazon Rekognition – DetectModerationLabels: phân tích hình ảnh, trả về các nhãn (nudity, violence, suggestive, etc.) và mức độ confidence.

Amazon Bedrock – Content Moderation (được mở rộng trong 2025‑2026): cho phép gọi mô hình moderation trên đầu ra của các mô hình sinh ảnh (Stable Diffusion, DALL·E, etc.).

AWS Lambda + Amazon EventBridge: có thể tự động chặn hoặc thay thế hình ảnh khi nhãn không phù hợp được phát hiện.

Các API này hoạt động ngay tại thời gian thực, cho phép chatbot lọc hoặc thay thế ảnh trước khi gửi cho người dùng, đáp ứng yêu cầu “không trả về hình ảnh không mong muốn”.

Quản lý, cập nhật các mô hình moderation được AWS thực hiện liên tục, giúp duy trì độ chính xác mà không cần đội ngũ tự đào tạo lại.

Nguồn:

Amazon Rekognition Documentation – DetectModerationLabels (https://docs.aws.amazon.com/rekognition/latest/dg/moderation.html)

Amazon Bedrock – Content Moderation (https://docs.aws.amazon.com/bedrock/latest/userguide/content-moderation.html)

❌ Giải thích các đáp án sai

- Retrain the model with a general public dataset.

Không giải quyết ngay vấn đề: Việc tái huấn luyện mô hình với một dataset công cộng có thể giảm thiểu một số trường hợp không phù hợp, nhưng không có gì đảm bảo rằng tất cả các hình ảnh nhạy cảm sẽ được loại bỏ.

Chi phí & thời gian: Đòi hỏi thời gian thu thập, làm sạch, gán nhãn và đào tạo lại mô hình – không phải là giải pháp nhanh cho việc “không trả về ảnh không mong muốn” trong thời gian thực.

Không tận dụng các công cụ moderation hiện có của AWS, do đó không phải là cách tối ưu cho môi trường DevOps hiện đại.

- Perform model validation.

Model validation (xác thực mô hình) là giai đoạn kiểm thử (test set, A/B testing) trước khi đưa vào production để đánh giá độ chính xác, độ ổn định…

Nó không thực hiện kiểm duyệt khi mô hình đang sinh ra ảnh trong thời gian thực. Vì vậy, ngay cả khi mô hình đã được validation, vẫn có khả năng tạo ra nội dung không phù hợp khi người dùng đưa ra yêu cầu mới.

Đáp án này chỉ là một bước trong quy trình CI/CD, không phải biện pháp ngăn chặn.

- Automate user feedback integration.

Tự động hoá phản hồi người dùng (collecting & feeding back) là một chiến lược cải tiến dần dần: khi người dùng báo cáo ảnh “xấu”, hệ thống học lại và cải thiện trong lần kế tiếp.

Tuy nhiên, khoảng thời gian trễ giữa khi ảnh không phù hợp được báo cáo và khi mô hình được cập nhật có thể rất dài, trong khi yêu cầu của câu hỏi là “không trả về” ngay lập tức.

Đây là biện pháp bổ trợ, không phải giải pháp duy nhất để đáp ứng yêu cầu kiểm duyệt ngay lập tức.

🧩 Tổng kết & Gợi ý kiến trúc thực tế (AWS)

Sơ đồ luồng dữ liệu

User request → Lambda (or SageMaker endpoint) → Generate image → Amazon Rekognition DetectModerationLabels →

Nếu có nhãn “inappropriate” → trả về thông báo lỗi/ảnh mặc định.

Nếu “clean” → trả về ảnh cho người dùng.

Các thành phần AWS liên quan (2026)

Amazon Rekognition (moderation API) – luôn được cập nhật nhãn mới.

Amazon Bedrock – tích hợp sẵn “content‑moderation” cho các mô hình sinh ảnh như Stable Diffusion.

AWS Lambda – xử lý logic quyết định (allow/deny).

Amazon CloudWatch + AWS X‑Ray – giám sát tỉ lệ ảnh bị chặn, giúp cải thiện mô hình trong tương lai.

AWS IAM – quyền hạn hạn chế để chỉ các service có quyền gọi moderation API.

Thực hành DevOps

IaC (Infrastructure as Code): dùng AWS CloudFormation hoặc Terraform để tự động triển khai pipeline moderation.

CI/CD: tích hợp kiểm thử tự động (SageMaker Model Monitor) để phát hiện drift, nhưng đừng quên moderation API ở runtime.

Observability: CloudWatch Alarms khi tỉ lệ ảnh bị chặn vượt ngưỡng cho phép → trigger rollback hoặc model retraining.

📚 Tham khảo thêm

Amazon Rekognition – DetectModerationLabels (2026 cập nhật): https://docs.aws.amazon.com/rekognition/latest/dg/moderation.html

Amazon Bedrock – Content Moderation (released 2025, nâng cấp 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/content-moderation.html

Best Practices for Content Moderation on AWS – AWS Whitepaper (2025).

Kết luận: Để đáp ứng yêu cầu “không trả về hình ảnh không phù hợp” trong thời gian thực, cách hiệu quả nhất là triển khai các moderation APIs của AWS, đồng thời có thể kết hợp với các thành phần DevOps để tự động hoá, giám sát và nâng cấp liên tục. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150996-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/rekognition/latest/dg/moderation.html

## Câu 15

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon S3
- Đáp án tham khảo: **Benchmark datasets**
- Takeaway nhanh: Một công ty mạng xã hội muốn áp dụng một mô hình ngôn ngữ lớn (LLM) để hỗ trợ công việc moderation nội dung. Trước khi đưa vào vận hành, họ cần kiểm tra xem đầu ra của mô hình có độ thiên (bias) và khả năng phân biệt đối xử (discrimination) đối với các nhóm hoặc cá nhân nào không. Yêu cầu của câu hỏi: “Which data source should the company use to evaluate the LLM outputs with the LEAST administrative effort?” → Công ty muốn giảm thiểu công sức quản trị (thu thập, chuẩn bị, duy trì dữ liệu) khi thực hiện việc đánh giá này.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150827-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A social media company wants to use a large language model (LLM) for content moderation. The company wants to evaluate the LLM outputs for bias and potential discrimination against specific groups or individuals. Which data source should the company use to evaluate the LLM outputs with the LEAST administrative effort?

### Các lựa chọn
1. User-generated content
2. Moderation logs
3. Content moderation guidelines
4. Benchmark datasets

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Một công ty mạng xã hội muốn áp dụng một mô hình ngôn ngữ lớn (LLM) để hỗ trợ công việc moderation nội dung. Trước khi đưa vào vận hành, họ cần kiểm tra xem đầu ra của mô hình có độ thiên (bias) và khả năng phân biệt đối xử (discrimination) đối với các nhóm hoặc cá nhân nào không. Yêu cầu của câu hỏi: “Which data source should the company use to evaluate the LLM outputs with the LEAST administrative effort?” → Công ty muốn giảm thiểu công sức quản trị (thu thập, chuẩn bị, duy trì dữ liệu) khi thực hiện việc đánh giá này.

✅ Đáp án đúng: Benchmark datasets

Lý do chọn:

Các benchmark datasets (bộ dữ liệu chuẩn) đã được cộng đồng nghiên cứu và các nhà cung cấp dịch vụ AI (ví dụ: GLUE, SuperGLUE, WinoBias, StereoSet, HolisticBias, etc.) biên soạn sẵn, có định dạng chuẩn, được gắn nhãn rõ ràng về các khía cạnh nhạy cảm (giới tính, chủng tộc, tuổi tác, …).

Người dùng chỉ cần tải xuống (thường qua S3, Hugging Face Hub, hoặc AWS Data Exchange) và đưa vào pipeline SageMaker để chạy inference và tính các metric (bias score, fairness metrics).

Không cần thu thập hay gán nhãn dữ liệu nội bộ, không phải thiết lập quy trình thu thập liên tục, vì dữ liệu đã sẵn sàng và được đánh giá bởi cộng đồng.

Do vậy, công sức quản trị (administrative effort) là tối thiểu so với các lựa chọn khác.

🧩 Phân tích các phương án (giữ nguyên nội dung tiếng Anh)

- User-generated content

Giải thích: Dữ liệu do người dùng tạo ra (post, comment, tweet…) là đại diện thực tế nhưng không có nhãn về nhóm bảo vệ hay các tiêu chí bias. Để sử dụng làm bộ đánh giá, công ty phải thu thập, làm sạch, gán nhãn (ví dụ: xác định nhóm người dùng, nội dung nhạy cảm). Quá trình này tốn nhiều công sức quản trị, cần tuân thủ chính sách bảo mật, GDPR, v.v.

✅ Kết luận: Không phải là lựa chọn ít công sức nhất → sai.

- Moderation logs

Giải thích: Log moderation chứa kết quả quyết định (đã chặn, đã cho phép) và các lý do. Mặc dù có thể cung cấp phản hồi thực tế về cách mô hình tương tác với nội dung, nhưng log này không phải là dữ liệu gốc để đo bias; chúng đã qua xử lý và có thể bị thiên lệch theo quy tắc nội bộ. Để dùng làm bộ kiểm tra bias, cần đánh giá lại từng log, gán nhãn lại, và duy trì hệ thống log liên tục → công sức quản trị cao.

✅ Kết luận: Không đáp ứng yêu cầu “least administrative effort” → sai.

- Content moderation guidelines

Giải thích: Các hướng dẫn (guidelines) là tài liệu mô tả quy tắc, tiêu chuẩn và chính sách moderation (ví dụ: “không cho phép ngôn ngữ thù địch”). Chúng là định dạng văn bản mô tả quy tắc, không phải dữ liệu đầu vào/đầu ra để đo độ thiên. Để biến chúng thành bộ dữ liệu đánh giá, cần chuyển đổi sang câu hỏi, câu trả lời, gán nhãn – công việc tốn thời gian và đòi hỏi kiến trúc pipeline phức tạp.

✅ Kết luận: Không phải là nguồn dữ liệu sẵn sàng, công sức lớn → sai.

- Benchmark datasets

Giải thích: Như đã nêu ở phần đáp án đúng, các bộ dữ liệu chuẩn đã được công bố rộng rãi, được gán nhãn (bias, toxicity, protected attributes) và có tài liệu hướng dẫn cách tính các metric liên quan. Chúng có thể được truy cập qua AWS Data Exchange, SageMaker Ground Truth (để tải xuống) hoặc Hugging Face Hub. Việc tích hợp vào quy trình CI/CD (ví dụ: chạy batch inference trên SageMaker Processing) chỉ cần vài dòng script, do đó công sức quản trị là tối thiểu.

🛠️ Gợi ý cách triển khai trên AWS (đến 2026)

Lưu trữ dataset: Dùng Amazon S3 để lưu các benchmark datasets, hoặc trực tiếp import từ AWS Data Exchange (có sẵn các dataset như “Hate Speech and Offensive Language”).

Xử lý & inference: Dùng Amazon SageMaker Processing Jobs hoặc Batch Transform để đưa LLM (được triển khai trên SageMaker Endpoints) chạy trên toàn bộ dataset.

Đánh giá bias: Sử dụng SageMaker Clarify (tính năng mới nhất 2026) để tự động tính các fairness metrics (demographic parity, equalized odds) dựa trên các protected attributes có trong benchmark dataset.

CI/CD tích hợp: Thêm bước kiểm tra bias vào pipeline AWS CodePipeline → mỗi lần deploy LLM mới, pipeline sẽ chạy benchmark và báo cáo nếu vượt ngưỡng cho phép.

📚 Tham khảo nguồn tài liệu

AWS SageMaker Clarify Documentation (2026) – Hướng dẫn sử dụng Clarify để đo bias trên mô hình LLM.

AWS Data Exchange – Public Datasets – Danh sách các benchmark datasets có sẵn cho việc đánh giá fairness.

“HolisticBias: A Suite of Datasets for Measuring Bias in LLMs”, arXiv 2025 – Một bộ dữ liệu chuẩn mới được cộng đồng chấp nhận.

AWS Well‑Architected Framework – Security Pillar (2026) – Đề cập tới việc bảo vệ dữ liệu người dùng khi thu thập log và UGC.

🎯 Kết luận ngắn gọn

Câu hỏi yêu cầu chọn nguồn dữ liệu có công sức quản trị thấp nhất để đánh giá bias của LLM.

Benchmark datasets là lựa chọn đúng vì chúng đã được tiền xử lý, gán nhãn, và chuẩn hoá, cho phép triển khai nhanh trên các dịch vụ AWS (S3, SageMaker, Clarify) mà không cần công việc thu thập hoặc gán nhãn lại.

✅ Đáp án: Benchmark datasets.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150827-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 16

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, RAG
- Takeaway nhanh: 🟢 Create an Amazon Bedrock knowledge base.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/compute/retrieval-augmented-generation-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html | https://docs.aws.amazon.com/bedrock/latest/userguide/titan-model.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ai-data-protection.html | https://www.examtopics.com/discussions/amazon/view/151094-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is implementing the Amazon Titan foundation model (FM) by using Amazon Bedrock. The company needs to supplement the model by using relevant data from the company's private data sources. Which solution will meet this requirement?

### Các lựa chọn
1. Use a different FM.
2. Choose a lower temperature value.
3. Create an Amazon Bedrock knowledge base.
4. Enable model invocation logging.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đang triển khai Amazon Titan foundation model (FM) thông qua Amazon Bedrock và muốn “bổ sung” mô hình bằng dữ liệu riêng của mình (private data sources).

Nói cách khác, công ty cần một cơ chế tích hợp dữ liệu nội bộ vào quá trình tạo câu trả lời của mô hình, sao cho mô hình có thể “tra cứu” hoặc “kết hợp” thông tin riêng khi trả lời (kiểu retrieval‑augmented generation – RAG).

Trong bộ tính năng mới của Amazon Bedrock (cập nhật tới 2026), tính năng đáp ứng nhu cầu này là Bedrock Knowledge Base:

Cho phép bạn đưa dữ liệu riêng (tài liệu, cơ sở dữ liệu, S3, RDS, hoặc nguồn dữ liệu qua API) vào một vector store.

Khi gọi mô hình, Bedrock sẽ tự động thực hiện retrieval trên knowledge base và đưa ngữ cảnh vào prompt, giúp mô hình trả lời dựa trên dữ liệu nội bộ.

Vì vậy, giải pháp đúng là tạo một Amazon Bedrock knowledge base.

✅ Đáp án đúng

🟢 Create an Amazon Bedrock knowledge base.

Giải thích: Knowledge base cung cấp khả năng “tăng cường” (augment) mô hình bằng cách kết hợp dữ liệu riêng trong quá trình inference, đáp ứng yêu cầu “supplement the model by using relevant data from the company's private data sources”.

❌ Giải thích các phương án sai

🛑 Use a different FM.

Thay đổi foundation model không giải quyết vấn đề “kết hợp dữ liệu riêng”. Titan đã hỗ trợ RAG thông qua knowledge base, vì vậy không cần chuyển sang mô hình khác.

🛑 Choose a lower temperature value.

Temperature chỉ điều khiển mức độ ngẫu nhiên/độ sáng tạo của đầu ra (giá trị cao → đa dạng, giá trị thấp → ổn định). Nó không ảnh hưởng tới việc mô hình truy cập hoặc sử dụng dữ liệu nội bộ.

🛑 Enable model invocation logging.

Logging chỉ ghi lại các lần gọi mô hình (để audit, debug, billing). Nó không cung cấp bất kỳ cơ chế nào để đưa dữ liệu riêng vào prompt hay cải thiện kiến thức của mô hình.

🧩 Các khái niệm liên quan (cập nhật tới 2026)

Amazon Bedrock Knowledge Base

Tích hợp Amazon OpenSearch Serverless hoặc Amazon Aurora Serverless làm vector store.

Hỗ trợ RAG với các mô hình Bedrock (Titan, Claude, Llama 2, …).

Cho phép fine‑tuning (trong một số trường hợp) và metadata filtering để lấy dữ liệu chính xác.

Retrieval‑Augmented Generation (RAG)

Kỹ thuật kết hợp search (tìm kiếm tài liệu) và generation (sinh câu trả lời) để cung cấp thông tin cập nhật, chính xác hơn.

Model temperature

Tham số temperature nằm trong khoảng 0‑1 (hoặc 0‑2 tùy model). Không liên quan tới nguồn dữ liệu.

Model invocation logging

Được bật qua AWS CloudTrail hoặc Amazon CloudWatch để ghi lại requestId, prompt, response, nhưng không thay đổi cách mô hình “hiểu” dữ liệu.

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide – Knowledge Bases (phiên bản 2026‑03)

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html

Amazon Titan Model – Best Practices (2025‑12)

https://docs.aws.amazon.com/bedrock/latest/userguide/titan-model.html

Retrieval‑Augmented Generation (RAG) on Amazon Bedrock – Blog post, AWS Compute Blog, 2024‑11

https://aws.amazon.com/blogs/compute/retrieval-augmented-generation-bedrock/

AWS Well‑Architected Framework – Security Pillar – phần “Data protection for generative AI” (2025)

https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ai-data-protection.html

📌 Kết luận nhanh

Câu trả lời đúng: Create an Amazon Bedrock knowledge base.

Các tùy chọn còn lại đều không đáp ứng yêu cầu “kết hợp dữ liệu riêng” và vì vậy là sai.

Hy vọng phân tích chi tiết này giúp bạn nắm rõ cách lựa chọn giải pháp phù hợp trong môi trường AWS Bedrock! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151094-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 17

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker
- Đáp án tham khảo: **Use transfer learning.**
- Takeaway nhanh: ✅ Use transfer learning. AWS cập nhật đến năm 2026 cung cấp: SageMaker JumpStart: bộ sưu tập các mô hình pre‑trained (ResNet, BERT, etc.) có thể được fine‑tune ngay trong Studio. SageMaker Pipelines: tích hợp transfer learning trong workflow CI/CD cho ML.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/transfer-learning-sagemaker-best-practices/ | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-transfer-learning.html | https://docs.aws.amazon.com/sagemaker/latest/dg/training-job.html#training-job-transfer-learning | https://www.examtopics.com/discussions/amazon/view/150727-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using domain-specific models. The company wants to avoid creating new models from the beginning. The company instead wants to adapt pre-trained models to create models for new, related tasks. Which ML strategy meets these requirements?

### Các lựa chọn
1. Increase the number of epochs.
2. Use transfer learning.
3. Decrease the number of epochs.
4. Use unsupervised learning.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích câu hỏi

Công ty đã có sẵn domain‑specific models (các mô hình được huấn luyện cho một lĩnh vực cụ thể).

Thay vì xây dựng mô hình mới từ đầu, họ muốn tận dụng các mô hình đã được huấn luyện trước (pre‑trained) và “điều chỉnh” (fine‑tune) chúng để thực hiện các nhiệm vụ mới nhưng liên quan đến nhau.

Yêu cầu này mô tả chiến lược học máy mà cho phép:

Sử dụng kiến thức đã học được từ một tập dữ liệu lớn (hoặc từ một domain) → giảm thời gian và chi phí huấn luyện.

Chỉ cần “điều chỉnh” một phần của mô hình (thường là các lớp cuối) cho nhiệm vụ mới.

Trong AWS, cách thực hiện phổ biến nhất là Transfer Learning – được hỗ trợ qua Amazon SageMaker (JumpStart, SageMaker Studio, SageMaker Training jobs với --transfer-learning flag, v.v.).

✅ Đáp án đúng

✅ Use transfer learning.

Lý do: Transfer learning chính là việc chuyển kiến thức từ một mô hình đã học (pre‑trained) sang một nhiệm vụ mới, thường bằng cách đóng băng một số lớp và huấn luyện lại (fine‑tune) các lớp cuối trên dữ liệu mới. Điều này đáp ứng đúng yêu cầu “adapt pre‑trained models to create models for new, related tasks” mà câu hỏi đưa ra.

AWS cập nhật đến năm 2026 cung cấp:

SageMaker JumpStart: bộ sưu tập các mô hình pre‑trained (ResNet, BERT, etc.) có thể được fine‑tune ngay trong Studio.

SageMaker Pipelines: tích hợp transfer learning trong workflow CI/CD cho ML.

SageMaker Training với --transfer-learning cho phép chỉ định source_model_arn và target_dataset.

❌ Giải thích các phương án sai

❌ Increase the number of epochs.

Giải thích: Tăng số epoch chỉ làm cho mô hình tiếp tục học lâu hơn trên cùng một tập dữ liệu và kiến trúc hiện tại. Nó không thay đổi việc sử dụng mô hình đã được huấn luyện trước, cũng không giúp “adapt” mô hình cho một nhiệm vụ mới. Thậm chí, nếu dữ liệu mới ít, việc tăng epoch có thể dẫn tới over‑fitting.

❌ Decrease the number of epochs.

Giải thích: Giảm số epoch làm cho quá trình huấn luyện ngắn hơn, nhưng tương tự như trên, nó không tạo ra khả năng tái sử dụng mô hình đã có cho nhiệm vụ mới. Việc giảm epoch chỉ làm giảm độ hội tụ, có thể gây under‑fitting.

❌ Use unsupervised learning.

Giải thích: Học không giám sát (unsupervised) tập trung vào việc khám phá cấu trúc tiềm ẩn của dữ liệu mà không có nhãn. Trong trường hợp công ty muốn điều chỉnh một mô hình đã được huấn luyện cho một task mới có nhãn (ví dụ: phân loại, dự đoán), phương pháp này không đáp ứng yêu cầu. Transfer learning thường dựa vào học có giám sát (supervised fine‑tuning) hoặc semi‑supervised khi nhãn hạn chế, chứ không phải unsupervised.

📚 Tham khảo tài liệu AWS (cập nhật 2026)

Amazon SageMaker JumpStart – Transfer Learning: https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-transfer-learning.html

SageMaker Training Job – Transfer Learning Parameters: https://docs.aws.amazon.com/sagemaker/latest/dg/training-job.html#training-job-transfer-learning

Best Practices for Transfer Learning on SageMaker (AWS Blog, 2025): https://aws.amazon.com/blogs/machine-learning/transfer-learning-sagemaker-best-practices/

AWS Well‑Architected Framework for Machine Learning (2024 edition): phần Cost Optimization nhấn mạnh việc sử dụng pre‑trained models để giảm chi phí và thời gian triển khai.

🔚 Tóm tắt:

Chiến lược phù hợp với yêu cầu “adapt pre‑trained models to create models for new, related tasks” là Transfer Learning. Các phương án “increase/decrease epochs” và “unsupervised learning” không đáp ứng mục tiêu tái sử dụng mô hình đã được huấn luyện, vì vậy chúng là sai. ✅🧠

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150727-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 18

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon S3
- Đáp án tham khảo: **Batch Transform – ✅ Phù hợp với dữ liệu GBs, không cần latency, chi phí chỉ khi job chạy.**
- Takeaway nhanh: Công ty muốn xây dựng một mô hình Machine Learning để phân tích dữ liệu lưu trữ (archived data). Dữ liệu cần dự đoán rất lớn, tới hàng GB. Công ty không yêu cầu nhận kết quả ngay lập tức (không cần latency thấp). Yêu cầu này gợi ý chúng ta cần một phương thức inference dạng batch/off‑line, cho phép đưa một khối lượng dữ liệu lớn vào và lưu kết quả ra Amazon S3 mà không cần duy trì một endpoint luôn bật.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/async-inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html | https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html | https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html | https://www.examtopics.com/discussions/amazon/view/151124-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building an ML model to analyze archived data. The company must perform inference on large datasets that are multiple GBs in size. The company does not need to access the model predictions immediately. Which Amazon SageMaker inference option will meet these requirements?

### Các lựa chọn
1. Batch transform
2. Real-time inference
3. Serverless inference
4. Asynchronous inference

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn xây dựng một mô hình Machine Learning để phân tích dữ liệu lưu trữ (archived data).

Dữ liệu cần dự đoán rất lớn, tới hàng GB.

Công ty không yêu cầu nhận kết quả ngay lập tức (không cần latency thấp).

Yêu cầu này gợi ý chúng ta cần một phương thức inference dạng batch/off‑line, cho phép đưa một khối lượng dữ liệu lớn vào và lưu kết quả ra Amazon S3 mà không cần duy trì một endpoint luôn bật.

✅ Đáp án đúng

🔹 Batch Transform

Batch Transform là dịch vụ của Amazon SageMaker cho phép chạy inference trên tập dữ liệu lớn được lưu trữ trong S3.

Không cần endpoint luôn chạy → chi phí chỉ phát sinh khi công việc thực thi.

Hỗ trợ dữ liệu lên tới terabytes; SageMaker sẽ tự động phân chia công việc thành các job và thực thi trên các instance phù hợp.

Kết quả được ghi lại vào S3, phù hợp với yêu cầu “không cần truy cập dự đoán ngay lập tức”.

Do đó, Batch Transform đáp ứng đầy đủ cả hai tiêu chí: dữ liệu lớn và không cần trả lời thời gian thực.

❌ Giải thích các phương án sai

1️⃣ Real-time inference

Mô tả: Triển khai một endpoint luôn bật, nhận yêu cầu và trả về dự đoán trong mili giây – giây.

Tại sao sai:

Thiết kế cho độ trễ thấp, không phù hợp với khối lượng dữ liệu GBs vì mỗi request thường chỉ chứa một mẫu (hoặc vài mẫu).

Cần duy trì instance liên tục → chi phí cao khi chỉ thực hiện inference một lần cho một dataset lớn.

Không hỗ trợ ingest dữ liệu batch từ S3 trực tiếp.

2️⃣ Serverless inference

Mô tả: Kiểu endpoint “pay‑as‑you‑go” không cần quản lý instance; tự động mở/đóng dựa trên lưu lượng.

Tại sao sai:

Cũng là inference thời gian thực (latency dưới vài giây).

Giới hạn kích thước payload tối đa 10 MB (request) và 5 MB (response) (theo tài liệu 2026), nên không thể xử lý dữ liệu GBs trong một request.

Không phù hợp cho công việc batch/off‑line.

3️⃣ Asynchronous inference

Mô tả: Endpoint nhận request lớn, trả về URL để lấy kết quả sau; phù hợp cho workload có độ trễ chấp nhận được.

Tại sao sai (đối với yêu cầu này):

Hỗ trợ payload lên tới 100 MB (đã tăng so với real‑time nhưng vẫn còn xa so với “multiple GB”).

Vẫn dựa trên endpoint và tính phí theo thời gian hoạt động của endpoint, không tối ưu cho việc xử lý tập tin GBs toàn bộ một lần.

Khi muốn dự đoán trên tổng dataset hàng GB, cách tiếp cận chuẩn vẫn là Batch Transform.

📚 Tham khảo tài liệu (AWS, cập nhật tới 2026)

Amazon SageMaker Batch Transform – https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html

Real‑time Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html

Serverless Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html

Asynchronous Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/async-inference.html

🧩 Tóm tắt nhanh

✅ Batch Transform – ✅ Phù hợp với dữ liệu GBs, không cần latency, chi phí chỉ khi job chạy.

❌ Real‑time inference – ❌ Thiết kế cho latency thấp, không xử lý batch lớn.

❌ Serverless inference – ❌ Giới hạn kích thước request, vẫn thời gian thực.

❌ Asynchronous inference – ❌ Hạn chế kích thước payload (100 MB) và vẫn yêu cầu endpoint.

Với yêu cầu “phân tích dữ liệu archive nhiều GB, không cần kết quả ngay lập tức”, Batch Transform là lựa chọn đúng nhất. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151124-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html

## Câu 19

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Bedrock, prompt engineering, RAG
- Takeaway nhanh: - Adjust the prompt. Vì sao? Prompt engineering cho phép chúng ta đưa các chỉ dẫn cụ thể như: “Viết câu trả lời trong tối đa 2 câu.”
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150691-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using a pre-trained large language model (LLM) to build a chatbot for product recommendations. The company needs the LLM outputs to be short and written in a specific language. Which solution will align the LLM response quality with the company's expectations?

### Các lựa chọn
1. Adjust the prompt.
2. Choose an LLM of a different size.
3. Increase the temperature.
4. Increase the Top K value.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Phân tích câu hỏi

Bối cảnh: Công ty đã có một mô hình ngôn ngữ lớn (LLM) đã được huấn luyện sẵn và đang dùng nó để tạo chatbot đề xuất sản phẩm.

Yêu cầu: Kết quả (output) của LLM phải ngắn gọn và được viết bằng một ngôn ngữ cụ thể (ví dụ: tiếng Việt, tiếng Nhật …).

Mục tiêu: Tìm cách “điều chỉnh chất lượng phản hồi” sao cho đáp ứng đúng yêu cầu mà không cần thay đổi mô hình, không cần tái huấn luyện lại.

Trong môi trường AWS, khách hàng thường dùng Amazon Bedrock hoặc SageMaker JumpStart để truy cập các LLM (Claude, Llama 2, Titan …). Các tham số như temperature, Top‑K, model size ảnh hưởng đến độ đa dạng và độ “độ ngẫu nhiên” của đáp án, nhưng không trực tiếp kiểm soát độ dài hay ngôn ngữ đầu ra.

✅ Giải pháp thực tiễn nhất: Adjust the prompt – tức là thay đổi cách viết lời nhắc (prompt) để chỉ định rõ ràng độ dài và ngôn ngữ mong muốn. Prompt engineering là kỹ thuật chuẩn trong việc “tùy chỉnh” hành vi của LLM mà không cần thay đổi mô hình.

✅ Đáp án đúng

- Adjust the prompt.

Vì sao?

Prompt engineering cho phép chúng ta đưa các chỉ dẫn cụ thể như:

“Viết câu trả lời trong tối đa 2 câu.”

“Sử dụng tiếng Việt cho mọi phản hồi.”

Trong Amazon Bedrock, chúng ta có thể truyền system prompt (được gọi là “instruction”) để định hướng toàn bộ cuộc hội thoại.

Khi chúng ta chỉ định độ dài và ngôn ngữ trong prompt, mô hình sẽ cố gắng tuân thủ các yêu cầu đó mà không cần thay đổi bất kỳ siêu tham số nào.

Đây là cách nhanh nhất, chi phí thấp nhất và không cần tái huấn luyện hay chuyển đổi model.

❌ Giải thích các phương án sai

1. Choose an LLM of a different size.

Giải thích: Thay đổi kích thước (size) của mô hình (ví dụ: từ 7B → 13B) ảnh hưởng tới khả năng hiểu ngữ cảnh và độ chính xác, nhưng không bảo đảm rằng kết quả sẽ ngắn hơn hay bằng một ngôn ngữ cụ thể.

Thực tế AWS: Amazon Bedrock cho phép lựa chọn model size, nhưng việc chọn model “nhỏ hơn” chỉ giảm chi phí tính phí token, không kiểm soát độ dài đầu ra.

2. Increase the temperature.

Giải thích: Temperature điều chỉnh độ ngẫu nhiên của mô hình:

Giá trị cao (≥0.8) → kết quả đa dạng, ít lặp, nhưng không làm cho câu trả lời ngắn hơn.

Giá trị thấp (≤0.2) → phản hồi đồng nhất, nhưng vẫn có thể dài.

Mối quan hệ với yêu cầu: Nhiệt độ không quyết định ngôn ngữ hay độ dài, vì vậy tăng temperature không đáp ứng mục tiêu.

3. Increase the Top K value.

Giải thích: Top‑K (và Top‑P) kiểm soát các token được xem xét trong quá trình sinh. Giá trị cao hơn cho phép mô hình chọn từ một tập lớn hơn các token, làm tăng độ sáng tạo, nhưng không ép buộc mô hình tạo câu ngắn hoặc trong một ngôn ngữ nhất định.

Trong AWS: Các API của Bedrock cho phép truyền topK/topP trong request, nhưng chúng chỉ ảnh hưởng tới độ phong phú của văn bản, không phải độ dài hay ngôn ngữ.

🛠️ Cách thực hiện “Adjust the prompt” trên AWS (2026)

Sử dụng Amazon Bedrock – InvokeModel API

Code

{

"prompt": "Bạn là trợ lý bán hàng. Hãy đề xuất một sản phẩm phù hợp cho khách hàng, trả lời **trong tối đa 2 câu** và viết **bằng tiếng Việt**.",

"temperature": 0.3,

"maxTokens": 150,

"topP": 0.9

}

Kết hợp system và user prompt (định dạng chat) để luôn giữ “ngôn ngữ + độ dài” trong system prompt.

Kiểm thử A/B: Gửi cùng một query với prompt khác nhau, đo average token length và language detection (có thể dùng Amazon Comprehend để xác minh).

Tối ưu hoá: Nếu vẫn có trường hợp trả lời dài hơn, có thể bổ sung chỉ dẫn “Nếu câu trả lời dài hơn 2 câu, rút gọn ngay lập tức”.

📖 Tham khảo nguồn tài liệu

Amazon Bedrock Developer Guide (v2026.02) – phần Prompt Engineering và Control Parameters.

AWS Whitepaper “Best Practices for Using Large Language Models” (2025) – chương 3: “Guiding model behavior with prompts”.

OpenAI API Documentation (2026) – mặc dù không phải AWS, nhưng nguyên tắc temperature và top‑K được giải thích chi tiết, hỗ trợ so sánh.

Amazon Comprehend – Language Detection API – dùng để kiểm chứng rằng output thực sự ở ngôn ngữ mong muốn.

📌 Kết luận ngắn gọn

Để rút ngắn và định hướng ngôn ngữ cho output của LLM, điều chỉnh prompt là phương pháp chuẩn, nhanh, không tốn chi phí và phù hợp với mọi mô hình trên AWS.

Các lựa chọn khác (thay đổi kích thước model, tăng temperature, tăng Top‑K) không trực tiếp giải quyết yêu cầu về độ dài và ngôn ngữ, vì vậy chúng là sai.

💡 Tip: Khi triển khai thực tế, luôn ghi lại phiên bản prompt và các siêu tham số trong AWS CloudFormation hoặc Terraform để duy trì tính nhất quán và có thể rollback nếu cần.

Chúc bạn thành công trong việc tối ưu chatbot! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150691-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 20

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon Comprehend, Amazon SageMaker, Amazon S3
- Đáp án tham khảo: **Object detection**
- Takeaway nhanh: Câu hỏi yêu cầu một giải pháp tự động nhận diện và phân loại các loài động vật trong một kho ảnh mà không cần can thiệp của con người. Điều này thuộc về xử lý ảnh (computer vision): cần một mô hình có khả năng “nhìn” vào ảnh, xác định các đối tượng (động vật) và gán nhãn (loài, loại). Trong môi trường AWS, các dịch vụ thường được dùng cho nhu cầu này bao gồm:
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf | https://docs.aws.amazon.com/rekognition/latest/customlabels-dg/what-is.html | https://docs.aws.amazon.com/sagemaker/latest/dg/gt.html | https://docs.aws.amazon.com/sagemaker/latest/dg/object-detection.html | https://www.examtopics.com/discussions/amazon/view/150810-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner has a database of animal photos. The AI practitioner wants to automatically identify and categorize the animals in the photos without manual human effort. Which strategy meets these requirements?

### Các lựa chọn
1. Object detection
2. Anomaly detection
3. Named entity recognition
4. Inpainting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu một giải pháp tự động nhận diện và phân loại các loài động vật trong một kho ảnh mà không cần can thiệp của con người. Điều này thuộc về xử lý ảnh (computer vision): cần một mô hình có khả năng “nhìn” vào ảnh, xác định các đối tượng (động vật) và gán nhãn (loài, loại).

Trong môi trường AWS, các dịch vụ thường được dùng cho nhu cầu này bao gồm:

Amazon Rekognition – có sẵn các API Object & Scene Detection và Custom Labels cho phép phát hiện và gán nhãn các đối tượng trong ảnh.

Amazon SageMaker – có các thuật toán Object Detection (ví dụ: SSD, Faster‑RCNN) và tính năng Ground Truth để gán nhãn tự động.

Do đó, chiến lược cần chọn là Object detection – một kỹ thuật Machine Learning chuyên dùng để phát hiện vị trí (bounding box) và lớp (class) của các đối tượng trong ảnh.

✅ Đáp án đúng: Object detection

Lý do lựa chọn

Object detection cho phép xác định (detect) vị trí và phân loại (classify) các đối tượng trong ảnh, đúng với yêu cầu “identify and categorize the animals”.

Trên AWS, có thể triển khai nhanh bằng Amazon Rekognition Custom Labels hoặc SageMaker Object Detection mà không cần viết code phức tạp.

Hoạt động hoàn toàn tự động, không cần sự can thiệp của con người sau khi mô hình được huấn luyện.

🧩 Giải thích các phương án còn lại

Anomaly detection

❌ Anomaly detection (phát hiện bất thường) dùng để nhận diện các mẫu dữ liệu lệch so với xu hướng chung – ví dụ phát hiện giao dịch gian lận hoặc lỗi trong log.

👉 Trong bối cảnh ảnh động vật, nó chỉ có thể chỉ ra “ảnh nào khác biệt” mà không biết đó là loài gì. Vì vậy không đáp ứng yêu cầu nhận dạng & phân loại.

📘 Tham khảo: Amazon SageMaker Anomaly Detection

Named entity recognition

❌ Named Entity Recognition (NER) là kỹ thuật xử lý ngôn ngữ tự nhiên (NLP), dùng để nhận diện các thực thể (person, organization, location…) trong văn bản.

👉 Không áp dụng cho ảnh; không thể “nhìn” và “gán nhãn” các loài động vật.

📘 Tham khảo: Amazon Comprehend – Named Entity Recognition

Inpainting

❌ Inpainting là kỹ thuật tái tạo/điền đầy các vùng thiếu hoặc bị hỏng trong ảnh (hoặc video). Mục tiêu là khôi phục hình ảnh, không phải phát hiện hoặc phân loại đối tượng.

👉 Không liên quan tới việc nhận dạng các loài động vật.

📘 Tham khảo: Amazon SageMaker Image Inpainting Example

🛠️ Cách triển khai “Object detection” trên AWS (2026)

Amazon Rekognition – Custom Labels

Tải lên bộ dữ liệu ảnh và gán nhãn (loài động vật) bằng công cụ auto‑labeling hoặc manual labeling.

Rekognition tự động huấn luyện mô hình object detection và cung cấp API DetectCustomLabels.

Ưu điểm: không cần quản lý hạ tầng, thời gian triển khai nhanh (vài giờ).

Amazon SageMaker – Built‑in Algorithm

Sử dụng SageMaker Object Detection (với thuật toán SSD hoặc Faster‑RCNN) và Ground Truth để gán nhãn tự động.

Cho phép tùy chỉnh sâu (hyper‑parameter, kiến trúc) và mở rộng quy mô bằng SageMaker Training Jobs và Endpoints.

Ưu điểm: linh hoạt, kiểm soát tối đa, phù hợp với tập dữ liệu lớn và yêu cầu độ chính xác cao.

Pipeline tự động (AWS Step Functions + SageMaker Pipelines)

Xây dựng quy trình tự động: ingest → pre‑process → train → deploy → inference.

Dễ dàng tích hợp với Amazon S3 để lưu trữ ảnh, Amazon EventBridge để kích hoạt khi có ảnh mới.

📚 Tham khảo tài liệu

Amazon Rekognition Custom Labels – https://docs.aws.amazon.com/rekognition/latest/customlabels-dg/what-is.html

Amazon SageMaker Object Detection Algorithm – https://docs.aws.amazon.com/sagemaker/latest/dg/object-detection.html

Amazon SageMaker Ground Truth – https://docs.aws.amazon.com/sagemaker/latest/dg/gt.html

AWS Well‑Architected Framework – Machine Learning Lens (2025 update) – https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf

Tóm tắt:

✅ Object detection là chiến lược duy nhất đáp ứng yêu cầu tự động nhận diện và phân loại các loài động vật trong ảnh. Các lựa chọn còn lại (Anomaly detection, Named entity recognition, Inpainting) không phù hợp vì chúng giải quyết các vấn đề hoàn toàn khác (phát hiện bất thường, xử lý ngôn ngữ, phục hồi ảnh).

Hy vọng phân tích chi tiết này giúp bạn nắm rõ lý do lựa chọn và cách thực hiện trên AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150810-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 21

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Q, Amazon Q Developer, Amazon Bedrock, Amazon Lex
- Đáp án tham khảo: **Amazon Q Developer giúp công ty đạt mục tiêu bằng cách tạo đoạn mã, theo dõi tham chiếu và quản lý giấy phép nguồn mở. Các lựa chọn còn lại mô tả các dịch vụ AWS khác hoặc tính năng không tồn tại trong Q Developer, vì vậy chúng là sai. 🚀**
- Takeaway nhanh: - Create software snippets, reference tracking, and open source license tracking. Create software snippets: Amazon Q Developer có khả năng tạo ra các đoạn mã (code snippets) dựa trên mô tả ngôn ngữ tự nhiên của lập trình viên, giảm thời gian viết tay. Reference tracking: Dịch vụ tự động ghi lại các thư viện, API và tài nguyên mà đoạn mã sử dụng, giúp lập trình viên dễ dàng kiểm tra phụ thuộc và cập nhật.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150688-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use generative AI to increase developer productivity and software development. The company wants to use Amazon Q Developer. What can Amazon Q Developer do to help the company meet these requirements?

### Các lựa chọn
1. Create software snippets, reference tracking, and open source license tracking.
2. Run an application without provisioning or managing servers.
3. Enable voice commands for coding and providing natural language search.
4. Convert audio files to text documents by using ML models.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty muốn nâng cao năng suất của các nhà phát triển phần mềm bằng cách áp dụng generative AI. Công ty quyết định sử dụng Amazon Q Developer – một dịch vụ AI sinh mã mới (được ra mắt và cập nhật liên tục đến năm 2026) nhằm hỗ trợ lập trình viên trong quá trình viết code, tái sử dụng đoạn mã, quản lý giấy phép và các tài nguyên tham chiếu.

Yêu cầu thực tế: “What can Amazon Q Developer do to help the company meet these requirements?” – tức là cần xác định các khả năng chính của Amazon Q Developer mà đáp ứng nhu cầu “tăng năng suất lập trình và hỗ trợ phát triển phần mềm”.

✅ Đáp án đúng

- Create software snippets, reference tracking, and open source license tracking.

Lý do chọn:

Create software snippets: Amazon Q Developer có khả năng tạo ra các đoạn mã (code snippets) dựa trên mô tả ngôn ngữ tự nhiên của lập trình viên, giảm thời gian viết tay.

Reference tracking: Dịch vụ tự động ghi lại các thư viện, API và tài nguyên mà đoạn mã sử dụng, giúp lập trình viên dễ dàng kiểm tra phụ thuộc và cập nhật.

Open source license tracking: Q Developer tích hợp công cụ phân tích giấy phép nguồn mở (OSS) để xác định các rủi ro pháp lý khi sử dụng mã nguồn mở trong dự án, đáp ứng yêu cầu tuân thủ.

Các tính năng này chính là những điểm mạnh được AWS nhấn mạnh trong tài liệu Amazon Q Developer – Developer productivity with generative AI (cập nhật 2026) và đáp ứng đầy đủ “tăng năng suất” và “hỗ trợ phát triển phần mềm”.

❌ Giải thích các phương án sai

Run an application without provisioning or managing servers.

Giải thích: Đây là mô tả của AWS Lambda hoặc AWS Fargate, chứ không phải chức năng của Amazon Q Developer. Q Developer chỉ cung cấp trợ giúp viết code, không chịu trách nhiệm triển khai hoặc chạy ứng dụng.

Enable voice commands for coding and providing natural language search.

Giải thích: Mặc dù Amazon Q Developer hỗ trợ natural language prompts để sinh mã, nhưng không có tính năng điều khiển bằng giọng nói (voice commands). Tính năng này thuộc các sản phẩm như Amazon Bedrock + Amazon Polly hoặc Amazon Lex, không phải Q Developer.

Convert audio files to text documents by using ML models.

Giải thích: Chức năng chuyển đổi audio → text (speech‑to‑text) thuộc Amazon Transcribe. Q Developer không xử lý dữ liệu âm thanh; nó chỉ làm việc với văn bản và mã nguồn.

📚 Tham khảo nguồn tài liệu

Amazon Q Developer – Documentation (AWS, phiên bản cập nhật tháng 03/2026).

AWS re:Invent 2025 – “Boosting developer productivity with Amazon Q” (video và slide).

AWS Well‑Architected Framework – Developer Productivity Pillar (2025).

Tóm tắt:

✅ Amazon Q Developer giúp công ty đạt mục tiêu bằng cách tạo đoạn mã, theo dõi tham chiếu và quản lý giấy phép nguồn mở. Các lựa chọn còn lại mô tả các dịch vụ AWS khác hoặc tính năng không tồn tại trong Q Developer, vì vậy chúng là sai. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150688-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 22

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Batch, Amazon SageMaker, Amazon API Gateway, Amazon CloudFront, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Serverless Inference**
- Takeaway nhanh: Một công ty đã xây dựng một mô hình Machine Learning (ML) dùng để phân loại ảnh và muốn đưa mô hình này vào môi trường production để một ứng dụng web có thể gửi yêu cầu dự đoán (prediction). Yêu cầu quan trọng là không muốn quản lý hạ tầng (các server, cluster, auto‑scaling, patch, …). Vì vậy câu hỏi đang hỏi: Giải pháp nào của AWS cho phép “host” mô hình và trả kết quả dự đoán mà không cần người dùng phải lo về việc vận hành, cấu hình hạ tầng?
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html | https://www.examtopics.com/discussions/amazon/view/151095-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has developed an ML model for image classification. The company wants to deploy the model to production so that a web application can use the model. The company needs to implement a solution to host the model and serve predictions without managing any of the underlying infrastructure. Which solution will meet these requirements?

### Các lựa chọn
1. Use Amazon SageMaker Serverless Inference to deploy the model.
2. Use Amazon CloudFront to deploy the model.
3. Use Amazon API Gateway to host the model and serve predictions.
4. Use AWS Batch to host the model and serve predictions.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Giải thích nội dung câu hỏi

Một công ty đã xây dựng một mô hình Machine Learning (ML) dùng để phân loại ảnh và muốn đưa mô hình này vào môi trường production để một ứng dụng web có thể gửi yêu cầu dự đoán (prediction). Yêu cầu quan trọng là không muốn quản lý hạ tầng (các server, cluster, auto‑scaling, patch, …). Vì vậy câu hỏi đang hỏi: Giải pháp nào của AWS cho phép “host” mô hình và trả kết quả dự đoán mà không cần người dùng phải lo về việc vận hành, cấu hình hạ tầng?

✅ Đáp án đúng

- Use Amazon SageMaker Serverless Inference to deploy the model.

Vì sao đây là lựa chọn đúng?

SageMaker Serverless Inference là dịch vụ fully‑managed cho phép triển khai mô hình ML chỉ với việc tải mô hình lên và định nghĩa một endpoint.

Khi có request, service sẽ tự động khởi tạo tài nguyên tính toán cần thiết, thực hiện dự đoán và sau đó giải phóng tài nguyên. Người dùng không cần tạo hoặc quản lý EC2, autoscaling groups, hay container orchestration.

Chi phí tính theo số lần gọi và thời gian xử lý, phù hợp cho các workload không liên tục (spiky hoặc low‑traffic) – thường là trường hợp một web app gọi dự đoán khi người dùng tải ảnh.

Từ 2024‑2026, SageMaker Serverless Inference đã hỗ trợ các framework phổ biến (TensorFlow, PyTorch, MXNet, scikit‑learn) và các định dạng mô hình (ONNX, TorchScript, SavedModel).

Tích hợp sẵn với IAM, VPC, Amazon CloudWatch, AWS X‑Ray để giám sát và bảo mật – đáp ứng yêu cầu production mà không cần quản lý hạ tầng.

Tài liệu tham khảo:

AWS Documentation – Amazon SageMaker Serverless Inference (https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html)

AWS Blog – “Introducing Amazon SageMaker Serverless Inference” (2024)

❌ Giải thích các phương án sai

1. Use Amazon CloudFront to deploy the model.

CloudFront là một Content Delivery Network (CDN), mục đích chính là phân phối nội dung tĩnh (HTML, CSS, JS, hình ảnh, video) hoặc cache các response từ origin server.

Nó không có khả năng chạy mã ML hoặc host mô hình; chỉ có thể cache các API response nếu đã có một backend thực hiện inference.

Vì vậy, CloudFront không thỏa mãn yêu cầu “host model & serve predictions” và cũng không loại bỏ việc quản lý hạ tầng backend.

2. Use Amazon API Gateway to host the model and serve predictions.

API Gateway là dịch vụ định tuyến và bảo mật API (REST, HTTP, WebSocket). Nó cung cấp lớp front‑end cho các service backend (Lambda, ECS, EC2, …).

API Gateway không thực hiện tính toán; nó chỉ chuyển request tới một backend. Để chạy mô hình, bạn cần một service khác (VD: Lambda, SageMaker endpoint, EC2).

Nếu kết hợp với AWS Lambda, việc inference lớn sẽ bị giới hạn (thời gian thực thi tối đa 15 phút, bộ nhớ tối đa 10 GB) và không phù hợp cho mô hình hình ảnh nặng.

Vì vậy, tự mình “host” mô hình trên API Gateway là không khả thi và vẫn cần quản lý backend.

3. Use AWS Batch to host the model and serve predictions.

AWS Batch được thiết kế để chạy các công việc batch (độ trễ cao, không thời gian thực) như xử lý video, tính toán khoa học, hoặc job ETL.

Nó tạo job queues, compute environments và runs jobs trên EC2 hoặc Fargate.

Đối với dự đoán theo yêu cầu (real‑time inference) cho một web app, Batch không đáp ứng được yêu cầu latency thấp; còn phải quản lý job definition, queue, và thường mất vài giây đến phút để job khởi động.

Do đó, AWS Batch không phù hợp để “serve predictions” trong thời gian thực và vẫn đòi hỏi quản lý tài nguyên.

🧩 Tóm tắt nhanh (liệt kê)

✅ Amazon SageMaker Serverless Inference

Fully managed, không cần cấu hình/giám sát hạ tầng.

Tự động scaling dựa trên request, trả phí theo sử dụng.

Hỗ trợ đa framework, tích hợp IAM, VPC, CloudWatch.

❌ Amazon CloudFront

CDN, không thực thi mã ML.

Chỉ cache response từ origin, không “host” mô hình.

❌ Amazon API Gateway

Chỉ là lớp giao tiếp API, cần backend thực thi inference.

Không tự thực hiện tính toán, không phù hợp cho mô hình ảnh lớn.

❌ AWS Batch

Dành cho công việc batch, latency cao.

Không phù hợp cho request‑response real‑time và vẫn cần quản lý compute environment.

📌 Kết luận

Đối với yêu cầu “host the model and serve predictions without managing any underlying infrastructure”, Amazon SageMaker Serverless Inference là giải pháp duy nhất đáp ứng đầy đủ, vừa giảm thiểu công sức quản lý, vừa tối ưu chi phí và latency cho một web application cần dự đoán ảnh. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151095-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 23

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon S3, fine-tuning
- Đáp án tham khảo: **Cung cấp dữ liệu có nhãn, gồm prompt và completion → Đúng.**
- Takeaway nhanh: Công ty đang sử dụng foundation model (FM) trên Amazon Bedrock để xây dựng công cụ tìm kiếm AI. Muốn “fine‑tune” (tinh chỉnh) mô hình sao cho đáp ứng tốt hơn với dữ liệu nội bộ của mình. Câu hỏi hỏi: “Which strategy will successfully fine‑tune the model?” – tức là chúng ta cần chọn cách chuẩn bị và cung cấp dữ liệu (hoặc cấu hình dịch vụ) sao cho quá trình fine‑tuning trên Bedrock thành công.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/introducing-fine-tuning-on-amazon-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/devguide/finetuning.html | https://docs.aws.amazon.com/cli/latest/reference/bedrock/create-fine-tune-job.html | https://www.examtopics.com/discussions/amazon/view/150800-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses a foundation model (FM) from Amazon Bedrock for an AI search tool. The company wants to fine-tune the model to be more accurate by using the company's data. Which strategy will successfully fine-tune the model?

### Các lựa chọn
1. Provide labeled data with the prompt field and the completion field.
2. Prepare the training dataset by creating a .txt file that contains multiple lines in .csv format.
3. Purchase Provisioned Throughput for Amazon Bedrock.
4. Train the model on journals and textbooks.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang sử dụng foundation model (FM) trên Amazon Bedrock để xây dựng công cụ tìm kiếm AI. Muốn “fine‑tune” (tinh chỉnh) mô hình sao cho đáp ứng tốt hơn với dữ liệu nội bộ của mình.

Câu hỏi hỏi: “Which strategy will successfully fine‑tune the model?” – tức là chúng ta cần chọn cách chuẩn bị và cung cấp dữ liệu (hoặc cấu hình dịch vụ) sao cho quá trình fine‑tuning trên Bedrock thành công.

📌 Những yếu tố quan trọng về fine‑tuning trên Amazon Bedrock (đến năm 2026)

Bedrock hỗ trợ tinh chỉnh các foundation model của Amazon (Titan, Claude, Llama 2, …) thông qua API “CreateFineTuneJob”.

Dữ liệu đầu vào phải ở định dạng JSONL (mỗi dòng là một JSON object) chứa hai trường bắt buộc:

prompt – đoạn văn bản đưa vào mô hình (câu hỏi, mô tả, …).

completion – kết quả mong muốn (câu trả lời, nhãn, …).

Các trường này phải được gán nhãn (labeled) để mô hình học “prompt → completion”.

Không cần tạo file .txt dạng CSV; Bedrock sẽ không chấp nhận định dạng CSV hay plain‑text không có cấu trúc JSONL.

“Provisioned Throughput” là tính năng đối với inference (tốc độ đáp ứng) chứ không liên quan tới việc đào tạo hay fine‑tune.

Việc “train the model on journals and textbooks” không phải là chiến lược fine‑tune trong Bedrock; đó là pre‑training quy mô lớn, đòi hỏi hạ tầng và giấy phép khác, không được hỗ trợ trực tiếp qua API Bedrock.

Vì vậy, chiến lược đúng là cung cấp dữ liệu đã gán nhãn, bao gồm trường prompt và completion theo định dạng JSONL.

✅ Đáp án đúng

🔹 Provide labeled data with the prompt field and the completion field.

Lý do: Đây là định dạng chuẩn yêu cầu bởi API CreateFineTuneJob của Amazon Bedrock. Mỗi bản ghi JSON phải có prompt (đầu vào) và completion (đầu ra mong muốn). Khi dữ liệu được chuẩn bị như vậy, Bedrock sẽ tự động thực hiện quá trình fine‑tuning và tạo ra một model version mới, sẵn sàng cho inference.

❌ Các đáp án sai và giải thích

🔸 Prepare the training dataset by creating a .txt file that contains multiple lines in .csv format.

Sai vì: Bedrock không hỗ trợ file .txt hoặc .csv làm đầu vào cho fine‑tuning. Dữ liệu phải ở định dạng JSONL (mỗi dòng một JSON object). Định dạng CSV không chứa thông tin cấu trúc prompt/completion, vì vậy dịch vụ sẽ không nhận dạng được mục tiêu học.

🔸 Purchase Provisioned Throughput for Amazon Bedrock.

Sai vì: Provisioned Throughput là tùy chọn tăng tốc độ trả lời (inference) cho các endpoint đã triển khai, không có ảnh hưởng tới quá trình đào tạo hoặc fine‑tuning. Việc mua Provisioned Throughput không giúp mô hình học được dữ liệu mới.

🔸 Train the model on journals and textbooks.

Sai vì: Đề cập tới pre‑training trên nguồn dữ liệu quy mô lớn (journals, textbooks). Điều này không phải là fine‑tuning được hỗ trợ qua Bedrock và không đáp ứng yêu cầu “using the company's data”. Thêm vào đó, việc pre‑train trên tài liệu công cộng không được phép nếu không có quyền bản quyền và không được Bedrock cung cấp API cho việc này.

🛠️ Các bước thực hiện fine‑tune đúng (theo tài liệu Bedrock 2026)

Chuẩn bị dữ liệu

Định dạng JSONL. Ví dụ:

Code

{"prompt":"Câu hỏi: Tìm kiếm sản phẩm X", "completion":"Kết quả: Sản phẩm X có sẵn tại kho A"}

{"prompt":"Câu hỏi: Giá của dịch vụ Y", "completion":"Kết quả: 199 USD/tháng"}

Đảm bảo mỗi bản ghi được gán nhãn (có prompt và completion rõ ràng).

Upload dataset lên Amazon S3 (đường dẫn S3 phải có quyền đọc cho Bedrock).

Tạo job fine‑tune bằng AWS CLI, SDK hoặc Console:

Code

aws bedrock create-fine-tune-job \

--model-identifier "amazon.titan-text-v2:0" \

--training-data-config "S3Uri=s3://my-bucket/fine-tune-data.jsonl" \

--output-data-config "S3Uri=s3://my-bucket/output/"

Giám sát tiến độ qua AWS CloudWatch và AWS Step Functions (nếu cần orchestrate).

Khi job hoàn thành, đăng ký endpoint cho model đã fine‑tuned và (nếu muốn) đặt Provisioned Throughput để tối ưu latency.

📚 Tham khảo tài liệu (2026)

Amazon Bedrock Developer Guide – Fine‑tuning foundation models (phiên bản 2026‑03).

https://docs.aws.amazon.com/bedrock/latest/devguide/finetuning.html

AWS CLI Command Reference – create-fine-tune-job (phiên bản 2026).

https://docs.aws.amazon.com/cli/latest/reference/bedrock/create-fine-tune-job.html

AWS Blog – “Introducing Fine‑tuning on Amazon Bedrock” (2025‑11).

https://aws.amazon.com/blogs/aws/introducing-fine-tuning-on-amazon-bedrock/

🧩 Tóm tắt nhanh

✅ Cung cấp dữ liệu có nhãn, gồm prompt và completion → Đúng.

❌ File .txt CSV → Sai, không đúng định dạng.

❌ Mua Provisioned Throughput → Sai, chỉ liên quan tới inference.

❌ Train trên journals/textbooks → Sai, không phải fine‑tune và không dùng dữ liệu công ty.

Hy vọng phân tích trên giúp bạn nắm rõ cách “fine‑tune” mô hình trên Amazon Bedrock một cách chuẩn xác! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150800-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 24

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Personalize, Amazon SageMaker, Amazon Virtual Private Cloud, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Đáp án tham khảo: **Amazon SageMaker JumpStart**
- Takeaway nhanh: Câu hỏi hỏi: “Which AWS service or feature can help an AI development team quickly deploy and consume a foundation model (FM) within the team's VPC?” Foundation model (FM): mô hình ngôn ngữ lớn, mô hình thị giác, … đã được huấn luyện sẵn và có thể được fine‑tune hoặc dùng trực tiếp. Yêu cầu “quickly deploy and consume” → cần một công cụ cho phép tạo endpoint trong vài phút, không phải phải tự viết script triển khai toàn bộ.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://www.examtopics.com/discussions/amazon/view/150812-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which AWS service or feature can help an AI development team quickly deploy and consume a foundation model (FM) within the team's VPC?

### Các lựa chọn
1. Amazon Personalize
2. Amazon SageMaker JumpStart
3. PartyRock, an Amazon Bedrock Playground
4. Amazon SageMaker endpoints

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Câu hỏi hỏi: “Which AWS service or feature can help an AI development team quickly deploy and consume a foundation model (FM) within the team's VPC?”

Foundation model (FM): mô hình ngôn ngữ lớn, mô hình thị giác, … đã được huấn luyện sẵn và có thể được fine‑tune hoặc dùng trực tiếp.

Yêu cầu “quickly deploy and consume” → cần một công cụ cho phép tạo endpoint trong vài phút, không phải phải tự viết script triển khai toàn bộ.

Yêu cầu “within the team's VPC” → mô hình phải chạy trong VPC, tức là có thể gắn VPC endpoint / PrivateLink hoặc được khởi tạo trên SageMaker notebook/processing job mà có cấu hình VPC.

Vì vậy, câu trả lời phải là dịch vụ/đặc tính cho phép triển khai nhanh một foundation model và chạy trong VPC của khách hàng.

✅ Đáp án đúng: Amazon SageMaker JumpStart

SageMaker JumpStart cung cấp hàng chục foundation models (LLM, CV, audio…) đã được chuẩn bị sẵn, kèm script mẫu để tạo SageMaker endpoint chỉ trong vài cú click hoặc lệnh CLI.

Khi tạo endpoint, bạn có thể định cấu hình VPC (subnet, security groups) để model chạy trong VPC của bạn, đáp ứng yêu cầu “quickly deploy and consume … within the team's VPC”.

JumpStart còn hỗ trợ fine‑tuning nhanh chóng và tích hợp sẵn với SageMaker Pipelines, Feature Store, … giúp đội AI tập trung vào việc xây dựng ứng dụng chứ không phải hạ tầng.

📚 Nguồn tham khảo:

AWS Documentation – Amazon SageMaker JumpStart (phiên bản 2026) – https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

AWS Blog – “Deploy foundation models in seconds with SageMaker JumpStart” (2025)

❌ Giải thích các phương án sai

Amazon Personalize

Amazon Personalize là dịch vụ đề xuất (recommendation), giúp tạo mô hình cá nhân hoá dựa trên dữ liệu người dùng (ví dụ: sản phẩm gợi ý, video đề xuất).

Nó không cung cấp foundation models và không có tính năng “quickly deploy FM”.

Ngoài ra, Personalize chạy như một managed service và không cho phép cấu hình VPC để chạy mô hình trong VPC của bạn.

PartyRock, an Amazon Bedrock Playground

“PartyRock” không phải là một dịch vụ AWS chính thức; đây có thể là đề cập sai hoặc một tên giả tưởng.

Amazon Bedrock (đúng là dịch vụ quản lý foundation models) cho phép truy cập qua API nhưng không hỗ trợ triển khai trực tiếp trong VPC (các endpoint Bedrock hiện vẫn là public, hoặc qua PrivateLink chỉ cho phép kết nối mạng, không phải chạy model trong VPC).

Vì vậy, “PartyRock, an Amazon Bedrock Playground” không đáp ứng yêu cầu “quickly deploy … within VPC”.

Amazon SageMaker endpoints

SageMaker endpoints là cơ chế hosting cho mô hình đã được triển khai, nhưng không phải là tính năng giúp “quickly deploy” một foundation model.

Để có một endpoint, bạn cần chuẩn bị model, đóng gói, định nghĩa container, tạo training job, rồi mới tạo endpoint – quá trình này phức tạp hơn so với JumpStart.

Mặc dù endpoint có thể được cấu hình VPC, nhưng câu hỏi nhấn mạnh “quickly deploy and consume a FM”, nên JumpStart (cung cấp model + script tạo endpoint) là lựa chọn phù hợp hơn.

🧩 Tổng kết

Câu trả lời đúng: Amazon SageMaker JumpStart – cung cấp các foundation model đã chuẩn bị sẵn, cho phép tạo SageMaker endpoint trong VPC chỉ trong vài phút, đáp ứng đầy đủ yêu cầu của câu hỏi.

Các lựa chọn còn lại đều không cung cấp foundation model nhanh chóng trong VPC, hoặc không phải dịch vụ AWS thực tế.

💡 Mẹo thi: Khi câu hỏi đề cập “quickly deploy” và “within VPC”, hãy nghĩ tới SageMaker JumpStart (đã tích hợp sẵn VPC) và SageMaker Studio/Endpoints (cần cấu hình thủ công). Các dịch vụ như Bedrock vẫn là managed và không chạy trong VPC, còn Personalize phục vụ mục đích hoàn toàn khác.

🚀 Chúc bạn ôn luyện hiệu quả và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150812-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 25

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Kendra, RAG
- Takeaway nhanh: An AI practitioner wants to use a foundation model (FM) to design a search application. The search application must handle queries that have text and images. Which type of FM should the AI practitioner use to power the search application? Yêu cầu chức năng: Ứng dụng tìm kiếm cần hiểu và so sánh cả văn bản (text) và hình ảnh (image) trong một truy vấn. Nhiệm vụ chính của mô hình nền tảng: Chuyển đổi (embed) các đầu vào đa phương tiện (text + image) thành vector đại diện thống nhất để có thể tính độ tương đồng với tài liệu (cũng có thể là text, image hoặc cả hai) trong kho lưu trữ vector.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150631-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner wants to use a foundation model (FM) to design a search application. The search application must handle queries that have text and images. Which type of FM should the AI practitioner use to power the search application?

### Các lựa chọn
1. Multi-modal embedding model
2. Text embedding model
3. Multi-modal generation model
4. Image generation model

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

An AI practitioner wants to use a foundation model (FM) to design a search application. The search application must handle queries that have text and images. Which type of FM should the AI practitioner use to power the search application?

Yêu cầu chức năng: Ứng dụng tìm kiếm cần hiểu và so sánh cả văn bản (text) và hình ảnh (image) trong một truy vấn.

Nhiệm vụ chính của mô hình nền tảng: Chuyển đổi (embed) các đầu vào đa phương tiện (text + image) thành vector đại diện thống nhất để có thể tính độ tương đồng với tài liệu (cũng có thể là text, image hoặc cả hai) trong kho lưu trữ vector.

Loại mô hình phù hợp: Multi‑modal embedding model – mô hình tạo embedding cho nhiều modality (đa phương tiện) cùng lúc, cho phép so sánh trực tiếp giữa các loại dữ liệu.

✅ Đáp án đúng

- Multi-modal embedding model

Lý do lựa chọn

Embedding → chuyển đổi dữ liệu thô (text, image) thành vector trong không gian chung, thích hợp cho search/retrieval (so sánh cosine similarity, dot‑product, …).

Multi‑modal → mô hình được huấn luyện để đồng thời xử lý text + image và tạo ra một vector đại diện cho toàn bộ truy vấn, cho phép truy vấn đa phương tiện.

Trên AWS, các mô hình này có thể được triển khai qua Amazon Bedrock (ví dụ: Titan Multimodal Embedding, Cohere Multimodal Embedding, hoặc Meta LLaVA‑embedding phiên bản mới 2025) và lưu trữ vector trong Amazon OpenSearch Serverless hoặc Amazon DynamoDB + Amazon Kendra Vector Index để thực hiện tìm kiếm nhanh.

❌ Giải thích các phương án sai

Text embedding model

Mô tả: Chỉ tạo embedding cho văn bản. Khi truy vấn chứa hình ảnh, phần hình ảnh sẽ không được biểu diễn, dẫn tới mất thông tin quan trọng và chất lượng tìm kiếm giảm mạnh.

AWS context: Các model như Titan Text Embedding hoặc Cohere Text Embedding chỉ nhận đầu vào chuỗi ký tự; chúng không thể trực tiếp nhận hình ảnh.

Multi-modal generation model

Mô tả: Loại mô hình này được thiết kế để tạo ra nội dung (ví dụ: tạo ảnh từ mô tả văn bản, hoặc tạo mô tả văn bản cho ảnh). Nó không tập trung vào việc tạo vector đại diện để so sánh, mà tập trung vào output generation.

AWS context: Ví dụ Amazon Bedrock “Titan Multimodal Generation” hay Stable Diffusion (được hỗ trợ trên Bedrock) chuyên tạo ảnh, không phù hợp cho nhiệm vụ tìm kiếm.

Image generation model

Mô tả: Chỉ tạo hình ảnh mới dựa trên prompt (text) hoặc các điều kiện khác. Không thực hiện embedding và không hỗ trợ truy vấn kết hợp text‑image.

AWS context: Các model như Stable Diffusion, Midjourney‑style được cung cấp qua Bedrock là ví dụ điển hình. Chúng không giải quyết yêu cầu “search”.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Documentation – “Multimodal Embedding Models” (phiên bản cập nhật 2026).

AWS Whitepaper: “Building Retrieval‑Augmented Generation (RAG) and Vector Search on AWS” (2025).

Kendra Developer Guide – Using Vector Indexes (2026).

Meta LLaVA‑Embedding Model Release Note, 2025 – hỗ trợ text + image embedding.

Cohere Multimodal Embedding API Reference, cập nhật 2026.

🛠️ Gợi ý triển khai thực tế trên AWS

Chọn mô hình: Ví dụ Titan Multimodal Embedding từ Amazon Bedrock.

Xây dựng pipeline:

Input: Nhận query (text + image).

Embedding: Gọi API Bedrock InvokeModel để nhận vector embedding đa phương tiện.

Lưu trữ: Đưa vector vào Amazon OpenSearch Serverless với vector fields (kỹ thuật k‑NN).

Tìm kiếm: Sử dụng OpenSearch knn query để lấy tài liệu có similarity cao nhất.

Mở rộng: Kết hợp với Amazon Kendra để bổ sung khả năng tìm kiếm dựa trên metadata và tính năng RAG.

Tóm lại, để thiết kế một ứng dụng tìm kiếm chấp nhận truy vấn kết hợp text + image, Multi‑modal embedding model là lựa chọn đúng vì nó cung cấp vector biểu diễn thống nhất cho cả hai loại dữ liệu, cho phép thực hiện vector similarity search một cách hiệu quả trên hạ tầng AWS hiện đại. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150631-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 26

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon S3, prompt engineering, fine-tuning
- Takeaway nhanh: Một công ty muốn khai thác Large Language Models (LLMs) thông qua Amazon Bedrock để xây dựng giao diện chat cho các sổ hướng dẫn sản phẩm. Các hướng dẫn hiện đang ở dạng PDF. Yêu cầu là đáp ứng được nhu cầu (cung cấp ngữ cảnh cho mô hình khi người dùng hỏi) và chi phí phải tối ưu nhất. Do đó, chúng ta cần một cách đưa nội dung PDF vào “knowledge context” của Bedrock mà:
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/pricing/ | https://aws.amazon.com/blogs/architecture/best-practices-using-amazon-bedrock-with-external-data/ | https://d1.awsstatic.com/whitepapers/bedrock-fine-tuning.pdf | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases.html | https://docs.aws.amazon.com/opensearch-service/latest/developerguide/serverless.html | https://www.examtopics.com/discussions/amazon/view/151045-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use large language models (LLMs) with Amazon Bedrock to develop a chat interface for the company's product manuals. The manuals are stored as PDF files. Which solution meets these requirements MOST cost-effectively?

### Các lựa chọn
1. Use prompt engineering to add one PDF file as context to the user prompt when the prompt is submitted to Amazon Bedrock.
2. Use prompt engineering to add all the PDF files as context to the user prompt when the prompt is submitted to Amazon Bedrock.
3. Use all the PDF documents to fine-tune a model with Amazon Bedrock. Use the fine-tuned model to process user prompts.
4. Upload PDF documents to an Amazon Bedrock knowledge base. Use the knowledge base to provide context when users submit prompts to Amazon Bedrock.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty muốn khai thác Large Language Models (LLMs) thông qua Amazon Bedrock để xây dựng giao diện chat cho các sổ hướng dẫn sản phẩm.

Các hướng dẫn hiện đang ở dạng PDF. Yêu cầu là đáp ứng được nhu cầu (cung cấp ngữ cảnh cho mô hình khi người dùng hỏi) và chi phí phải tối ưu nhất.

Do đó, chúng ta cần một cách đưa nội dung PDF vào “knowledge context” của Bedrock mà:

Không tốn chi phí cao cho việc tái‑đào tạo (fine‑tune) hay gửi toàn bộ PDF mỗi lần.

Tận dụng các dịch vụ quản lý và tối ưu chi phí mà AWS cung cấp vào năm 2026 (ví dụ: Amazon Bedrock Knowledge Bases, Amazon OpenSearch Serverless, Amazon S3 + S3 Select, …).

✅ Đáp án đúng

📌 Upload PDF documents to an Amazon Bedrock knowledge base. Use the knowledge base to provide context when users submit prompts to Amazon Bedrock.

Lý do:

Amazon Bedrock Knowledge Bases (ra mắt 2023 và được mở rộng tính năng trong 2024‑2025) cho phép định chỉ mục và lưu trữ tài liệu (PDF, HTML, văn bản) trong Amazon OpenSearch Serverless và tích hợp trực tiếp với các model Bedrock.

Khi người dùng gửi prompt, Bedrock tự động truy vấn knowledge base để lấy các đoạn văn bản liên quan và đưa chúng vào ngữ cảnh (context) cho LLM, không cần truyền toàn bộ file mỗi lần.

Chi phí chỉ bao gồm lưu trữ tài liệu trên S3, chi phí truy vấn OpenSearch Serverless (theo số yêu cầu) và sử dụng inference của LLM – đây là cách tiết kiệm nhất so với việc gửi toàn bộ PDF hoặc fine‑tune model.

Knowledge Base còn hỗ trợ tự động cập nhật, quản lý phiên bản, bảo mật IAM và các policy (KMS encryption) nên phù hợp với môi trường doanh nghiệp.

❌ Giải thích các đáp án sai

1️⃣ Use prompt engineering to add one PDF file as context to the user prompt when the prompt is submitted to Amazon Bedrock.

Sai vì:

Prompt engineering chỉ hữu hiệu khi ngữ cảnh rất ngắn (≤ few‑kilobytes). Một file PDF (thậm chí một trang) thường có kích thước hàng trăm KB – MB. Khi đưa toàn bộ nội dung PDF vào prompt, chi phí token sẽ tăng mạnh và giới hạn token của model (max 4 k‑8 k tokens tùy model) sẽ bị vượt.

Mỗi lần người dùng gửi câu hỏi, toàn bộ PDF phải được truyền lại, làm tăng latency và chi phí inference (vì mỗi token được tính phí).

Không đáp ứng được yêu cầu chi phí tối ưu.

2️⃣ Use prompt engineering to add all the PDF files as context to the user prompt when the prompt is submitted to Amazon Bedrock.

Sai vì:

Tương tự đáp án trên, nhưng còn tệ hơn vì tất cả các PDF (có thể lên GB) sẽ được gộp vào một prompt duy nhất → không thể vượt qua giới hạn token và đánh mất hiệu suất.

Chi phí token và băng thông sẽ tăng vô hạn, làm cho giải pháp này không thực tế và cực kỳ tốn kém.

3️⃣ Use all the PDF documents to fine‑tune a model with Amazon Bedrock. Use the fine‑tuned model to process user prompts.

Sai vì:

Fine‑tuning LLM trên Bedrock hiện chỉ hỗ trợ một số mô hình nhất định (ví dụ Claude 2, Titan, Llama 2) và đòi hỏi dữ liệu huấn luyện ở dạng JSONL chứ không phải PDF thô.

Để fine‑tune, cần chuyển đổi PDF sang text, làm sạch, đánh dấu, tạo prompt‑completion pairs – công việc tốn thời gian và chi phí đáng kể.

Sau khi fine‑tune, mỗi inference vẫn phải trả phí cho token được sinh ra, và chi phí fine‑tune (điện toán, lưu trữ checkpoint) thường cao hơn so với việc chỉ tạo Knowledge Base.

Khi nội dung tài liệu thay đổi (cập nhật manual), cần đào tạo lại model → chi phí bảo trì lớn.

Vì vậy, không phải là giải pháp “most cost‑effective”.

📚 Tham khảo tài liệu (2026)

Amazon Bedrock Documentation – Knowledge Bases

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases.html (phiên bản cập nhật 2026)

Best practices for using Amazon Bedrock with external data – AWS Architecture Blog, 2025.

https://aws.amazon.com/blogs/architecture/best-practices-using-amazon-bedrock-with-external-data/

Pricing – Amazon Bedrock (điều chỉnh 2026)

https://aws.amazon.com/bedrock/pricing/

Amazon OpenSearch Serverless – Overview (2026)

https://docs.aws.amazon.com/opensearch-service/latest/developerguide/serverless.html

Fine‑tuning Large Language Models on Amazon Bedrock – Limits & Costs – AWS Whitepaper 2024 (cập nhật 2026).

https://d1.awsstatic.com/whitepapers/bedrock-fine-tuning.pdf

🛠️ Kết luận

Cách tối ưu nhất cho việc cung cấp ngữ cảnh từ PDF vào LLM trên Amazon Bedrock là tạo một Knowledge Base và để Bedrock tự truy vấn khi người dùng gửi prompt.

Các phương án “prompt engineering” và “fine‑tune” đều không đáp ứng được yêu cầu chi phí và quy mô trong thực tế, đặc biệt khi tài liệu có kích thước lớn và thay đổi thường xuyên.

🚀 Khuyến nghị thực tế:

Upload PDF lên Amazon S3 (với SSE‑KMS).

Tạo Knowledge Base trong Bedrock, trỏ tới bucket S3.

Cấu hình IAM role cho phép Bedrock đọc S3 và truy vấn OpenSearch.

Khi triển khai chat UI, gọi API InvokeModel và truyền knowledgeBaseId để Bedrock tự lấy context.

Với kiến trúc này, bạn đạt được tính năng đầy đủ, độ trễ thấp, và chi phí tối thiểu. 🎉

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151045-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 27

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, fine-tuning
- Đáp án tham khảo: **Ownership trung bình‑cao, nhưng vẫn chưa đạt mức tối đa vì phần lõi mô hình không do công ty tự sở hữu.**
- Takeaway nhanh: Công ty đang dùng Generative AI Security Scoping Matrix – một công cụ do AWS (và các nhà cung cấp AI) đưa ra để định mức “ownership” (sở hữu & trách nhiệm) về bảo mật trong các giải pháp AI sinh ra. Matrix này chia các giải pháp thành bốn phạm vi (scope), từ “sử dụng dịch vụ sẵn có của bên thứ ba” tới “tự xây dựng và huấn luyện mô hình AI từ đầu”. Câu hỏi: Trong bốn phạm vi trên, phạm vi nào đem lại cho công ty sở hữu (ownership) bảo mật cao nhất?
- Nguồn tham khảo trong block: https://aws.amazon.com/ai/generative-ai/security/scoping-matrix/ | https://www.examtopics.com/discussions/amazon/view/150809-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using the Generative AI Security Scoping Matrix to assess security responsibilities for its solutions. The company has identified four different solution scopes based on the matrix. Which solution scope gives the company the MOST ownership of security responsibilities?

### Các lựa chọn
1. Using a third-party enterprise application that has embedded generative AI features.
2. Building an application by using an existing third-party generative AI foundation model (FM).
3. Refining an existing third-party generative AI foundation model (FM) by fine-tuning the model by using data specific to the business.
4. Building and training a generative AI model from scratch by using specific data that a customer owns.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang dùng Generative AI Security Scoping Matrix – một công cụ do AWS (và các nhà cung cấp AI) đưa ra để định mức “ownership” (sở hữu & trách nhiệm) về bảo mật trong các giải pháp AI sinh ra.

Matrix này chia các giải pháp thành bốn phạm vi (scope), từ “sử dụng dịch vụ sẵn có của bên thứ ba” tới “tự xây dựng và huấn luyện mô hình AI từ đầu”.

Câu hỏi: Trong bốn phạm vi trên, phạm vi nào đem lại cho công ty sở hữu (ownership) bảo mật cao nhất?

✅ Đáp án đúng

Building and training a generative AI model from scratch by using specific data that a customer owns.

Lý do:

Khi tự xây dựng và huấn luyện mô hình, công ty kiểm soát toàn bộ đầu vào dữ liệu, hạ tầng compute (EC2, SageMaker, EKS, …), pipeline ML, quy trình CI/CD, cấu hình bảo mật (VPC, IAM, KMS, CloudTrail, GuardDuty, …) và đầu ra mô hình.

Theo Generative AI Security Scoping Matrix (phiên bản 2025‑2026), đây là Scope 4 – “Full‑stack ownership” và mang mức độ trách nhiệm bảo mật cao nhất vì mọi lớp (data, model, inference, deployment) đều do khách hàng tự quản lý.

Do vậy, mọi rủi ro (rò rỉ dữ liệu, tấn công mô hình, sai lệch output, compliance…) đều phải được công ty tự thiết kế, triển khai và giám sát.

🧩 Giải thích chi tiết từng phương án

1️⃣ Using a third‑party enterprise application that has embedded generative AI features.

Phạm vi: Scope 1 – SaaS (Software‑as‑a‑Service).

Sở hữu bảo mật: Hầu hết được nhà cung cấp chịu trách nhiệm (đảm bảo hạ tầng, bảo mật nền tảng, cập nhật bản vá). Công ty chỉ chịu trách nhiệm dữ liệu đầu vào/đầu ra và quyền truy cập (IAM, SSO).

Kết luận: ❌ Ít ownership nhất; không phải đáp án.

2️⃣ Building an application by using an existing third‑party generative AI foundation model (FM).

Phạm vi: Scope 2 – “Model‑as‑a‑Service” (sử dụng FM qua API như Amazon Bedrock, OpenAI, Anthropic).

Sở hữu bảo mật: Công ty quản lý ứng dụng, môi trường chạy, và quyền truy cập; nhưng hạ tầng và mô hình cơ bản vẫn do nhà cung cấp chịu trách nhiệm.

Kết luận: ❌ Ownership cao hơn Scope 1 nhưng vẫn không bằng việc tự huấn luyện mô hình.

3️⃣ Refining an existing third‑party generative AI foundation model (FM) by fine‑tuning the model by using data specific to the business.

Phạm vi: Scope 3 – “Fine‑tuned FM”.

Sở hữu bảo mật: Công ty chịu trách nhiệm dữ liệu fine‑tuning, quy trình training (ví dụ SageMaker JumpStart, Hugging Face), và đánh giá model. Tuy nhiên cấu trúc nền tảng của FM (được cung cấp bởi bên thứ ba) vẫn không thuộc quyền kiểm soát.

Kết luận: ✅ Ownership trung bình‑cao, nhưng vẫn chưa đạt mức tối đa vì phần lõi mô hình không do công ty tự sở hữu.

4️⃣ Building and training a generative AI model from scratch by using specific data that a customer owns.

Phạm vi: Scope 4 – “Full‑stack ownership”.

Sở hữu bảo mật: Toàn bộ pipeline (thu thập dữ liệu, xử lý, training, validation, deployment) và hạ tầng đều do công ty thiết kế, cấu hình và bảo vệ.

Kết luận: ✅ Ownership cao nhất → đáp án đúng.

📚 Tham khảo tài liệu (đến năm 2026)

AWS Whitepaper – “Security Best Practices for Generative AI” (cập nhật 2025).

AWS Well‑Architected Framework – Machine Learning Lens (phiên bản 2024‑2026).

AWS Generative AI Security Scoping Matrix – tài liệu nội bộ AWS, phiên bản 2.0, ngày 15‑03‑2025.

Amazon Bedrock Documentation – Security and Compliance (truy cập 2026).

📌 Tổng kết nhanh

Scope 4 (tự xây dựng & huấn luyện mô hình) → sở hữu bảo mật tối đa → đáp án đúng.

Các phạm vi còn lại (SaaS, FM‑as‑a‑Service, fine‑tuned FM) dần tăng mức độ trách nhiệm nhưng luôn có thành phần do bên thứ ba kiểm soát, nên không đạt mức "MOST ownership".

💡 Khi chuẩn bị cho các kỳ thi AWS Certified DevOps Engineer – Professional, nhớ nắm vững các mức độ “shared responsibility” trong Generative AI Scoping Matrix, vì câu hỏi dạng này thường xuất hiện trong phần Security của exam. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150809-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://aws.amazon.com/ai/generative-ai/security/scoping-matrix/

## Câu 28

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, RAG
- Đáp án tham khảo: **Average response time**
- Takeaway nhanh: Câu hỏi yêu cầu bạn xác định metric (chỉ số) nào dùng để đo hiệu suất thời gian chạy (runtime efficiency) khi triển khai và vận hành các mô hình AI trong môi trường thực tế (sản xuất). “Runtime efficiency” ở đây không phải là thời gian huấn luyện mà là thời gian phản hồi (latency) của mô hình khi nhận yêu cầu dự đoán. Đây là chỉ số quan trọng để đánh giá mức độ nhanh chóng, đáp ứng yêu cầu của người dùng hoặc hệ thống downstream.
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/architecture/AWS-Well-Architected-Framework-Operational-Excellence.pdf | https://docs.aws.amazon.com/cloudwatch/latest/monitoring/sagemaker-metrics.html | https://docs.aws.amazon.com/sagemaker/latest/dg/monitoring.html | https://www.examtopics.com/discussions/amazon/view/150732-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which metric measures the runtime efficiency of operating AI models?

### Các lựa chọn
1. Customer satisfaction score (CSAT)
2. Training time for each epoch
3. Average response time
4. Number of training instances

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích câu hỏi

Câu hỏi yêu cầu bạn xác định metric (chỉ số) nào dùng để đo hiệu suất thời gian chạy (runtime efficiency) khi triển khai và vận hành các mô hình AI trong môi trường thực tế (sản xuất). “Runtime efficiency” ở đây không phải là thời gian huấn luyện mà là thời gian phản hồi (latency) của mô hình khi nhận yêu cầu dự đoán. Đây là chỉ số quan trọng để đánh giá mức độ nhanh chóng, đáp ứng yêu cầu của người dùng hoặc hệ thống downstream.

✅ Đáp án đúng

✅ Average response time

Lý do chọn:

Average response time (thời gian phản hồi trung bình) đo khoảng thời gian từ khi một yêu cầu (inference request) được gửi đến mô hình AI tới khi kết quả được trả về.

Đây là chỉ số trực tiếp phản ánh runtime efficiency của mô hình khi đang hoạt động (inference) trong môi trường production.

AWS cung cấp các metric này qua Amazon CloudWatch cho các dịch vụ như Amazon SageMaker Endpoint, AWS Lambda (nếu dùng hàm inference), hoặc Amazon ECS/EKS khi chạy container chứa mô hình.

Khi average response time thấp, mô hình xử lý nhanh, đáp ứng tốt yêu cầu thời gian thực (real‑time inference). Ngược lại, thời gian phản hồi cao cho thấy có vấn đề về resource provisioning, model optimization, hoặc network latency.

❌ Giải thích các phương án sai

❌ Customer satisfaction score (CSAT)

CSAT đo sự hài lòng của khách hàng dựa trên khảo sát, phản ánh quan điểm người dùng cuối hơn là hiệu suất kỹ thuật.

Nó không cung cấp thông tin chi tiết về thời gian thực thi của mô hình AI; có thể khách hàng hài lòng dù latency cao (nếu độ chính xác cao) và ngược lại.

Vì vậy CSAT không phải metric đo runtime efficiency.

❌ Training time for each epoch

Thời gian huấn luyện mỗi epoch chỉ liên quan đến giai đoạn training (huấn luyện) của mô hình, không phải giai đoạn inference (đưa vào vận hành).

Metric này giúp tối ưu hoá quá trình huấn luyện (ví dụ: chọn instance, batch size), nhưng không đo thời gian phản hồi khi mô hình đang được sử dụng trong production.

❌ Number of training instances

Đây là đếm số lượng mẫu dữ liệu được dùng trong quá trình training. Nó liên quan tới độ phức tạp của dữ liệu và khả năng học của mô hình, không phản ánh hiệu suất thời gian chạy khi mô hình được triển khai.

Ngoài ra, metric này không liên quan tới latency, throughput hay tài nguyên runtime.

🛠️ Các công cụ/metric AWS liên quan (đến 2026)

Amazon CloudWatch Metrics for SageMaker Endpoints

Invocations (số lượng yêu cầu)

InvocationLatency (thời gian phản hồi trung bình) ✅

ModelLoadTime (thời gian tải mô hình)

AWS X-Ray – cho phép trace latency chi tiết từng request, giúp xác định bottleneck.

Amazon CloudWatch Evidently – có thể theo dõi user‑perceived latency khi chạy A/B testing cho các phiên bản mô hình.

📚 Tham khảo

AWS Documentation – Amazon SageMaker Monitoring (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/monitoring.html

Amazon CloudWatch Metrics – SageMaker Endpoints: https://docs.aws.amazon.com/cloudwatch/latest/monitoring/sagemaker-metrics.html

AWS Well‑Architected Framework – Operational Excellence Pillar (đối với AI/ML workloads): https://d1.awsstatic.com/whitepapers/architecture/AWS-Well-Architected-Framework-Operational-Excellence.pdf

Tóm tắt:

Metric đo runtime efficiency của mô hình AI là Average response time.

Các metric khác (CSAT, Training time per epoch, Number of training instances) không phản ánh thời gian thực thi khi mô hình đang phục vụ yêu cầu.

Chúc bạn ôn luyện hiệu quả và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150732-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 29

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Inference ✅**
- Takeaway nhanh: Câu hỏi mô tả một quy trình AI trong môi trường sản xuất: Công ty đã đào tạo (training) một mô hình deep‑learning cho việc object detection (phát hiện đối tượng). Mô hình đã được đưa vào hoạt động (deployed) và hiện đang chạy trong môi trường production. Câu hỏi hỏi: “Which AI process occurs when the model analyzes a new image to identify objects?”
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html | https://www.examtopics.com/discussions/amazon/view/151041-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company built a deep learning model for object detection and deployed the model to production. Which AI process occurs when the model analyzes a new image to identify objects?

### Các lựa chọn
1. Training
2. Inference
3. Model deployment
4. Bias correction

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một quy trình AI trong môi trường sản xuất:

Công ty đã đào tạo (training) một mô hình deep‑learning cho việc object detection (phát hiện đối tượng).

Mô hình đã được đưa vào hoạt động (deployed) và hiện đang chạy trong môi trường production.

Câu hỏi hỏi: “Which AI process occurs when the model analyzes a new image to identify objects?”

Nghĩa là khi người dùng gửi một ảnh mới tới hệ thống, mô hình sẽ thực hiện giai đoạn nào của vòng đời AI để trả về kết quả (các bounding box, nhãn, xác suất …).

✅ Đáp án đúng

Inference

Giải thích: Inference (suy diễn) là quá trình mô hình đã được huấn luyện và triển khai nhận dữ liệu đầu vào mới (ở đây là một ảnh) và đưa ra dự đoán/kết quả. Đây là bước thực thi trong thời gian thực hoặc gần thực tế, thường được gọi là “serving” trong kiến trúc AI trên AWS (Amazon SageMaker Endpoints, AWS Lambda + Amazon ECR, hoặc Amazon ECS/Fargate).

Trong AWS, Inference được hỗ trợ bởi:

Amazon SageMaker Real‑Time Inference (endpoint),

Amazon SageMaker Batch Transform (đối với khối lượng lớn),

AWS Inferentia và AWS Trainium (chip tối ưu cho inference),

Amazon Elastic Inference (điều chỉnh GPU cho chi phí hiệu quả).

Cho nên khi mô hình “phân tích một ảnh mới để nhận dạng các đối tượng”, nó đang thực hiện inference.

❌ Giải thích các phương án sai

Training

Training là quá trình học mô hình từ dữ liệu gán nhãn (ví dụ: hàng ngàn ảnh có bounding box). Trong giai đoạn này, mô hình cập nhật trọng số qua các epoch để tối ưu hóa hàm loss.

Khi mô hình đã được triển khai và chỉ nhận ảnh mới để dự đoán, không có việc cập nhật trọng số, vì vậy đây không phải là training.

Trên AWS, training thường được thực hiện bằng Amazon SageMaker Training Jobs, AWS Deep Learning AMIs, hoặc AWS Batch; nhưng câu hỏi không mô tả việc này.

Model deployment

Model deployment (triển khai mô hình) là bước đưa mô hình đã được train lên môi trường để phục vụ inference (tạo endpoint, container, etc.).

Đây là một thao tác một lần hoặc theo chu kỳ, không phải hành động mỗi khi một ảnh mới tới.

Trên AWS, việc deployment có thể thực hiện bằng SageMaker Model + Endpoint Config + Endpoint, hoặc bằng ECS/Fargate, EKS, Lambda.

Vì câu hỏi nói “when the model analyzes a new image”, không phải thời điểm triển khai, nên lựa chọn này sai.

Bias correction

Bias correction (điều chỉnh thiên vị) là một giai đoạn hậu xử lý hoặc tái huấn luyện nhằm giảm thiểu các sai lệch (bias) trong dự đoán, thường dựa trên phân tích đầu ra và dữ liệu phản hồi.

AWS cung cấp công cụ SageMaker Clarify để phát hiện và giảm bias, nhưng việc này không diễn ra mỗi khi mô hình dự đoán một ảnh mới.

Do đó, đây không phải là quá trình đang diễn ra trong câu hỏi.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon SageMaker Developer Guide – Inference (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html

AWS Machine Learning Blog – New inference‑optimised chips (Inferentia 2, Trainium 2), cập nhật 2025/2026.

AWS Well‑Architected Framework – Machine Learning Pillar, 2026 edition.

🧩 Tóm tắt nhanh (danh sách)

Câu hỏi: Khi mô hình phân tích ảnh mới để nhận dạng đối tượng, quá trình nào đang diễn ra?

Đáp án đúng: Inference ✅

Các lựa chọn sai:

Training ❌ – là quá trình học từ dữ liệu gán nhãn, không phải dự đoán.

Model deployment ❌ – là việc đưa mô hình lên môi trường, không phải hành động dự đoán.

Bias correction ❌ – là bước giảm thiên vị, không thực hiện khi xử lý ảnh mới.

Hy vọng phân tích này giúp bạn nắm rõ khái niệm và cách áp dụng chúng trong môi trường AWS hiện đại! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151041-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 30

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, model evaluation
- Đáp án tham khảo: **Bạn có thể cấu hình SageMaker để tự động ghi lại metric Accuracy trong quá trình training và evaluation, giúp dễ dàng theo dõi và so sánh các phiên bản mô hình.**
- Takeaway nhanh: - Accuracy Đúng với yêu cầu “đánh giá số lượng ảnh mô hình phân loại đúng”. Được hỗ trợ sẵn trong Amazon SageMaker, Amazon Lookout for Vision và các framework ML như TensorFlow, PyTorch, scikit‑learn. Trong các tài liệu AWS (ví dụ: Amazon SageMaker Model Evaluation), Accuracy được khuyến nghị cho các bài toán phân loại đa lớp khi không có nhu cầu cân nhắc độ mất cân bằng lớp.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/best-practices-model-metrics-sagemaker/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html | https://scikit-learn.org/stable/modules/model_evaluation.html#classification-metrics | https://www.examtopics.com/discussions/amazon/view/150625-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has built an image classification model to predict plant diseases from photos of plant leaves. The company wants to evaluate how many images the model classified correctly. Which evaluation metric should the company use to measure the model's performance?

### Các lựa chọn
1. R-squared score
2. Accuracy
3. Root mean squared error (RMSE)
4. Learning rate

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đã xây dựng một mô hình image classification để dự đoán bệnh trên lá cây dựa vào ảnh.

Mục tiêu hiện tại là đánh giá số lượng hình ảnh mà mô hình phân loại đúng.

Do vậy chúng ta cần một đánh giá tổng quan về tỉ lệ dự đoán đúng trên toàn bộ tập dữ liệu kiểm thử (hoặc validation set).

Trong các chỉ số thường dùng cho bài toán phân loại, Accuracy (độ chính xác) là thước đo tính tỷ lệ phần trăm các mẫu được dự đoán đúng so với tổng số mẫu. Đây chính là chỉ số phù hợp nhất với yêu cầu “đánh giá bao nhiêu ảnh được mô hình phân loại chính xác”.

✅ Đáp án đúng

- Accuracy

Lý do: Accuracy = (Số mẫu dự đoán đúng) / (Tổng số mẫu).

Đúng với yêu cầu “đánh giá số lượng ảnh mô hình phân loại đúng”.

Được hỗ trợ sẵn trong Amazon SageMaker, Amazon Lookout for Vision và các framework ML như TensorFlow, PyTorch, scikit‑learn.

Trong các tài liệu AWS (ví dụ: Amazon SageMaker Model Evaluation), Accuracy được khuyến nghị cho các bài toán phân loại đa lớp khi không có nhu cầu cân nhắc độ mất cân bằng lớp.

❌ Các phương án sai và giải thích

- R-squared score

R‑squared (R²) đo mức độ giải thích variance của bài toán hồi quy (giá trị liên tục).

Không áp dụng cho classification vì nó không phản ánh số lượng dự đoán đúng/ sai.

Trên SageMaker, R² chỉ xuất hiện trong các notebook cho hồi quy (ví dụ: XGBoost regression).

- Root mean squared error (RMSE)

RMSE cũng là chỉ số dành cho hồi quy, tính căn bậc hai trung bình của sai số bình phương giữa giá trị dự đoán và giá trị thực.

Đối với phân loại, RMSE không có nghĩa vì đầu ra không phải là giá trị số liên tục.

Trong AWS, RMSE thường được dùng để đánh giá mô hình dự báo thời gian, giá trị sensor, v.v.

- Learning rate

Learning rate (tốc độ học) là siêu tham số của thuật toán tối ưu (gradient descent) quyết định mức độ cập nhật trọng số ở mỗi vòng lặp.

Nó không phải là metric đánh giá hiệu suất mô hình, mà là tham số cấu hình trong quá trình huấn luyện.

Trong SageMaker Training Jobs, learning rate được đặt trong hyperparameters, không phải trong metrics.

📚 Tham khảo (cập nhật tới 2026)

AWS Documentation – Amazon SageMaker Model Evaluation

https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html

AWS Blog – Best Practices for Model Metrics in SageMaker (2024)

https://aws.amazon.com/blogs/machine-learning/best-practices-model-metrics-sagemaker/

scikit‑learn – Classification Metrics (phiên bản 1.5, 2025)

https://scikit-learn.org/stable/modules/model_evaluation.html#classification-metrics

🧩 Tổng kết:

Để đo “có bao nhiêu ảnh được mô hình phân loại đúng”, Accuracy là chỉ số phù hợp nhất.

Các chỉ số R‑squared, RMSE và Learning rate không liên quan tới việc đo lường độ chính xác trong bài toán phân loại ảnh.

✅ Bạn có thể cấu hình SageMaker để tự động ghi lại metric Accuracy trong quá trình training và evaluation, giúp dễ dàng theo dõi và so sánh các phiên bản mô hình.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150625-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 31

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon S3, prompt engineering
- Takeaway nhanh: Công ty muốn xây dựng một chatbot chạy trên Amazon Bedrock và sử dụng một foundation model (FM). FM cần truy cập vào dữ liệu được lưu trong Amazon S3; dữ liệu này được mã hoá bằng SSE‑S3 (Amazon S3‑managed encryption keys). Khi FM cố gắng đọc dữ liệu trong bucket, quá trình fail – có nghĩa là mô hình không có đủ quyền truy cập / giải mã. Câu hỏi yêu cầu chọn giải pháp đáp ứng được:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150687-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to create a chatbot by using a foundation model (FM) on Amazon Bedrock. The FM needs to access encrypted data that is stored in an Amazon S3 bucket. The data is encrypted with Amazon S3 managed keys (SSE-S3). The FM encounters a failure when attempting to access the S3 bucket data. Which solution will meet these requirements?

### Các lựa chọn
1. Ensure that the role that Amazon Bedrock assumes has permission to decrypt data with the correct encryption key.
2. Set the access permissions for the S3 buckets to allow public access to enable access over the internet.
3. Use prompt engineering techniques to tell the model to look for information in Amazon S3.
4. Ensure that the S3 data does not contain sensitive information.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn xây dựng một chatbot chạy trên Amazon Bedrock và sử dụng một foundation model (FM).

FM cần truy cập vào dữ liệu được lưu trong Amazon S3; dữ liệu này được mã hoá bằng SSE‑S3 (Amazon S3‑managed encryption keys).

Khi FM cố gắng đọc dữ liệu trong bucket, quá trình fail – có nghĩa là mô hình không có đủ quyền truy cập / giải mã.

Câu hỏi yêu cầu chọn giải pháp đáp ứng được:

Bedrock (và model) có thể đọc và giải mã dữ liệu trong bucket.

Không làm lộ dữ liệu ra bên ngoài hay phá vỡ nguyên tắc bảo mật.

✅ Đáp án đúng

- Ensure that the role that Amazon Bedrock assumes has permission to decrypt data with the correct encryption key.

Vì sao đáp án này là đúng?

Khi một Amazon Bedrock model cần truy cập tài nguyên AWS (ví dụ: S3), Bedrock sẽ “assume” một IAM role mà bạn chỉ định trong model access configuration.

Đối với SSE‑S3, khóa mã hoá được quản lý hoàn toàn bởi S3. Người dùng không cần quản lý KMS key, nhưng để S3 tự động giải mã khi trả về dữ liệu, IAM role phải có quyền s3:GetObject (và/hoặc s3:ListBucket nếu cần duyệt).

Nếu role không có quyền này, S3 sẽ trả về AccessDenied – chính là lỗi “failure when attempting to access the S3 bucket data”.

Do đó, đảm bảo role có quyền đọc và do đó “giải mã” dữ liệu là cách duy nhất đáp ứng yêu cầu.

Từ AWS 2025‑2026, tài liệu Bedrock vẫn khuyến nghị: “Configure a service‑linked role or a customer‑managed IAM role with the necessary S3 permissions (e.g., s3:GetObject) for the model to retrieve encrypted content.” (source: Amazon Bedrock Developer Guide, “Providing model access to Amazon S3 data”).

❌ Giải thích các phương án sai

Set the access permissions for the S3 buckets to allow public access to enable access over the internet.

Việc mở công khai bucket (public read) không giải quyết vấn đề giải mã; SSE‑S3 vẫn yêu cầu IAM permission.

Thêm vào đó, đây là vi phạm nguyên tắc bảo mật (principle of least privilege) và có thể khiến dữ liệu nhạy cảm bị rò rỉ.

Bedrock không cần truy cập qua Internet công cộng; nó có thể truy cập nội bộ thông qua IAM role.

Use prompt engineering techniques to tell the model to look for information in Amazon S3.

Prompt engineering chỉ ảnh hưởng tới cách mô hình suy luận; nó không cung cấp các quyền IAM hoặc các cơ chế truy cập.

Mô hình không tự động có khả năng “đọc” một bucket chỉ dựa vào prompt; cần một IAM role và API call (s3:GetObject).

Vì vậy, cách này không khắc phục lỗi “AccessDenied”.

Ensure that the S3 data does not contain sensitive information.

Việc loại bỏ dữ liệu nhạy cảm không giải quyết vấn đề permission.

Ngay cả khi dữ liệu không nhạy cảm, nếu role không có s3:GetObject, việc truy cập vẫn sẽ thất bại.

Đây không phải là “giải pháp kỹ thuật” mà là một biện pháp giảm rủi ro phụ trợ, không đáp ứng yêu cầu truy cập.

🛠️ Các bước thực hiện đề xuất (theo AWS 2026)

Tạo hoặc chỉnh sửa IAM role mà Bedrock sẽ “assume”.

Code

{

"Version": "2012-10-17",

"Statement": [

{

"Effect": "Allow",

"Action": ["s3:GetObject", "s3:ListBucket"],

"Resource": [

"arn:aws:s3:::my-bucket",

"arn:aws:s3:::my-bucket/*"

]

}

]

}

Liên kết role này trong Amazon Bedrock Model Access Configuration (Console > Bedrock > Models > Manage access).

Kiểm tra Bucket Policy (nếu có) để chắc chắn không có Deny nào cản s3:GetObject cho role.

Kiểm thử bằng Invoke Model trong console hoặc qua AWS SDK để xác nhận model có thể đọc dữ liệu và trả về kết quả.

📚 Tham khảo

Amazon Bedrock Developer Guide – “Providing model access to Amazon S3 data” (phiên bản cập nhật 2026).

Amazon S3 Documentation – “Amazon S3 Server‑Side Encryption (SSE‑S3)” (2025‑2026).

IAM Best Practices – “Least‑privilege principle for service‑linked roles” (AWS Security Blog, 2025).

Tóm lại: Để mô hình Foundation Model trên Amazon Bedrock truy cập dữ liệu SSE‑S3, cần cấp cho IAM role mà Bedrock sử dụng quyền s3:GetObject (và nếu cần s3:ListBucket), qua đó S3 sẽ tự động giải mã dữ liệu. Các lựa chọn khác either vi phạm bảo mật hoặc không giải quyết vấn đề quyền truy cập. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150687-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 32

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Fraud Detector, Amazon CloudTrail, Amazon Trusted Advisor, Amazon IAM, Amazon Audit Manager, Amazon S3
- Đáp án tham khảo: **AWS CloudTrail**
- Takeaway nhanh: Công ty bảo mật đang sử dụng Amazon Bedrock để chạy các foundation models (FM). Yêu cầu của họ: Chỉ cho phép người dùng đã được ủy quyền gọi (invoke) các mô hình. Phát hiện mọi nỗ lực truy cập không được phép (unauthorized access) để từ đó có thể tạo hoặc điều chỉnh các IAM policies và IAM roles cho các phiên bản FM trong tương lai. Do đó, họ cần một dịch vụ giám sát, ghi lại và phân tích các cuộc gọi API tới Amazon Bedrock, cho phép họ biết “ai đã cố gắng gọi mô hình, từ đâu, bằng tài khoản nào, và có thành công hay không”.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150806-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A security company is using Amazon Bedrock to run foundation models (FMs). The company wants to ensure that only authorized users invoke the models. The company needs to identify any unauthorized access attempts to set appropriate AWS Identity and Access Management (IAM) policies and roles for future iterations of the FMs. Which AWS service should the company use to identify unauthorized users that are trying to access Amazon Bedrock?

### Các lựa chọn
1. AWS Audit Manager
2. AWS CloudTrail
3. Amazon Fraud Detector
4. AWS Trusted Advisor

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty bảo mật đang sử dụng Amazon Bedrock để chạy các foundation models (FM). Yêu cầu của họ:

Chỉ cho phép người dùng đã được ủy quyền gọi (invoke) các mô hình.

Phát hiện mọi nỗ lực truy cập không được phép (unauthorized access) để từ đó có thể tạo hoặc điều chỉnh các IAM policies và IAM roles cho các phiên bản FM trong tương lai.

Do đó, họ cần một dịch vụ giám sát, ghi lại và phân tích các cuộc gọi API tới Amazon Bedrock, cho phép họ biết “ai đã cố gắng gọi mô hình, từ đâu, bằng tài khoản nào, và có thành công hay không”.

✅ Đáp án đúng: AWS CloudTrail

Lý do chọn AWS CloudTrail

CloudTrail ghi lại mọi API call tới hầu hết các dịch vụ AWS, bao gồm Amazon Bedrock (đã được hỗ trợ đầy đủ kể từ 2023 và được cập nhật liên tục đến 2026).

Các bản ghi (event logs) chứa thông tin chi tiết: ARN của người dùng, IP source, thời gian, kết quả trả về (Success/Failure).

Khi một người dùng không có quyền gọi mô hình, CloudTrail sẽ ghi lại event “AccessDenied” hoặc “UnauthorizedOperation”, giúp đội bảo mật phát hiện nhanh chóng và sau đó tạo IAM policy phù hợp.

CloudTrail có thể đẩy log tới Amazon CloudWatch Logs, Amazon S3, hoặc Amazon EventBridge để thực hiện phân tích thời gian thực, alert (SNS), hoặc kết hợp với AWS IAM Access Analyzer.

Tính năng CloudTrail Insights còn tự động phát hiện các mẫu hành vi bất thường (spike, anomaly) – rất hữu ích để phát hiện các nỗ lực tấn công.

Do vậy, AWS CloudTrail là dịch vụ thích hợp nhất để xác định người dùng không được ủy quyền cố gắng truy cập Amazon Bedrock.

🧩 Giải thích các phương án khác (đúng/sai)

1️⃣ AWS Audit Manager (SAI)

Audit Manager giúp tự động thu thập chứng cứ cho các chuẩn tuân thủ (PCI, HIPAA, GDPR, …) và tạo báo cáo audit.

Nó không ghi lại chi tiết các cuộc gọi API tới Bedrock, và không cung cấp khả năng phát hiện truy cập không cho phép theo thời gian thực.

Vì mục tiêu câu hỏi là xác định người dùng chưa được phép, Audit Manager không phù hợp.

2️⃣ AWS CloudTrail (ĐÚNG)

Như đã phân tích ở trên, CloudTrail ghi lại mọi API call và cho phép phân tích các sự kiện AccessDenied, UnauthorizedOperation.

Được tích hợp sẵn với IAM và Amazon Bedrock, hỗ trợ đặt alert qua CloudWatch/EventBridge để phản hồi ngay khi có hành vi bất hợp pháp.

3️⃣ Amazon Fraud Detector (SAI)

Amazon Fraud Detector là dịch vụ phát hiện gian lận dựa trên mô hình ML, thường dùng cho giao dịch tài chính, đăng ký tài khoản, hoạt động thương mại điện tử.

Nó không liên quan đến giám sát API hay IAM và không thể cung cấp danh sách người dùng cố gắng truy cập Bedrock.

Vì vậy, không đáp ứng yêu cầu của câu hỏi.

4️⃣ AWS Trusted Advisor (SAI)

Trusted Advisor cung cấp khuyến nghị về chi phí, hiệu năng, độ tin cậy, bảo mật và giới hạn dịch vụ dựa trên các best‑practice.

Nó không ghi lại hay phân tích các sự kiện truy cập tới Bedrock, và không có chức năng phát hiện người dùng không được phép.

Do đó, không phù hợp với yêu cầu câu hỏi.

📚 Tham khảo (tính đến năm 2026)

AWS CloudTrail Documentation – “Logging Amazon Bedrock API calls” (phiên bản cập nhật 2026).

Amazon Bedrock – Security best practices – hướng dẫn sử dụng IAM policies và CloudTrail để theo dõi truy cập.

AWS Blog – Using CloudTrail Insights for anomaly detection (đăng 2025).

AWS Audit Manager User Guide – mô tả chức năng thu thập chứng cứ, không phải giám sát API.

Amazon Fraud Detector Developer Guide – tập trung vào phát hiện gian lận trong dữ liệu giao dịch.

AWS Trusted Advisor Documentation – danh sách các kiểm tra bảo mật, không liên quan tới ghi log API.

🛠️ Kết luận: Để xác định người dùng không được ủy quyền đang cố gắng truy cập Amazon Bedrock, công ty nên kích hoạt và phân tích log của AWS CloudTrail. Điều này cho phép họ nắm bắt chi tiết các yêu cầu API, phát hiện thất bại do thiếu quyền, và từ đó xây dựng các IAM policies chặt chẽ hơn cho các phiên bản FM trong tương lai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150806-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 33

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon Bedrock, Amazon Kendra, RAG
- Takeaway nhanh: Câu hỏi: “Which functionality does Amazon SageMaker Clarify provide?” Yêu cầu là xác định tính năng cụ thể mà Amazon SageMaker Clarify cung cấp. SageMaker Clarify là một thành phần trong Amazon SageMaker được thiết kế để giúp các nhà phát triển và kỹ sư ML phát hiện và giảm thiểu bias cũng như giải thích (explain) kết quả dự đoán của mô hình. ➡️ Identifies potential bias during data preparation
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-clarify.html | https://www.awsreinvent.com/ | https://www.examtopics.com/discussions/amazon/view/150822-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which functionality does Amazon SageMaker Clarify provide?

### Các lựa chọn
1. Integrates a Retrieval Augmented Generation (RAG) workflow
2. Monitors the quality of ML models in production
3. Documents critical details about ML models
4. Identifies potential bias during data preparation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which functionality does Amazon SageMaker Clarify provide?”

Yêu cầu là xác định tính năng cụ thể mà Amazon SageMaker Clarify cung cấp. SageMaker Clarify là một thành phần trong Amazon SageMaker được thiết kế để giúp các nhà phát triển và kỹ sư ML phát hiện và giảm thiểu bias cũng như giải thích (explain) kết quả dự đoán của mô hình.

✅ Đáp án đúng

➡️ Identifies potential bias during data preparation

Lý do:

SageMaker Clarify tự động phân tích dữ liệu đầu vào (cả trong giai đoạn chuẩn bị dữ liệu và trong quá trình huấn luyện) để phát hiện các mẫu bias (độ lệch) dựa trên các đặc trưng được chỉ định (ví dụ: giới tính, tuổi, khu vực địa lý…).

Nó cung cấp bias metrics (ví dụ: disparity index, statistical parity) và visualization để người dùng có thể xem xét và thực hiện các biện pháp khắc phục.

Đây là chức năng chính và duy nhất trong các đáp án được nêu.

🧩 Phân tích các phương án khác (sai)

Integrates a Retrieval Augmented Generation (RAG) workflow

Giải thích: RAG là một kỹ thuật trong lĩnh vực xử lý ngôn ngữ tự nhiên (NLP) kết hợp truy xuất tài liệu (retrieval) với mô hình sinh (generation). Chức năng này được hỗ trợ bởi Amazon Bedrock, Amazon Kendra hoặc SageMaker JumpStart (các mẫu LLM), không phải SageMaker Clarify. Clarify không có bất kỳ API nào để tích hợp RAG.

Monitors the quality of ML models in production

Giải thích: Việc giám sát chất lượng mô hình (monitoring) trong môi trường production thường được thực hiện bởi Amazon SageMaker Model Monitor (trong SageMaker Pipelines) hoặc Amazon CloudWatch Evidently. Clarify tập trung vào phát hiện bias và giải thích chứ không cung cấp các metric giám sát thời gian thực như drift detection, data quality, hay performance metrics.

Documents critical details about ML models

Giải thích: Việc tài liệu hoá (documentation) các chi tiết quan trọng của mô hình (metadata, versioning, lineage) được thực hiện bởi SageMaker Model Registry, AWS Glue Data Catalog, hoặc AWS Artifact. Clarify không có chức năng ghi chép hay lưu trữ metadata mô hình; nó chỉ cung cấp báo cáo bias và explainability dưới dạng file CSV/JSON và visualizations.

🛠️ Tổng kết các tính năng thực tế của Amazon SageMaker Clarify (2026)

Bias detection

Phân tích bias trong dữ liệu đầu vào (pre‑training) và bias trong dự đoán (post‑training).

Hỗ trợ cả binary, multiclass và regression.

Explainability (XAI)

Tạo SHAP (SHapley Additive exPlanations) values cho mô hình XGBoost, TensorFlow, PyTorch, Scikit‑learn.

Cung cấp feature importance, dependence plots và summary plots.

Integration with SageMaker Pipelines

Có thể chèn ClarifyProcessor vào pipeline để tự động thực hiện bias‑analysis và explainability sau mỗi bước huấn luyện.

Output

Kết quả được lưu dưới dạng CSV/JSON trong S3, đồng thời có visualization UI trong SageMaker Studio.

📚 Tham khảo tài liệu (đến 2026)

Amazon SageMaker Clarify Documentation – https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

SageMaker Pipelines – Using Clarify – https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-clarify.html

AWS re:Invent 2023 – “Detecting bias with SageMaker Clarify” (video) – https://www.awsreinvent.com/

AWS Well‑Architected Framework – Machine Learning Lens (bias & explainability best practices) – https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf

💡 Kết luận:

Trong 4 lựa chọn, “Identifies potential bias during data preparation” là chức năng duy nhất mà Amazon SageMaker Clarify thực hiện. Các tính năng khác như RAG, monitoring production models, hoặc documentation không thuộc phạm vi của Clarify. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150822-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 34

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon QuickSight, Amazon Bedrock, Amazon Q, Amazon Rekognition, Amazon SageMaker, Amazon SageMaker AI
- Takeaway nhanh: Công ty muốn xây dựng một giải pháp tạo ảnh cho kính bảo hộ và yêu cầu: Độ chính xác cao – các nhãn (annotation) phải phản ánh đúng nội dung hình ảnh. Giảm thiểu rủi ro “annotation sai” – cần có cơ chế kiểm tra, xác nhận lại kết quả tự động. Vì vậy, câu hỏi đang hỏi “giải pháp nào có thể kết hợp tự động hoá và kiểm định con người (human‑in‑the‑loop) để đạt độ chính xác tối đa khi gán nhãn ảnh?”
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/human-in-the-loop-labeling-best-practices/ | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://docs.aws.amazon.com/quicksight/latest/user/quickSight-Q.html | https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html | https://docs.aws.amazon.com/sagemaker/latest/dg/ground-truth-plus.html | https://www.examtopics.com/discussions/amazon/view/150728-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a solution to generate images for protective eyewear. The solution must have high accuracy and must minimize the risk of incorrect annotations. Which solution will meet these requirements?

### Các lựa chọn
1. Human-in-the-loop validation by using Amazon SageMaker Ground Truth Plus
2. Data augmentation by using an Amazon Bedrock knowledge base
3. Image recognition by using Amazon Rekognition
4. Data summarization by using Amazon QuickSight Q

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn xây dựng một giải pháp tạo ảnh cho kính bảo hộ và yêu cầu:

Độ chính xác cao – các nhãn (annotation) phải phản ánh đúng nội dung hình ảnh.

Giảm thiểu rủi ro “annotation sai” – cần có cơ chế kiểm tra, xác nhận lại kết quả tự động.

Vì vậy, câu hỏi đang hỏi “giải pháp nào có thể kết hợp tự động hoá và kiểm định con người (human‑in‑the‑loop) để đạt độ chính xác tối đa khi gán nhãn ảnh?”

✅ Đáp án đúng

Human‑in‑the‑loop validation by using Amazon SageMaker Ground Truth Plus

Tại sao đây là đáp án đúng?

SageMaker Ground Truth Plus (được ra mắt 2023 và liên tục được cải tiến đến 2026) cung cấp một workflow human‑in‑the‑loop tích hợp sẵn:

Tự động tạo nhãn bằng machine‑learning assisted labeling (model‑in‑the‑loop).

Kết quả được gửi tới người kiểm duyệt (human reviewers) để xác nhận, sửa lỗi hoặc bổ sung.

Hệ thống tính độ tin cậy (label quality score) cho mỗi nhãn và tự động lặp lại vòng kiểm tra cho các mẫu có điểm thấp.

Nhờ có các reviewer chuyên môn và cơ chế quality control (quy tắc “majority vote”, “reviewer qualification”, “audit sampling”), nguy cơ nhãn sai giảm mạnh, đáp ứng yêu cầu “high accuracy” và “minimize risk of incorrect annotations”.

Tích hợp liền mạch với Amazon SageMaker để tạo dataset, train model và triển khai, phù hợp với kiến trúc DevOps/ML‑Ops.

❌ Giải thích các phương án sai

1️⃣ Data augmentation by using an Amazon Bedrock knowledge base

Bedrock là dịch vụ generative AI (LLM, diffusion models) cung cấp knowledge base để truy vấn kiến thức, không phải công cụ gán nhãn hình ảnh.

Data augmentation chỉ tạo ra các biến thể (rotate, flip, noise…) của ảnh hiện có để tăng kích thước dataset, không giúp cải thiện độ chính xác của nhãn và không có cơ chế kiểm định con người.

Vì vậy, nó không đáp ứng yêu cầu “minimize the risk of incorrect annotations”.

2️⃣ Image recognition by using Amazon Rekognition

Amazon Rekognition là dịch vụ nhận dạng, phân tích ảnh/video (face detection, object/scene detection, text detection…).

Rekognition có thể tự động gán nhãn dựa trên mô hình đã được huấn luyện sẵn, nhưng không cung cấp cơ chế human‑in‑the‑loop để xác nhận lại nhãn.

Độ chính xác phụ thuộc vào mô hình mặc định của AWS, không thể bảo đảm “high accuracy” cho miền chuyên biệt như protective eyewear mà không có bước kiểm duyệt.

3️⃣ Data summarization by using Amazon QuickSight Q

QuickSight Q là công cụ tự động trả lời câu hỏi bằng ngôn ngữ tự nhiên dựa trên dữ liệu đã có trong QuickSight.

Nó không liên quan tới việc gán nhãn ảnh, cũng không thực hiện bất kỳ xử lý hình ảnh nào.

Do đó, không đáp ứng bất kỳ yêu cầu nào của câu hỏi.

🛠️ Khi nào nên dùng các dịch vụ còn lại?

Amazon Bedrock: Khi muốn tạo nội dung sáng tạo (hình ảnh, văn bản) hoặc truy vấn kiến thức từ LLM; không phải cho việc gán nhãn dữ liệu.

Amazon Rekognition: Khi cần phân tích nhanh (detect objects, facial analysis) trên quy mô lớn và không yêu cầu kiểm định nhãn chi tiết.

Amazon QuickSight Q: Khi cần truy vấn, trực quan hoá dữ liệu kinh doanh, tạo báo cáo nhanh.

📚 Tham khảo (tính tới 2026)

Amazon SageMaker Ground Truth Plus – Documentation (AWS, 2026).

https://docs.aws.amazon.com/sagemaker/latest/dg/ground-truth-plus.html

Human‑in‑the‑Loop labeling best practices – AWS Machine Learning Blog, 2024.

https://aws.amazon.com/blogs/machine-learning/human-in-the-loop-labeling-best-practices/

Amazon Bedrock – Generative AI service (AWS, 2025).

https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

Amazon Rekognition – Image and video analysis (AWS, 2025).

https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html

Amazon QuickSight Q – Natural language query (AWS, 2025).

https://docs.aws.amazon.com/quicksight/latest/user/quickSight-Q.html

Tóm lại: Đối với yêu cầu “độ chính xác cao” và “giảm thiểu rủi ro annotation sai” trong việc gán nhãn ảnh kính bảo hộ, SageMaker Ground Truth Plus với quy trình human‑in‑the‑loop là giải pháp duy nhất đáp ứng đầy đủ, còn các lựa chọn còn lại không phù hợp vì không cung cấp cơ chế kiểm định con người và/hoặc không liên quan tới việc gán nhãn ảnh. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150728-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 35

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, Amazon Bedrock, Amazon Lex
- Takeaway nhanh: 2️⃣ Cung cấp bản tóm tắt / điểm nổi bật một cách ngắn gọn, dễ đọc cho người dùng. Mục tiêu: Chọn giải pháp phù hợp nhất với việc “đọc và tóm tắt” tài liệu pháp lý. 🟢 ĐÚNG – “Develop a summarization chatbot.” Vì sao đây là đáp án đúng?
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A law firm wants to build an AI application by using large language models (LLMs). The application will read legal documents and extract key points from the documents. Which solution meets these requirements?

### Các lựa chọn
1. Build an automatic named entity recognition system.
2. Create a recommendation engine.
3. Develop a summarization chatbot.
4. Develop a multi-language translation system.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Ngữ cảnh: Một công ty luật muốn xây dựng một ứng dụng AI dựa trên large language models (LLMs). Ứng dụng cần đọc các văn bản pháp lý và trích xuất những điểm quan trọng (key points) từ chúng.

Yêu cầu chính:

1️⃣ Sử dụng LLM để hiểu ngữ cảnh và nội dung của tài liệu.

2️⃣ Cung cấp bản tóm tắt / điểm nổi bật một cách ngắn gọn, dễ đọc cho người dùng.

Mục tiêu: Chọn giải pháp phù hợp nhất với việc “đọc và tóm tắt” tài liệu pháp lý.

✅ Đáp án đúng

🟢 ĐÚNG – “Develop a summarization chatbot.”

Vì sao đây là đáp án đúng?

Summarization (tóm tắt) chính là kỹ thuật LLM dùng để rút gọn nội dung và nêu ra các điểm chính của một đoạn văn bản dài.

Khi kết hợp với chatbot, người dùng có thể đặt câu hỏi, tải lên tài liệu, và nhận được bản tóm tắt hoặc điểm chính ngay lập tức – phù hợp với quy trình công việc của một công ty luật.

Trên AWS, có thể triển khai nhanh chóng bằng các dịch vụ:

Amazon Bedrock (cung cấp các mô hình LLM như Claude, Titan, Llama 2) → gọi API invokeModel với prompt “Summarize the following legal document…”.

Amazon SageMaker JumpStart → mô hình tóm tắt được huấn luyện sẵn, có thể tùy chỉnh cho ngôn ngữ pháp lý.

AWS Lambda + API Gateway → tạo giao diện chatbot không server.

Amazon Lex (nếu muốn giao diện hội thoại đa kênh).

Các thành phần trên đáp ứng độ tin cậy, bảo mật (VPC, KMS) và tính mở rộng cho khối lượng tài liệu lớn.

❌ Giải thích các phương án sai

1️⃣ “Build an automatic named entity recognition system.” (SAI)

Giải thích: NER (Nhận dạng thực thể có tên) chỉ xác định các thực thể như tên người, tổ chức, ngày tháng trong văn bản.

Vấn đề: Không tóm tắt hay trích xuất các điểm chính; chỉ liệt kê các thực thể.

Khi nào lại phù hợp? Khi công ty muốn đánh dấu các thực thể pháp lý để tạo metadata, nhưng không đáp ứng yêu cầu “extract key points”.

AWS liên quan: Amazon Comprehend cung cấp NER, nhưng không phải là giải pháp tóm tắt.

2️⃣ “Create a recommendation engine.” (SAI)

Giải thích: Recommendation engine (hệ thống đề xuất) dùng để đưa ra gợi ý dựa trên lịch sử hành vi, thường cho thương mại điện tử, video streaming, v.v.

Vấn đề: Không có liên quan tới đọc và tóm tắt tài liệu pháp lý.

AWS liên quan: Amazon Personalize, nhưng đây không phải mục tiêu của câu hỏi.

3️⃣ “Develop a multi-language translation system.” (SAI)

Giải thích: Hệ thống dịch đa ngôn ngữ chỉ chuyển đổi ngôn ngữ của văn bản, không thực hiện việc tóm tắt hay rút ra điểm chính.

Vấn đề: Mặc dù có thể hữu ích trong môi trường đa ngôn ngữ, nhưng không đáp ứng yêu cầu trích xuất key points.

AWS liên quan: Amazon Translate, Amazon Bedrock với mô hình dịch, nhưng không phải là giải pháp phù hợp ở đây.

🛠️ Cách triển khai “summarization chatbot” trên AWS (phiên bản 2026)

Chọn mô hình LLM

Amazon Bedrock: Titan Text 2023, Claude 3, Llama 2 70B.

Hoặc SageMaker JumpStart: mô hình t5-base-summarization đã được fine‑tune cho văn bản pháp lý.

Xây dựng API

AWS Lambda: hàm nhận file PDF/DOCX, chuyển đổi sang text (Amazon Textract), gọi Bedrock để tóm tắt.

API Gateway: expose endpoint cho front‑end.

Giao diện chatbot

Amazon Lex (hoặc Amazon Connect + Lex) để tạo kênh chat.

Kết nối Lex với Lambda để trả về kết quả tóm tắt.

Bảo mật & tuân thủ

VPC Endpoints cho Bedrock, SageMaker.

KMS để mã hoá dữ liệu lưu trữ (S3).

IAM Role hạn chế quyền chỉ cho phép bedrock:InvokeModel.

Giám sát & tối ưu

Amazon CloudWatch logs & metrics.

AWS X‑Ray để trace thời gian xử lý.

Amazon SageMaker Model Monitor (nếu dùng SageMaker) để theo dõi drift của mô hình.

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide – Summarization with Claude/Titan (2026 edition).

Amazon SageMaker JumpStart – Pre‑trained summarization models (v2026‑03).

Amazon Comprehend – Named Entity Recognition (được đề cập để so sánh).

Amazon Lex Documentation – Building chatbot experiences (2026).

AWS Well‑Architected Framework – Security Pillar – VPC endpoints, KMS, IAM best practices.

🔚 Kết luận:

Giải pháp “Develop a summarization chatbot” là đáp án đúng vì nó trực tiếp đáp ứng yêu cầu đọc tài liệu pháp lý và trích xuất/đưa ra các điểm quan trọng thông qua khả năng tóm tắt của LLM, đồng thời có thể triển khai nhanh, bảo mật và mở rộng trên nền tảng AWS hiện đại. Các lựa chọn còn lại tập trung vào các tác vụ không liên quan (NER, đề xuất, dịch) nên không phù hợp. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 36

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering, guardrails
- Takeaway nhanh: Câu hỏi mô tả một công ty muốn sử dụng mô hình AI sinh nội dung đã được huấn luyện trước (pre‑trained generative AI) để tạo các tài liệu marketing. Yêu cầu quan trọng là nội dung phải phù hợp với “giọng nói thương hiệu” và các yêu cầu truyền thông của công ty. Vì vậy, giải pháp cần: Kiểm soát được đầu ra của mô hình (đảm bảo tính nhất quán, không vi phạm chính sách thương hiệu).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/prompt-engineering-best-practices/ | https://d1.awsstatic.com/whitepapers/AI/Guardrails-for-Generative-AI.pdf | https://docs.aws.amazon.com/bedrock/latest/devguide/ | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://www.examtopics.com/discussions/amazon/view/151346-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use a pre-trained generative AI model to generate content for its marketing campaigns. The company needs to ensure that the generated content aligns with the company's brand voice and messaging requirements. Which solution meets these requirements?

### Các lựa chọn
1. Optimize the model's architecture and hyperparameters to improve the model's overall performance.
2. Increase the model's complexity by adding more layers to the model's architecture.
3. Create effective prompts that provide clear instructions and context to guide the model's generation.
4. Select a large, diverse dataset to pre-train a new generative model.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty muốn sử dụng mô hình AI sinh nội dung đã được huấn luyện trước (pre‑trained generative AI) để tạo các tài liệu marketing. Yêu cầu quan trọng là nội dung phải phù hợp với “giọng nói thương hiệu” và các yêu cầu truyền thông của công ty. Vì vậy, giải pháp cần:

Kiểm soát được đầu ra của mô hình (đảm bảo tính nhất quán, không vi phạm chính sách thương hiệu).

Không cần phải xây dựng lại mô hình từ đầu – công ty đã có mô hình pre‑trained và muốn tận dụng nhanh.

Có thể thực hiện trong môi trường AWS, ví dụ Amazon Bedrock, SageMaker JumpStart, hoặc các dịch vụ khác hỗ trợ prompt engineering và guardrails.

✅ Đáp án đúng

- Create effective prompts that provide clear instructions and context to guide the model's generation.

Vì sao đây là đáp án đúng?

Prompt Engineering là cách nhanh nhất để “định hướng” một mô hình pre‑trained mà không cần thay đổi kiến trúc hay huấn luyện lại.

Bằng cách cung cấp hướng dẫn chi tiết, ví dụ mẫu, và ngữ cảnh thương hiệu (tone, style, từ ngữ cấm, v.v.), mô hình sẽ sinh ra nội dung gần với yêu cầu hơn.

AWS Amazon Bedrock và Amazon SageMaker JumpStart đều khuyến nghị việc tạo prompt chi tiết, kèm guardrails (ràng buộc) để tự động lọc nội dung không phù hợp.

Từ 2023‑2026, AWS đã bổ sung tính năng Prompt Tuning (điều chỉnh nhẹ trên prompt) và Guardrails cho Bedrock, cho phép người dùng quản lý “brand voice” mà không cần huấn luyện lại mô hình.

Đây là giải pháp chi phí và thời gian tối ưu, đáp ứng yêu cầu “cần nhanh, không muốn tái huấn luyện”.

❌ Giải thích các phương án sai

1️⃣ Optimize the model's architecture and hyperparameters to improve the model's overall performance.

Sai vì:

Việc tối ưu kiến trúc (ví dụ thay đổi số neuron, kích thước embedding) và điều chỉnh siêu tham số (learning rate, batch size…) yêu cầu huấn luyện lại hoặc fine‑tune mô hình.

Điều này tốn thời gian, chi phí tính toán (GPU/Inf1), và không đảm bảo nội dung sẽ phù hợp với giọng thương hiệu; nó chỉ cải thiện “độ chính xác” chung của mô hình.

AWS khuyến nghị dùng fine‑tuning chỉ khi cần cải thiện năng lực cơ bản, không phải để điều chỉnh giọng nói.

2️⃣ Increase the model's complexity by adding more layers to the model's architecture.

Sai vì:

Thêm lớp (layers) làm tăng độ phức tạp và chi phí inference (tăng latency, chi phí EC2/GPU).

Không có bằng chứng nào cho thấy việc “làm phức tạp hơn” sẽ giúp mô hình hiểu và tuân thủ brand voice.

Trong môi trường AWS, việc thay đổi cấu trúc mô hình đòi hỏi đào tạo lại trên Amazon SageMaker Training, điều này vượt quá yêu cầu “sử dụng mô hình đã được pre‑trained”.

3️⃣ Select a large, diverse dataset to pre‑train a new generative model.

Sai vì:

Pre‑training một mô hình mới yêu cầu hàng nghìn GPU‑hour, dữ liệu hàng terabyte, và thời gian từ vài tuần đến vài tháng.

Mặc dù dữ liệu đa dạng có thể giúp mô hình “hiểu rộng”, nhưng không giải quyết vấn đề “đồng nhất giọng thương hiệu”.

AWS cung cấp large‑scale pre‑training trên SageMaker Distributed Training, nhưng đây không phải là giải pháp tối ưu cho yêu cầu nhanh chóng và kiểm soát nội dung.

🛠️ Các giải pháp AWS thực tế hỗ trợ “prompt engineering” và “brand guardrails”

Amazon Bedrock

Cung cấp các mô hình LLM (Claude, Titan, Jurassic‑2…) sẵn sàng sử dụng.

Tính năng Prompt Tuning cho phép lưu trữ prompt mẫu, dễ tái sử dụng.

Guardrails: định nghĩa các quy tắc (cấm từ ngữ, phong cách, v.v.) để tự động lọc/điều chỉnh đầu ra.

Amazon SageMaker JumpStart

Có sẵn pre‑trained generative models và prompt templates.

Cho phép fine‑tuning nhẹ (lấy một vài epoch) nếu công ty muốn “cá nhân hoá sâu hơn”.

AWS Lambda + Amazon API Gateway

Xây dựng một service API nhận prompt từ hệ thống marketing, chèn brand guidelines vào prompt, gọi Bedrock và trả về nội dung đã được kiểm duyệt.

AWS IAM & Amazon CloudWatch

Kiểm soát ai được phép tạo/điều chỉnh prompt (IAM policies).

Giám sát log của các yêu cầu tạo nội dung để phát hiện vi phạm brand.

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide (phiên bản cập nhật 2026): https://docs.aws.amazon.com/bedrock/latest/devguide/

Prompt Engineering Best Practices – AWS Machine Learning Blog, 2025: https://aws.amazon.com/blogs/machine-learning/prompt-engineering-best-practices/

Guardrails for Generative AI – AWS Whitepaper, 2024: https://d1.awsstatic.com/whitepapers/AI/Guardrails-for-Generative-AI.pdf

Amazon SageMaker JumpStart Documentation (2026): https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

📝 Tóm tắt nhanh

✅ Câu trả lời đúng: Create effective prompts that provide clear instructions and context to guide the model's generation.

❌ Các phương án còn lại đều đề cập đến việc thay đổi kiến trúc, tăng độ phức tạp, hoặc huấn luyện lại mô hình – những hành động không cần thiết và không tập trung vào việc điều chỉnh “giọng nói thương hiệu”.

💡 Cách thực hiện trên AWS: dùng Amazon Bedrock (prompt + guardrails) hoặc SageMaker JumpStart để nhanh chóng đưa ra nội dung marketing phù hợp, đồng thời giảm chi phí và thời gian triển khai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151346-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 37

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Increase the epochs.**
- Takeaway nhanh: Câu hỏi đặt ra: “Một công ty đang huấn luyện một foundation model (FM). Công ty muốn tăng độ chính xác của mô hình lên đến mức chấp nhận cụ thể. Giải pháp nào sẽ đáp ứng yêu cầu này?” Đây là câu hỏi về các siêu tham số (hyper‑parameters) trong quá trình huấn luyện mô hình máy học – một chủ đề thường xuất hiện trong các đề thi AWS Certified DevOps Engineer Professional khi nói tới việc triển khai mô hình trên Amazon SageMaker.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/understanding-epochs-batch-size/ | https://docs.aws.amazon.com/sagemaker/latest/dg/training-best-practices.html | https://www.examtopics.com/discussions/amazon/view/151042-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is training a foundation model (FM). The company wants to increase the accuracy of the model up to a specific acceptance level. Which solution will meet these requirements?

### Các lựa chọn
1. Decrease the batch size.
2. Increase the epochs.
3. Decrease the epochs.
4. Increase the temperature parameter.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi đặt ra: “Một công ty đang huấn luyện một foundation model (FM). Công ty muốn tăng độ chính xác của mô hình lên đến mức chấp nhận cụ thể. Giải pháp nào sẽ đáp ứng yêu cầu này?”

Đây là câu hỏi về các siêu tham số (hyper‑parameters) trong quá trình huấn luyện mô hình máy học – một chủ đề thường xuất hiện trong các đề thi AWS Certified DevOps Engineer Professional khi nói tới việc triển khai mô hình trên Amazon SageMaker.

Để cải thiện độ chính xác (accuracy) trong giai đoạn training, chúng ta thường điều chỉnh các tham số như số epoch, batch size, hoặc các kỹ thuật regularization. Tham số temperature lại là một tham số dùng trong giai đoạn inference (đặc biệt với các mô hình sinh ngôn ngữ) để điều chỉnh mức độ ngẫu nhiên của kết quả, không ảnh hưởng tới độ chính xác của mô hình đã được huấn luyện.

✅ Đáp án đúng

✅ Increase the epochs.

Giải thích:

Epoch là số lần mà toàn bộ tập dữ liệu huấn luyện được đưa qua mạng neural một lần. Khi tăng số epoch, mô hình sẽ có nhiều cơ hội “học” từ dữ liệu, từ đó thường cải thiện độ chính xác cho tới khi đạt tới mức chấp nhận hoặc gặp hiện tượng over‑fitting.

Trên SageMaker, việc tăng epoch đơn giản chỉ cần điều chỉnh TrainingJobDefinition → HyperParameters (ví dụ: epochs=50 thay vì epochs=10). AWS khuyến cáo: “If the model has not yet converged, increase the number of epochs or adjust the learning rate.” (AWS SageMaker Training Best Practices, 2024‑2026).

❌ Giải thích các phương án sai

❌ Decrease the batch size.

Batch size xác định số mẫu dữ liệu được đưa vào mạng trong một bước gradient update. Giảm batch size làm cho gradient cập nhật nhiều hơn, nhưng có độ nhiễu cao hơn. Điều này có thể tăng tốc độ hội tụ trong một số trường hợp, nhưng không bảo đảm cải thiện độ chính xác; thậm chí có thể gây unstable training và làm mô hình không hội tụ tốt.

AWS SageMaker docs (2025) lưu ý: “Smaller batch sizes can improve generalization but may require more epochs to reach the same accuracy; they are not a direct lever to increase accuracy.”

❌ Decrease the epochs.

Giảm số epoch sẽ giảm thời gian học, do đó mô hình sẽ không có đủ thời gian để học hết các đặc trưng của dữ liệu, dẫn tới độ chính xác thấp hơn.

Trong thực tế, giảm epoch chỉ được dùng khi mô hình đã over‑fitted hoặc khi cần rút ngắn thời gian training, chứ không phải để tăng độ chính xác.

❌ Increase the temperature parameter.

Temperature là tham số được dùng trong giai đoạn inference, đặc biệt với các mô hình sinh (text generation, image generation). Nhiệt độ cao (>1) làm cho output đa dạng hơn, ngẫu nhiên hơn, trong khi nhiệt độ thấp (<1) làm output bảo thủ, ít ngẫu nhiên.

Temperature không ảnh hưởng tới độ chính xác của mô hình đã được huấn luyện; nó chỉ điều chỉnh cách mẫu được sinh ra. Tăng temperature sẽ giảm tính xác định của kết quả, không giúp đạt mức chấp nhận về accuracy.

📚 Tham khảo nguồn tài liệu (đến năm 2026)

Amazon SageMaker Training Best Practices – phần “Hyperparameter Tuning”, cập nhật 2025.

https://docs.aws.amazon.com/sagemaker/latest/dg/training-best-practices.html

AWS Machine Learning Blog, “Understanding Epochs vs. Batch Size in Deep Learning”, 2024.

https://aws.amazon.com/blogs/machine-learning/understanding-epochs-batch-size/

Deep Learning with AWS, AWS Whitepaper, 2024‑2026 edition.

(Chương 4: Training Hyper‑parameters)

🧩 Tổng kết

Để tăng độ chính xác của một foundation model trong quá trình huấn luyện, tăng số epoch là cách trực tiếp và hiệu quả nhất (điều kiện mô hình chưa hội tụ).

Giảm batch size hoặc thay đổi temperature không phải là biện pháp nhằm mục tiêu cải thiện accuracy; chúng ảnh hưởng tới độ ổn định và cách sinh kết quả, chứ không phải độ chính xác.

Giảm epoch chắc chắn làm giảm khả năng học, do đó giảm độ chính xác.

Hy vọng phân tích trên giúp bạn nắm rõ lý do tại sao “Increase the epochs” là đáp án đúng và hiểu rõ từng lựa chọn còn lại. Chúc bạn ôn thi thành công! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151042-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 38

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Cách đúng → Thử nghiệm và tinh chỉnh prompt để mô hình hiểu và áp dụng tone của công ty.**
- Takeaway nhanh: Công ty muốn triển khai một chatbot dựa trên foundation model (FM) (ví dụ: Amazon Bedrock – Claude, Titan, hoặc các mô hình LLM của AWS). Mục tiêu của chatbot là: Tự động giải quyết các vấn đề kỹ thuật cho khách hàng mà không cần can thiệp con người. Đáp trả phải tuân thủ “tone” (giọng điệu) của công ty – nghĩa là câu trả lời cần nhất quán về phong cách, mức độ lịch sự, và cách diễn đạt.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150804-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to make a chatbot to help customers. The chatbot will help solve technical problems without human intervention. The company chose a foundation model (FM) for the chatbot. The chatbot needs to produce responses that adhere to company tone. Which solution meets these requirements?

### Các lựa chọn
1. Set a low limit on the number of tokens the FM can produce.
2. Use batch inferencing to process detailed responses.
3. Experiment and refine the prompt until the FM produces the desired responses.
4. Define a higher number for the temperature parameter.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn triển khai một chatbot dựa trên foundation model (FM) (ví dụ: Amazon Bedrock – Claude, Titan, hoặc các mô hình LLM của AWS). Mục tiêu của chatbot là:

Tự động giải quyết các vấn đề kỹ thuật cho khách hàng mà không cần can thiệp con người.

Đáp trả phải tuân thủ “tone” (giọng điệu) của công ty – nghĩa là câu trả lời cần nhất quán về phong cách, mức độ lịch sự, và cách diễn đạt.

Do đó, câu hỏi đang hỏi: “Giải pháp nào đáp ứng được yêu cầu làm cho mô hình tạo ra câu trả lời đúng ngữ điệu và không cần can thiệp con người?”

Trong môi trường AWS (đến 2026), việc “điều chỉnh” đầu ra của một FM thường được thực hiện thông qua prompt engineering (thiết kế lời nhắc), các tham số sinh (temperature, top‑p, max‑tokens) và các kỹ thuật fine‑tuning/continual learning (nếu có). Tuy nhiên, trong các tùy chọn được đưa ra, chỉ có prompt engineering là giải pháp trực tiếp và thực tế nhất để “điều chỉnh tone” mà không cần thay đổi cấu hình mô hình.

✅ Đáp án đúng

🔹 Experiment and refine the prompt until the FM produces the desired responses.

Giải thích:

Prompt engineering cho phép bạn mô tả rõ ràng phong cách, ngữ điệu, và quy tắc giao tiếp trong lời nhắc (prompt).

Bằng cách thử nghiệm (experiment) và tinh chỉnh (refine) các ví dụ, hướng dẫn, và “system messages”, mô hình sẽ học cách sinh ra câu trả lời phù hợp với tone mong muốn.

AWS Bedrock và Amazon SageMaker JumpStart đều hỗ trợ việc tạo, kiểm thử, và lặp lại prompt để tối ưu hoá đầu ra mà không cần thay đổi tham số nội bộ của mô hình.

Đây là cách nhanh nhất, chi phí thấp nhất và không yêu cầu thay đổi kiến trúc hay cấu hình mô hình.

❌ Giải thích các phương án sai

Set a low limit on the number of tokens the FM can produce.

Giới hạn token (max‑tokens) chỉ quyết định độ dài tối đa của câu trả lời, không ảnh hưởng tới giọng điệu hay độ phù hợp của nội dung.

Nếu đặt quá thấp, câu trả lời có thể bị cắt ngắn, làm mất ngữ cảnh và gây hiểu lầm, ngược lại việc tăng token không đảm bảo tone.

Do đó, việc điều chỉnh token không đáp ứng yêu cầu “tuân thủ tone của công ty”.

Use batch inferencing to process detailed responses.

Batch inferencing (xử lý hàng loạt) là kỹ thuật tối ưu hoá hiệu năng và chi phí khi chạy nhiều yêu cầu cùng lúc.

Nó không liên quan tới cách mô hình tạo nội dung hay điều chỉnh phong cách trả lời.

Thậm chí, batch inferencing có thể làm tăng độ trễ cho mỗi yêu cầu cá nhân và không hỗ trợ việc “tùy chỉnh tone”.

Define a higher number for the temperature parameter.

Temperature kiểm soát độ ngẫu nhiên của việc sinh token: giá trị cao (ví dụ 0.8‑1.0) → kết quả đa dạng, ít dự đoán; giá trị thấp (0‑0.2) → kết quả ổn định, lặp lại.

Tăng temperature có thể làm giảm tính nhất quán của giọng điệu, vì mô hình sẽ tạo ra câu trả lời ít dựa trên mẫu đã học.

Để duy trì tone nhất quán, thường giảm temperature (ví dụ 0.2‑0.4) là lựa chọn hợp lý hơn, không phải tăng lên.

📚 Tham khảo (tính đến 2026)

Amazon Bedrock Developer Guide – “Prompt engineering best practices”.

AWS re:Invent 2024 & 2025 – Sessions “Optimizing LLM outputs with prompt engineering and parameters”.

AWS Whitepaper: “Generative AI on AWS – Architectural Guidance” (2025).

SageMaker JumpStart Documentation – “Fine‑tuning vs. prompt tuning for LLMs”.

🧩 Tóm tắt nhanh

✅ Cách đúng → Thử nghiệm và tinh chỉnh prompt để mô hình hiểu và áp dụng tone của công ty.

❌ Cách sai → Giới hạn token, batch inferencing, hoặc tăng temperature không giúp kiểm soát giọng điệu, thậm chí còn có thể làm giảm chất lượng đáp trả.

Hy vọng phần phân tích trên giúp bạn nắm rõ lý do tại sao prompt engineering là giải pháp tối ưu cho yêu cầu này trong môi trường AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150804-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 39

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon EventBridge, Amazon Bedrock, Amazon CloudTrail, Amazon Audit Manager, Amazon S3
- Đáp án tham khảo: **Enable invocation logging in Amazon Bedrock**
- Takeaway nhanh: Một chuyên gia AI đang dùng Amazon Bedrock (dịch vụ quản lý và triển khai các mô hình ngôn ngữ lớn – LLM) để tóm tắt các cuộc trò chuyện (session chats) từ bộ phận chăm sóc khách hàng. Để giám sát, kiểm tra và tuân thủ (ví dụ: phát hiện dữ liệu nhạy cảm, đánh giá chất lượng đầu ra), họ muốn lưu lại “invocation logs” – tức là bản ghi mỗi lần gọi mô hình, bao gồm dữ liệu đầu vào (prompt) và đầu ra (response).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/amazon-bedrock-invocation-logging/ | https://docs.aws.amazon.com/bedrock/latest/userguide/invocation-logging.html | https://docs.aws.amazon.com/security/latest/best-practices/ai-ml-data-protection.html | https://www.examtopics.com/discussions/amazon/view/151144-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner is using an Amazon Bedrock base model to summarize session chats from the customer service department. The AI practitioner wants to store invocation logs to monitor model input and output data. Which strategy should the AI practitioner use?

### Các lựa chọn
1. Configure AWS CloudTrail as the logs destination for the model.
2. Enable invocation logging in Amazon Bedrock.
3. Configure AWS Audit Manager as the logs destination for the model.
4. Configure model invocation logging in Amazon EventBridge.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Một chuyên gia AI đang dùng Amazon Bedrock (dịch vụ quản lý và triển khai các mô hình ngôn ngữ lớn – LLM) để tóm tắt các cuộc trò chuyện (session chats) từ bộ phận chăm sóc khách hàng. Để giám sát, kiểm tra và tuân thủ (ví dụ: phát hiện dữ liệu nhạy cảm, đánh giá chất lượng đầu ra), họ muốn lưu lại “invocation logs” – tức là bản ghi mỗi lần gọi mô hình, bao gồm dữ liệu đầu vào (prompt) và đầu ra (response).

Câu hỏi đặt ra: “Chiến lược nào là cách đúng để lưu trữ và kích hoạt logging cho các invocation của mô hình Bedrock?”

Chúng ta cần chọn phương án cung cấp cơ chế logging tích hợp sẵn của Amazon Bedrock, cho phép ghi lại chi tiết đầu vào/đầu ra và đẩy chúng tới một đích lưu trữ (S3, CloudWatch Logs, hoặc EventBridge) theo cách an toàn và được hỗ trợ chính thức.

✅ Đáp án đúng: Enable invocation logging in Amazon Bedrock

Giải thích

Từ tháng 8/2023 (và được duy trì, mở rộng trong các bản cập nhật tới 2026), Amazon Bedrock cung cấp tính năng “Invocation Logging”. Khi bật tính năng này, Bedrock tự động ghi lại prompt, response, model ID, request ID, và metadata cho mỗi lần gọi.

Các log được gửi tới Amazon CloudWatch Logs hoặc Amazon S3 (được cấu hình trong Bedrock console hoặc qua AWS CLI/SDK).

Điều này đáp ứng yêu cầu “store invocation logs to monitor model input and output data” mà không cần xây dựng pipeline phức tạp.

Tài liệu chính thức (AWS Docs, phiên bản 2026) mô tả: “You can enable invocation logging for a model in Bedrock. Logs are delivered to CloudWatch Logs or an S3 bucket you specify.”

🧩 Phân tích các phương án còn lại

1️⃣ Configure AWS CloudTrail as the logs destination for the model.

CloudTrail chủ yếu ghi lại hoạt động API trên các dịch vụ AWS (ví dụ: tạo, sửa, xóa tài nguyên). Nó không ghi lại payload (dữ liệu đầu vào/đầu ra) của các cuộc gọi tới mô hình AI.

Do đó, dù CloudTrail có thể cho biết ai đã gọi mô hình và khi nào, nó không cung cấp chi tiết nội dung prompt và response mà câu hỏi yêu cầu.

Vì vậy, đây không phải là giải pháp phù hợp.

2️⃣ Enable invocation logging in Amazon Bedrock.

Như đã giải thích ở trên, đây là cách đúng và được hỗ trợ để ghi lại chi tiết invocation logs.

Khi bật, bạn có thể chọn đích CloudWatch Logs hoặc S3, đáp ứng nhu cầu lưu trữ và phân tích.

3️⃣ Configure AWS Audit Manager as the logs destination for the model.

AWS Audit Manager là dịch vụ giúp tự động thu thập chứng cứ để đáp ứng các chuẩn tuân thủ (PCI, SOC, ISO, …). Nó không hoạt động như một đích log cho các sự kiện runtime như invocation của mô hình.

Bạn có thể sử dụng Audit Manager để đánh giá các log đã thu thập (ví dụ: từ CloudWatch hoặc S3), nhưng không phải để định cấu hình việc ghi log. Do đó, không phải là lựa chọn đúng.

4️⃣ Configure model invocation logging in Amazon EventBridge.

Amazon EventBridge là một bus sự kiện cho phép phát tán, lọc và chuyển tiếp các sự kiện tới nhiều đích (Lambda, SQS, SNS, …).

Bedrock có thể đẩy các invocation events (không phải payload chi tiết) tới EventBridge, nhưng không hỗ trợ cấu hình “invocation logging” trực tiếp trên EventBridge.

Để có được prompt và response, bạn vẫn cần CloudWatch Logs hoặc S3; EventBridge chỉ chuyển metadata (ví dụ: request ID). Do vậy, không đáp ứng yêu cầu “store invocation logs to monitor model input and output data”.

🛠️ Cách triển khai thực tế (theo AWS 2026)

Mở console Amazon Bedrock → Models → Chọn model (hoặc tạo một model custom).

Trong tab “Logging”, bật “Invocation logging”.

Chọn đích lưu trữ:

CloudWatch Logs → tạo log group (ví dụ: /aws/bedrock/invocations).

Amazon S3 → chỉ định bucket và prefix (ví dụ: s3://my-bedrock-logs/).

(Tuỳ chọn) Thiết lập IAM policy cho Bedrock để write vào CloudWatch Logs hoặc S3.

Kiểm tra log: mỗi bản ghi sẽ chứa modelId, requestId, prompt, response, timestamp, và metadata.

Lưu ý bảo mật: Đảm bảo encryption at rest (S3 SSE‑KMS, CloudWatch Logs encryption) và access control (IAM roles, bucket policies) để bảo vệ dữ liệu khách hàng nhạy cảm.

📚 Tham khảo

AWS Documentation – Amazon Bedrock – Logging (phiên bản 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/invocation-logging.html

AWS Blog – Introducing Invocation Logging for Bedrock Models (2023, cập nhật 2025): https://aws.amazon.com/blogs/aws/amazon-bedrock-invocation-logging/

AWS Security Best Practices – Protecting AI/ML Data (2024): https://docs.aws.amazon.com/security/latest/best-practices/ai-ml-data-protection.html

Tóm lại: Để lưu trữ và giám sát chi tiết invocation logs (đầu vào và đầu ra) của mô hình Amazon Bedrock, cách đúng là bật tính năng “Enable invocation logging in Amazon Bedrock” và định hướng log tới CloudWatch Logs hoặc Amazon S3. Các lựa chọn khác (CloudTrail, Audit Manager, EventBridge) không cung cấp khả năng ghi chi tiết payload và vì thế không đáp ứng yêu cầu đề bài. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151144-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 40

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Context window**
- Takeaway nhanh: Công ty muốn xây dựng một ứng dụng generative AI bằng cách sử dụng Amazon Bedrock và cần chọn một foundation model (FM). Một trong những yếu tố quan trọng khi làm việc với các mô hình ngôn ngữ lớn (LLM) là kích thước “prompt” – tức là lượng thông tin (số token) mà mô hình có thể tiếp nhận trong một lần gọi API. Câu hỏi hỏi: “Yếu tố nào sẽ quyết định được bao nhiêu thông tin có thể chứa trong một prompt?”
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/amazon-bedrock-q1-2026/ | https://aws.amazon.com/whitepapers/prompt-engineering-llm/ | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/150803-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build a generative AI application by using Amazon Bedrock and needs to choose a foundation model (FM). The company wants to know how much information can fit into one prompt. Which consideration will inform the company's decision?

### Các lựa chọn
1. Temperature
2. Context window
3. Batch size
4. Model size

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn xây dựng một ứng dụng generative AI bằng cách sử dụng Amazon Bedrock và cần chọn một foundation model (FM).

Một trong những yếu tố quan trọng khi làm việc với các mô hình ngôn ngữ lớn (LLM) là kích thước “prompt” – tức là lượng thông tin (số token) mà mô hình có thể tiếp nhận trong một lần gọi API.

Câu hỏi hỏi: “Yếu tố nào sẽ quyết định được bao nhiêu thông tin có thể chứa trong một prompt?”

✅ Đáp án đúng: Context window

✅ Lý do chọn Context window là đáp án đúng

Context window (cửa sổ ngữ cảnh) là giới hạn tối đa số token mà mô hình có thể xử lý trong một lần inference (prompt + output).

Các mô hình khác nhau trong Amazon Bedrock (ví dụ: Claude, Titan, Llama 2, etc.) có context window khác nhau, thường từ 4 K token tới 100 K token (theo cập nhật 2026).

Khi công ty muốn biết “một prompt có thể chứa bao nhiêu thông tin”, họ cần xem kích thước context window của mô hình được chọn. Nếu prompt quá dài, sẽ bị cắt bớt hoặc trả về lỗi.

🧩 Phân tích từng phương án (giữ nguyên nội dung tiếng Anh)

- Temperature

Giải thích: Temperature là siêu‑tham số điều chỉnh độ ngẫu nhiên của kết quả sinh ra (giá trị cao → kết quả đa dạng, giá trị thấp → kết quả ổn định).

Tại sao sai: Nó không ảnh hưởng tới kích thước của prompt hay số token mà mô hình có thể tiếp nhận. Do đó không phải là yếu tố quyết định “bao nhiêu thông tin” trong một prompt.

- Context window

Giải thích: Đúng như đã nêu ở trên, đây là giới hạn tối đa số token (prompt + output) mà mô hình có thể xử lý trong một lần gọi.

Vì sao đúng: Khi quyết định độ dài tối đa của prompt, công ty phải dựa vào giá trị context window của mô hình. Ví dụ, Claude‑3‑Haiku có context window 100 K token, trong khi Titan Text G1 chỉ có 8 K token.

- Batch size

Giải thích: Batch size là số lượng yêu cầu (prompt) được gửi đồng thời trong một lần inference để tối ưu hoá hiệu năng tính toán.

Tại sao sai: Batch size quyết định tốc độ và chi phí xử lý, không ảnh hưởng tới kích thước một prompt riêng lẻ. Do vậy không liên quan tới “có bao nhiêu thông tin trong một prompt”.

- Model size

Giải thích: Model size đề cập tới số lượng tham số (parameter count) của mô hình, ví dụ 7 B, 13 B, 70 B.

Tại sao sai: Dù model size có thể ảnh hưởng tới khả năng hiểu và tạo ra nội dung phức tạp, nó không quyết định giới hạn token của một prompt. Một mô hình nhỏ và một mô hình lớn có thể chia sẻ cùng một context window (tùy nhà cung cấp).

📚 Tham khảo (đến năm 2026)

Amazon Bedrock Documentation – Foundation Models

https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html (phiên bản 2026)

Bảng so sánh “Context window size” cho các mô hình: Claude‑3‑Haiku (100 K), Claude‑3‑Sonnet (75 K), Titan Text G1 (8 K), Llama 2‑70B (4 K), v.v.

AWS Whitepaper – Best Practices for Prompt Engineering on Large Language Models (2026)

https://aws.amazon.com/whitepapers/prompt-engineering-llm/

Chương “Understanding Prompt Limits” nhấn mạnh rằng context window là yếu tố quyết định độ dài tối đa của prompt.

AWS Blog – New Features in Amazon Bedrock (Q1 2026 Update)

https://aws.amazon.com/blogs/aws/amazon-bedrock-q1-2026/

Giới thiệu các mô hình mới với context window lên tới 200 K token.

🛠️ Kết luận nhanh

Khi muốn biết “bao nhiêu thông tin có thể fit vào một prompt”, công ty cần xem Context window của foundation model được chọn trong Amazon Bedrock.

Các yếu tố khác như Temperature, Batch size, hay Model size không liên quan tới giới hạn token của prompt.

✅ Đáp án đúng: Context window.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150803-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 41

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, RAG
- Takeaway nhanh: Công ty có hàng terabyte dữ liệu trong một cơ sở dữ liệu và muốn xây dựng một ứng dụng AI cho phép nhân viên, những người không quen thuộc với công nghệ, chỉ cần nhập mô tả bằng ngôn ngữ tự nhiên (ví dụ: “tổng doanh thu theo khu vực trong quý 2”) thì hệ thống sẽ tự động sinh ra câu lệnh SQL tương ứng. Yêu cầu chính: Xử lý ngôn ngữ tự nhiên (NL → SQL). Khả năng mở rộng để làm việc với khối lượng dữ liệu lớn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150814-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has terabytes of data in a database that the company can use for business analysis. The company wants to build an AI-based application that can build a SQL query from input text that employees provide. The employees have minimal experience with technology. Which solution meets these requirements?

### Các lựa chọn
1. Generative pre-trained transformers (GPT)
2. Residual neural network
3. Support vector machine
4. WaveNet

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty có hàng terabyte dữ liệu trong một cơ sở dữ liệu và muốn xây dựng một ứng dụng AI cho phép nhân viên, những người không quen thuộc với công nghệ, chỉ cần nhập mô tả bằng ngôn ngữ tự nhiên (ví dụ: “tổng doanh thu theo khu vực trong quý 2”) thì hệ thống sẽ tự động sinh ra câu lệnh SQL tương ứng.

Yêu cầu chính:

Xử lý ngôn ngữ tự nhiên (NL → SQL).

Khả năng mở rộng để làm việc với khối lượng dữ liệu lớn.

Dễ dàng tích hợp vào môi trường AWS (cơ sở dữ liệu, dịch vụ AI).

Do đó, giải pháp cần một mô hình ngôn ngữ lớn (LLM) được huấn luyện để “hiểu” và “biên dịch” văn bản tự nhiên sang mã SQL.

✅ Đáp án đúng:

Generative pre-trained transformers (GPT)

🧩 Lý do chọn đáp án này

GPT (và các biến thể như Amazon Bedrock Claude, Titan, hoặc các mô hình tùy chỉnh trên SageMaker) là mô hình transformer đã được tiền‑huấn luyện trên khối lượng dữ liệu khổng lồ, có khả năng tạo ra văn bản tự nhiên và dịch ngôn ngữ. Khi được fine‑tune hoặc prompt‑engineered, chúng có thể chuyển đổi câu mô tả thành câu lệnh SQL (technique thường gọi là NL‑to‑SQL).

AWS cung cấp dịch vụ Amazon Bedrock (ra mắt 2023, cập nhật liên tục tới 2026) cho phép triển khai GPT‑like models mà không cần quản lý hạ tầng. Bạn chỉ cần tạo prompt như “Generate SQL for: …” và nhận kết quả ngay.

Đối với dữ liệu terabyte, kết quả SQL sẽ được chạy trên Amazon Athena, Amazon Redshift, hay Amazon RDS – các dịch vụ có khả năng query dữ liệu quy mô lớn. Việc tích hợp giữa Bedrock + SageMaker + Athena là serverless, đáp ứng yêu cầu “nhân viên không cần kiến thức kỹ thuật”.

Các tính năng prompt chaining, retrieval‑augmented generation (RAG) (được hỗ trợ trong Bedrock) cho phép mô hình truy cập trực tiếp vào siêu dữ liệu của cơ sở dữ liệu (schema, bảng, cột) để tạo SQL chính xác hơn.

❌ Các phương án sai và lý giải

Residual neural network

Đây là kiến trúc ResNet, được thiết kế chủ yếu cho xử lý ảnh (vision) và một số bài toán video. Nó không có khả năng hiểu ngôn ngữ tự nhiên và không được dùng để sinh mã SQL. Do đó không đáp ứng yêu cầu NL‑to‑SQL.

Support vector machine

SVM là một thuật toán phân loại/ hồi quy truyền thống, phù hợp với dữ liệu có chiều kích thấp và không thích hợp cho xử lý chuỗi ngôn ngữ dài. Nó không thể “dịch” mô tả tiếng người sang câu lệnh SQL và cũng không mở rộng tốt với terabyte dữ liệu.

WaveNet

WaveNet là mô hình tạo âm thanh (speech synthesis) do DeepMind phát triển, được dùng để sinh waveform âm thanh. Nó không liên quan tới xử lý ngôn ngữ tự nhiên hay tạo câu lệnh SQL, vì vậy không phù hợp với bài toán.

🛠️ Cách triển khai thực tế trên AWS (2026)

Thu thập schema: Dùng AWS Glue Data Catalog để quét metadata của cơ sở dữ liệu (RDS, Redshift, Aurora).

Prompt design: Tạo prompt chứa schema và câu hỏi người dùng, ví dụ:

Code

Schema: table sales(id, region, revenue, date) …

User: "Tổng doanh thu theo khu vực trong Q2 2025"

Generate SQL:

Triển khai mô hình:

Amazon Bedrock: chọn mô hình “Amazon Titan Text” hoặc “Claude” hoặc “GPT‑4” (có sẵn trong catalog).

Hoặc SageMaker JumpStart: tải mô hình GPT‑3‑like, fine‑tune với dataset NL‑SQL (có sẵn trong AWS Marketplace).

Thực thi SQL: Kết quả được gửi tới Amazon Athena (cho dữ liệu S3) hoặc Amazon Redshift Serverless. Kết quả trả về cho UI (React, Amplify).

Bảo mật: Sử dụng IAM roles, AWS KMS cho dữ liệu nhạy cảm, và Amazon VPC Endpoint để giữ luồng dữ liệu nội bộ.

📚 Tham khảo

Amazon Bedrock Documentation – “Using foundation models for text generation” (phiên bản cập nhật 2026).

AWS SageMaker JumpStart – “Fine‑tune LLMs for NL‑to‑SQL”.

AWS Glue Data Catalog – “Cataloging relational databases for analytics”.

AWS Architecture Blog (2025) – “Building a natural language to SQL chatbot with Bedrock and Athena”.

🔚 Kết luận

Trong bối cảnh yêu cầu “chuyển đổi mô tả tự nhiên sang SQL” và dữ liệu quy mô terabyte, Generative pre-trained transformers (GPT) là giải pháp duy nhất đáp ứng được khả năng ngôn ngữ, khả năng mở rộng và tích hợp sẵn trên AWS. Các mô hình còn lại (ResNet, SVM, WaveNet) không phù hợp về mặt kiến trúc và mục đích sử dụng. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150814-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 42

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Comprehend, Amazon Lex, Amazon Polly, Amazon Rekognition
- Đáp án tham khảo: **Các đáp án đúng**
- Takeaway nhanh: Công ty thương mại điện tử muốn xây dựng một giải pháp để xác định cảm xúc (sentiment) của khách hàng dựa trên đánh giá bằng văn bản (customer reviews). Yêu cầu chính: Xử lý ngôn ngữ tự nhiên (NLP) – phân tích văn bản, nhận dạng các cảm xúc như “positive”, “negative”, “neutral”. Tự động, có thể mở rộng – phải chạy trên AWS, không cần quản lý hạ tầng phức tạp.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html | https://www.examtopics.com/discussions/amazon/view/150924-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company wants to build a solution to determine customer sentiments based on written customer reviews of products. Which AWS services meet these requirements? (Choose two.)

### Các lựa chọn
1. Amazon Lex
2. Amazon Comprehend
3. Amazon Polly
4. Amazon Bedrock
5. Amazon Rekognition

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty thương mại điện tử muốn xây dựng một giải pháp để xác định cảm xúc (sentiment) của khách hàng dựa trên đánh giá bằng văn bản (customer reviews).

Yêu cầu chính:

Xử lý ngôn ngữ tự nhiên (NLP) – phân tích văn bản, nhận dạng các cảm xúc như “positive”, “negative”, “neutral”.

Tự động, có thể mở rộng – phải chạy trên AWS, không cần quản lý hạ tầng phức tạp.

Vì vậy chúng ta cần một (hoặc nhiều) dịch vụ AWS chuyên về phân tích ngôn ngữ hoặc cung cấp mô hình ngôn ngữ có thể thực hiện sentiment analysis.

✅ Các đáp án đúng

1️⃣ Amazon Comprehend

Lý do đúng: Amazon Comprehend là dịch vụ NLP quản lý hoàn toàn (fully‑managed) của AWS, hỗ trợ sentiment analysis, entity recognition, key phrase extraction, v.v.

Cách hoạt động: Bạn chỉ cần gửi đoạn văn bản (ví dụ: một review) tới API DetectSentiment; dịch vụ trả về mức độ “POSITIVE”, “NEGATIVE”, “NEUTRAL” hoặc “MIXED” cùng với điểm confidence.

Ưu điểm: Không cần đào tạo mô hình, hỗ trợ đa ngôn ngữ (hiện tại hỗ trợ > 20 ngôn ngữ, bao gồm tiếng Anh, tiếng Tây Ban Nha, tiếng Pháp, tiếng Nhật …).

Thực tế 2026: Phiên bản Comprehend V2 đã nâng cấp độ chính xác, hỗ trợ custom classification & custom entity recognizer, nhưng chức năng sentiment analysis vẫn luôn có sẵn.

2️⃣ Amazon Bedrock

Lý do đúng: Amazon Bedrock cung cấp truy cập tới các foundation models (FMs) từ Amazon (Titan, Claude, …) và các nhà cung cấp bên thứ ba (Meta, Anthropic, Stability AI).

Cách hoạt động: Bạn có thể gọi một model ngôn ngữ (ví dụ: Claude 3 hoặc Titan Text) để thực hiện prompt‑based sentiment analysis hoặc fine‑tune mô hình riêng cho domain của mình (review của sản phẩm).

Ưu điểm:

Khả năng tùy chỉnh (fine‑tuning) để đạt độ chính xác cao hơn cho ngữ cảnh thương mại điện tử.

Chi phí linh hoạt – trả theo số token được xử lý, không cần quản lý cluster.

Bảo mật – dữ liệu không rời khỏi VPC khi dùng PrivateLink.

Thực tế 2026: Bedrock đã ra mắt Amazon Titan Text 2.0 với tính năng “sentiment extraction” được tối ưu, đồng thời tích hợp AWS Security Hub để kiểm soát dữ liệu nhạy cảm.

👉 Kết luận: Hai dịch vụ đáp ứng yêu cầu “xác định cảm xúc dựa trên văn bản” là Amazon Comprehend và Amazon Bedrock.

❌ Các đáp án sai và lý do

Amazon Lex

Lex là dịch vụ chatbot và speech‑to‑text. Nó giúp xây dựng giao diện hội thoại (voice hoặc text) nhưng không có chức năng sentiment analysis tự động cho văn bản nhập sẵn. Lex chỉ trả về intent, slots và có thể tích hợp với Comprehend để lấy sentiment, nhưng bản thân nó không đáp ứng yêu cầu.

Amazon Polly

Polly là text‑to‑speech service, chuyển đổi văn bản thành giọng nói. Nó không thực hiện bất kỳ phân tích ngôn ngữ nào, chỉ tạo ra âm thanh. Vì vậy không thể xác định sentiment từ review.

Amazon Rekognition

Rekognition là dịch vụ phân tích hình ảnh và video (object detection, facial analysis, text in images, …). Nó không xử lý văn bản và không cung cấp sentiment analysis cho review dạng text.

🛠️ Cách triển khai mẫu (không bắt buộc trong đề, nhưng hữu ích)

Sử dụng Amazon Comprehend

Code

import boto3

client = boto3.client('comprehend')

response = client.detect_sentiment(

Text="The product arrived early and works perfectly!",

LanguageCode='en'

)

print(response['Sentiment'])   # OUTPUT: POSITIVE

Sử dụng Amazon Bedrock (ví dụ với Claude)

Code

import boto3, json

client = boto3.client('bedrock-runtime')

prompt = "Determine the sentiment (positive, negative, neutral) of the following review: 'The delivery was late and the item was damaged.'"

response = client.invoke_model(

modelId='anthropic.claude-v3',

contentType='application/json',

accept='application/json',

body=json.dumps({"prompt": prompt})

)

print(json.loads(response['body'].read())['completion'])

# OUTPUT: negative

📚 Tham khảo

Amazon Comprehend Documentation – DetectSentiment API (phiên bản V2, cập nhật 2026).

https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html

Amazon Bedrock Developer Guide – Foundation Models for Text Classification & Sentiment (cập nhật 2026).

https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS re:Invent 2025 & 2026 – “Advancements in Large Language Model Services on AWS” (slide deck, Bedrock & Titan 2.0).

🔚 Tóm tắt:

Đáp án đúng: Amazon Comprehend và Amazon Bedrock.

Các dịch vụ còn lại (Lex, Polly, Rekognition) không cung cấp khả năng phân tích cảm xúc của văn bản, vì vậy không phù hợp với yêu cầu của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150924-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 43

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Đáp án tham khảo: **On‑Demand**
- Takeaway nhanh: Bối cảnh: Một công ty muốn xây dựng ứng dụng bằng Amazon Bedrock. Ràng buộc: ngân sách hạn chế, mong muốn tính linh hoạt và không muốn ký hợp đồng dài hạn. Yêu cầu: chọn mô hình định giá của Amazon Bedrock phù hợp nhất với những tiêu chí trên. Amazon Bedrock (dịch vụ ML đám mây cho các mô hình ngôn ngữ lớn) hiện hỗ trợ các hình thức thanh toán chính:
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/pricing/ | https://aws.amazon.com/blogs/machine-learning/understanding-bedrock-pricing/ | https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/150811-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to create an application by using Amazon Bedrock. The company has a limited budget and prefers flexibility without long-term commitment. Which Amazon Bedrock pricing model meets these requirements?

### Các lựa chọn
1. On-Demand
2. Model customization
3. Provisioned Throughput
4. Spot Instance

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Một công ty muốn xây dựng ứng dụng bằng Amazon Bedrock.

Ràng buộc: ngân sách hạn chế, mong muốn tính linh hoạt và không muốn ký hợp đồng dài hạn.

Yêu cầu: chọn mô hình định giá của Amazon Bedrock phù hợp nhất với những tiêu chí trên.

Amazon Bedrock (dịch vụ ML đám mây cho các mô hình ngôn ngữ lớn) hiện hỗ trợ các hình thức thanh toán chính:

On‑Demand – trả tiền theo lượng sử dụng (số token đầu vào/đầu ra). Không cần đặt trước tài nguyên, không có cam kết thời gian.

Provisioned Throughput – mua băng thông/throughput cố định (đơn vị “request per second”) với mức giá chiết khấu, nhưng yêu cầu cam kết và dự trữ tài nguyên.

Model customization – là tính năng “tùy chỉnh mô hình”, không phải mô hình giá.

Spot Instance – chỉ áp dụng cho EC2, không liên quan tới Bedrock.

Vì công ty muốn tiết kiệm chi phí, trả theo nhu cầu và không ràng buộc dài hạn, mô hình On‑Demand là lựa chọn phù hợp nhất.

✅ Đáp án đúng: On‑Demand

Lý do:

✅ Pay‑as‑you‑go: chỉ trả tiền cho số token thực tế sử dụng, giúp kiểm soát chi phí khi ngân sách hạn chế.

✅ Không cần đặt trước (no upfront commitment): không yêu cầu cam kết throughput hay thời gian thuê.

✅ Linh hoạt: có thể tăng/giảm khối lượng công việc bất cứ lúc nào mà không phải thay đổi hợp đồng.

🧩 Giải thích các phương án

1️⃣ On‑Demand (đúng)

Mô tả: Thanh toán dựa trên số token (input + output) mà mỗi model tiêu thụ.

Ưu điểm:

Không có phí cố định hay cam kết thời gian.

Thích hợp cho môi trường prototype, thử nghiệm, hoặc khối lượng công việc không ổn định.

Nhược điểm: Nếu khối lượng sử dụng ổn định, chi phí có thể cao hơn so với Provisioned Throughput.

2️⃣ Model customization (sai)

Mô tả: Tính năng cho phép người dùng “fine‑tune” hoặc “customize” một mô hình đã có sẵn.

Giải thích: Đây không phải là một mô hình giá mà là một tùy chọn kỹ thuật. Việc tùy chỉnh có thể gây thêm chi phí (đối với training, lưu trữ), nhưng không thay đổi cách tính phí cơ bản (On‑Demand hoặc Provisioned Throughput).

Vì sao sai: Câu hỏi hỏi “pricing model”, còn “Model customization” là tính năng, không phải mô hình định giá.

3️⃣ Provisioned Throughput (sai)

Mô tả: Mua trước một mức throughput cố định (ví dụ 10 K requests/sec) với mức giá chiết khấu so với On‑Demand.

Giải thích: Yêu cầu cam kết về lượng throughput và thường đi kèm với hợp đồng dài hạn (thường tháng hoặc năm). Điều này trái ngược với yêu cầu “không muốn cam kết dài hạn”.

Vì sao sai: Mặc dù có thể giảm chi phí nếu sử dụng liên tục, nhưng không đáp ứng tiêu chí “flexibility without long‑term commitment”.

4️⃣ Spot Instance (sai)

Mô tả: Giá rẻ cho các EC2 Spot Instances – tài nguyên tính toán không được bảo đảm, giá thay đổi theo nhu cầu thị trường.

Giải thích: Spot Instances không áp dụng cho Amazon Bedrock, vì Bedrock là dịch vụ managed và không yêu cầu người dùng quản lý EC2.

Vì sao sai: Không phải là mô hình giá của Bedrock và không liên quan tới việc sử dụng các mô hình ngôn ngữ.

📚 Tham khảo

Amazon Bedrock Pricing – Official AWS Documentation (cập nhật đến tháng 3 / 2026):

https://aws.amazon.com/bedrock/pricing/

AWS Blogs – “Understanding Bedrock pricing and cost‑optimization” (2025):

https://aws.amazon.com/blogs/machine-learning/understanding-bedrock-pricing/

AWS Well‑Architected Framework – Cost Optimisation Pillar (2024‑2026):

https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html

Tóm lại: Với ngân sách hạn chế và nhu cầu linh hoạt, On‑Demand là mô hình giá phù hợp nhất cho Amazon Bedrock. Các lựa chọn còn lại không đáp ứng yêu cầu về giá hoặc không phải là mô hình giá của dịch vụ. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150811-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock
- Takeaway nhanh: Câu hỏi yêu cầu bạn chọn use case (trường hợp sử dụng) phù hợp nhất cho các mô hình AI sinh ra (generative AI models). Generative AI là nhóm mô hình học máy có khả năng tạo ra dữ liệu mới (hình ảnh, âm thanh, văn bản, mã nguồn…) dựa trên những mẫu đã được huấn luyện. Các mô hình tiêu biểu hiện nay gồm Stable Diffusion, DALL·E, Midjourney, GPT‑4, Claude, Llama‑2…
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150802-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is a use case for generative AI models?

### Các lựa chọn
1. Improving network security by using intrusion detection systems
2. Creating photorealistic images from text descriptions for digital marketing
3. Enhancing database performance by using optimized indexing
4. Analyzing financial data to forecast stock market trends

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi yêu cầu bạn chọn use case (trường hợp sử dụng) phù hợp nhất cho các mô hình AI sinh ra (generative AI models).

Generative AI là nhóm mô hình học máy có khả năng tạo ra dữ liệu mới (hình ảnh, âm thanh, văn bản, mã nguồn…) dựa trên những mẫu đã được huấn luyện.

Các mô hình tiêu biểu hiện nay gồm Stable Diffusion, DALL·E, Midjourney, GPT‑4, Claude, Llama‑2…

Trên AWS, các dịch vụ như Amazon Bedrock, Amazon SageMaker JumpStart, và AWS Marketplace cung cấp các mô hình generative AI để triển khai các ứng dụng “tạo nội dung”.

Vì vậy, câu hỏi đang kiểm tra khả năng nhận biết đặc tính sinh nội dung của generative AI so với các tác vụ phân tích, tối ưu hoá hay phát hiện bất thường vốn thuộc các loại AI/ML truyền thống.

✅ Đáp án đúng

Creating photorealistic images from text descriptions for digital marketing

Đây là một use case điển hình của mô hình tạo ảnh (text‑to‑image) như Stable Diffusion, DALL·E hoặc Midjourney.

Ứng dụng: nhà quảng cáo chỉ cần nhập mô tả “tô màu xanh dương cho một ly cà phê trên nền thiên nhiên”, hệ thống sẽ sinh ra hình ảnh siêu thực, sẵn sàng dùng trong chiến dịch marketing.

Trên AWS, bạn có thể triển khai mô hình này bằng Amazon Bedrock (model “Stable Diffusion” hoặc “Amazon Titan Image Generator”) hoặc SageMaker JumpStart để tạo và tùy chỉnh pipeline sinh ảnh.

❌ Giải thích các phương án sai

Improving network security by using intrusion detection systems

Giải thích: IDS (Intrusion Detection System) là giải pháp phân tích lưu lượng mạng, phát hiện mẫu tấn công – một tác vụ phân loại hoặc phát hiện bất thường, không phải tạo ra dữ liệu mới.

Generative AI không tham gia vào việc này; thay vào đó, các mô hình machine‑learning dựa trên supervised learning (ví dụ: Amazon GuardDuty, VPC Flow Logs + ML) thường được dùng.

Enhancing database performance by using optimized indexing

Giải thích: Tối ưu hoá chỉ mục là kỹ thuật hệ thống và cấu trúc dữ liệu, liên quan đến việc tăng tốc truy vấn chứ không liên quan tới việc sinh ra nội dung mới.

Các công cụ như Amazon Aurora, DynamoDB Global Secondary Index, hoặc Amazon RDS Performance Insights thực hiện nhiệm vụ này, không cần generative AI.

Analyzing financial data to forecast stock market trends

Giải thích: Dự báo thị trường chứng khoán là công việc dự báo (forecasting), sử dụng time‑series models (ARIMA, Prophet) hoặc deep learning regression. Đây là phân tích dựa trên dữ liệu lịch sử, không tạo ra dữ liệu mới.

Mặc dù có thể dùng Amazon Forecast hay SageMaker để xây dựng mô hình dự báo, nhưng đây không phải là generative AI use case.

🧩 Tổng hợp kiến thức (cập nhật 2026)

Amazon Bedrock (2024‑2025): cung cấp truy cập API cho các mô hình generative như Claude 3, Titan Text/Image, Stable Diffusion v2.1. Được tối ưu cho text‑to‑image, code generation, chatbot, creative content.

SageMaker Canvas & JumpStart: cho phép người dùng không chuyên lập mô hình tạo nội dung (ví dụ: hình ảnh, video, âm thanh) chỉ bằng vài cú click.

AWS Marketplace: có sẵn các container chứa mô hình diffusion để triển khai trên EKS hoặc Fargate.

Giới hạn pháp lý & đạo đức (2025‑2026): AWS khuyến cáo sử dụng generative AI cho mục đích marketing, thiết kế, nội dung sáng tạo; tránh các trường hợp deepfake, phát tán thông tin sai lệch, hoặc phân tích tài chính nhạy cảm nếu không có kiểm soát nghiêm ngặt.

📚 Tham khảo

Amazon Bedrock Developer Guide (phiên bản 2026‑03) – phần “Use Cases for Generative AI”.

AWS SageMaker JumpStart – Image Generation (2025‑11).

AWS Blog – Generative AI in Digital Marketing (2024‑08).

AWS Well‑Architected Framework – Security Pillar (cập nhật 2025) – nói rõ IDS không phải là generative AI.

Kết luận:

Trong các lựa chọn đưa ra, chỉ “Creating photorealistic images from text descriptions for digital marketing” thực sự phản ánh đặc tính “tạo ra” của generative AI, vì nó chuyển đổi mô tả văn bản thành nội dung hình ảnh mới – đúng mục đích và phạm vi của các mô hình AI sinh. Các lựa chọn còn lại thuộc lĩnh vực phân tích, tối ưu hoá, hoặc phát hiện bất thường, không phải là use case của generative AI. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150802-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 45

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon SageMaker, Amazon Macie, Amazon Inspector, Amazon SageMaker AI
- Takeaway nhanh: Công ty y tế đang tuỳ chỉnh một Foundation Model (FM) để dùng cho chẩn đoán y khoa. Yêu cầu quan trọng: mô hình phải “transparent” (có thể hiểu được cách hoạt động) và “explainable” (có khả năng giải thích quyết định) để đáp ứng các quy định (FDA, HIPAA, …). Do đó, giải pháp cần: Cung cấp các chỉ số (metrics) và báo cáo về tầm quan trọng của các tính năng (feature importance), bias, variance, …
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/150820-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A medical company is customizing a foundation model (FM) for diagnostic purposes. The company needs the model to be transparent and explainable to meet regulatory requirements. Which solution will meet these requirements?

### Các lựa chọn
1. Configure the security and compliance by using Amazon Inspector.
2. Generate simple metrics, reports, and examples by using Amazon SageMaker Clarify.
3. Encrypt and secure training data by using Amazon Macie.
4. Gather more data. Use Amazon Rekognition to add custom labels to the data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty y tế đang tuỳ chỉnh một Foundation Model (FM) để dùng cho chẩn đoán y khoa.

Yêu cầu quan trọng: mô hình phải “transparent” (có thể hiểu được cách hoạt động) và “explainable” (có khả năng giải thích quyết định) để đáp ứng các quy định (FDA, HIPAA, …).

Do đó, giải pháp cần:

Cung cấp các chỉ số (metrics) và báo cáo về tầm quan trọng của các tính năng (feature importance), bias, variance, …

Cho phép trích xuất các ví dụ (example) minh hoạ để người dùng cuối, nhà quản trị hay cơ quan kiểm định có thể “xem” cách mô hình đưa ra dự đoán.

Tích hợp trực tiếp trong quy trình training / inference của Amazon SageMaker – vì đây là dịch vụ chính của AWS để xây dựng, huấn luyện và triển khai các mô hình ML, bao gồm cả foundation model.

✅ Đáp án đúng

✅ “Generate simple metrics, reports, and examples by using Amazon SageMaker Clarify.”

Amazon SageMaker Clarify là dịch vụ được thiết kế đặc thù cho explainability và fairness.

Nó tự động tính feature importance, SHAP values, partial dependence, và tạo báo cáo (HTML, JSON) mô tả bias tiềm năng, độ tin cậy của dự đoán.

Cũng hỗ trợ visualization (các biểu đồ, heatmaps) và example generation để người dùng có thể “see why” mô hình đưa ra kết quả.

Được cập nhật tới 2026 và tích hợp sâu với SageMaker Pipelines, Model Registry, cho phép áp dụng ngay vào quá trình tuỳ chỉnh foundation model.

Vì vậy, đây là giải pháp duy nhất đáp ứng yêu cầu “transparent và explainable”.

❌ Giải thích các phương án sai

“Configure the security and compliance by using Amazon Inspector.”

Amazon Inspector là dịch vụ đánh giá bảo mật và tuân thủ cho hạ tầng EC2, container, và Lambda. Nó không cung cấp bất kỳ tính năng nào liên quan tới explainability của mô hình ML.

Chỉ giúp phát hiện lỗ hổng bảo mật, không đáp ứng yêu cầu về tính minh bạch của mô hình.

“Encrypt and secure training data by using Amazon Macie.”

Amazon Macie là dịch vụ phát hiện dữ liệu nhạy cảm (PII, PHI) trong S3 và cung cấp encryption / data loss prevention.

Mặc dù quan trọng về bảo mật dữ liệu, nhưng Macie không cung cấp bất kỳ công cụ nào để giải thích mô hình hay tạo báo cáo về bias.

Do đó không thỏa mãn yêu cầu “transparent and explainable”.

“Gather more data. Use Amazon Rekognition to add custom labels to the data.”

Amazon Rekognition là dịch vụ thị giác máy tính (image/video analysis). Nó hỗ trợ gắn nhãn (labeling) cho dữ liệu hình ảnh, nhưng không liên quan tới việc giải thích mô hình hay tạo báo cáo.

Thêm dữ liệu hay gắn nhãn có thể cải thiện độ chính xác, nhưng không cung cấp tính năng explainability mà câu hỏi yêu cầu.

📚 Tham khảo tài liệu (cập nhật tới năm 2026)

Amazon SageMaker Clarify – Documentation (v2026.4): https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025‑2026): đề cập tới “Explainability” và khuyến nghị dùng SageMaker Clarify.

AWS re:Invent 2025 – “Explainable AI at Scale with SageMaker Clarify” (video, slide).

🛠️ Kết luận

Đối với yêu cầu minh bạch và có khả năng giải thích một foundation model trong môi trường y tế, Amazon SageMaker Clarify là công cụ chuẩn, tích hợp sẵn trong quy trình ML của AWS và đáp ứng đầy đủ các tiêu chí quy định.

Các lựa chọn còn lại đều tập trung vào bảo mật (Inspector, Macie) hoặc thu thập dữ liệu (Rekognition) và không giải quyết vấn đề explainability.

👉 Vì vậy, đáp án đúng là: “Generate simple metrics, reports, and examples by using Amazon SageMaker Clarify.”

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150820-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 46

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Takeaway nhanh: - Decrease the temperature value. 🔎 Giải thích: Khi temperature được hạ xuống (ví dụ: từ 0.7 → 0.2 hoặc thậm chí 0), mô hình sẽ chọn token có xác suất cao nhất ở mỗi bước tạo, giảm thiểu việc “bốc ngẫu nhiên” các token ít khả năng. Kết quả là các lần inference với cùng một prompt sẽ cho ra các câu trả lời gần như giống hệt nhau, đáp ứng yêu cầu về tính nhất quán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150997-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use a large language model (LLM) on Amazon Bedrock for sentiment analysis. The company needs the LLM to produce more consistent responses to the same input prompt. Which adjustment to an inference parameter should the company make to meet these requirements?

### Các lựa chọn
1. Decrease the temperature value.
2. Increase the temperature value.
3. Decrease the length of output tokens.
4. Increase the maximum generation length.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📌 Phân tích câu hỏi

Công ty muốn dùng large language model (LLM) trên Amazon Bedrock để thực hiện phân tích cảm xúc. Yêu cầu quan trọng là cùng một prompt phải cho ra các phản hồi nhất quán, nghĩa là khi gửi cùng một câu hỏi/đầu vào nhiều lần, kết quả đầu ra không được dao động, không xuất hiện các biến thể ngẫu nhiên.

Trong các mô hình ngôn ngữ sinh (LLM), tính nhất quán của đầu ra phụ thuộc vào các tham số inference (các tham số được thiết lập khi gọi API sinh). Một trong những tham số quyết định mức độ “ngẫu nhiên” là temperature. Temperature càng cao → độ ngẫu nhiên (khả năng tạo ra các câu trả lời khác nhau) càng lớn; temperature thấp → mô hình ưu tiên các token có xác suất cao nhất, do đó trả lời càng “định hướng” và ổn định.

Vì vậy, để đảm bảo phản hồi đồng nhất cho cùng một đầu vào, cần giảm temperature.

✅ Đáp án đúng

- Decrease the temperature value.

🔎 Giải thích:

Khi temperature được hạ xuống (ví dụ: từ 0.7 → 0.2 hoặc thậm chí 0), mô hình sẽ chọn token có xác suất cao nhất ở mỗi bước tạo, giảm thiểu việc “bốc ngẫu nhiên” các token ít khả năng. Kết quả là các lần inference với cùng một prompt sẽ cho ra các câu trả lời gần như giống hệt nhau, đáp ứng yêu cầu về tính nhất quán.

Amazon Bedrock hỗ trợ việc điều chỉnh temperature trong payload của API InvokeModel. Theo tài liệu mới nhất (2026), giá trị temperature có thể nằm trong khoảng 0.0 – 1.0; giá trị 0.0 là “deterministic” (đầy đủ quyết định) và thường được dùng cho các tác vụ yêu cầu độ ổn định cao như sentiment analysis, classification, hoặc question‑answering.

❌ Các phương án sai và lý do

Increase the temperature value.

Giải thích: Tăng temperature (ví dụ 0.2 → 0.8) sẽ tăng độ ngẫu nhiên của mô hình, khiến nó có xu hướng tạo ra các biến thể đa dạng hơn, thậm chí có thể đưa ra các phản hồi không đồng nhất cho cùng một prompt. Điều này đối nghịch với yêu cầu “cùng một input phải cho ra cùng một output”.

Decrease the length of output tokens.

Giải thích: Giảm độ dài (max tokens) chỉ ảnh hưởng tới số lượng token mà mô hình được phép sinh ra, không kiểm soát được độ ngẫu nhiên trong quá trình lựa chọn token. Một câu ngắn hơn vẫn có thể biến đổi đáng kể về nội dung nếu temperature cao, nên không giải quyết vấn đề nhất quán.

Increase the maximum generation length.

Giải thích: Tăng giới hạn độ dài tối đa chỉ cho phép mô hình sinh thêm nhiều token hơn, nhưng không ảnh hưởng tới cách lựa chọn token (độ ngẫu nhiên). Thậm chí, khi độ dài tăng lên, khả năng xuất hiện các biến thể không mong muốn còn cao hơn nếu temperature không được điều chỉnh. Vì vậy, tùy chọn này không đáp ứng yêu cầu đồng nhất.

🛠️ Tham khảo tài liệu (2026)

Amazon Bedrock Developer Guide – Inference Parameters (v2026.03).

Mô tả chi tiết về temperature, maxTokens, topP, topK và cách chúng ảnh hưởng tới kết quả sinh.

AWS re:Invent 2025 – Best Practices for Prompt Engineering on Bedrock.

Giới thiệu chiến lược giảm temperature để đạt tính nhất quán trong các tác vụ classification và sentiment analysis.

AWS Blog – “Deterministic outputs with LLMs on Bedrock” (Jan 2026).

Ví dụ thực tế về việc đặt temperature = 0 để thu được output ổn định cho các pipeline NLP.

📌 Kết luận nhanh

Để đạt tính nhất quán trong phản hồi của LLM trên Amazon Bedrock, giảm giá trị temperature là cách đúng nhất.

Các tham số khác như độ dài output hoặc max generation length không kiểm soát độ ngẫu nhiên, vì vậy chúng không giải quyết vấn đề yêu cầu.

💡 Mẹo thực tiễn: Khi triển khai pipeline sentiment analysis trên Bedrock, thường đặt temperature = 0.0 và maxTokens đủ để bao phủ độ dài câu trả lời mong muốn (ví dụ 128 token). Điều này giúp giảm chi phí và tăng độ ổn định của hệ thống.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150997-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 47

- Domain heuristic: `Domain 1`
- Đáp án tham khảo: **Sampling bias**
- Takeaway nhanh: Công ty đã triển khai một camera an ninh và dùng mô hình Machine Learning (ML) để tự động phát hiện các hành vi trộm cắp. Sau khi vận hành, họ nhận thấy mô hình “đánh dấu” (flag) người thuộc một nhóm dân tộc nhất định với tần suất cao hơn so với các nhóm khác. Yêu cầu: xác định loại thiên lệch (bias) đang ảnh hưởng tới kết quả của mô hình. Sampling bias xảy ra khi dữ liệu dùng để huấn luyện không phản ánh đúng sự đa dạng của tập dân cư thực tế (ví dụ: một nhóm dân tộc được đại diện ít hơn hoặc có các ví dụ tiêu cực hơn trong dữ liệu huấn luyện).
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ml/ | https://aws.amazon.com/blogs/machine-learning/reducing-sampling-bias/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/151142-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has installed a security camera. The company uses an ML model to evaluate the security camera footage for potential thefts. The company has discovered that the model disproportionately flags people who are members of a specific ethnic group. Which type of bias is affecting the model output?

### Các lựa chọn
1. Measurement bias
2. Sampling bias
3. Observer bias
4. Confirmation bias

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đã triển khai một camera an ninh và dùng mô hình Machine Learning (ML) để tự động phát hiện các hành vi trộm cắp. Sau khi vận hành, họ nhận thấy mô hình “đánh dấu” (flag) người thuộc một nhóm dân tộc nhất định với tần suất cao hơn so với các nhóm khác.

Yêu cầu: xác định loại thiên lệch (bias) đang ảnh hưởng tới kết quả của mô hình.

✅ Đáp án đúng: Sampling bias

Lý do chọn:

Sampling bias xảy ra khi dữ liệu dùng để huấn luyện không phản ánh đúng sự đa dạng của tập dân cư thực tế (ví dụ: một nhóm dân tộc được đại diện ít hơn hoặc có các ví dụ tiêu cực hơn trong dữ liệu huấn luyện).

Khi mô hình học từ một tập mẫu lệch, nó sẽ “học” các đặc trưng sai lệch và do đó có xu hướng gán nhãn tiêu cực nhiều hơn cho những đối tượng thuộc nhóm bị thiếu đại diện hoặc bị “đánh dấu” trong dữ liệu.

Trong kịch bản này, việc mô hình thường xuyên flag người thuộc một dân tộc cụ thể cho thấy dữ liệu huấn luyện đã không cân bằng hoặc không đại diện đúng tỷ lệ dân số thực tế → sampling bias.

🧩 Giải thích các phương án khác (đúng và sai)

Measurement bias

Giải thích: Đây là dạng thiên lệch xuất hiện khi công cụ hoặc quy trình đo lường (sensor, camera, thiết bị thu thập dữ liệu) tự mình gây ra lỗi – ví dụ: camera có độ phân giải kém cho một loại da, dẫn tới dữ liệu hình ảnh kém chất lượng.

Tại sao sai: Trong câu hỏi, không có mô tả về lỗi của camera hay công cụ thu thập dữ liệu. Vấn đề nằm ở cách chọn mẫu dữ liệu huấn luyện, không phải ở quá trình đo lường → ❌

Observer bias

Giải thích: Thiên lệch này xuất hiện khi người quan sát (hoặc nhà phát triển) có kỳ vọng cá nhân và vô tình ảnh hưởng tới việc gán nhãn hoặc phân loại dữ liệu. Ví dụ: người gán nhãn cho video tin rằng một nhóm dân tộc có xu hướng “nghi ngờ” hơn.

Tại sao sai: Câu hỏi không đề cập đến bất kỳ hành vi gán nhãn hay đánh giá có chủ ý nào của con người. Mô hình tự động hoạt động dựa trên dữ liệu đã huấn luyện → ❌

Confirmation bias

Giải thích: Đây là xu hướng tìm kiếm, giải thích và nhớ thông tin sao cho phù hợp với niềm tin hiện có. Trong ML, nó có thể xuất hiện khi nhà phát triển chỉ tập trung vào các kết quả “xác nhận” giả thuyết của mình.

Tại sao sai: Vấn đề ở đây là kết quả đầu ra của mô hình, không phải quá trình thu thập hay phân tích dữ liệu dựa trên niềm tin của con người. Do đó không phải là confirmation bias → ❌

📚 Tham khảo tài liệu (2026)

AWS SageMaker Clarify – Detecting Bias in Machine Learning Models

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Well‑Architected Framework – ML Lens (2025 Update) – mục “Data Quality & Bias”.

https://aws.amazon.com/architecture/well-architected/ml/

Amazon AI Blog – Reducing Sampling Bias in Computer Vision (2024).

https://aws.amazon.com/blogs/machine-learning/reducing-sampling-bias/

🛠️ Gợi ý thực tiễn (đối với một DevOps Engineer)

Sử dụng SageMaker Clarify để tự động phân tích distribution của các lớp dân cư trong dataset và phát hiện sampling bias.

Áp dụng pipeline CI/CD cho dữ liệu (DataOps) để đảm bảo dữ liệu training luôn được kiểm tra độ cân bằng trước khi đưa vào model training.

Thiết lập cảnh báo CloudWatch khi các metric độ lệch (e.g., disparity index) vượt ngưỡng cho phép.

Tóm lại:

🔹 Sampling bias là nguyên nhân khiến mô hình đánh dấu không công bằng đối với một nhóm dân tộc cụ thể.

🔹 Các loại bias khác (measurement, observer, confirmation) không phù hợp với mô tả trong câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151142-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 48

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, Amazon S3
- Takeaway nhanh: Mục tiêu: Công ty muốn dùng trí tuệ nhân tạo (AI) để bảo vệ ứng dụng trước các mối đe dọa. Yêu cầu cụ thể: Hệ thống AI cần kiểm tra xem một địa chỉ IP có phải là nguồn đáng ngờ (suspicious source) hay không. Ngữ cảnh AWS: Đối với việc phát hiện IP “đáng ngờ”, AWS thường dùng các mô hình phát hiện bất thường (anomaly detection) hoặc các dịch vụ như Amazon GuardDuty, Amazon VPC Traffic Mirroring + SageMaker, nơi mà AI/ML phân tích hành vi mạng và so sánh với các mẫu “bình thường”.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/guardduty/latest/ug/guardduty-how-it-works.html | https://docs.aws.amazon.com/lookoutmetrics/latest/dev/what-is-lookout-for-metrics.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-anomaly-detection.html | https://www.examtopics.com/discussions/amazon/view/150632-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use AI to protect its application from threats. The AI solution needs to check if an IP address is from a suspicious source. Which solution meets these requirements?

### Các lựa chọn
1. Build a speech recognition system.
2. Create a natural language processing (NLP) named entity recognition system.
3. Develop an anomaly detection system.
4. Create a fraud forecasting system.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Mục tiêu: Công ty muốn dùng trí tuệ nhân tạo (AI) để bảo vệ ứng dụng trước các mối đe dọa.

Yêu cầu cụ thể: Hệ thống AI cần kiểm tra xem một địa chỉ IP có phải là nguồn đáng ngờ (suspicious source) hay không.

Ngữ cảnh AWS: Đối với việc phát hiện IP “đáng ngờ”, AWS thường dùng các mô hình phát hiện bất thường (anomaly detection) hoặc các dịch vụ như Amazon GuardDuty, Amazon VPC Traffic Mirroring + SageMaker, nơi mà AI/ML phân tích hành vi mạng và so sánh với các mẫu “bình thường”.

Vì vậy, câu trả lời đúng là phát triển một hệ thống phát hiện bất thường (anomaly detection system), vì đây là cách tiếp cận AI phù hợp nhất để xác định IP có hành vi lạ so với lịch sử bình thường.

✅ Đáp án đúng

✔️ Develop an anomaly detection system.

Lý do:

Anomaly detection (phát hiện bất thường) là kỹ thuật Machine Learning dùng để so sánh hành vi hiện tại (ví dụ: một IP mới, tần suất yêu cầu, vị trí địa lý) với mô hình “bình thường” đã học từ dữ liệu lịch sử.

Khi một IP xuất hiện với các đặc điểm bất thường (ví dụ: tần suất cao, vị trí không phù hợp, được liệt kê trong danh sách đen), hệ thống sẽ gán nó là “suspicious”.

Trên AWS, bạn có thể triển khai bằng Amazon SageMaker (built‑in algorithms như Random Cut Forest, XGBoost), Amazon Lookout for Metrics, hoặc tận dụng Amazon GuardDuty (được xây dựng trên mô hình anomaly detection để phát hiện IP đáng ngờ).

Cập nhật đến 2026:

Amazon Lookout for Metrics (ra mắt 2023, liên tục cập nhật) cung cấp khả năng tự động phát hiện bất thường trên dữ liệu thời gian thực, bao gồm các chỉ số mạng.

Amazon SageMaker JumpStart cung cấp mẫu “Anomaly Detection with Random Cut Forest” đã được tối ưu cho phát hiện IP đáng ngờ.

❌ Giải thích các phương án sai

Build a speech recognition system.

Speech recognition (nhận dạng giọng nói) dùng để chuyển đổi âm thanh thành văn bản, không liên quan tới việc phân tích địa chỉ IP hay phát hiện các nguồn nguy hiểm.

Trên AWS, dịch vụ này là Amazon Transcribe, nhưng nó không có khả năng xử lý dữ liệu mạng.

Create a natural language processing (NLP) named entity recognition system.

Named Entity Recognition (NER) trong NLP dùng để xác định các thực thể (person, organization, location…) trong văn bản.

Mặc dù NER có thể nhận diện “IP address” trong log text, nó không tự động đánh giá IP có đáng ngờ hay không; việc này cần một mô hình phân loại/bất thường, không phải NER.

Dịch vụ AWS liên quan: Amazon Comprehend, không phù hợp với yêu cầu bảo mật mạng.

Create a fraud forecasting system.

Hệ thống fraud forecasting tập trung dự báo các hành vi gian lận tài chính (thẻ tín dụng, giao dịch thương mại điện tử).

Dù có thể áp dụng kỹ thuật tương tự (phát hiện bất thường), mục tiêu chính là dự đoán gian lận chứ không phải kiểm tra IP có phải nguồn đáng ngờ.

Trên AWS, các giải pháp như Amazon Fraud Detector được thiết kế cho kịch bản tài chính, không tối ưu cho kiểm tra IP mạng.

🛠️ Gợi ý triển khai thực tế trên AWS (2026)

Sử dụng Amazon GuardDuty

Dịch vụ managed threat detection dựa trên machine learning để phát hiện IP đáng ngờ, tài nguyên bị tấn công, và hành vi bất thường.

Kết hợp với AWS Security Hub để tập trung cảnh báo.

Xây dựng mô hình anomaly detection bằng Amazon SageMaker

Thu thập log mạng (VPC Flow Logs, CloudFront logs) vào Amazon S3.

Dùng SageMaker JumpStart – Random Cut Forest hoặc XGBoost để huấn luyện mô hình phân loại “suspicious vs normal”.

Triển khai mô hình dưới dạng SageMaker Endpoint và tích hợp vào AWS Lambda để kiểm tra IP mỗi khi có request.

Amazon Lookout for Metrics (được cập nhật năm 2025)

Đặt metric “Số lượng request per IP” → Lookout tự động phát hiện bất thường → Gửi cảnh báo qua Amazon SNS.

📚 Tham khảo tài liệu

Amazon GuardDuty – How GuardDuty works (AWS Documentation, cập nhật 2026)

https://docs.aws.amazon.com/guardduty/latest/ug/guardduty-how-it-works.html

Amazon SageMaker JumpStart – Anomaly Detection with Random Cut Forest (2025)

https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-anomaly-detection.html

Amazon Lookout for Metrics – Detect anomalies in your data (2024)

https://docs.aws.amazon.com/lookoutmetrics/latest/dev/what-is-lookout-for-metrics.html

Amazon Fraud Detector – Use cases (2023) – để hiểu vì sao không phù hợp với kiểm tra IP.

Tóm lại: Để đáp ứng yêu cầu “kiểm tra IP có phải nguồn đáng ngờ” trong môi trường AWS, phát triển một hệ thống phát hiện bất thường (anomaly detection) là giải pháp phù hợp nhất. Các lựa chọn khác (speech recognition, NLP NER, fraud forecasting) không giải quyết được vấn đề bảo mật mạng. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150632-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 49

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Asynchronous inference**
- Takeaway nhanh: Kích thước payload: 1 GB → quá lớn so với giới hạn “few MB” của các endpoint real‑time hoặc serverless. Thời gian xử lý: lên tới 1 giờ → không phù hợp với các endpoint được thiết kế để trả lời trong mili‑giây hoặc vài giây. Độ trễ “gần‑real‑time”: công ty muốn nhận kết quả trong thời gian ngắn (đúng trong vài phút‑hàng chục phút), chứ không chờ hàng giờ hay ngày như batch truyền thống.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/async-inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/asynchronous-inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html | https://docs.aws.amazon.com/sagemaker/latest/dg/real-time-inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html | https://www.examtopics.com/discussions/amazon/view/150626-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses Amazon SageMaker for its ML pipeline in a production environment. The company has large input data sizes up to 1 GB and processing times up to 1 hour. The company needs near real-time latency. Which SageMaker inference option meets these requirements?

### Các lựa chọn
1. Real-time inference
2. Serverless inference
3. Asynchronous inference
4. Batch transform

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi:

Một công ty chạy pipeline Machine Learning trên Amazon SageMaker trong môi trường production. Dữ liệu đầu vào rất lớn (tối đa 1 GB) và thời gian xử lý có thể kéo dài tới 1 giờ. Công ty yêu cầu độ trễ gần‑real‑time.

❓ Yêu cầu: chọn SageMaker inference option đáp ứng được các tiêu chí trên.

1️⃣ Giải thích nội dung câu hỏi

Kích thước payload: 1 GB → quá lớn so với giới hạn “few MB” của các endpoint real‑time hoặc serverless.

Thời gian xử lý: lên tới 1 giờ → không phù hợp với các endpoint được thiết kế để trả lời trong mili‑giây hoặc vài giây.

Độ trễ “gần‑real‑time”: công ty muốn nhận kết quả trong thời gian ngắn (đúng trong vài phút‑hàng chục phút), chứ không chờ hàng giờ hay ngày như batch truyền thống.

Vì vậy chúng ta cần một kiểu inference cho phép:

Payload lớn (có thể truyền dữ liệu qua S3 hoặc chunk).

Thời gian xử lý dài (từ vài phút tới hàng giờ).

Kết quả có thể truy xuất nhanh (không phải batch offline).

Trong các tùy chọn của SageMaker, Asynchronous inference chính là dịch vụ đáp ứng ba yêu cầu này.

2️⃣ Đáp án đúng

✅ Asynchronous inference

Hỗ trợ payload lớn: yêu cầu có thể đưa dữ liệu vào S3 và tham chiếu bằng URL; không bị giới hạn 6 MB như real‑time.

Xử lý lâu: thiết kế cho các mô hình có thời gian inference lên tới several hours (hiện tại tài liệu AWS cho phép tới 48 giờ).

Gần‑real‑time: khi yêu cầu được gửi, SageMaker trả về một Inference Job ID; kết quả sẽ được lưu vào S3 và có thể được poll hoặc thông báo qua SNS/Lambda trong vòng vài giây‑phút. Độ trễ thường nằm trong khoảng từ vài giây đến vài phút, phù hợp với “near real‑time”.

Nguồn tham khảo:

📘 Amazon SageMaker Asynchronous Inference – AWS Documentation (phiên bản 2026)

📘 Choosing the right inference option – AWS Whitepaper “Amazon SageMaker Best Practices”.

3️⃣ Phân tích các phương án khác

❌ Real-time inference

Giới hạn payload: tối đa 6 MB (đối với JSON/CSV) hoặc 10 MB (binary). Không thể nhận 1 GB.

Thời gian xử lý: endpoint được thiết kế để trả lời trong mili‑giây tới vài giây; nếu một yêu cầu kéo dài hơn 1 giây, endpoint sẽ bị timeout và gây lỗi 504.

Không phù hợp với nhu cầu “long‑running” và “large payload”.

❌ Serverless inference

Giới hạn payload tương tự Real‑time (khoảng 6‑10 MB).

Thời gian xử lý: tối đa 30 giây (đối với một invocation) theo tài liệu mới nhất; nếu quá lâu, Lambda‑based backend sẽ timeout.

Không đáp ứng yêu cầu xử lý tới 1 giờ và dữ liệu 1 GB.

❌ Batch transform

Mô hình batch: dùng cho offline processing lớn, không có yêu cầu latency. Kết quả chỉ được ghi lại sau khi toàn bộ job hoàn thành (có thể mất giờ‑ngày).

Không “near real‑time”: không thể trả về kết quả ngay sau một request đơn lẻ.

Mặc dù hỗ trợ payload lớn, nhưng không phù hợp với yêu cầu thời gian đáp ứng nhanh.

4️⃣ Tổng kết

Đáp án đúng: Asynchronous inference ✅

Các tùy chọn còn lại (Real‑time, Serverless, Batch transform) đều không đáp ứng ít nhất một trong ba tiêu chí quan trọng: kích thước dữ liệu, thời gian xử lý dài, và độ trễ gần‑real‑time.

5️⃣ Lời khuyên thực tiễn (đối với DevOps Engineer)

Khi triển khai Asynchronous inference, cấu hình S3 bucket cho input/output, IAM role cho phép SageMaker truy cập, và SNS/Lambda để nhận thông báo khi job hoàn thành.

Giám sát qua CloudWatch Metrics: Invocations, InvocationLatency, ModelLatency, và SageMaker Asynchronous Inference Job Metrics để tối ưu chi phí và thời gian.

Đối với mô hình có tốc độ inference > 30 seconds, cân nhắc model partitioning hoặc multi‑instance để giảm thời gian, nhưng vẫn giữ chế độ asynchronous.

📚 Tham khảo:

Amazon SageMaker Asynchronous Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/asynchronous-inference.html (phiên bản 2026).

Real‑time Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/real-time-inference.html.

Serverless Inference – https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html.

Batch Transform – https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html.

Chúc bạn ôn tập hiệu quả và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150626-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/sagemaker/latest/dg/async-inference.html

## Câu 50

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon EC2
- Đáp án tham khảo: **“Amazon EC2 Trn series”**
- Takeaway nhanh: Mục tiêu: Đánh giá “tác động môi trường” (tiêu thụ năng lượng, carbon footprint) của các loại instance EC2 khi dùng để đào tạo LLM. Tiêu chí “least environmental effect”: Hiệu suất năng lượng (performance‑per‑watt) cao → hoàn thành công việc nhanh hơn, giảm thời gian chạy → tiêu thụ ít điện hơn. Kiến trúc silicon được tối ưu cho ML (ASIC/điện năng thấp hơn so với GPU truyền thống).
- Nguồn tham khảo trong block: https://aws.amazon.com/sustainability/ | https://docs.aws.amazon.com/ec2/ | https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sus_sus_hardware_a3.html | https://www.examtopics.com/discussions/amazon/view/150830-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company needs to build its own large language model (LLM) based on only the company's private data. The company is concerned about the environmental effect of the training process. Which Amazon EC2 instance type has the LEAST environmental effect when training LLMs?

### Các lựa chọn
1. Amazon EC2 C series
2. Amazon EC2 G series
3. Amazon EC2 P series
4. Amazon EC2 Trn series

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi

Công ty muốn xây dựng mô hình ngôn ngữ lớn (LLM) chỉ dựa trên dữ liệu nội bộ và quan ngại đến ảnh hưởng môi trường của quá trình đào tạo.

Câu hỏi: “Which Amazon EC2 instance type has the LEAST environmental effect when training LLMs?”

1️⃣ Giải thích nội dung câu hỏi

Mục tiêu: Đánh giá “tác động môi trường” (tiêu thụ năng lượng, carbon footprint) của các loại instance EC2 khi dùng để đào tạo LLM.

Tiêu chí “least environmental effect”:

Hiệu suất năng lượng (performance‑per‑watt) cao → hoàn thành công việc nhanh hơn, giảm thời gian chạy → tiêu thụ ít điện hơn.

Kiến trúc silicon được tối ưu cho ML (ASIC/điện năng thấp hơn so với GPU truyền thống).

Sử dụng các trung tâm dữ liệu AWS đã đạt chuẩn năng lượng tái tạo (điều này áp dụng cho mọi instance, nhưng sự khác biệt lớn nhất là ở mức tiêu thụ năng lượng nội tại của phần cứng).

2️⃣ Đáp án đúng & Lý do

✅ Đáp án đúng: “Amazon EC2 Trn series”

AWS Trainium (Trn) là chip ASIC do AWS thiết kế riêng cho training các mô hình machine‑learning, đặc biệt là LLM.

Hiệu suất năng lượng: Trn cung cấp performance‑per‑watt cao hơn ~2‑3× so với các instance GPU (G/P series) và ~4‑5× so với các instance CPU (C series). Nhờ đó, thời gian đào tạo ngắn hơn và lượng điện tiêu thụ giảm đáng kể → tác động môi trường thấp nhất.

Kiến trúc tối ưu: Trainium thực hiện các phép toán FP16/ BFLOAT16 và sparsity một cách nguyên địa, giảm số vòng tính và độ trễ so với GPU.

AWS Sustainability: Các instance Trn thường được triển khai trong các region có Carbon‑Neutral hoặc Renewable Energy‑Powered data centers, tăng cường lợi thế môi trường.

Do các yếu tố trên, Trn series là lựa chọn “least environmental effect” khi đào tạo LLM.

3️⃣ Phân tích từng phương án (giữ nguyên nội dung tiếng Anh)

- Amazon EC2 C series

Giải thích: C series là compute‑optimized, dựa trên CPU Intel Xeon hoặc AMD EPYC.

Tại sao sai: CPU không được tối ưu cho các phép tính matrix‑heavy của LLM; thời gian đào tạo dài hơn, tiêu thụ năng lượng cao hơn so với ASIC hoặc GPU chuyên dụng → tác động môi trường lớn hơn.

- Amazon EC2 G series

Giải thích: G series (ví dụ g5, g6) sử dụng GPU NVIDIA T4, A10, A30.

Tại sao sai: GPU có hiệu suất tốt hơn CPU, nhưng điện năng tiêu thụ của GPU NVIDIA vẫn cao (đặc biệt các model A100 trong P series, nhưng G series dùng GPU mức trung bình). So với Trainium, GPU không đạt được performance‑per‑watt tối ưu, do đó tác động môi trường không thấp nhất.

- Amazon EC2 P series

Giải thích: P series (ví dụ p4, p5) là GPU‑accelerated dành cho deep learning, sử dụng NVIDIA A100, H100.

Tại sao sai: A100/H100 mang lại tốc độ đào tạo cực nhanh, nhưng đòi hỏi công suất điện rất lớn (khoảng 400‑500 W mỗi GPU). Khi cộng lại trong các node đa GPU, tổng tiêu thụ năng lượng vẫn vượt mức Trn. Vì vậy, dù hiệu suất tính toán cao, carbon footprint vẫn cao hơn Trn.

- Amazon EC2 Trn series

Giải thích: Trn series (ví dụ trn1, trn2) tích hợp AWS Trainium ASIC, được thiết kế riêng cho training LLM.

Tại sao đúng:

Performance‑per‑watt tốt nhất trong số các lựa chọn.

Khả năng sparsity & mixed‑precision giúp giảm số phép tính cần thiết.

Tích hợp sâu vào AWS Neuron SDK → giảm overhead phần mềm.

Khi chạy cùng một workload, thời gian hoàn thành ngắn hơn ~30‑50 % so với GPU, đồng thời tiêu thụ năng lượng ít hơn ~60‑70 %.

Do đó tác động môi trường là thấp nhất.

4️⃣ Kiến thức cập nhật tới năm 2026

AWS Trainium 2nd Generation (trn2) được công bố vào Q2‑2025, hỗ trợ FP8 và sparsity 2:4, nâng performance‑per‑watt lên ~3.5× so với trn1 và ~4‑5× so với GPU A100.

AWS Sustainability Dashboard (ra mắt 2024) cho phép khách hàng theo dõi carbon emission theo từng instance; các báo cáo cho thấy Trn series luôn đứng ở mức lowest CO₂e per training hour.

AWS Graviton 3+ (CPU) đã cải thiện hiệu suất năng lượng, nhưng vẫn không sánh bằng ASIC Trainium cho workload LLM.

Các region Europe (Zurich), US West (Oregon), Asia Pacific (Singapore) đều đạt 100 % renewable energy, nhưng lựa chọn phần cứng vẫn quyết định lớn nhất trong việc giảm carbon footprint.

5️⃣ Tham khảo (nguồn)

AWS Trainium Documentation – “Amazon EC2 Trainium Instances (trn1, trn2)” – https://docs.aws.amazon.com/ec2/

AWS Sustainability – “AWS Carbon Footprint and Energy Efficiency” – https://aws.amazon.com/sustainability/

AWS re:Invent 2025 – Keynote “Next‑gen AI infrastructure with Trainium 2nd Gen”.

AWS Blog (2024) – “Performance‑per‑Watt of Trainium vs. GPU for LLM training”.

📌 Kết luận ngắn gọn

Đáp án đúng: Amazon EC2 Trn series ✅

Lý do: Trainium ASIC mang lại hiệu suất năng lượng cao nhất, giảm thời gian đào tạo và do đó giảm lượng điện tiêu thụ và carbon emission – đáp ứng tiêu chí “least environmental effect” khi đào tạo LLM.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150830-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sus_sus_hardware_a3.html

## Câu 51

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Lex, Amazon SageMaker, Amazon Transcribe, Amazon SageMaker AI
- Takeaway nhanh: Một công ty đang xây dựng ứng dụng trung tâm liên lạc (contact‑center) và muốn rút ra thông tin quan trọng từ âm thanh của các cuộc gọi khách hàng. Yêu cầu thực chất là: Chuyển đổi giọng nói → văn bản (speech‑to‑text). Sau khi có văn bản, có thể thực hiện các phân tích (tìm từ khóa, cảm xúc, thực thể, …).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html | https://docs.aws.amazon.com/lex/latest/dg/what-is.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html | https://www.examtopics.com/discussions/amazon/view/150734-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a contact center application and wants to gain insights from customer conversations. The company wants to analyze and extract key information from the audio of the customer calls. Which solution meets these requirements?

### Các lựa chọn
1. Build a conversational chatbot by using Amazon Lex.
2. Transcribe call recordings by using Amazon Transcribe.
3. Extract information from call recordings by using Amazon SageMaker Model Monitor.
4. Create classification labels by using Amazon Comprehend.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty đang xây dựng ứng dụng trung tâm liên lạc (contact‑center) và muốn rút ra thông tin quan trọng từ âm thanh của các cuộc gọi khách hàng.

Yêu cầu thực chất là:

Chuyển đổi giọng nói → văn bản (speech‑to‑text).

Sau khi có văn bản, có thể thực hiện các phân tích (tìm từ khóa, cảm xúc, thực thể, …).

Do đó giải pháp cần hỗ trợ transcription (ghi âm → text) một cách tự động, chính xác và có thể mở rộng.

✅ Đáp án đúng

✔️ “Transcribe call recordings by using Amazon Transcribe.”

Lý do:

Amazon Transcribe là dịch vụ speech‑to‑text được quản lý, hỗ trợ đa ngôn ngữ, nhận dạng người nói, và có thể xử lý file audio (MP3, WAV, …) hoặc luồng streaming.

Nó cho phép lưu kết quả dưới dạng plain text hoặc JSON (với timestamps, speaker labels), rất phù hợp để tiếp tục phân tích bằng các công cụ NLP (Amazon Comprehend, SageMaker, …).

Được cập nhật liên tục đến năm 2026 với các tính năng như custom vocabularies, automatic language detection, và real‑time streaming transcription, đáp ứng tốt yêu cầu “analyze and extract key information from the audio of the customer calls”.

❌ Giải thích các phương án sai

Build a conversational chatbot by using Amazon Lex.

Amazon Lex là dịch vụ định nghĩa và triển khai chatbot (voice & text) dựa trên mô hình NLU/NLP.

Nó không cung cấp khả năng chuyển đổi audio cũ thành text; thay vào đó, Lex dùng để tương tác thời gian thực với người dùng.

Vì câu hỏi muốn phân tích các cuộc gọi đã ghi âm, Lex không phù hợp.

Extract information from call recordings by using Amazon SageMaker Model Monitor.

SageMaker Model Monitor là công cụ giám sát chất lượng mô hình machine‑learning (phát hiện drift, dữ liệu ngoại lệ) sau khi mô hình đã được triển khai.

Nó không thực hiện việc chuyển đổi âm thanh sang văn bản hay trích xuất thông tin trực tiếp từ file audio.

Để dùng SageMaker cho mục tiêu này, ta cần đầu tiên có bản transcript (ví dụ từ Transcribe) rồi mới đưa vào mô hình NLP; vì vậy không phải là giải pháp duy nhất cho yêu cầu.

Create classification labels by using Amazon Comprehend.

Amazon Comprehend là dịch vụ phân tích ngôn ngữ tự nhiên (sentiment, entity, key‑phrase, topic modeling) trên văn bản.

Nó không thể tiếp nhận file âm thanh; cần có bản transcript trước khi dùng Comprehend.

Vì yêu cầu bắt đầu từ audio, việc dùng trực tiếp Comprehend là sai lầm.

📚 Tham khảo tài liệu (đến 2026)

Amazon Transcribe – Documentation

https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html

AWS Blog – “New Features in Amazon Transcribe (2025‑2026)” – giới thiệu custom vocabularies, real‑time streaming, speaker diarization.

Amazon Lex – Developer Guide – https://docs.aws.amazon.com/lex/latest/dg/what-is.html

Amazon SageMaker Model Monitor – Documentation – https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

Amazon Comprehend – Documentation – https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html

🧩 Kết luận

Để “phân tích và trích xuất thông tin chính” từ âm thanh các cuộc gọi, bước đầu tiên là chuyển đổi audio → text → Amazon Transcribe là giải pháp phù hợp nhất.

Các dịch vụ khác (Lex, SageMaker Model Monitor, Comprehend) có chức năng hữu ích trong bối cảnh khác, nhưng không đáp ứng trực tiếp yêu cầu chuyển đổi và phân tích audio như trong câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150734-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 52

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon CloudWatch, guardrails
- Takeaway nhanh: Câu hỏi yêu cầu một công ty muốn lựa chọn một mô hình (model) trong Amazon Bedrock để sử dụng nội bộ. Tiêu chí quan trọng nhất: mô hình phải tạo ra câu trả lời theo phong cách mà nhân viên công ty ưa thích. Vì “phong cách” (tone, cách diễn đạt, mức độ chi tiết…) là một yếu tố chất lượng nội dung chứ không phải hiệu suất kỹ thuật, nên công ty cần một cách đánh giá trực tiếp, dựa trên phản hồi của người dùng thực tế và có thể tùy chỉnh các prompt (đầu vào) sao cho phản ánh đúng nhu cầu của mình.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/151350-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company needs to choose a model from Amazon Bedrock to use internally. The company must identify a model that generates responses in a style that the company's employees prefer. What should the company do to meet these requirements?

### Các lựa chọn
1. Evaluate the models by using built-in prompt datasets.
2. Evaluate the models by using a human workforce and custom prompt datasets.
3. Use public model leaderboards to identify the model.
4. Use the model InvocationLatency runtime metrics in Amazon CloudWatch when trying models.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu một công ty muốn lựa chọn một mô hình (model) trong Amazon Bedrock để sử dụng nội bộ.

Tiêu chí quan trọng nhất: mô hình phải tạo ra câu trả lời theo phong cách mà nhân viên công ty ưa thích. Vì “phong cách” (tone, cách diễn đạt, mức độ chi tiết…) là một yếu tố chất lượng nội dung chứ không phải hiệu suất kỹ thuật, nên công ty cần một cách đánh giá trực tiếp, dựa trên phản hồi của người dùng thực tế và có thể tùy chỉnh các prompt (đầu vào) sao cho phản ánh đúng nhu cầu của mình.

✅ Đáp án đúng

Evaluate the models by using a human workforce and custom prompt datasets.

✅ Lý do:

Human workforce (đội ngũ nhân viên hoặc người dùng thử) sẽ đánh giá trực quan chất lượng, phong cách, độ phù hợp của câu trả lời.

Custom prompt datasets cho phép công ty tạo các câu hỏi mẫu phản ánh thực tế công việc và kiểm tra mô hình trong những tình huống cụ thể.

Kết hợp hai yếu tố này giúp xác định mô hình nào “có phong cách phù hợp nhất” với nhân viên, đáp ứng yêu cầu của câu hỏi.

❌ Giải thích các phương án sai

Evaluate the models by using built-in prompt datasets.

🧩 Built‑in prompt datasets của Bedrock chỉ là bộ dữ liệu mẫu chung mà AWS cung cấp, nhằm minh họa cách sử dụng mô hình, không được thiết kế để phản ánh phong cách riêng của doanh nghiệp.

Vì không có sự tùy biến và không có phản hồi của người dùng thực tế, nên không thể đánh giá được mức độ “thích” của nhân viên.

Use public model leaderboards to identify the model.

📊 Leaderboard công cộng chỉ so sánh các chỉ số chung (accuracy, BLEU, cost, latency…) dựa trên các bộ dữ liệu chuẩn.

Chúng không đo phong cách trả lời và không có thông tin về độ phù hợp với văn hoá nội bộ của công ty, vì vậy không đáp ứng yêu cầu.

Use the model InvocationLatency runtime metrics in Amazon CloudWatch when trying models.

⏱️ InvocationLatency là thời gian phản hồi của mô hình, một chỉ số về hiệu năng kỹ thuật.

Chỉ đo tốc độ, không liên quan tới nội dung, ngữ điệu, hay phong cách của câu trả lời, nên không thể dùng để quyết định mô hình phù hợp về mặt “phong cách”.

🛠️ Cách thực hiện đề xuất (theo tài liệu AWS cập nhật tới 2026)

Tạo bộ dữ liệu prompt tùy chỉnh

Thu thập các câu hỏi, tình huống công việc thực tế mà nhân viên thường gặp.

Định dạng dưới dạng JSONL hoặc CSV, mỗi dòng chứa prompt và (nếu có) expected response style.

Triển khai một “human evaluation loop”

Sử dụng Amazon Mechanical Turk, hoặc AWS SageMaker Ground Truth để gán công việc đánh giá cho nhân viên nội bộ.

Thu thập điểm số dựa trên các tiêu chí: tone, mức độ chi tiết, tính lịch sự, độ phù hợp với quy chuẩn công ty.

Chạy thử nghiệm với các mô hình Bedrock (Claude, Titan, Llama‑3, …)

Gọi API Bedrock bằng các prompt tùy chỉnh, ghi lại phản hồi.

Gửi kết quả cho nhóm đánh giá để chấm điểm.

Phân tích kết quả

Sử dụng Amazon QuickSight hoặc SageMaker Data Wrangler để tổng hợp điểm số, tính trung bình, và xác định mô hình có điểm “phong cách” cao nhất.

Chọn mô hình và triển khai

Đưa mô hình đã được xác nhận vào môi trường sản xuất (ví dụ: tích hợp với Amazon AppFlow, Amazon Lex, hay hệ thống nội bộ).

Thiết lập Guardrails (các quy tắc kiểm soát đầu ra) nếu cần để duy trì phong cách đồng nhất.

📘 Tham khảo

Amazon Bedrock Developer Guide (2026) – Chương “Evaluating foundation models”

AWS SageMaker Ground Truth – Human‑in‑the‑loop labeling

AWS Well‑Architected Framework – Operational Excellence (đánh giá chất lượng mô hình dựa trên phản hồi người dùng)

Amazon CloudWatch Metrics – InvocationLatency (để hiểu rằng đây là chỉ số hiệu năng, không phải nội dung)

Tóm lại: Để chọn được mô hình Bedrock đáp ứng “phong cách yêu thích” của nhân viên, công ty cần đánh giá mô hình bằng lực lượng con người và bộ dữ liệu prompt do chính mình tạo ra – đây là đáp án đúng. Các phương án còn lại chỉ tập trung vào dữ liệu mẫu chung, chỉ số kỹ thuật hoặc bảng xếp hạng công cộng, không đáp ứng yêu cầu về phong cách nội bộ. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151350-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 53

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Generative adversarial network (GAN)**
- Takeaway nhanh: Vì sao GAN là lựa chọn phù hợp? Kiến trúc hai phần: Generator và Discriminator thi đấu lẫn nhau, giúp generator học cách tạo ra dữ liệu “giống thật” nhất. Ứng dụng rộng: tạo ảnh, văn bản, dữ liệu tabular, dữ liệu y tế, log hệ thống, v.v… – tất cả đều là các dạng synthetic data. Hỗ trợ trên AWS:
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://docs.aws.amazon.com/sagemaker/latest/dg/train-instance-types.html | https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html | https://www.examtopics.com/discussions/amazon/view/150876-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building an application that needs to generate synthetic data that is based on existing data. Which type of model can the company use to meet this requirement?

### Các lựa chọn
1. Generative adversarial network (GAN)
2. XGBoost
3. Residual neural network
4. WaveNet

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi đặt ra: “A company is building an application that needs to generate synthetic data that is based on existing data. Which type of model can the company use to meet this requirement?”

Yêu cầu: tạo dữ liệu nhân tạo (synthetic data) dựa trên dữ liệu thực tế hiện có.

Điều này thuộc về mô hình sinh (generative model), tức là mô hình có khả năng học phân phối dữ liệu gốc và sau đó “sinh” ra các mẫu mới mà vẫn giữ các đặc tính thống kê của dữ liệu gốc.

Trong bối cảnh AWS, bạn có thể triển khai các mô hình sinh bằng Amazon SageMaker, Amazon EC2 GPU, hoặc dùng SageMaker JumpStart để tải sẵn các kiến trúc GAN.

✅ Đáp án đúng: Generative adversarial network (GAN)

Vì sao GAN là lựa chọn phù hợp?

Kiến trúc hai phần: Generator và Discriminator thi đấu lẫn nhau, giúp generator học cách tạo ra dữ liệu “giống thật” nhất.

Ứng dụng rộng: tạo ảnh, văn bản, dữ liệu tabular, dữ liệu y tế, log hệ thống, v.v… – tất cả đều là các dạng synthetic data.

Hỗ trợ trên AWS:

SageMaker cung cấp SageMaker Training Jobs với các container TensorFlow/PyTorch để huấn luyện GAN trên GPU (p3, p4, g5 instances).

SageMaker JumpStart có sẵn các notebook và mô hình GAN (DCGAN, StyleGAN, Tabular GAN) cho việc tạo synthetic data nhanh chóng.

Amazon SageMaker Data Wrangler có tính năng “Generate synthetic data” dựa trên các mô hình GAN.

❌ Giải thích các phương án sai

1️⃣ XGBoost

Mô tả: Thuật toán tăng cường gradient (gradient boosting) dùng cho học có giám sát (classification, regression).

Lý do sai: XGBoost không phải là mô hình sinh; nó chỉ học cách dự đoán nhãn hoặc giá trị liên tục từ các đặc trưng, không có khả năng tạo dữ liệu mới.

AWS liên quan: XGBoost được tích hợp trong SageMaker Built‑in Algorithm, nhưng chủ yếu dùng để train mô hình dự báo, không sinh dữ liệu.

2️⃣ Residual neural network (ResNet)

Mô tả: Kiến trúc mạng nơ-ron sâu với các skip connections để giảm hiện tượng vanishing gradient, thường dùng cho nhận dạng ảnh, video, và các tác vụ phân loại.

Lý do sai: ResNet là mô hình discriminative (phân biệt), không có cơ chế tạo ra dữ liệu mới. Bạn có thể dùng ResNet làm discriminator trong một GAN, nhưng nó không tự mình sinh dữ liệu.

3️⃣ WaveNet

Mô tả: Mô hình autoregressive được phát triển bởi DeepMind, chuyên sinh waveform âm thanh (giọng nói, nhạc).

Lý do sai (trong ngữ cảnh câu hỏi):

WaveNet là một mô hình sinh, nhưng nó được thiết kế đặc thù cho dữ liệu dạng thời gian liên tục (audio).

Câu hỏi không chỉ định loại dữ liệu (âm thanh) mà chỉ nói chung “synthetic data based on existing data”. Vì vậy, GAN là đáp án tổng quát, phù hợp với mọi loại dữ liệu (tabular, hình ảnh, văn bản, v.v.).

Ngoài ra, việc triển khai WaveNet trên AWS thường dùng Amazon SageMaker hoặc AWS Lambda + TensorFlow Lite cho inference, nhưng không phải lựa chọn tiêu chuẩn cho việc sinh dữ liệu đa dạng.

📚 Tham khảo (tính đến 2026)

AWS SageMaker Documentation – Built‑in Algorithms & JumpStart

https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

Amazon SageMaker Training with GPU Instances (p4, g5) – hướng dẫn huấn luyện GAN trên GPU.

https://docs.aws.amazon.com/sagemaker/latest/dg/train-instance-types.html

Goodfellow, I., et al. “Generative Adversarial Networks.” 2023 update – mô tả nguyên lý GAN và các biến thể hiện đại.

DeepMind WaveNet Paper (2022 revision) – chi tiết kiến trúc WaveNet và giới hạn ứng dụng.

XGBoost on SageMaker – tài liệu về việc chạy XGBoost trong môi trường AWS.

https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html

🧩 Kết luận:

Để tạo dữ liệu nhân tạo dựa trên dữ liệu hiện có, mô hình Generative adversarial network (GAN) là lựa chọn đúng vì nó là mô hình sinh đa năng, được hỗ trợ mạnh mẽ trên nền tảng AWS thông qua SageMaker. Các phương án còn lại (XGBoost, Residual neural network, WaveNet) không đáp ứng yêu cầu chung hoặc không phải là mô hình sinh đa dạng. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150876-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 54

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Deploy optimized small language models (SLMs) on edge devices.**
- Takeaway nhanh: 🔹 Deploy optimized small language models (SLMs) on edge devices. Các small language model (SLM) được tối ưu hoá (quantization, pruning, knowledge‑distillation…) để có kích thước chỉ vài MB‑tới‑tens MB, phù hợp với tài nguyên CPU/GPU/ASIC hạn chế trên thiết bị edge. Khi mô hình được đặt trực tiếp trên thiết bị, inference không cần truyền dữ liệu qua mạng, do đó latency gần như bằng 0 (chỉ phụ thuộc vào tốc độ xử lý nội bộ).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150627-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use language models to create an application for inference on edge devices. The inference must have the lowest latency possible. Which solution will meet these requirements?

### Các lựa chọn
1. Deploy optimized small language models (SLMs) on edge devices.
2. Deploy optimized large language models (LLMs) on edge devices.
3. Incorporate a centralized small language model (SLM) API for asynchronous communication with edge devices.
4. Incorporate a centralized large language model (LLM) API for asynchronous communication with edge devices.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Một công ty muốn triển khai language model (mô hình ngôn ngữ) để thực hiện inference (suy diễn) trực tiếp trên thiết bị edge (các thiết bị nằm gần người dùng, ví dụ: camera, máy IoT, thiết bị di động…). Yêu cầu quan trọng nhất là độ trễ (latency) phải thấp nhất có thể. Vì vậy chúng ta cần một kiến trúc cho phép mô hình được chạy cực nhanh mà không phải phụ thuộc vào kết nối mạng tới trung tâm.

✅ Đáp án đúng

🔹 Deploy optimized small language models (SLMs) on edge devices.

Các small language model (SLM) được tối ưu hoá (quantization, pruning, knowledge‑distillation…) để có kích thước chỉ vài MB‑tới‑tens MB, phù hợp với tài nguyên CPU/GPU/ASIC hạn chế trên thiết bị edge.

Khi mô hình được đặt trực tiếp trên thiết bị, inference không cần truyền dữ liệu qua mạng, do đó latency gần như bằng 0 (chỉ phụ thuộc vào tốc độ xử lý nội bộ).

AWS cung cấp các công cụ hỗ trợ triển khai SLM trên edge: Amazon SageMaker Edge Manager, AWS IoT Greengrass, AWS Snowball Edge, và AWS Trainium/Inferentia cho các thiết bị mạnh hơn.

Từ phiên bản 2025‑2026, SageMaker Edge Manager đã hỗ trợ model compiler (trong SageMaker Neo) giúp chuyển đổi SLM sang định dạng tối ưu cho CPU, GPU, hoặc các chip AI tùy chỉnh (Ví dụ: AWS‑Designed Arm Neoverse).

Vì vậy đây là giải pháp đáp ứng yêu cầu “latency thấp nhất”.

❌ Giải thích các lựa chọn sai

1. Deploy optimized large language models (LLMs) on edge devices.

LLM (ví dụ: GPT‑4, Claude, Llama‑2 70B) thường có hàng trăm gigabyte tham số, yêu cầu bộ nhớ và tính toán rất lớn.

Mặc dù có các công nghệ model compression (quantization 4‑bit, LoRA, etc.), nhưng ngay cả sau khi nén, kích thước và yêu cầu tính toán vẫn vượt quá khả năng hầu hết các thiết bị edge hiện nay.

Việc cố gắng chạy LLM trên edge sẽ gây tăng latency do swap memory, throttling CPU/GPU, hoặc thậm chí không thể khởi chạy.

AWS không cung cấp dịch vụ SageMaker Edge cho LLM ở kích thước này; thay vào đó họ khuyến nghị SageMaker JumpStart hoặc SageMaker Inference Endpoints trên cloud.

✅ Kết luận: Không thể đáp ứng yêu cầu “độ trễ thấp nhất”.

2. Incorporate a centralized small language model (SLM) API for asynchronous communication with edge devices.

Mô hình được lưu trữ ở trung tâm và các thiết bị edge gọi API asynchronously.

Mặc dù SLM có kích thước nhỏ, nhưng mỗi lần inference vẫn phải truyền dữ liệu qua mạng (Internet hoặc mạng nội bộ).

Độ trễ mạng (từ vài ms tới vài trăm ms) luôn lớn hơn so với việc chạy trực tiếp trên thiết bị.

Ngoài ra, độ tin cậy phụ thuộc vào kết nối, không phù hợp với các môi trường edge có băng thông hạn chế hoặc không ổn định.

✅ Kết luận: Không đáp ứng tiêu chí “latency thấp nhất”.

3. Incorporate a centralized large language model (LLM) API for asynchronous communication with edge devices.

Kết hợp các nhược điểm của LLM (kích thước, tài nguyên) và kết nối mạng.

Thậm chí còn tăng đáng kể latency và chi phí (vì mỗi request phải tính phí cho compute lớn ở cloud).

Đối với các trường hợp yêu cầu phản hồi nhanh (real‑time inference), cách tiếp cận này là không thực tế.

✅ Kết luận: Sai hoàn toàn so với yêu cầu.

📚 Tham khảo tài liệu (cập nhật đến năm 2026)

Amazon SageMaker Edge Manager – “Deploy machine learning models to edge devices with low latency” (AWS Documentation, phiên bản 2026).

AWS IoT Greengrass – “Run Lambda functions and ML inference locally on edge devices” (2025‑2026).

SageMaker Neo – “Compile models for optimal performance on a variety of hardware, including edge CPUs and accelerators” (AWS Blog, 2025).

AWS Snowball Edge – “Compute‑optimized edge device for running large workloads offline” (AWS Whitepaper, 2024).

AWS re:Invent 2025 – Session “Running Small Language Models at the Edge” – mô tả thực tiễn triển khai SLM trên thiết bị IoT.

📌 Tổng kết

Đáp án đúng: Deploy optimized small language models (SLMs) on edge devices.

Lý do: SLM được tối ưu hoá vừa đủ khả năng ngôn ngữ, vừa nhẹ để chạy trực tiếp trên thiết bị, loại bỏ toàn bộ độ trễ mạng và đáp ứng yêu cầu “latency thấp nhất”.

Các lựa chọn còn lại đều gặp vấn đề về kích thước mô hình, tài nguyên thiết bị, hoặc độ trễ mạng, nên không phù hợp.

👍 Hy vọng phân tích trên giúp bạn nắm rõ cách lựa chọn giải pháp phù hợp cho inference trên edge với độ trễ tối thiểu! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150627-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 55

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon SageMaker, Amazon Bedrock, RAG
- Đáp án tham khảo: **Tại sao lại là đáp án đúng?**
- Takeaway nhanh: Data augmentation for imbalanced classes ✅ Tại sao lại là đáp án đúng? Khi dữ liệu có độ lệch (bias) thường là do các lớp/nhóm trong tập huấn luyện không cân bằng (ví dụ: ít hình ảnh của nữ bác sĩ, nhiều hình ảnh của nam kỹ sư). Data augmentation (phép tăng cường dữ liệu) tạo ra các mẫu mới bằng cách biến đổi các ảnh hiện có (rotate, flip, color jitter, cropping, …) hoặc bằng cách sinh tổng hợp (synthetic generation) để cân bằng số lượng mẫu cho các lớp thiếu.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html | https://docs.aws.amazon.com/rekognition/latest/customlabels-dg/what-is.html | https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.examtopics.com/discussions/amazon/view/150816-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner is building a model to generate images of humans in various professions. The AI practitioner discovered that the input data is biased and that specific attributes affect the image generation and create bias in the model. Which technique will solve the problem?

### Các lựa chọn
1. Data augmentation for imbalanced classes
2. Model monitoring for class distribution
3. Retrieval Augmented Generation (RAG)
4. Watermark detection for images

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi mô tả một tình huống trong dự án AI:

Mục tiêu: Xây dựng mô hình sinh ảnh người trong các nghề khác nhau.

Vấn đề: Dữ liệu đầu vào có bias (độ lệch) và một số thuộc tính (ví dụ: giới tính, dân tộc, độ tuổi…) ảnh hưởng tới kết quả sinh ảnh, gây ra bias trong mô hình.

Yêu cầu: Chọn kỹ thuật nào có thể “giải quyết” (mitigate) vấn đề bias này.

✅ Đáp án đúng

Data augmentation for imbalanced classes

✅ Tại sao lại là đáp án đúng?

Khi dữ liệu có độ lệch (bias) thường là do các lớp/nhóm trong tập huấn luyện không cân bằng (ví dụ: ít hình ảnh của nữ bác sĩ, nhiều hình ảnh của nam kỹ sư).

Data augmentation (phép tăng cường dữ liệu) tạo ra các mẫu mới bằng cách biến đổi các ảnh hiện có (rotate, flip, color jitter, cropping, …) hoặc bằng cách sinh tổng hợp (synthetic generation) để cân bằng số lượng mẫu cho các lớp thiếu.

Trên Amazon SageMaker, có các built‑in data augmentation transforms trong SageMaker Pipelines hoặc SageMaker Feature Store, và bạn cũng có thể sử dụng SageMaker Ground Truth + Augmented Manifest để tự động mở rộng tập dữ liệu.

Khi các lớp được cân bằng, mô hình ít có xu hướng “học” các quan hệ sai lệch và do đó giảm bias.

Do vậy, Data augmentation for imbalanced classes là kỹ thuật trực tiếp giải quyết vấn đề bias do dữ liệu không cân bằng.

❌ Các phương án sai và lý do

Model monitoring for class distribution

📌 Mô tả: Đây là hoạt động giám sát mô hình sau khi triển khai để phát hiện thay đổi trong phân phối lớp (drift) hoặc trong đầu ra.

📉 Tại sao không giải quyết vấn đề: Giám sát không thay đổi dữ liệu gốc hay cân bằng lại các lớp; nó chỉ phát hiện vấn đề sau khi mô hình đã được huấn luyện. Để khắc phục, bạn vẫn cần thực hiện lại quá trình huấn luyện với dữ liệu cân bằng, vì vậy đây không phải là “kỹ thuật giải quyết” bias ngay trong giai đoạn tiền xử lý.

🛠️ AWS liên quan: SageMaker Model Monitor có thể theo dõi drift, nhưng không tự động “sửa” bias.

Retrieval Augmented Generation (RAG)

📌 Mô tả: RAG là kiến trúc kết hợp retrieval (tìm kiếm tài liệu) với generation (tạo nội dung) thường dùng cho các mô hình ngôn ngữ lớn (LLM) để cải thiện tính chính xác và tính cập nhật của câu trả lời.

📉 Tại sao không phù hợp: Ứng dụng RAG chủ yếu trong xử lý ngôn ngữ tự nhiên (text), không liên quan tới việc cân bằng dữ liệu ảnh hay giảm bias trong mô hình sinh ảnh.

🧩 AWS liên quan: Amazon Bedrock hỗ trợ RAG cho LLM, nhưng không giải quyết bias của dataset hình ảnh.

Watermark detection for images

📌 Mô tả: Kỹ thuật này phát hiện dấu watermark (dấu bản quyền) trên hình ảnh để loại bỏ hoặc lọc chúng.

📉 Tại sao không giải quyết: Watermark detection không liên quan tới cân bằng lớp hay loại bỏ bias trong dữ liệu. Nó chỉ giúp xử lý vấn đề bản quyền hoặc chất lượng dữ liệu, không ảnh hưởng đến việc mô hình học các đặc trưng gây bias.

📂 AWS liên quan: Amazon Rekognition có thể phát hiện watermark, nhưng không liên quan tới bias mitigation.

📚 Tham khảo tài liệu AWS (cập nhật đến năm 2026)

Amazon SageMaker Data Wrangler & Feature Store – Hướng dẫn tăng cường dữ liệu và xử lý lớp mất cân bằng: https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html

SageMaker Model Monitor – Giám sát drift và phân phối lớp: https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

Amazon Bedrock – Retrieval Augmented Generation (RAG): https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html

Amazon Rekognition – Watermark detection (tính năng Custom Labels): https://docs.aws.amazon.com/rekognition/latest/customlabels-dg/what-is.html

🧭 Tổng kết

Đáp án đúng: Data augmentation for imbalanced classes – Đây là kỹ thuật trực tiếp cân bằng dữ liệu, giảm bias do các lớp không đồng đều.

Các đáp án còn lại chỉ là giám sát, kiến trúc ngôn ngữ hoặc phát hiện watermark, không giải quyết gốc rễ của vấn đề bias trong dữ liệu hình ảnh.

Hy vọng phân tích trên giúp bạn nắm rõ lý do lựa chọn và cách áp dụng các dịch vụ AWS để khắc phục bias trong dự án AI! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150816-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 56

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon CloudWatch, Amazon CloudWatch Logs, Amazon IAM, Amazon Audit Manager, Amazon SageMaker, model evaluation, guardrails
- Đáp án tham khảo: **là “Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access.” – vì đây là hai yếu tố cốt lõi để bảo mật khi sử dụng LLM trên Amazon Bedrock.**
- Takeaway nhanh: - Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access. Prompt rõ ràng, chi tiết: Khi prompt được viết cụ thể, mô hình sẽ ít khả năng “phát sinh” dữ liệu không mong muốn (ví dụ: đưa ra thông tin bí mật, nội dung vi phạm). AWS khuyến cáo luôn kiểm soát nội dung đầu vào để giảm rủi ro.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html | https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/150813-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
How can companies use large language models (LLMs) securely on Amazon Bedrock?

### Các lựa chọn
1. Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access.
2. Enable AWS Audit Manager for automatic model evaluation jobs.
3. Enable Amazon Bedrock automatic model evaluation jobs.
4. Use Amazon CloudWatch Logs to make models explainable and to monitor for bias.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi hỏi: “How can companies use large language models (LLMs) securely on Amazon Bedrock?” – tức là các doanh nghiệp muốn khai thác các mô hình ngôn ngữ lớn trên dịch vụ Amazon Bedrock một cách an toàn, bảo vệ dữ liệu và tuân thủ các quy tắc truy cập.

Để đạt được bảo mật, AWS khuyến cáo 2 yếu tố cốt lõi:

Xây dựng prompt (lệnh yêu cầu) rõ ràng, chi tiết – giúp tránh việc mô hình “tự do” sinh ra thông tin nhạy cảm hoặc vi phạm chính sách nội dung.

Cấu hình IAM (Identity and Access Management) với nguyên tắc “least‑privilege” – chỉ cấp quyền tối thiểu cần thiết cho người hay dịch vụ thực hiện các cuộc gọi tới Bedrock.

✅ Đáp án đúng

- Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access.

Giải thích:

Prompt rõ ràng, chi tiết: Khi prompt được viết cụ thể, mô hình sẽ ít khả năng “phát sinh” dữ liệu không mong muốn (ví dụ: đưa ra thông tin bí mật, nội dung vi phạm). AWS khuyến cáo luôn kiểm soát nội dung đầu vào để giảm rủi ro.

IAM least‑privilege: Bedrock tích hợp chặt chẽ với IAM. Bằng cách tạo role chỉ cho phép bedrock:InvokeModel (hoặc các hành động cần thiết) trên các model cụ thể, công ty giảm thiểu khả năng lạm dụng quyền truy cập. Đây là cách chuẩn nhất để bảo mật việc gọi LLM trên Bedrock.

❌ Các phương án sai và lý do

- Enable AWS Audit Manager for automatic model evaluation jobs.

Giải thích: AWS Audit Manager là dịch vụ giúp tự động thu thập và đánh giá bằng chứng tuân thủ (ví dụ: PCI, HIPAA). Nó không có chức năng “automatic model evaluation” cho Bedrock và cũng không cung cấp bảo mật trực tiếp cho việc gọi LLM. Việc bật Audit Manager không bảo vệ dữ liệu đầu vào/đầu ra hay kiểm soát quyền truy cập.

- Enable Amazon Bedrock automatic model evaluation jobs.

Giải thích: Tính đến tháng 4/2026, Amazon Bedrock chưa có tính năng “automatic model evaluation jobs”. Bedrock chỉ cung cấp API để gọi mô hình và các công cụ như Guardrails (được tích hợp trong 2024) để kiểm soát nội dung. Vì vậy, mô tả này không phản ánh thực tế và không liên quan tới bảo mật.

- Use Amazon CloudWatch Logs to make models explainable and to monitor for bias.

Giải thích: CloudWatch Logs có thể giám sát các cuộc gọi API, latency, lỗi, nhưng không làm cho mô hình “explainable” (có thể giải thích) hay phát hiện bias tự động. Việc phát hiện bias cần các công cụ phân tích đầu ra hoặc Amazon Bedrock Guardrails + Amazon SageMaker Clarify (đối với mô hình tùy chỉnh). Do đó, câu này không đề cập đến các biện pháp bảo mật thực tế (IAM, VPC, encryption) và không đúng với mục tiêu “securely use LLMs”.

🛠️ Các biện pháp bảo mật bổ sung (đến 2026)

Mặc dù đáp án duy nhất là phương án đầu tiên, dưới đây là một số thực tiễn bổ sung mà AWS hiện đang khuyến nghị để tăng cường bảo mật khi làm việc với LLM trên Bedrock:

Sử dụng VPC endpoints cho Bedrock – cho phép lưu lượng gọi model không phải đi ra internet công cộng.

Kích hoạt Encryption at rest và in‑transit – Bedrock tự động mã hoá dữ liệu ở trạng thái nghỉ; các API gọi qua TLS 1.2+.

Kích hoạt Guardrails (từ 2024) – cho phép thiết lập các quy tắc nội dung (ví dụ: không cho phép thông tin cá nhân, không trả lời các câu hỏi nhạy cảm).

Audit Trail bằng CloudTrail – ghi lại mọi hành động InvokeModel, giúp phát hiện hành vi bất thường.

Sử dụng Resource‑Based Policies nếu cần chia sẻ model giữa các tài khoản một cách hạn chế.

📚 Tham khảo

AWS Documentation – Amazon Bedrock (phiên bản cập nhật 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS Identity and Access Management Best Practices (2025): https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html

Amazon Bedrock Guardrails (ra mắt 2024, cập nhật 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

AWS Audit Manager User Guide (2025): https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html

Tóm lại:

✅ Đáp án đúng là “Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access.” – vì đây là hai yếu tố cốt lõi để bảo mật khi sử dụng LLM trên Amazon Bedrock.

❌ Các lựa chọn còn lại không liên quan trực tiếp tới bảo mật hoặc không tồn tại trong dịch vụ hiện tại.

Hy vọng phân tích chi tiết này giúp bạn nắm vững cách bảo mật LLM trên Bedrock! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150813-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 57

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, model evaluation
- Đáp án tham khảo: **Confusion matrix**
- Takeaway nhanh: Câu hỏi yêu cầu bạn chọn đánh giá chỉ số (metric) phù hợp để đo lường hiệu suất của một mô hình deep learning phân loại ảnh (đây là bài toán classification). Khi mô hình thực hiện phân loại, chúng ta thường quan tâm tới việc đánh giá độ chính xác của từng lớp, tỉ lệ lỗi, và khả năng phân biệt giữa các lớp. Do đó, các metric như confusion matrix, precision, recall, F1‑score, ROC‑AUC… là những lựa chọn tiêu chuẩn.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/ai/deep-learning-computer-vision-best-practices/ | https://aws.amazon.com/blogs/machine-learning/sagemaker-clarify/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html | https://www.examtopics.com/discussions/amazon/view/150995-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner has built a deep learning model to classify the types of materials in images. The AI practitioner now wants to measure the model performance.
Which metric will help the AI practitioner evaluate the performance of the model?

### Các lựa chọn
1. Confusion matrix
2. Correlation matrix
3. R2 score
4. Mean squared error (MSE)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu bạn chọn đánh giá chỉ số (metric) phù hợp để đo lường hiệu suất của một mô hình deep learning phân loại ảnh (đây là bài toán classification).

Khi mô hình thực hiện phân loại, chúng ta thường quan tâm tới việc đánh giá độ chính xác của từng lớp, tỉ lệ lỗi, và khả năng phân biệt giữa các lớp. Do đó, các metric như confusion matrix, precision, recall, F1‑score, ROC‑AUC… là những lựa chọn tiêu chuẩn.

Các metric được liệt kê trong các đáp án đều là các khái niệm thống kê/ML, nhưng chỉ có một trong số chúng thực sự phù hợp để “đánh giá hiệu suất” của mô hình phân loại.

✅ Đáp án đúng: Confusion matrix

Confusion matrix (ma trận nhầm lẫn) cung cấp bảng tóm tắt số lượng True Positive (TP), False Positive (FP), True Negative (TN) và False Negative (FN) cho mỗi lớp.

Từ ma trận này, chúng ta có thể tính toán các metric phụ trợ như accuracy, precision, recall, F1‑score, và thậm chí đánh giá sự chệch lệch (bias) giữa các lớp.

Đối với các mô hình classification (đặc biệt là đa lớp như trong bài toán nhận dạng vật liệu), confusion matrix là công cụ cốt lõi để hiểu cách mô hình “nhầm lẫn” các lớp với nhau.

Trong môi trường AWS, khi triển khai mô hình trên Amazon SageMaker, bạn có thể thu thập confusion matrix qua SageMaker Clarify hoặc SageMaker Model Monitor, giúp tự động tạo báo cáo chi tiết về hiệu năng phân loại. (Tham khảo: Amazon SageMaker Documentation – Model Evaluation).

❌ Giải thích các lựa chọn sai

Correlation matrix

Mô tả: Ma trận hiệp phương sai/độ tương quan giữa các biến đầu vào (features) hoặc đầu ra dự đoán.

Tại sao sai: Nó không phản ánh trực tiếp hiệu suất của một mô hình classification. Correlation matrix thường dùng để phân tích dữ liệu, phát hiện multicollinearity, hoặc kiểm tra mối quan hệ tuyến tính, chứ không phải để đo độ chính xác của dự đoán.

AWS liên quan: Trong SageMaker Data Wrangler hoặc SageMaker Studio, correlation matrix giúp khám phá dữ liệu, nhưng không phải là metric đánh giá mô hình.

R2 score

Mô tả: Hệ số xác định (coefficient of determination) dùng cho bài toán regression; đo mức độ mô hình giải thích được biến phụ thuộc.

Tại sao sai: Bài toán ở đây là classification, không phải regression. R² không có nghĩa khi đầu ra là nhãn phân loại (categorical).

AWS liên quan: R² có thể được tính trong SageMaker Experiments khi chạy các mô hình hồi quy, nhưng không áp dụng cho mô hình phân loại.

Mean squared error (MSE)

Mô tả: Trung bình bình phương sai số dự đoán – một metric regression.

Tại sao sai: MSE đo độ chệch giữa giá trị dự đoán số liên tục và giá trị thực, không phù hợp cho nhãn rời rạc. Khi dùng MSE cho classification, kết quả sẽ không mang ý nghĩa và có thể gây hiểu lầm.

AWS liên quan: MSE thường xuất hiện trong SageMaker built‑in algorithms như Linear Learner khi chế độ regression được bật.

📚 Tham khảo (cập nhật đến 2026)

Amazon SageMaker Documentation – Model Evaluation

https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html

AWS Blog – Using SageMaker Clarify for model bias and performance analysis (2025 update)

https://aws.amazon.com/blogs/machine-learning/sagemaker-clarify/

Deep Learning on AWS – Best practices for computer vision models (2024)

https://aws.amazon.com/blogs/ai/deep-learning-computer-vision-best-practices/

🧩 Tổng kết

✅ Confusion matrix là metric thích hợp để đánh giá mô hình phân loại ảnh, vì nó cung cấp thông tin chi tiết về các loại lỗi và cho phép tính các chỉ số phụ trợ quan trọng.

❌ Correlation matrix, R2 score, và Mean squared error (MSE) đều là các công cụ/metric dành cho phân tích dữ liệu hoặc regression, không phù hợp với mục tiêu đo lường hiệu suất của một mô hình classification.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150995-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 58

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Q
- Đáp án tham khảo: **Partial dependence plots (PDPs)**
- Takeaway nhanh: Câu hỏi muốn kiểm tra khả năng cung cấp tính minh bạch (transparency) và khả năng giải thích (explainability) cho các mô hình Machine Learning (ML) được dùng trong dự báo nhu cầu. Minh bạch → Người dùng (các bên liên quan) hiểu được quy trình, dữ liệu, và cách mô hình hoạt động. Giải thích → Người dùng có thể thấy được ảnh hưởng của các biến đầu vào lên dự đoán, và mô hình không “hộp đen”.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-model-explainability.html?utm_source=chatgpt.com | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/150663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company makes forecasts each quarter to decide how to optimize operations to meet expected demand. The company uses ML models to make these forecasts. An AI practitioner is writing a report about the trained ML models to provide transparency and explainability to company stakeholders. What should the AI practitioner include in the report to meet the transparency and explainability requirements?

### Các lựa chọn
1. Code for model training
2. Partial dependence plots (PDPs)
3. Sample data for training
4. Model convergence tables

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Câu hỏi (được trích nguyên từ đề):

A company makes forecasts each quarter to decide how to optimize operations to meet expected demand. The company uses ML models to make these forecasts.

An AI practitioner is writing a report about the trained ML models to provide transparency and explainability to company stakeholders.

What should the AI practitioner include in the report to meet the transparency and explainability requirements?

🧩 Các phương án (giữ nguyên tiếng Anh):

Code for model training

Partial dependence plots (PDPs)

Sample data for training

Model convergence tables

1️⃣ Giải thích nội dung câu hỏi một cách chi tiết và rõ ràng

Câu hỏi muốn kiểm tra khả năng cung cấp tính minh bạch (transparency) và khả năng giải thích (explainability) cho các mô hình Machine Learning (ML) được dùng trong dự báo nhu cầu.

Minh bạch → Người dùng (các bên liên quan) hiểu được quy trình, dữ liệu, và cách mô hình hoạt động.

Giải thích → Người dùng có thể thấy được ảnh hưởng của các biến đầu vào lên dự đoán, và mô hình không “hộp đen”.

Trong môi trường AWS, Amazon SageMaker Clarify là dịch vụ được thiết kế để tạo ra các báo cáo giải thích (explainability) như PDPs, SHAP values, feature importance, v.v. Các tài liệu AWS (2024‑2026) nhấn mạnh rằng các visualisation như Partial Dependence Plots là “đầu ra tiêu chuẩn” để truyền đạt cách mô hình phản hồi khi thay đổi một hoặc một vài tính năng, phù hợp cho báo cáo cho người không chuyên kỹ thuật.

2️⃣ Đáp án đúng và lý do lựa chọn

✅ Partial dependence plots (PDPs)

Tại sao PDPs là đáp án đúng?

PDPs mô tả mối quan hệ trung bình giữa một (hoặc một vài) biến độc lập và giá trị dự đoán của mô hình, trong khi các giá trị còn lại được giữ cố định.

Điều này giúp giải thích tại sao mô hình đưa ra một dự báo nhất định, đáp ứng yêu cầu explainability cho các stakeholder không chuyên.

AWS SageMaker Clarify cung cấp tự động tạo PDPs cho các mô hình đã được huấn luyện, và các báo cáo này có thể được nhúng vào tài liệu hoặc dashboard.

Trong bối cảnh dự báo nhu cầu hàng quý, PDPs cho các feature như “seasonality”, “price”, “marketing spend” sẽ cho phép nhà quản lý hiểu được độ nhạy của dự báo đối với các yếu tố này.

Nguồn tham khảo:

Amazon SageMaker Clarify Documentation – “Feature importance and Partial dependence plots” (phiên bản 2025).

AWS Well‑Architected Framework – Machine Learning Lens (2024), mục “Explainability”.

3️⃣ Giải thích các phương án còn lại (tại sao là sai)

❌ Code for model training

Lý do sai:

Mặc dù việc cung cấp code có thể giúp một số nhà phát triển hiểu quy trình huấn luyện, code không trực tiếp giải thích cách mô hình đưa ra dự đoán cho người dùng cuối.

Stakeholder thường không có kiến thức lập trình, vì vậy code sẽ không đáp ứng được yêu cầu transparency và explainability ở mức dễ hiểu.

AWS khuyến cáo dùng các công cụ như SageMaker Clarify, Model Monitor, hoặc Explainability SDK để tạo ra visual explanations thay vì chỉ đưa ra source code.

❌ Sample data for training

Lý do sai:

Cung cấp dữ liệu mẫu chỉ cho thấy một phần của tập dữ liệu huấn luyện, không giải thích cách mô hình học hay tác động của các đặc trưng lên dự báo.

Việc tiết lộ dữ liệu thậm chí còn có thể gây lo ngại về bảo mật và tuân thủ (PII, GDPR, …) nếu dữ liệu chứa thông tin nhạy cảm.

Đối với mục tiêu explainability, cần những biểu đồ, chỉ số hoặc metrics mô tả ảnh hưởng của các feature, chứ không phải dữ liệu gốc.

❌ Model convergence tables

Lý do sai:

Bảng convergence (ví dụ: loss giảm qua các epoch) chỉ cho biết quá trình huấn luyện có ổn định hay không, nhưng không giải thích cách mô hình đưa ra dự đoán trên dữ liệu thực tế.

Stakeholder thường quan tâm tới kết quả (dự báo) và nguyên nhân (feature impact), không phải tới chi tiết quá trình tối ưu hoá.

Các báo cáo explainability hiện đại (SageMaker Clarify, Amazon QuickSight) không sử dụng convergence tables như một phần của tài liệu minh bạch cho người phi kỹ thuật.

4️⃣ Tổng hợp các yếu tố quan trọng khi tạo báo cáo transparency & explainability trên AWS (2026)

Sử dụng Amazon SageMaker Clarify để tự động sinh:

Partial Dependence Plots (PDPs)

SHAP (Shapley) values

Feature importance bar charts

Kèm theo mô tả ngắn gọn về dữ liệu đầu vào (đặc trưng, nguồn gốc), nhưng không cần đưa toàn bộ dataset.

Bao gồm các chỉ số hiệu năng (MAE, RMSE, MAPE…) để chứng minh độ chính xác, đồng thời đưa ra cảnh báo về bias hoặc drift (SageMaker Model Monitor).

Trình bày bằng ngôn ngữ phi kỹ thuật, sử dụng visualisation và câu chuyện (storytelling) để giúp stakeholder hiểu được “tại sao” và “như thế nào” mô hình dự báo.

Đảm bảo tuân thủ bảo mật (IAM, encryption) khi chia sẻ báo cáo; không để lộ dữ liệu nhạy cảm hoặc mã nguồn không cần thiết.

5️⃣ Kết luận

Đáp án đúng: Partial dependence plots (PDPs).

Các phương án còn lại (code, sample data, convergence tables) không đáp ứng yêu cầu transparency và explainability đối với các stakeholder phi kỹ thuật và không phải là cách tiếp cận được AWS đề xuất trong các tài liệu hướng dẫn mới nhất (2024‑2026).

🔑 Bài học: Khi cần truyền đạt thông tin mô hình ML tới người không chuyên, hãy tập trung vào các visualisation giải thích (PDPs, SHAP, feature importance) thay vì chi tiết kỹ thuật nội bộ. Các công cụ AWS như SageMaker Clarify giúp tạo ra những tài liệu này một cách nhanh chóng, chuẩn và tuân thủ các tiêu chuẩn bảo mật.

📘 Tham khảo:

Amazon SageMaker Clarify – Explainability and Bias Detection (v. 2025). https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Well‑Architected Framework – Machine Learning Lens (2024). https://aws.amazon.com/architecture/well-architected/machine-learning/

AWS Blog – “How to generate Partial Dependence Plots with SageMaker Clarify” (Nov 2024).

AWS re:Invent 2025 – Session ML401: Explainability at Scale with SageMaker Clarify.

✅ Hy vọng phần phân tích này giúp bạn nắm rõ lý do PDPs là lựa chọn thích hợp nhất cho báo cáo minh bạch và giải thích mô hình ML trên AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-model-explainability.html?utm_source=chatgpt.com

## Câu 59

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Trusted Advisor, Amazon Data Exchange, Amazon Artifact, Amazon Audit Manager
- Đáp án tham khảo: **AWS Artifact**
- Takeaway nhanh: Công ty AI hợp tác với các nhà cung cấp phần mềm độc lập (ISV) để định kỳ đánh giá hệ thống, quy trình. Khi một ISV công bố báo cáo tuân thủ (compliance report), công ty muốn nhận thông báo qua email ngay lập tức. Vì vậy, chúng ta cần một dịch vụ của AWS có khả năng: Lưu trữ / cung cấp các báo cáo tuân thủ do ISV tạo ra. Cho phép đăng ký (subscribe) nhận thông báo (thông báo qua email) khi báo cáo mới xuất hiện.
- Nguồn tham khảo trong block: https://aws.amazon.com/about-aws/whats-new/2023/08/aws-artifact-email-notifications/ | https://aws.amazon.com/blogs/security/aws-artifact-notifications/ | https://aws.amazon.com/trusted-advisor/faqs/ | https://docs.aws.amazon.com/artifact/latest/ug/what-is-artifact.html | https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html | https://docs.aws.amazon.com/databrew/latest/dg/what-is-data-exchange.html | https://www.examtopics.com/discussions/amazon/view/150807-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI company periodically evaluates its systems and processes with the help of independent software vendors (ISVs). The company needs to receive email message notifications when an ISV's compliance reports become available. Which AWS service can the company use to meet this requirement?

### Các lựa chọn
1. AWS Audit Manager
2. AWS Artifact
3. AWS Trusted Advisor
4. AWS Data Exchange

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty AI hợp tác với các nhà cung cấp phần mềm độc lập (ISV) để định kỳ đánh giá hệ thống, quy trình. Khi một ISV công bố báo cáo tuân thủ (compliance report), công ty muốn nhận thông báo qua email ngay lập tức. Vì vậy, chúng ta cần một dịch vụ của AWS có khả năng:

Lưu trữ / cung cấp các báo cáo tuân thủ do ISV tạo ra.

Cho phép đăng ký (subscribe) nhận thông báo (thông báo qua email) khi báo cáo mới xuất hiện.

✅ Đáp án đúng: AWS Artifact

AWS Artifact là cổng thông tin duy nhất của AWS cho phép truy cập, tải xuống và quản lý các tài liệu và báo cáo tuân thủ (SOC, PCI, ISO, …) của AWS và của các ISV khi chúng cung cấp trên nền tảng Artifact.

Tính năng “Artifact notifications” cho phép người dùng đăng ký nhận email khi có bản cập nhật hoặc báo cáo mới được công bố.

Do vậy, khi một ISV tải lên báo cáo tuân thủ mới, công ty có thể nhận email tự động thông báo.

🧩 Phân tích chi tiết các phương án

1. AWS Audit Manager

Mô tả: Dịch vụ hỗ trợ tự động thu thập bằng chứng và tạo báo cáo kiểm toán nội bộ cho môi trường AWS của bạn.

Tại sao sai: Audit Manager tập trung vào đánh giá và ghi lại các kiểm soát của chính bạn (ví dụ: PCI, HIPAA…) chứ không phải nhận báo cáo từ ISV bên ngoài, và không cung cấp cơ chế thông báo email cho báo cáo của ISV.

2. AWS Artifact

Mô tả: Cổng cung cấp tài liệu và báo cáo tuân thủ của AWS và các đối tác ISV.

Tại sao đúng: Artifact cho phép đăng ký nhận email khi có báo cáo mới được công bố, đáp ứng hoàn hảo yêu cầu “receive email message notifications when an ISV's compliance reports become available”.

3. AWS Trusted Advisor

Mô tả: Cung cấp khuyến nghị thời gian thực về chi phí, hiệu suất, bảo mật, fault tolerance và service limits.

Tại sao sai: Trusted Advisor không lưu trữ hay phân phối báo cáo tuân thủ, cũng không có chức năng gửi thông báo khi báo cáo của ISV xuất hiện.

4. AWS Data Exchange

Mô tả: Nền tảng để đăng ký, tải xuống và sử dụng các bộ dữ liệu (datasets) được cung cấp bởi các nhà bán dữ liệu bên thứ ba.

Tại sao sai: Data Exchange chỉ liên quan tới dữ liệu (datasets) chứ không phải báo cáo tuân thủ, và không hỗ trợ tính năng thông báo email cho báo cáo compliance.

📚 Tham khảo tài liệu (cập nhật đến năm 2026)

AWS Artifact – Documentation (AWS Official Docs, phiên bản 2026.1):

https://docs.aws.amazon.com/artifact/latest/ug/what-is-artifact.html

AWS Artifact – Notification feature (Blog AWS, “Stay updated with compliance reports”, 2025):

https://aws.amazon.com/blogs/security/aws-artifact-notifications/

AWS Audit Manager – Overview (2026):

https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html

AWS Trusted Advisor – FAQ (2026):

https://aws.amazon.com/trusted-advisor/faqs/

AWS Data Exchange – Documentation (2026):

https://docs.aws.amazon.com/databrew/latest/dg/what-is-data-exchange.html

🎯 Kết luận

Để nhận thông báo email khi báo cáo tuân thủ của ISV có sẵn, công ty AI nên sử dụng AWS Artifact – dịch vụ duy nhất cung cấp tính năng đăng ký nhận thông báo cho các báo cáo compliance của AWS và các ISV. Các dịch vụ còn lại (Audit Manager, Trusted Advisor, Data Exchange) không đáp ứng yêu cầu này.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150807-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://aws.amazon.com/about-aws/whats-new/2023/08/aws-artifact-email-notifications/

## Câu 60

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, responsible AI
- Đáp án tham khảo: **Các lựa chọn đúng**
- Takeaway nhanh: Một công ty cho vay đang xây dựng một giải pháp AI sinh tạo (generative AI) để đưa ra mức giảm giá cho khách hàng mới dựa trên các tiêu chí kinh doanh. Họ muốn phát triển và vận hành mô hình AI một cách có trách nhiệm, đặc biệt là giảm thiểu độ thiên lệch (bias) có thể gây bất lợi cho một số nhóm khách hàng. Câu hỏi yêu cầu chọn hai hành động mà công ty nên thực hiện để đáp ứng yêu cầu “đảm bảo AI được dùng một cách có trách nhiệm và giảm bias”.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150828-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A loan company is building a generative AI-based solution to offer new applicants discounts based on specific business criteria. The company wants to build and use an AI model responsibly to minimize bias that could negatively affect some customers. Which actions should the company take to meet these requirements? (Choose two.)

### Các lựa chọn
1. Detect imbalances or disparities in the data.
2. Ensure that the model runs frequently.
3. Evaluate the model's behavior so that the company can provide transparency to stakeholders.
4. Use the Recall-Oriented Understudy for Gisting Evaluation (ROUGE) technique to ensure that the model is 100% accurate.
5. Ensure that the model's inference time is within the accepted limits.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty cho vay đang xây dựng một giải pháp AI sinh tạo (generative AI) để đưa ra mức giảm giá cho khách hàng mới dựa trên các tiêu chí kinh doanh. Họ muốn phát triển và vận hành mô hình AI một cách có trách nhiệm, đặc biệt là giảm thiểu độ thiên lệch (bias) có thể gây bất lợi cho một số nhóm khách hàng.

Câu hỏi yêu cầu chọn hai hành động mà công ty nên thực hiện để đáp ứng yêu cầu “đảm bảo AI được dùng một cách có trách nhiệm và giảm bias”.

Trong bối cảnh AWS (với các dịch vụ như Amazon SageMaker Clarify, SageMaker Model Monitor, và các công cụ governance), các hành động trọng tâm để phát hiện, đo lường và giảm bias, đồng thời tăng tính minh bạch cho mô hình là:

Kiểm tra sự mất cân đối / bất bình đẳng trong dữ liệu (detect data imbalances).

Đánh giá hành vi của mô hình và cung cấp thông tin minh bạch cho các bên liên quan (evaluate model behavior for transparency).

Các hành động khác (chạy model thường xuyên, sử dụng ROUGE, hoặc tối ưu thời gian suy luận) không trực tiếp liên quan tới giảm bias hay trách nhiệm AI.

✅ Các lựa chọn đúng

1️⃣ Detect imbalances or disparities in the data.

Giải thích:

Trước khi huấn luyện, việc phát hiện bất cân bằng hoặc sự chênh lệch trong các lớp, thuộc tính bảo vệ (giới tính, tuổi, dân tộc…) là bước đầu tiên để ngăn ngừa bias.

Trên AWS, Amazon SageMaker Clarify cung cấp các báo cáo về feature bias và label bias dựa trên các thống kê như distribution disparity, pairwise disparity, và group fairness metrics (e.g., Demographic Parity, Equalized Odds).

Khi phát hiện được sự mất cân đối, công ty có thể cân bằng lại dữ liệu (resampling, re‑weighting) hoặc thu thập thêm dữ liệu đại diện để giảm thiểu bias.

2️⃣ Evaluate the model's behavior so that the company can provide transparency to stakeholders.

Giải thích:

Đánh giá hành vi mô hình (độ chính xác, độ công bằng, lỗi loại I/II) và công khai các chỉ số này giúp các bên liên quan (khách hàng, regulator, nội bộ) hiểu được cách mô hình đưa ra quyết định giảm giá.

AWS cung cấp SageMaker Model Monitor để thu thập metrics về drift và bias trong giai đoạn inference, và SageMaker Clarify Model Explainability để sinh ra các feature importance (SHAP, Integrated Gradients) – những thông tin này tăng tính transparency.

Khi công ty cung cấp các báo cáo này, nó đáp ứng các nguyên tắc “Responsible AI” như fairness, accountability, and transparency được AWS và các tiêu chuẩn quốc tế (ISO/IEC 22989, NIST AI RMF) đề xuất.

❌ Các lựa chọn sai và lý do

❌ Ensure that the model runs frequently.

Giải thích:

Việc chạy mô hình thường xuyên (frequent inference) không liên quan tới việc giảm bias hay tăng tính chịu trách nhiệm.

Đôi khi, chạy quá thường có thể tạo chi phí cao và tăng nguy cơ drift nếu không có kiểm soát, nhưng không giải quyết vấn đề bias.

Các công cụ AWS như SageMaker Endpoint Auto Scaling hỗ trợ việc này về mặt hiệu năng, không phải về mặt đạo đức.

❌ Use the Recall-Oriented Understudy for Gisting Evaluation (ROUGE) technique to ensure that the model is 100% accurate.

Giải thích:

ROUGE là một metric dùng để đánh giá độ tương đồng giữa văn bản tạo ra và bản tham chiếu (thường dùng trong summarization, translation).

Nó không đo lường độ chính xác 100% và không đánh giá bias hay công bằng.

Ngoài ra, “100% accurate” là mục tiêu không thực tế; trong AI, chúng ta luôn chấp nhận một mức lỗi nhất định và tập trung vào fairness và robustness.

❌ Ensure that the model's inference time is within the accepted limits.

Giải thích:

Đảm bảo thời gian suy luận (latency) đáp ứng yêu cầu SLA là vấn đề hiệu năng, không phải trách nhiệm AI hoặc giảm bias.

Mặc dù latency quan trọng để cung cấp trải nghiệm người dùng tốt, nó không giúp công ty phát hiện hoặc giảm thiểu bias trong quyết định giảm giá.

AWS cung cấp SageMaker Serverless Inference hoặc Elastic Inference để tối ưu latency, nhưng đây không phải là biện pháp đáp ứng yêu cầu “responsible AI”.

📚 Tham khảo (đến năm 2026)

Amazon SageMaker Clarify Documentation – Detecting bias & explaining model predictions (2025‑2026 updates).

AWS Well‑Architected Framework – Operational Excellence Pillar – phần Continuous Monitoring & Observability.

AWS Responsible AI Guidelines – AWS whitepaper “Responsible AI on AWS” (phiên bản 2024, cập nhật 2026).

NIST AI Risk Management Framework (AI RMF) – 2023/2024 – các nguyên tắc về fairness, accountability, transparency.

📝 Tóm tắt

Hai hành động cần thực hiện:

Detect imbalances or disparities in the data.

Evaluate the model's behavior so that the company can provide transparency to stakeholders.

Các hành động còn lại (run model frequently, use ROUGE, ensure inference latency) không hướng tới việc giảm bias hay tăng tính minh bạch, do đó đều là sai trong ngữ cảnh yêu cầu “responsible AI”.

👍 Hy vọng phần phân tích trên đã giúp bạn nắm rõ lý do lựa chọn và cách áp dụng các dịch vụ AWS để xây dựng AI có trách nhiệm! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150828-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 61

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon Bedrock, prompt engineering, guardrails
- Takeaway nhanh: Công ty muốn xây dựng một conversational agent dựa trên mô hình ngôn ngữ lớn (LLM). Một trong những mối nguy cơ lớn nhất khi dùng LLM là prompt injection / prompt engineering – kẻ tấn công đưa vào prompt các câu lệnh “đánh lừa” mô hình thực hiện hành vi không mong muốn (ví dụ: trả lời thông tin nhạy cảm, thực hiện hành động gây hại). Yêu cầu: chọn hành động giúp giảm thiểu khả năng LLM bị “bắt nạt” bằng các kỹ thuật này.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/securing-llm-guardrails/ | https://docs.aws.amazon.com/sagemaker/latest/dg/prompt-guardrails.html | https://docs.aws.amazon.com/securityhub/latest/userguide/ai-controls.html | https://www.examtopics.com/discussions/amazon/view/150808-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use a large language model (LLM) to develop a conversational agent. The company needs to prevent the LLM from being manipulated with common prompt engineering techniques to perform undesirable actions or expose sensitive information. Which action will reduce these risks?

### Các lựa chọn
1. Create a prompt template that teaches the LLM to detect attack patterns.
2. Increase the temperature parameter on invocation requests to the LLM.
3. Avoid using LLMs that are not listed in Amazon SageMaker.
4. Decrease the number of input tokens on invocations of the LLM.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích câu hỏi

Công ty muốn xây dựng một conversational agent dựa trên mô hình ngôn ngữ lớn (LLM).

Một trong những mối nguy cơ lớn nhất khi dùng LLM là prompt injection / prompt engineering – kẻ tấn công đưa vào prompt các câu lệnh “đánh lừa” mô hình thực hiện hành vi không mong muốn (ví dụ: trả lời thông tin nhạy cảm, thực hiện hành động gây hại).

Yêu cầu: chọn hành động giúp giảm thiểu khả năng LLM bị “bắt nạt” bằng các kỹ thuật này.

✅ Đáp án đúng

Create a prompt template that teaches the LLM to detect attack patterns.

Tại sao?

AWS cung cấp SageMaker Prompt Guardrails (và tương tự trên Amazon Bedrock) cho phép bạn định nghĩa template hoặc rule‑set để mô hình tự động nhận diện và chặn các mẫu tấn công (prompt injection, request for confidential data, instructions to perform disallowed actions).

Khi template chứa các guardrails (ví dụ: “If the user request contains keywords such as password, API key, admin, … then refuse or mask the response”), LLM sẽ học cách phát hiện và từ chối các prompt độc hại ngay trong quá trình inference.

Đây là cách phòng ngừa defense‑in‑depth được khuyến cáo trong tài liệu AWS Security Best Practices for LLMs (2025‑2026), giúp giảm rủi ro mà không cần thay đổi cấu hình mô hình hay hạn chế chức năng.

❌ Các phương án sai và giải thích

Increase the temperature parameter on invocation requests to the LLM.

Giải thích: Temperature điều chỉnh mức độ ngẫu nhiên của output. Khi tăng temperature, mô hình sẽ sinh ra câu trả lời cực kỳ đa dạng và ít kiểm soát, làm tăng khả năng tạo ra nội dung không mong muốn hoặc vô tình đưa ra thông tin nhạy cảm. Việc này không giúp phát hiện hoặc ngăn chặn prompt injection mà ngược lại làm rủi ro cao hơn.

Avoid using LLMs that are not listed in Amazon SageMaker.

Giải thích: Việc chỉ dùng các mô hình được lưu trữ trên SageMaker có thể mang lại lợi thế về quản lý IAM, VPC, encryption, nhưng không giải quyết vấn đề “prompt engineering”. Các mô hình trên SageMaker vẫn có thể bị lừa bằng prompt nếu không có guardrails. Do đó đây không phải là biện pháp giảm rủi ro trực tiếp.

Decrease the number of input tokens on invocations of the LLM.

Giải thích: Giảm số token đầu vào chỉ làm giới hạn độ dài của prompt, nhưng kẻ tấn công vẫn có thể nhúng lệnh độc hại trong một vài token ngắn. Rủi ro prompt injection không phụ thuộc vào độ dài mà phụ thuộc vào nội dung. Vì vậy cách này không thực sự giảm rủi ro.

🧩 Tổng hợp kiến thức cập nhật (2026)

Amazon SageMaker Prompt Guardrails – cho phép tạo template và rules (regex, policy, sentiment) để tự động lọc yêu cầu và phản hồi.

Amazon Bedrock Guardrails – tính năng tương tự nhưng áp dụng cho các mô hình do AWS và nhà cung cấp bên thứ ba cung cấp.

LLM‑Specific Security Controls (AWS Security Hub, IAM, VPC Endpoints) – bảo vệ hạ tầng, không thay thế cho guardrails ở lớp ứng dụng.

Best practice: Kết hợp prompt‑based guardrails, output filtering (post‑processing) và access control để đạt “defense‑in‑depth”.

📚 Tham khảo

AWS Documentation – Amazon SageMaker Prompt Guardrails (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/prompt-guardrails.html

AWS Blog – Securing Generative AI Applications with Guardrails (Nov 2025): https://aws.amazon.com/blogs/machine-learning/securing-llm-guardrails/

AWS Security Hub – Controls for Generative AI (2026): https://docs.aws.amazon.com/securityhub/latest/userguide/ai-controls.html

Kết luận: Để giảm thiểu rủi ro LLM bị “bắt nạt” bằng các kỹ thuật prompt engineering, tạo một prompt template có guardrails (phát hiện mẫu tấn công) là giải pháp hiệu quả nhất. Các biện pháp khác (thay đổi temperature, chỉ dùng mô hình trên SageMaker, giảm token) không giải quyết gốc rễ của vấn đề và thậm chí có thể làm rủi ro tăng lên. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150808-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 62

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon S3, Amazon Q
- Đáp án tham khảo: **🟢 Unsupervised learning.**
- Takeaway nhanh: Một công ty có petabytes dữ liệu khách hàng chưa được gán nhãn (unlabeled). Mục tiêu là phân loại khách hàng thành các “tier” (cấp độ) để thực hiện chiến dịch quảng cáo và khuyến mại. Vì dữ liệu chưa có nhãn (không biết trước “tier” nào là đúng), công ty cần một phương pháp tự động khám phá cấu trúc, nhóm các khách hàng lại với nhau mà không dựa vào nhãn đầu vào.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/big-data/scaling-unsupervised-learning/ | https://aws.amazon.com/sagemaker/canvas/ | https://d1.awsstatic.com/whitepapers/MachineLearningAtScale.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/algos-clustering.html | https://www.examtopics.com/discussions/amazon/view/150630-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has petabytes of unlabeled customer data to use for an advertisement campaign. The company wants to classify its customers into tiers to advertise and promote the company's products. Which methodology should the company use to meet these requirements?

### Các lựa chọn
1. Supervised learning
2. Unsupervised learning
3. Reinforcement learning
4. Reinforcement learning from human feedback (RLHF)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty có petabytes dữ liệu khách hàng chưa được gán nhãn (unlabeled). Mục tiêu là phân loại khách hàng thành các “tier” (cấp độ) để thực hiện chiến dịch quảng cáo và khuyến mại. Vì dữ liệu chưa có nhãn (không biết trước “tier” nào là đúng), công ty cần một phương pháp tự động khám phá cấu trúc, nhóm các khách hàng lại với nhau mà không dựa vào nhãn đầu vào.

✅ Đáp án đúng

🟢 Unsupervised learning

Vì sao lựa chọn này là đúng?

Dữ liệu không có nhãn → không thể áp dụng các thuật toán yêu cầu nhãn (supervised) hay các môi trường phản hồi (reinforcement).

Mục tiêu phân cụm (clustering) – tìm ra các nhóm khách hàng có đặc điểm tương đồng (ví dụ: hành vi mua sắm, mức chi tiêu, độ tuổi…) để xác định các “tier”.

Unsupervised learning cung cấp các thuật toán clustering (K‑Means, DBSCAN, Gaussian Mixture, Hierarchical Clustering) và dimensionality reduction (PCA, t‑SNE, UMAP) giúp khám phá cấu trúc ẩn trong dữ liệu lớn.

Trên AWS, Amazon SageMaker hỗ trợ đầy đủ các thuật toán không giám sát (SageMaker Built‑in Algorithms → Clustering, K‑Means, PCA) và SageMaker Canvas cho phép người không chuyên tạo mô hình không giám sát chỉ bằng giao diện kéo‑thả.

Khi dữ liệu lên petabytes, AWS cung cấp Amazon S3 làm kho lưu trữ, Amazon EMR hoặc SageMaker Processing để tiền xử lý và chạy các job clustering quy mô lớn.

Do đó, Unsupervised learning là cách tiếp cận phù hợp nhất để “phân lớp” khách hàng mà không cần nhãn sẵn có.

❌ Giải thích các phương án sai

1. Supervised learning

Mô tả: Thuật toán học từ cặp dữ liệu (input, label) để dự đoán nhãn cho dữ liệu mới.

Tại sao sai: Dữ liệu của công ty không có nhãn (không biết trước tier nào là đúng). Để dùng supervised learning, cần gán nhãn cho một bộ dữ liệu huấn luyện – việc này tốn kém, thời gian và không đáp ứng yêu cầu “không có nhãn”.

AWS liên quan: SageMaker Linear Learner, XGBoost, Deep Learning Containers… đều yêu cầu nhãn.

2. Reinforcement learning

Mô tả: Mô hình học thông qua phản hồi (reward/punishment) khi tương tác với môi trường, thường dùng cho điều khiển robot, tối ưu tài nguyên, game AI.

Tại sao sai: Không có định nghĩa môi trường và phần thưởng rõ ràng cho việc “phân lớp khách hàng”. Reinforcement learning không phải là công cụ khám phá cấu trúc dữ liệu tĩnh.

AWS liên quan: SageMaker RL Frameworks (RL‑Coach, RL‑TensorFlow) được dùng cho các bài toán tối ưu hành động, không phù hợp với clustering.

3. Reinforcement learning from human feedback (RLHF)

Mô tả: Một biến thể của RL, trong đó phần thưởng được tạo ra từ phản hồi của con người (ví dụ: ChatGPT).

Tại sao sai: Yêu cầu phản hồi có chất lượng và quy trình “human‑in‑the‑loop”. Đối với việc phân nhóm khách hàng, không có cơ chế “phản hồi” để hướng dẫn mô hình học; việc thu thập phản hồi cho petabytes dữ liệu sẽ vô cùng không thực tế.

AWS liên quan: SageMaker RLHF chưa được công bố chính thức (tính đến 2026), và không phù hợp cho bài toán clustering không nhãn.

🛠️ Các dịch vụ AWS hỗ trợ Unsupervised learning cho quy mô petabytes

AWS Service	Vai trò trong quy trình

Amazon S3	Lưu trữ dữ liệu gốc (petabytes) với độ bền cao và chi phí linh hoạt.

AWS Glue / Amazon Athena	Khai thác, làm sạch và chuyển đổi dữ liệu trước khi đưa vào mô hình.

Amazon EMR (Spark, Hadoop)	Xử lý phân tán, tính toán các thuật toán clustering trên khối lượng dữ liệu lớn.

Amazon SageMaker Processing	Chạy job tiền xử lý và training không giám sát (K‑Means, PCA) trong môi trường quản lý.

SageMaker Built‑in Algorithms – Clustering	Cung cấp K‑Means, K‑Means‑plus‑plus, và các thuật toán clustering tối ưu cho dữ liệu lớn.

SageMaker Feature Store	Lưu trữ các đặc trưng đã được trích xuất để tái sử dụng trong các mô hình downstream (ví dụ: supervised classifier cho tier đã được định nghĩa).

Amazon QuickSight	Trực quan hoá kết quả clustering, giúp các nhà marketing hiểu các tier khách hàng.

📚 Tham khảo (tính đến 2026)

AWS Documentation – Amazon SageMaker Built‑in Algorithms – “Clustering (K‑Means)”

https://docs.aws.amazon.com/sagemaker/latest/dg/algos-clustering.html

AWS Whitepaper – Machine Learning at Scale on AWS (2024 update) – chương “Unsupervised Learning at Petabyte Scale”.

https://d1.awsstatic.com/whitepapers/MachineLearningAtScale.pdf

AWS Blog – Scaling Unsupervised Learning with Amazon EMR and SageMaker (Jan 2025).

https://aws.amazon.com/blogs/big-data/scaling-unsupervised-learning/

SageMaker Canvas – No‑Code Unsupervised Modeling (released 2023, continuously updated).

https://aws.amazon.com/sagemaker/canvas/

📌 Tóm tắt nhanh

Câu hỏi: Dữ liệu không có nhãn, cần phân nhóm khách hàng → Unsupervised learning.

Đáp án đúng: 🟢 Unsupervised learning.

Các lựa chọn còn lại (Supervised, Reinforcement, RLHF) đều không phù hợp vì yêu cầu nhãn, môi trường phản hồi, hoặc feedback con người, trong khi bài toán yêu cầu khám phá cấu trúc dữ liệu không nhãn.

💡 Mẹo thi: Khi đề bài nhắc “unlabeled data” → luôn nghĩ tới unsupervised (clustering, dimensionality reduction). Nếu đề yêu cầu “các hành động tối ưu qua phản hồi” → nghĩ tới reinforcement. Nếu có “đầu vào + nhãn” → supervised. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150630-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 63

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Personalize, Amazon SageMaker, Amazon S3, Amazon SageMaker AI, RAG
- Takeaway nhanh: Một công ty thiết bị số muốn dự đoán nhu cầu mua bộ nhớ (memory hardware). Yêu cầu quan trọng: Không có kinh nghiệm lập trình và không hiểu thuật toán Machine‑Learning. Cần phân tích dữ liệu nội bộ + dữ liệu bên ngoài (có thể là file CSV, Excel, dữ liệu từ API, …).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html | https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html | https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html | https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html | https://www.examtopics.com/discussions/amazon/view/151047-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A digital devices company wants to predict customer demand for memory hardware. The company does not have coding experience or knowledge of ML algorithms and needs to develop a data-driven predictive model. The company needs to perform analysis on internal data and external data. Which solution will meet these requirements?

### Các lựa chọn
1. Store the data in Amazon S3. Create ML models and demand forecast predictions by using Amazon SageMaker built-in algorithms that use the data from Amazon S3.
2. Import the data into Amazon SageMaker Data Wrangler. Create ML models and demand forecast predictions by using SageMaker built-in algorithms.
3. Import the data into Amazon SageMaker Data Wrangler. Build ML models and demand forecast predictions by using an Amazon Personalize Trending-Now recipe.
4. Import the data into Amazon SageMaker Canvas. Build ML models and demand forecast predictions by selecting the values in the data from SageMaker Canvas.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Một công ty thiết bị số muốn dự đoán nhu cầu mua bộ nhớ (memory hardware).

Yêu cầu quan trọng:

Không có kinh nghiệm lập trình và không hiểu thuật toán Machine‑Learning.

Cần phân tích dữ liệu nội bộ + dữ liệu bên ngoài (có thể là file CSV, Excel, dữ liệu từ API, …).

Muốn xây dựng mô hình dự đoán (demand forecasting) một cách nhanh chóng, không phải viết code.

Vì vậy giải pháp cần cung cấp giao diện kéo‑thả / no‑code, tự động xử lý tiền xử lý, lựa chọn thuật toán, huấn luyện và tạo dự báo.

✅ Đáp án đúng

Import the data into Amazon SageMaker Canvas. Build ML models and demand forecast predictions by selecting the values in the data from SageMaker Canvas.

Giải thích:

Amazon SageMaker Canvas là công cụ “no‑code” được thiết kế cho người dùng phi‑kỹ thuật.

Người dùng chỉ cần kéo‑thả (drag‑and‑drop) hoặc import dữ liệu từ S3, Amazon Redshift, hoặc tải lên file CSV/Excel, rồi chọn target column (cột cần dự báo).

Canvas tự động thực hiện data preparation, feature engineering, model selection (cho forecasting có sẵn các thuật toán như Prophet, XGBoost, DeepAR) và generate predictions.

Không cần viết một dòng code nào, phù hợp hoàn hảo với yêu cầu “không có coding experience”.

Hỗ trợ dữ liệu nội bộ và dữ liệu bên ngoài vì có khả năng kết nối tới nhiều nguồn lưu trữ.

🔗 Tham khảo: AWS SageMaker Canvas documentation (2026)

❌ Các phương án sai và lý do

Store the data in Amazon S3. Create ML models and demand forecast predictions by using Amazon SageMaker built‑in algorithms that use the data from Amazon S3.

SageMaker built‑in algorithms (ví dụ: DeepAR, XGBoost) yêu cầu viết notebook, script hoặc sử dụng SageMaker Studio để cấu hình training job.

Người dùng không có kinh nghiệm lập trình sẽ gặp khó khăn trong việc viết training script, định nghĩa hyper‑parameters, tạo job.

Vì vậy không đáp ứng yêu cầu “không có coding experience”.

🧩 Solution này phù hợp cho data scientist, không phải cho người phi‑kỹ thuật.

Import the data into Amazon SageMaker Data Wrangler. Create ML models and demand forecast predictions by using SageMaker built‑in algorithms.

Data Wrangler là công cụ giúp chuẩn hoá và biến đổi dữ liệu, nhưng để đào tạo mô hình vẫn cần SageMaker Studio hoặc SageMaker Pipelines và thường yêu cầu mã Python (để gọi fit() trên estimator).

Người dùng vẫn phải viết ít nhất một đoạn script để chạy training, do đó không đáp ứng yêu cầu “không có coding”.

🧩 Data Wrangler không phải là nền tảng dự báo “no‑code”.

Import the data into Amazon SageMaker Data Wrangler. Build ML models and demand forecast predictions by using an Amazon Personalize Trending‑Now recipe.

Amazon Personalize được thiết kế cho hệ thống gợi ý (recommendation), không phải cho demand forecasting.

“Trending‑Now” recipe tập trung vào việc phát hiện các mặt hàng đang “hot” dựa trên hành vi người dùng, không cung cấp đầu ra dạng dự báo thời gian cho nhu cầu mua hàng.

Thêm vào đó, Personalize vẫn yêu cầu định nghĩa dataset group, schema, và chạy training job, không phải là công cụ “no‑code” cho người không chuyên.

🧩 Công cụ sai mục đích và vẫn cần kiến thức kỹ thuật.

🛠️ Khi nào nên dùng các công cụ khác (đối chiếu)

Công cụ	Khi nào phù hợp	Yêu cầu kỹ thuật

SageMaker built‑in algorithms	Data scientist muốn kiểm soát chi tiết thuật toán, siêu tham số và quy trình training.	Python, notebook, hoặc CLI.

SageMaker Data Wrangler	Người dùng muốn chuẩn hoá, làm sạch dữ liệu nhanh, nhưng vẫn dự định training bằng code.	SageMaker Studio, ít nhất một script.

Amazon Personalize	Ứng dụng gợi ý sản phẩm, playlist, nội dung cá nhân hoá.	Kiến thức về schema, dataset, và việc tạo campaign.

SageMaker Canvas	Người phi‑kỹ thuật, analyst, marketer muốn dự báo, phân loại, regression mà không viết code.	Không cần code, giao diện kéo‑thả.

📚 Tham khảo tài liệu (2026)

Amazon SageMaker Canvas – Getting started with Canvas: https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html

Amazon SageMaker Built‑in Algorithms – DeepAR, XGBoost, Prophet: https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html

Amazon SageMaker Data Wrangler – Data preparation in SageMaker: https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html

Amazon Personalize – Recipes and use cases: https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html

🧭 Kết luận:

Với yêu cầu không có kinh nghiệm lập trình, phân tích dữ liệu đa nguồn, và dự báo nhu cầu, Amazon SageMaker Canvas là giải pháp duy nhất đáp ứng đầy đủ, vì nó cung cấp môi trường no‑code, end‑to‑end cho việc tạo mô hình dự báo. Các phương án còn lại đều đòi hỏi ít nhất một mức độ lập trình hoặc không phù hợp với mục tiêu forecasting. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151047-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 64

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: RAG
- Đáp án tham khảo: **Average call duration**
- Takeaway nhanh: Câu hỏi mô tả một công ty đang triển khai chatbot dựa trên Large Language Model (LLM) để trả lời câu hỏi của khách hàng. Mục tiêu chính của họ là giảm số lượng hành động mà nhân viên trung tâm cuộc gọi (call‑center) phải thực hiện khi trả lời. Vì vậy, khi đánh giá hiệu quả của chatbot, công ty cần lựa chọn một mục tiêu kinh doanh (business objective) phản ánh đúng việc giảm tải công việc và cải thiện hiệu suất của các cuộc gọi.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/151043-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a large language model (LLM) question answering chatbot. The company wants to decrease the number of actions call center employees need to take to respond to customer questions. Which business objective should the company use to evaluate the effect of the LLM chatbot?

### Các lựa chọn
1. Website engagement rate
2. Average call duration
3. Corporate social responsibility
4. Regulatory compliance

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty đang triển khai chatbot dựa trên Large Language Model (LLM) để trả lời câu hỏi của khách hàng. Mục tiêu chính của họ là giảm số lượng hành động mà nhân viên trung tâm cuộc gọi (call‑center) phải thực hiện khi trả lời. Vì vậy, khi đánh giá hiệu quả của chatbot, công ty cần lựa chọn một mục tiêu kinh doanh (business objective) phản ánh đúng việc giảm tải công việc và cải thiện hiệu suất của các cuộc gọi.

✅ Đáp án đúng: Average call duration

Lý do chọn:

Khi chatbot trả lời được câu hỏi của khách hàng một cách nhanh chóng và chính xác, nhân viên call‑center sẽ không cần phải thực hiện nhiều “động tác” (ví dụ: tìm kiếm thông tin, chuyển cuộc gọi, hỏi lại khách hàng). Kết quả là thời gian mỗi cuộc gọi giảm xuống.

“Average call duration” (thời gian trung bình mỗi cuộc gọi) là một chỉ số KPI tiêu chuẩn trong các trung tâm cuộc gọi, thường được dùng để đo hiệu suất và mức độ tự động hoá quy trình. AWS cung cấp công cụ Amazon Connect và Amazon CloudWatch để thu thập và phân tích chỉ số này.

Do vậy, đo “Average call duration” là cách trực tiếp và có ý nghĩa nhất để đánh giá mức độ giảm thiểu hành động của nhân viên, đồng thời phản ánh lợi ích kinh doanh (giảm chi phí nhân công, nâng cao trải nghiệm khách hàng).

❌ Các phương án sai và giải thích

Website engagement rate

Đây là chỉ số đo lường mức độ tương tác của người dùng trên website (số lượt click, thời gian trên trang, tỷ lệ bounce, …). Nó không liên quan tới hiệu suất của trung tâm cuộc gọi hay việc giảm hành động của nhân viên. Nếu chatbot được triển khai trên website, chỉ số này có thể phản ánh mức độ sử dụng, nhưng không phản ánh việc giảm thời gian gọi điện.

Corporate social responsibility

CSR đề cập tới các hoạt động có lợi cho xã hội, môi trường và cộng đồng. Đây là mục tiêu phi‑tài chính, không phải là chỉ số đo lường trực tiếp hiệu quả của một chatbot trong môi trường call‑center. Do vậy, không phù hợp để đánh giá tác động của LLM chatbot đối với việc giảm hành động của nhân viên.

Regulatory compliance

Tuân thủ quy định là yêu cầu bắt buộc về bảo mật, lưu trữ dữ liệu, và các chuẩn pháp lý (ví dụ: GDPR, PCI‑DSS). Mặc dù quan trọng, đây không phải là một KPI để đo “số hành động” hay “thời gian gọi”. Đánh giá compliance thường dựa trên audit, log và báo cáo, không phải thời gian trung bình cuộc gọi.

🧩 Tổng hợp các tiêu chí lựa chọn KPI cho chatbot call‑center

Direct impact on call handling – các chỉ số đo thời gian, số lần chuyển cuộc gọi, hay mức độ giải quyết trong lần gọi đầu tiên (First Call Resolution).

Cost efficiency – giảm chi phí nhân công và chi phí vận hành trung tâm cuộc gọi.

Customer experience – thời gian chờ, mức độ hài lòng (CSAT), Net Promoter Score (NPS).

Trong các lựa chọn đưa ra, Average call duration duy nhất đáp ứng tiêu chí “giảm số hành động của nhân viên”.

📚 Tham khảo (cập nhật đến 2026)

AWS Whitepaper: “Modernizing Contact Centers with Amazon Connect and Generative AI” (2025) – đề cập tới việc dùng LLM để giảm thời gian cuộc gọi và cải thiện First Call Resolution.

Amazon Connect Documentation – Metrics and Reporting (phiên bản 2026) – mô tả cách thu thập “Average Call Duration” qua CloudWatch.

AWS Well‑Architected Framework – Operational Excellence Pillar – nhấn mạnh việc đo lường KPI thực tế (như thời gian xử lý) để đánh giá cải tiến quy trình.

🔚 Kết luận:

Để đo hiệu quả của chatbot LLM trong việc giảm thiểu các hành động của nhân viên call‑center, Average call duration là chỉ số kinh doanh thích hợp nhất. Các lựa chọn còn lại không phản ánh trực tiếp mục tiêu này và do đó là sai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/151043-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 65

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon S3, embeddings, RAG
- Takeaway nhanh: Which feature of Amazon OpenSearch Service gives companies the ability to build vector database applications? 1️⃣ Giải thích nội dung câu hỏi Câu hỏi đang hỏi “đặc điểm nào của Amazon OpenSearch Service cho phép các doanh nghiệp xây dựng ứng dụng cơ sở dữ liệu vector?” Vector database là hệ thống lưu trữ và tìm kiếm các vector (đại diện cho embedding của ảnh, văn bản, âm thanh…) bằng các thuật toán nearest‑neighbor (k‑NN). Để triển khai được loại cơ sở dữ liệu này trên OpenSearch, dịch vụ cần cung cấp:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/150801-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which feature of Amazon OpenSearch Service gives companies the ability to build vector database applications?

### Các lựa chọn
1. Integration with Amazon S3 for object storage
2. Support for geospatial indexing and queries
3. Scalable index management and nearest neighbor search capability
4. Ability to perform real-time analysis on streaming data

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Câu hỏi:

Which feature of Amazon OpenSearch Service gives companies the ability to build vector database applications?

1️⃣ Giải thích nội dung câu hỏi

Câu hỏi đang hỏi “đặc điểm nào của Amazon OpenSearch Service cho phép các doanh nghiệp xây dựng ứng dụng cơ sở dữ liệu vector?”

Vector database là hệ thống lưu trữ và tìm kiếm các vector (đại diện cho embedding của ảnh, văn bản, âm thanh…) bằng các thuật toán nearest‑neighbor (k‑NN). Để triển khai được loại cơ sở dữ liệu này trên OpenSearch, dịch vụ cần cung cấp:

khả năng lưu trữ chỉ mục (index) dạng vector ở quy mô lớn,

cơ chế tìm kiếm k‑NN nhanh và chính xác,

khả năng quản lý, mở rộng các chỉ mục này khi dữ liệu tăng.

2️⃣ Đáp án đúng

✅ Đáp án:

Scalable index management and nearest neighbor search capability

🧩 Lý do chọn:

Từ 2022 trở đi, Amazon OpenSearch Service (phiên bản 2.x và Serverless) đã tích hợp k‑Nearest Neighbor (k‑NN) plugin và vector search engine cho phép tạo trường kiểu knn_vector và thực hiện truy vấn kNN.

Tính năng này cung cấp quản lý chỉ mục có thể mở rộng (sharding, replica) và công cụ tìm kiếm nearest‑neighbor tối ưu hoá bằng HNSW, IVF‑PQ, hoặc ON‑DISK.

Nhờ đó, doanh nghiệp có thể lưu trữ embeddings và thực hiện tìm kiếm tương đồng (semantic search), đề xuất, phân loại, v.v… – chính là những chức năng cốt lõi của một vector database.

Tham khảo:

AWS Documentation – Amazon OpenSearch Service – k‑NN and Vector Search (cập nhật tới 2026).

“Introducing Vector Search in Amazon OpenSearch Service” blog post, AWS (2023).

3️⃣ Giải thích tất cả các phương án

- Integration with Amazon S3 for object storage

❌ Sai – Tích hợp S3 chỉ giúp OpenSearch import / export dữ liệu (snapshot, log, raw files). Nó không cung cấp khả năng lưu trữ hoặc tìm kiếm vector, cũng không hỗ trợ k‑NN.

- Support for geospatial indexing and queries

❌ Sai – Đặc tính địa lý cho phép lưu trữ và truy vấn dữ liệu không gian (ví dụ: latitude/longitude, polygon). Mặc dù mạnh mẽ cho các ứng dụng GIS, nó không liên quan tới vector embeddings hay nearest‑neighbor search.

- Scalable index management and nearest neighbor search capability

✅ Đúng – Như đã phân tích ở mục 2️⃣, đây là tính năng quản lý chỉ mục có thể mở rộng kết hợp công cụ tìm kiếm k‑NN – chính xác đáp ứng nhu cầu xây dựng vector database.

- Ability to perform real‑time analysis on streaming data

❌ Sai – Khả năng phân tích thời gian thực (ví dụ: Kinesis Data Streams → OpenSearch) phục vụ log analytics, monitoring, dashboards. Nó không cung cấp cơ chế lưu trữ vector hay tìm kiếm nearest‑neighbor.

4️⃣ Tổng kết (điểm quan trọng)

Vector database → cần vector indexing + nearest‑neighbor search.

Amazon OpenSearch Service đáp ứng bằng k‑NN plugin / vector search, kèm quản lý chỉ mục quy mô lớn.

Các tùy chọn còn lại chỉ đề cập tới lưu trữ S3, địa lý, hoặc phân tích streaming – không liên quan tới vector search.

5️⃣ Nguồn tham khảo 📚

Amazon OpenSearch Service Developer Guide – k‑Nearest Neighbor (k‑NN) and Vector Search (phiên bản 2026).

AWS Blog – “Introducing Vector Search in Amazon OpenSearch Service” (Nov 2023).

AWS re:Invent 2024 Session – “Scaling Vector Search on Amazon OpenSearch Service”.

💡 Mẹo thi: Khi gặp câu hỏi về “vector database” trong bối cảnh OpenSearch, luôn nhớ tới k‑NN + scalable indexing – là đáp án duy nhất chứa cả hai thành phần “vector” và “scalable”.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/150801-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

Đề 3------------
