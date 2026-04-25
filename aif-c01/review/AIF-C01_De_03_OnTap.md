# AIF-C01 - Bộ Ôn Tập Chi Tiết - Đề 03

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 03 tham khảo từ Đề Internet - ExamTopics (Full6de.md)
- Blueprint tham chiếu: `w:\AI Practitioner\AIF\AWS-Certified-AI-Practitioner_Exam-Guide.pdf`
- Ghi chú kỹ thuật: dữ liệu được tách từ `Full6de.md`; parser dùng reset `Câu hỏi 1`/`Câu 1:` và link tham khảo để vá các câu thiếu marker.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon SageMaker | 41 |
| Amazon Bedrock | 35 |
| Amazon SageMaker JumpStart | 12 |
| Amazon SageMaker AI | 11 |
| Amazon S3 | 7 |
| Amazon Q | 6 |
| Amazon Comprehend | 6 |
| Amazon Kendra | 4 |
| Amazon Lex | 3 |
| Amazon Rekognition | 3 |
| Amazon OpenSearch Service | 2 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon Bedrock | 5 |
| Amazon SageMaker | 4 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| model evaluation | 281 |
| prompt engineering | 209 |
| responsible AI | 131 |
| embeddings | 95 |
| guardrails | 69 |
| RAG | 62 |
| fine-tuning | 30 |
| hallucination | 14 |

### Domain heuristic

| Domain | Tên | Tỷ trọng chính thức | Số câu ước lượng |
| --- | --- | --- | --- |
| Domain 1 | Fundamentals of AI and ML | 20% | 22 |
| Domain 2 | Fundamentals of Generative AI | 24% | 17 |
| Domain 3 | Applications of Foundation Models | 28% | 12 |
| Domain 4 | Guidelines for Responsible AI | 14% | 5 |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% | 9 |

## Service Key-Notes

### Amazon SageMaker
- Bộ dịch vụ managed cho vòng đời ML: chuẩn bị dữ liệu, huấn luyện, tuning, deploy, monitor và governance.
- Trong đề AIF, cần phân biệt SageMaker với Bedrock: SageMaker thiên về build/train/deploy ML model; Bedrock thiên về consume/customize foundation model.

### Amazon Bedrock
- Dịch vụ managed để dùng foundation models qua API, thường là đáp án cho generative AI với ít vận hành.
- Các mảng hay gặp: model selection, Knowledge Bases/RAG, Agents, Guardrails, logging, VPC endpoint và dữ liệu không dùng để train model nền mặc định.

### Amazon SageMaker JumpStart
- Cung cấp model và solution template dựng sẵn, phù hợp khi cần triển khai hoặc fine-tune model nguồn mở với ít operational effort.
- Nếu câu hỏi nhấn mạnh least operational effort cho open-source LLM, JumpStart thường là lựa chọn mạnh.

### Amazon SageMaker AI
- Tên mới/biến thể cách gọi SageMaker trong nguồn câu hỏi, thường trỏ về cùng nhóm năng lực ML managed.
- Hay đi cùng training job, endpoint, Feature Store, Clarify, Model Cards và JumpStart.

### Amazon S3
- Object storage nền tảng cho dataset, artifact, log, nguồn dữ liệu RAG và output pipeline ML.
- Hay đi cùng security/governance như encryption, lifecycle, access control và data residency.

### Amazon Q
- Trợ lý generative AI của AWS cho công việc doanh nghiệp, code và tri thức nội bộ.
- Amazon Q Developer thường gắn với hỗ trợ lập trình, giải thích code, tạo code và tăng năng suất developer.

### Amazon Comprehend
- Dịch vụ NLP managed cho entity, key phrases, sentiment, topic và phân tích văn bản.
- Không phải công cụ tạo nội dung generative AI hay vector database.

### Amazon Kendra
- Enterprise search managed, thường làm nguồn retrieval cho RAG trên dữ liệu doanh nghiệp.
- Hữu ích khi đề hỏi tìm kiếm tài liệu nội bộ với connector và relevance ranking.

## Pattern Key-Notes

### model evaluation
- Chọn metric theo task: ROUGE cho summarization, accuracy/precision/recall/F1 cho classification, MSE cho regression.
- Không dùng metric không liên quan chỉ vì quen thuộc trong ML truyền thống.

### prompt engineering
- Kỹ thuật thiết kế chỉ dẫn cho foundation model để tăng độ chính xác, định dạng và tính nhất quán của output.
- Không thay thế guardrails, validation hoặc kiểm soát bảo mật trước prompt injection.

### responsible AI
- Nhóm nguyên tắc về fairness, transparency, explainability, privacy, safety và accountability.
- Trong AIF-C01, cần nhận diện rủi ro như bias, toxicity, plagiarism, hallucination và misuse.

### embeddings
- Vector số biểu diễn ý nghĩa của văn bản/hình ảnh/đối tượng để tìm kiếm tương đồng và clustering.
- Embedding thường đi cùng vector database, semantic search và RAG.

### guardrails
- Cơ chế kiểm soát input/output nhằm giảm nội dung độc hại, prompt injection và vi phạm policy.
- Trên Bedrock, Guardrails là keyword quan trọng cho yêu cầu responsible/safe generative AI.

### RAG
- Retrieval-Augmented Generation đưa tri thức ngoài vào context để giảm hallucination và tăng tính cập nhật.
- Trên AWS thường ghép Bedrock với Knowledge Bases, Kendra, OpenSearch hoặc S3.

## Cách Học Đề Này

- Đọc nhanh các service/pattern nổi bật để biết đề nghiêng về Bedrock, SageMaker, responsible AI hay governance.
- Với câu generative AI, xác định trước keyword như `RAG`, `prompt`, `embedding`, `guardrails`, `fine-tuning`, `hallucination`.
- Với câu ML nền tảng, chọn metric/kỹ thuật đúng theo task thay vì nhớ máy móc đáp án.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Increase the temperature value → đúng ✅**
- Takeaway nhanh: Câu hỏi mô tả một AI practitioner muốn thu được đầu ra đa dạng hơn và sáng tạo hơn từ một large language model (LLM). Trong giai đoạn inference (sinh đáp án), các tham số quan trọng nhất để điều khiển độ ngẫu nhiên và đa dạng của mô hình là: temperature – mức độ “nóng” của phân phối xác suất; giá trị cao → lựa chọn từ các token có xác suất thấp hơn → kết quả đa dạng, ít dự đoán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308675-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner wants to generate more diverse and more creative outputs from a large language model (LLM).
How should the AI practitioner adjust the inference parameter?

### Các lựa chọn
1. Increase the temperature value.
2. Decrease the Top K value.
3. Increase the response length.
4. Decrease the prompt length.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một AI practitioner muốn thu được đầu ra đa dạng hơn và sáng tạo hơn từ một large language model (LLM).

Trong giai đoạn inference (sinh đáp án), các tham số quan trọng nhất để điều khiển độ ngẫu nhiên và đa dạng của mô hình là:

temperature – mức độ “nóng” của phân phối xác suất; giá trị cao → lựa chọn từ các token có xác suất thấp hơn → kết quả đa dạng, ít dự đoán.

top‑k (hoặc top‑p) – giới hạn số token được xem xét; giảm top‑k → chỉ giữ lại các token có xác suất cao → kết quả ít đa dạng.

response length – chiều dài câu trả lời; tăng độ dài không nhất thiết làm tăng tính sáng tạo.

prompt length – độ dài của prompt; giảm độ dài không cải thiện độ đa dạng.

Do đó, để “tăng tính đa dạng và sáng tạo”, chúng ta cần tăng giá trị temperature.

✅ Đáp án đúng

Increase the temperature value.

✅ Khi tăng temperature (thường từ 0.0 → 1.0 hoặc hơn), mô hình sẽ “phóng đại” các xác suất ít xuất hiện, cho phép chọn các token ít phổ biến hơn. Kết quả: câu trả lời trở nên đa dạng, bất ngờ, và sáng tạo hơn. Đây là cách chuẩn được khuyến nghị trong hầu hết tài liệu LLM, bao gồm Amazon Bedrock và SageMaker JumpStart (tài liệu 2026).

❌ Giải thích các phương án sai

Decrease the Top K value.

❌ Top K xác định số lượng token có xác suất cao nhất được xét tới ở mỗi bước sinh. Giảm giá trị này (ví dụ từ 50 → 10) sẽ hạn chế lựa chọn chỉ còn những token “đáng tin cậy” nhất, làm giảm độ đa dạng và tính sáng tạo. Để tăng đa dạng, thường tăng top‑k (hoặc dùng top‑p) chứ không giảm.

Increase the response length.

❌ Việc tăng độ dài câu trả lời (số token tối đa) chỉ cho phép mô hình tạo ra câu trả lời dài hơn, nhưng không ảnh hưởng trực tiếp tới việc mô hình có chọn các token ít khả năng hay không. Nếu temperature vẫn thấp, câu trả lời dài vẫn sẽ rất “định hướng” và ít sáng tạo.

Decrease the prompt length.

❌ Rút ngắn prompt có thể làm mất thông tin ngữ cảnh quan trọng, dẫn đến câu trả lời kém chính xác hoặc không liên quan. Độ dài prompt không quyết định mức độ ngẫu nhiên; vì vậy việc giảm prompt không làm tăng tính đa dạng hay sáng tạo.

🧩 Tổng kết nhanh

✅ Increase the temperature value → đúng ✅

❌ Decrease the Top K value → sai ❌

❌ Increase the response length → sai ❌

❌ Decrease the prompt length → sai ❌

📚 Tham khảo nguồn tài liệu (cập nhật tới 2026)

Amazon Bedrock Developer Guide – “Controlling LLM Generation Parameters” (2025‑2026).

Mô tả chi tiết cách temperature, top‑k, top‑p, và max tokens ảnh hưởng tới độ đa dạng.

AWS SageMaker JumpStart – “Fine‑tuning and Inference for LLMs” (2026).

Ví dụ thực tiễn: tăng temperature từ 0.2 → 0.8 để tạo nội dung sáng tạo hơn.

OpenAI API Documentation – “Sampling Parameters” (phiên bản 2026).

Giải thích nguyên lý thống kê của temperature và top‑k.

“Prompt Engineering for LLMs” – AWS Machine Learning Blog, March 2026.

Nhấn mạnh rằng độ dài prompt không liên quan tới tính ngẫu nhiên; thay vào đó, các tham số sampling là yếu tố quyết định.

🔧 Mẹo thực hành trên AWS

Khi sử dụng Amazon Bedrock hoặc SageMaker Inference Endpoint, bạn có thể truyền các tham số dưới dạng JSON:

Code

{

"temperature": 0.9,

"top_k": 50,

"maxTokens": 512,

"prompt": "..."

}

Đối với mục tiêu sáng tạo, khởi đầu với temperature khoảng 0.7‑0.9 và top_k từ 40‑80 (hoặc top_p ~0.9) thường cho kết quả tốt.

💡 Kết luận: Để tăng tính đa dạng và sáng tạo của LLM, tăng giá trị temperature là cách đúng nhất. Các phương án còn lại không đáp ứng mục tiêu này và thậm chí có thể làm giảm chất lượng hoặc độ sáng tạo của đầu ra.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308675-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 02

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Bedrock, guardrails
- Takeaway nhanh: Công ty mạng xã hội muốn ngăn người dùng đăng nội dung mang tính phân biệt đối xử. Họ quyết định dùng Amazon Bedrock – dịch vụ nền tảng AI/ML của AWS, trong đó có tính năng Guardrails (các rào chắn nội dung) cho phép: Xác định các chủ đề/đầu vào không được chấp nhận (ví dụ: “hate speech”, “discrimination”, “harassment”). Chặn hoặc đánh dấu các tương tác chứa các chủ đề này trước khi chúng được trả về cho người dùng.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/guardrails-content-moderation-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/308649-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A social media company wants to prevent users from posting discriminatory content on the company's application. The company wants to use Amazon Bedrock as part of the solution.
How can the company use Amazon Bedrock to meet these requirements?

### Các lựa chọn
1. Give users the ability to interact based on user preferences.
2. Block interactions related to predefined topics.
3. Restrict user conversations to predefined topics.
4. Provide a variety of responses to select from for user engagement.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty mạng xã hội muốn ngăn người dùng đăng nội dung mang tính phân biệt đối xử.

Họ quyết định dùng Amazon Bedrock – dịch vụ nền tảng AI/ML của AWS, trong đó có tính năng Guardrails (các rào chắn nội dung) cho phép:

Xác định các chủ đề/đầu vào không được chấp nhận (ví dụ: “hate speech”, “discrimination”, “harassment”).

Chặn hoặc đánh dấu các tương tác chứa các chủ đề này trước khi chúng được trả về cho người dùng.

Vì vậy, câu trả lời đúng phải mô tả cách chặn (block) các tương tác liên quan tới các chủ đề đã định sẵn.

✅ Đáp án đúng

- Block interactions related to predefined topics.

Giải thích:

Amazon Bedrock cung cấp Guardrails cho phép bạn định nghĩa pre‑defined topics (ví dụ: “racial slurs”, “gender discrimination”).

Khi người dùng gửi yêu cầu, Bedrock sẽ kiểm tra nội dung và chặn (block) bất kỳ tương tác nào có chứa các chủ đề bị cấm, trả về thông báo lỗi hoặc phản hồi “content not allowed”.

Đây chính là cơ chế đáp ứng yêu cầu “ngăn người dùng đăng nội dung phân biệt đối xử”.

❌ Các phương án sai và lý do

- Give users the ability to interact based on user preferences.

Giải thích: Tùy chọn này cho phép người dùng tự lựa chọn cách tương tác (ví dụ: tone, style). Nó không cung cấp cơ chế kiểm soát nội dung hay chặn những nội dung gây phân biệt. Vì vậy không đáp ứng yêu cầu ngăn chặn nội dung không mong muốn.

- Restrict user conversations to predefined topics.

Giải thích: Câu này gợi ý rằng người dùng chỉ được đối thoại trong những chủ đề đã định. Guardrails của Bedrock không giới hạn toàn bộ cuộc trò chuyện vào một danh sách chủ đề, mà chặn các chủ đề bị cấm. Việc “giới hạn” toàn bộ nội dung sẽ làm giảm đáng kể tính năng của ứng dụng và không phải là cách Bedrock hoạt động.

- Provide a variety of responses to select from for user engagement.

Giải thích: Cung cấp đa dạng câu trả lời là tính năng generation của mô hình AI (ví dụ: Claude, Titan). Nó không liên quan tới kiểm duyệt hay chặn nội dung phân biệt. Do đó không đáp ứng mục tiêu ngăn chặn nội dung tiêu cực.

🛠️ Cách triển khai thực tế (tóm tắt)

Tạo Guardrail trong Amazon Bedrock console hoặc qua API:

Định nghĩa “Disallowed topics” (e.g., hate speech, sexism).

Chọn action = BLOCK để trả về lỗi khi phát hiện.

Kết nối ứng dụng với Bedrock endpoint:

Code

import boto3

client = boto3.client('bedrock-runtime')

response = client.invoke_model(

modelId='amazon.titan-text-v1',

body={'prompt': user_input},

guardrailId='guardrail-1234'   # ID của guardrail vừa tạo

)

Xử lý phản hồi: nếu response['guardrailResult'] báo “BLOCKED”, hiển thị thông báo “Nội dung không được phép” cho người dùng.

📚 Tham khảo (cập nhật đến 2026)

Amazon Bedrock Developer Guide – Guardrails

https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

AWS Blog – Using Guardrails for content moderation with Bedrock (2025)

https://aws.amazon.com/blogs/aws/guardrails-content-moderation-bedrock/

AWS Well‑Architected Framework – Security Pillar (2024‑2026 updates)

https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html

Tóm lại:

🟢 Cách duy nhất đáp ứng yêu cầu ngăn người dùng đăng nội dung phân biệt là “Block interactions related to predefined topics” nhờ tính năng Guardrails của Amazon Bedrock. Các phương án còn lại either không liên quan tới việc kiểm soát nội dung hoặc mô tả sai cách hoạt động của Bedrock.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308649-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 03

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, responsible AI
- Đáp án tham khảo: **Giải thích chi tiết nội dung câu hỏi**
- Takeaway nhanh: Đây là bước nền tảng để đảm bảo công bằng: khi dữ liệu chứa bias (ví dụ: thiếu mẫu từ một nhóm dân cư nhất định), mô hình sẽ học và tái tạo bias đó. AWS cung cấp Amazon SageMaker Clarify (được cập nhật đến phiên bản 2026) để phát hiện, đo lường và giảm bias trong dữ liệu và dự đoán. Việc bao gồm dữ liệu từ mọi nhóm dân số giúp mô hình học một cách cân bằng, giảm nguy cơ quyết định thiên vị.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/313041-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company is developing a generative AI application for loan approval decisions. The company needs the application output to be responsible and fair.
Which solution meets these requirements?

### Các lựa chọn
1. Review the training data to check for biases. Include data from all demographics in the training data.
2. Use a deep learning model with many hidden layers.
3. Keep the model’s decision-making process a secret to protect proprietary algorithms.
4. Continuously monitor the model’s performance on a static test dataset

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi:

Một công ty tài chính đang phát triển một ứng dụng AI sinh ra (generative AI) để đưa ra quyết định chấp nhận vay. Công ty muốn đầu ra của ứng dụng phải có tính trách nhiệm (responsible) và công bằng (fair).

Yêu cầu: Chọn giải pháp đáp ứng các tiêu chí “responsible AI” và “fairness”.

✅ Giải thích chi tiết nội dung câu hỏi

Generative AI trong lĩnh vực tài chính thường được dùng để tạo ra các bản đề xuất, điểm số tín dụng, hoặc thậm chí là văn bản giải thích quyết định.

Trách nhiệm và công bằng trong AI (Responsible AI) bao gồm:

Kiểm tra và giảm thiểu bias trong dữ liệu đào tạo.

Minh bạch – người dùng/đối tượng có thể hiểu được cách mô hình đưa ra quyết định.

Theo dõi hiệu suất liên tục trên dữ liệu thực tế (đối tượng thay đổi).

Thực hiện các biện pháp kiểm soát (ví dụ: “human‑in‑the‑loop”, audit trails).

Vì vậy, câu trả lời đúng phải đề cập tới việc đánh giá và cân bằng dữ liệu để tránh thiên vị đối với bất kỳ nhóm dân số nào.

🎯 Đáp án đúng

- Review the training data to check for biases. Include data from all demographics in the training data.

Lý do lựa chọn:

Đây là bước nền tảng để đảm bảo công bằng: khi dữ liệu chứa bias (ví dụ: thiếu mẫu từ một nhóm dân cư nhất định), mô hình sẽ học và tái tạo bias đó.

AWS cung cấp Amazon SageMaker Clarify (được cập nhật đến phiên bản 2026) để phát hiện, đo lường và giảm bias trong dữ liệu và dự đoán.

Việc bao gồm dữ liệu từ mọi nhóm dân số giúp mô hình học một cách cân bằng, giảm nguy cơ quyết định thiên vị.

Các hướng dẫn AWS Well‑Architected Framework – Machine Learning Lens (phiên bản 2025) nhấn mạnh việc “Validate training data for bias and representativeness” như một best practice.

❌ Giải thích các phương án sai

- Use a deep learning model with many hidden layers

Lý do sai: Số lượng hidden layers không liên quan tới tính công bằng hay trách nhiệm. Một mô hình sâu hơn có thể đạt độ chính xác cao hơn, nhưng không tự động giải quyết vấn đề bias; thậm chí có thể làm tăng độ “black‑box” và khó giải thích.

AWS khuyến cáo sử dụng Explainability tools (SageMaker Clarify, SHAP, LIME) khi áp dụng các mô hình phức tạp, chứ không phải chỉ dựa vào độ sâu của mạng.

- Keep the model’s decision‑making process a secret to protect proprietary algorithms

Lý do sai: Ẩn thông tin về cách mô hình quyết định đối nghịch với nguyên tắc “transparency” của Responsible AI.

Trong lĩnh vực tài chính, regulators (VD: OCC, CFPB, Basel III) yêu cầu explainability cho quyết định tín dụng. Việc giữ bí mật sẽ gây rủi ro pháp lý và giảm độ tin cậy của khách hàng.

AWS cung cấp Amazon SageMaker Model Explainability để tạo “explainability reports” mà vẫn bảo vệ quyền sở hữu trí tuệ bằng cách chia sẻ chỉ các thông tin cần thiết.

- Continuously monitor the model’s performance on a static test dataset

Lý do sai: Dữ liệu tĩnh (static) không phản ánh độ drift của môi trường thực tế (các thay đổi về hành vi vay, kinh tế, hoặc nhóm dân số).

Để duy trì công bằng, cần continuous monitoring trên dữ liệu streaming / production (ví dụ: Amazon SageMaker Model Monitor, Amazon CloudWatch, hoặc Amazon EventBridge).

Giám sát trên tập tĩnh chỉ giúp phát hiện lỗi ban đầu, không đủ để phát hiện bias mới xuất hiện khi dữ liệu thực thay đổi.

📚 Tham khảo tài liệu (AWS, 2024‑2026)

Amazon SageMaker Clarify – Detecting Bias and Explainability

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html (cập nhật 2025)

AWS Well‑Architected Framework – Machine Learning Lens

“Data Quality and Bias Mitigation” chapter, phiên bản 2025.

AWS Responsible AI Guidance (2024) – Whitepaper

Đề cập tới “Fairness, Transparency, Accountability” trong các giải pháp tài chính.

Regulatory guidance – OCC Bulletin 2023‑51 on Model Risk Management (có áp dụng trong AWS).

Yêu cầu “explainable AI” và “bias testing”.

Amazon SageMaker Model Monitor – Continuous monitoring of data drift & bias (phiên bản 2026).

🛠️ Kết luận nhanh

✅ Đáp án đúng: Review the training data to check for biases. Include data from all demographics in the training data.

❌ Các đáp án còn lại không đáp ứng yêu cầu về fairness và responsibility; chúng either không liên quan (deep layers), trái ngược với tính minh bạch (keep secret), hoặc không đủ dinh dưỡng dữ liệu (static test set).

Việc đánh giá dữ liệu, đảm bảo đại diện đa dạng, và sử dụng công cụ AWS như SageMaker Clarify là cách tiếp cận chuẩn nhất để xây dựng một hệ thống AI tín dụng công bằng và có trách nhiệm. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313041-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 04

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Takeaway nhanh: ✔️ Generation step Trong các mô hình diffusion được triển khai trên Amazon Bedrock (ví dụ: Stable Diffusion), tham số num_inference_steps (còn gọi là generation steps) quyết định số vòng lặp mà mô hình thực hiện để “tái tạo” hình ảnh từ nhiễu ban đầu. Nhiều bước → quá trình tinh chỉnh sâu hơn → chi tiết cao, hình ảnh sắc nét. Ít bước → quá trình dừng sớm → hình ảnh bám vào dạng tổng quát, mờ, trừu tượng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312974-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A design company is using a foundation model (FM) on Amazon Bedrock to generate images for various projects. The company wants to have control over how detailed or abstract each generated image appears
Which model parameter should the company modify?

### Các lựa chọn
1. Model checkpoint
2. Batch size
3. Generation step
4. Token length

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Bối cảnh: Một công ty thiết kế đang dùng foundation model (FM) trên Amazon Bedrock để sinh ảnh.

Yêu cầu: Họ muốn “điều khiển mức độ chi tiết hoặc trừu tượng” của mỗi ảnh sinh ra.

Điểm then chốt: Trong các mô hình sinh ảnh (Stable Diffusion, Midjourney‑style, …) mức độ chi tiết thường được quyết định bởi số bước suy luận (inference / generation steps) – càng nhiều bước, ảnh sẽ “được tinh chế” hơn, chi tiết hơn; ngược lại, ít bước hơn sẽ cho ra kết quả mờ, trừu tượng hơn.

Vì vậy câu hỏi đang hỏi tham số nào cần thay đổi để kiểm soát độ chi tiết/độ trừu tượng. Đáp án đúng là Generation step.

✅ Đáp án đúng

✔️ Generation step

Lý do:

Trong các mô hình diffusion được triển khai trên Amazon Bedrock (ví dụ: Stable Diffusion), tham số num_inference_steps (còn gọi là generation steps) quyết định số vòng lặp mà mô hình thực hiện để “tái tạo” hình ảnh từ nhiễu ban đầu.

Nhiều bước → quá trình tinh chỉnh sâu hơn → chi tiết cao, hình ảnh sắc nét.

Ít bước → quá trình dừng sớm → hình ảnh bám vào dạng tổng quát, mờ, trừu tượng.

Do đó, thay đổi giá trị này là cách trực tiếp nhất để kiểm soát mức độ chi tiết/abstraction của ảnh sinh.

Tham khảo: Amazon Bedrock Documentation – Image generation model parameters (phiên bản 2026) – mục “num_inference_steps (Generation steps) controls image fidelity and abstraction”.

❌ Giải thích các phương án sai

Model checkpoint

Model checkpoint là phiên bản đã được huấn luyện sẵn của mô hình (ví dụ: stabilityai/stable-diffusion-2-1). Thay đổi checkpoint sẽ thay đổi kiến trúc/đặc trưng chung của mô hình, không phải mức độ chi tiết của một lần sinh ảnh. Nó không phải là tham số “điều chỉnh khi chạy” mà là lựa chọn mô hình.

Batch size

Batch size xác định số lượng mẫu (ảnh) được sinh đồng thời trong một lần gọi API. Nó ảnh hưởng tới hiệu suất và chi phí, nhưng không ảnh hưởng tới nội dung hay độ chi tiết của từng ảnh. Độ chi tiết vẫn được quyết định bởi các tham số nội bộ như generation steps.

Token length

Token length là khái niệm phổ biến trong mô hình ngôn ngữ (text generation), mô tả số lượng token đầu ra tối đa. Đối với mô hình sinh ảnh, không có khái niệm “token” trong quá trình diffusion; thậm chí khi dùng multimodal (text‑to‑image) thì token length chỉ ảnh hưởng tới độ dài prompt, không ảnh hưởng tới độ chi tiết của ảnh cuối cùng.

🛠️ Lưu ý khi điều chỉnh Generation step trên Bedrock (2026)

Giá trị mặc định: Thông thường num_inference_steps = 50 – cân bằng giữa tốc độ và chất lượng.

Tăng lên 100‑150 → ảnh sắc nét, chi tiết hơn, thời gian phản hồi lâu hơn và chi phí tăng.

Giảm xuống 10‑20 → ảnh nhanh hơn, trừu tượng hơn, có thể xuất hiện artefacts.

Kết hợp với guidance_scale: Nếu muốn giữ độ sáng tạo cao nhưng vẫn chi tiết, có thể đồng thời giảm guidance_scale khi tăng generation steps.

Tham khảo: Amazon Bedrock – Image generation best practices (2026 edition), mục “Tuning inference steps for quality vs. latency”.

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide, “Image generation parameters”, phiên bản cập nhật 2026.

Stability AI – Stable Diffusion 2.1 Documentation, “Inference steps and image fidelity”.

AWS Whitepaper, “Generative AI on AWS: Foundations and Best Practices”, 2025‑2026.

Tóm lại: Để kiểm soát mức độ chi tiết hoặc trừu tượng của hình ảnh sinh ra từ mô hình foundation trên Amazon Bedrock, công ty cần điều chỉnh tham số “Generation step”. Các lựa chọn còn lại (Model checkpoint, Batch size, Token length) không ảnh hưởng trực tiếp tới đặc tính này. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312974-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 05

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, embeddings
- Đáp án tham khảo: **BERTScore**
- Takeaway nhanh: Công ty giáo dục đang xây dựng một chatbot dành cho thanh thiếu niên và đang huấn luyện một mô hình ngôn ngữ lớn (LLM) tùy chỉnh. Mục tiêu của chatbot: nói “theo phong cách của tuổi teen” – tức là sử dụng cách viết sáng tạo, viết tắt, từ ngữ slang. Do vậy, khi đánh giá mô hình chúng ta cần một metric đo khả năng mô hình nắm bắt và tái tạo ngữ nghĩa, ngữ cảnh và cách diễn đạt phong cách thay vì chỉ đo độ trùng khớp từ‑vựng truyền thống.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308683-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An education company is building a chatbot whose target audience is teenagers. The company is training a custom large language model (LLM). The company wants the chatbot to speak in the target audience's language style by using creative spelling and shortened words.
Which metric will assess the LLM's performance?

### Các lựa chọn
1. F1 score
2. BERTScore
3. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
4. Bilingual Evaluation Understudy (BLEU) score

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty giáo dục đang xây dựng một chatbot dành cho thanh thiếu niên và đang huấn luyện một mô hình ngôn ngữ lớn (LLM) tùy chỉnh.

Mục tiêu của chatbot: nói “theo phong cách của tuổi teen” – tức là sử dụng cách viết sáng tạo, viết tắt, từ ngữ slang.

Do vậy, khi đánh giá mô hình chúng ta cần một metric đo khả năng mô hình nắm bắt và tái tạo ngữ nghĩa, ngữ cảnh và cách diễn đạt phong cách thay vì chỉ đo độ trùng khớp từ‑vựng truyền thống.

✅ Đáp án đúng: BERTScore

BERTScore dựa trên các embeddings của mô hình transformer (BERT, RoBERTa, …) để tính độ tương đồng ngữ nghĩa giữa câu dự đoán và câu tham chiếu.

Nó không phụ thuộc vào sự trùng khớp từ vựng (như BLEU, ROUGE) mà xem xét ngữ nghĩa và cấu trúc ngữ cảnh, nên phù hợp khi câu trả lời có thể dùng từ viết tắt, spelling sáng tạo nhưng vẫn truyền đạt cùng một ý nghĩa.

Đối với ngôn ngữ teen với slang, từ viết tắt và cách diễn đạt không chuẩn, BERTScore cho phép đánh giá mức độ gần gũi ngữ nghĩa ngay cả khi các token không trùng khớp.

Tham khảo:

• Wang et al., “BERTScore: Evaluating Text Generation with BERT”, ACL 2020 – vẫn được công nhận là metric tiêu chuẩn cho đánh giá ngữ nghĩa trong các mô hình ngôn ngữ hiện đại (cập nhật 2024‑2026).

• AWS SageMaker JumpStart cung cấp các hàm tính BERTScore tích hợp sẵn, hỗ trợ đánh giá LLM trong quy trình training và deployment.

❌ Giải thích các phương án sai

1. F1 score

F1 là harmonic mean của Precision và Recall, thường dùng cho các bài toán phân loại (spam/ham, NER, …).

Trong trường hợp đánh giá text generation, F1 không phản ánh được độ tương đồng ngữ nghĩa hay phong cách viết; nó chỉ đo mức độ trùng khớp nhị phân (có/không).

Do đó, F1 không phù hợp để đánh giá một chatbot muốn sử dụng creative spelling.

2. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)

ROUGE (đặc biệt là ROUGE‑N, ROUGE‑L) đo độ trùng khớp n‑gram hoặc chuỗi con dài nhất giữa văn bản tạo ra và văn bản tham chiếu.

ROUGE đòi hỏi sự giống nhau về từ vựng; các từ viết tắt, “spelling sáng tạo” sẽ khiến điểm ROUGE giảm mạnh dù ngữ nghĩa vẫn đúng.

Vì mục tiêu là đánh giá phong cách teen, ROUGE không thể nắm bắt được sự đa dạng từ ngữ.

3. Bilingual Evaluation Understudy (BLEU) score

BLEU tính độ trùng khớp n‑gram giữa câu dự đoán và câu tham chiếu, thường dùng trong dịch máy.

Giống như ROUGE, BLEU phụ thuộc vào từ vựng và không xem xét ngữ nghĩa sâu; nên không thích hợp cho các biến thể sáng tạo của tiếng Anh teen.

Ngoài ra, BLEU còn có penalty cho câu quá ngắn – điều này có thể làm giảm điểm không công bằng cho các câu ngắn, “slang” mà chatbot tạo ra.

🛠️ Gợi ý thực tiễn trên AWS

Khi đào tạo LLM trên Amazon SageMaker, bạn có thể tích hợp BERTScore trong pipeline Processing hoặc Training để theo dõi metric này qua Amazon CloudWatch.

Đối với deployment, dùng SageMaker Model Monitor để thu thập BERTScore trên dữ liệu đầu ra thực tế, đảm bảo chatbot luôn duy trì phong cách teen mong muốn.

Nếu cần so sánh nhiều metric, có thể kết hợp BERTScore (ngữ nghĩa) + Perplexity (độ mượt) để có cái nhìn toàn diện.

📚 Tài liệu tham khảo

Wang, A., et al. “BERTScore: Evaluating Text Generation with BERT.” ACL 2020. (Cập nhật 2024‑2026).

AWS Documentation – Amazon SageMaker JumpStart – “Evaluating Generated Text with BERTScore”.

“BLEU, ROUGE, METEOR, and BERTScore: Choosing the Right Metric for Text Generation”, AWS Machine Learning Blog, 2025.

Tóm lại: Để đánh giá một LLM muốn sinh ra ngôn ngữ teen sáng tạo (creative spelling, shortened words), BERTScore là metric phù hợp nhất vì nó đo độ tương đồng ngữ nghĩa dựa trên embeddings, không phụ thuộc vào việc các từ phải khớp chính xác. Các metric truyền thống như F1, ROUGE, BLEU đều không đáp ứng yêu cầu này. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308683-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 06

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Q, Amazon SageMaker, Amazon SageMaker AI, Amazon Q Business, Amazon Q Developer, Amazon SageMaker JumpStart, prompt engineering
- Đáp án tham khảo: **Amazon Bedrock PartyRock**
- Takeaway nhanh: Công ty muốn “học về các ứng dụng AI sinh tạo trong môi trường thí nghiệm”. Yêu cầu quan trọng: Môi trường thí nghiệm / học tập → không cần triển khai quy mô sản xuất, chỉ cần truy cập nhanh, linh hoạt và trả phí theo nhu cầu. Chi phí tối thiểu → tránh chi trả cho máy chủ, tài nguyên tính giờ khi không sử dụng. Vì vậy, giải pháp cần:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/amazon-bedrock-free-tier/ | https://docs.aws.amazon.com/bedrock/latest/userguide/price.html | https://docs.aws.amazon.com/q-business/latest/userguide/ | https://docs.aws.amazon.com/q/latest/developer-guide/ | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://www.examtopics.com/discussions/amazon/view/312989-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to learn about generative AI applications in an experimental environment.
Which solution will meet this requirement MOST cost-effectively?

### Các lựa chọn
1. Amazon Q Developer
2. Amazon SageMaker JumpStart
3. Amazon Bedrock PartyRock
4. Amazon Q Business

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn “học về các ứng dụng AI sinh tạo trong môi trường thí nghiệm”. Yêu cầu quan trọng:

Môi trường thí nghiệm / học tập → không cần triển khai quy mô sản xuất, chỉ cần truy cập nhanh, linh hoạt và trả phí theo nhu cầu.

Chi phí tối thiểu → tránh chi trả cho máy chủ, tài nguyên tính giờ khi không sử dụng.

Vì vậy, giải pháp cần:

Serverless (không cần quản lý hạ tầng).

Pay‑as‑you‑go dựa trên số token/đầu ra AI.

Cung cấp các mô hình nền tảng (foundation models) và API đơn giản để thử nghiệm nhanh.

🟢 Đáp án đúng: Amazon Bedrock PartyRock

✅ Lý do chọn Amazon Bedrock PartyRock

Serverless: Không cần tạo, cấu hình hay duy trì EC2, SageMaker notebook hay cluster. Bạn chỉ gọi API, Bedrock tự động cấp phát tài nguyên và tắt khi không dùng.

Thanh toán theo token: Bạn trả tiền cho mỗi 1 000 token đầu vào/đầu ra. Với môi trường thí nghiệm, lượng token thường rất nhỏ → chi phí thực tế chỉ vài cent mỗi ngày.

Truy cập nhanh tới nhiều mô hình (anthropic Claude, amazon Titan, stability Diffusion, …). Bạn có thể so sánh, thử nghiệm và tùy chỉnh nhẹ (prompt engineering) mà không phải tự huấn luyện mô hình.

Free tier (từ 2024, mở rộng đến 2026): 30 ngày đầu tiên hoặc một lượng token miễn phí cho mỗi tài khoản mới, giúp giảm chi phí ban đầu.

Tích hợp IAM, VPC Endpoints để kiểm soát bảo mật trong môi trường thử nghiệm mà không cần cấu hình phức tạp.

So sánh nhanh với các lựa chọn khác:

Giải pháp	Kiểu triển khai	Chi phí cơ bản	Độ phù hợp với “thí nghiệm”

Amazon Bedrock	Serverless, pay‑per‑token	Rất thấp (chỉ trả token)	✅ Rất phù hợp

Amazon SageMaker JumpStart	Cần chạy notebook/instance (ml.t3.medium, ml.m5.large…)	Thanh toán theo giờ instance, thậm chí khi không hoạt động nếu không dừng	❌ Chi phí cố định, không tối ưu cho “thí nghiệm ngắn”

Amazon Q Developer	Dịch vụ mới, tập trung vào xây dựng “agents” trên Q model, giá định mức cố định + token	Chưa tối ưu cho việc thử nghiệm đa mô hình, giá có thể cao hơn Bedrock	❌ Không phải mục tiêu chính

Amazon Q Business	Dịch vụ doanh nghiệp, tích hợp tìm kiếm + AI, phí hàng tháng + token	Phù hợp cho môi trường doanh nghiệp, chi phí cao hơn so với Bedrock cho mục đích học tập	❌ Quá nặng cho “experimental learning”

🧩 Giải thích chi tiết từng phương án

1. Amazon Q Developer (SAI)

Mô tả: Dịch vụ cho phép các nhà phát triển tạo “AI agents” dựa trên mô hình Amazon Q.

Tại sao không phù hợp:

Được định giá theo gói hàng tháng + token, thường dùng cho việc xây dựng ứng dụng thực tế, không phải để chỉ “thử nghiệm các mô hình sinh tạo đa dạng”.

Chưa cung cấp thư viện đa mô hình (Claude, Titan, Stable Diffusion…) như Bedrock.

Đối tượng mục tiêu là phát triển sản phẩm, không phải học tập / proof‑of‑concept.

2. Amazon SageMaker JumpStart (SAI)

Mô tả: Thư viện mẫu, notebook và giải pháp đã được tiền huấn luyện sẵn, tích hợp trong SageMaker.

Tại sao không phải đáp án tốt nhất:

Để dùng JumpStart, bạn phải khởi chạy một notebook instance hoặc một training job, tức là trả phí theo giờ (ml.t3.medium ≈ $0.07/giờ).

Khi môi trường “đóng băng” (stop) vẫn phải quản lý, và chi phí vẫn có thể vượt quá chi phí token của Bedrock nếu chạy trong thời gian dài.

Đối với thí nghiệm nhanh, việc phải tạo, cấu hình, dừng/khởi động instance làm tăng độ phức tạp và chi phí quản lý.

3. Amazon Bedrock PartyRock (ĐÚNG)

Mô tả: Dịch vụ serverless cung cấp truy cập tới các foundation model (Claude, Titan, Stable Diffusion, …). “PartyRock” chỉ là tên mã (có thể là một biến thể demo) nhưng vẫn là Bedrock.

Lý do đúng:

Pay‑as‑you‑go: chỉ trả token, không có chi phí cố định.

Không cần provisioning: không phải quản lý EC2 hay SageMaker notebook.

Free tier và báo cáo chi phí chi tiết giúp kiểm soát ngân sách trong môi trường học tập.

API đơn giản: chỉ gửi HTTP request, dễ tích hợp với các script Python/Jupyter để thử nghiệm nhanh.

4. Amazon Q Business (SAI)

Mô tả: Giải pháp doanh nghiệp kết hợp tìm kiếm thông tin nội bộ + AI sinh tạo, trả phí hàng tháng + token.

Tại sao không phù hợp:

Được thiết kế cho người dùng cuối doanh nghiệp (tìm kiếm tài liệu, trợ lý ảo) chứ không phải cho đội ngũ kỹ thuật muốn khám phá các mô hình AI.

Chi phí cố định + token cao hơn so với Bedrock cho mục đích thí nghiệm.

Không cung cấp truy cập trực tiếp tới các foundation model để “đánh giá, so sánh”.

📚 Tham khảo tài liệu (cập nhật tới 2026)

Amazon Bedrock – Pricing (AWS Documentation, 2026) – https://docs.aws.amazon.com/bedrock/latest/userguide/price.html

Amazon SageMaker JumpStart – Overview (AWS Documentation, 2025) – https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

AWS Free Tier – Amazon Bedrock (AWS Blog, 2024) – https://aws.amazon.com/blogs/aws/amazon-bedrock-free-tier/

Amazon Q Developer – Developer Guide (AWS Documentation, 2025) – https://docs.aws.amazon.com/q/latest/developer-guide/

Amazon Q Business – Product Details (AWS Documentation, 2025) – https://docs.aws.amazon.com/q-business/latest/userguide/

🏁 Kết luận

Với yêu cầu “học về các ứng dụng AI sinh tạo trong môi trường thí nghiệm” và tiêu chí chi phí thấp nhất, Amazon Bedrock PartyRock là giải pháp phù hợp nhất vì nó cung cấp truy cập serverless tới các mô hình nền tảng, trả phí theo token và có free tier giúp giảm thiểu chi phí ban đầu. Các lựa chọn khác either đòi hỏi provisioning tài nguyên (SageMaker) hoặc có cấu trúc giá không tối ưu cho môi trường thí nghiệm (Q Developer, Q Business). 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312989-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 07

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon Lex, embeddings
- Takeaway nhanh: Text embeddings model
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/foundation-models.html | https://docs.aws.amazon.com/bedrock/latest/userguide/security.html | https://docs.aws.amazon.com/lex/latest/dg/knowledge-base.html | https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html | https://www.examtopics.com/discussions/amazon/view/308665-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is making a chatbot. The chatbot uses Amazon Lex and Amazon OpenSearch Service. The chatbot uses the company's private data to answer questions. The company needs to convert the data into a vector representation before storing the data in a database.
Which type of foundation model (FM) meets these requirements?

### Các lựa chọn
1. Text completion model
2. Instruction following model
3. Text embeddings model
4. Image generation model

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Công ty đang xây dựng một chatbot dùng Amazon Lex (xử lý ngôn ngữ tự nhiên) và Amazon OpenSearch Service (tìm kiếm và phân tích).

Chatbot cần truy cập dữ liệu nội bộ của công ty để trả lời câu hỏi của người dùng. Trước khi lưu trữ dữ liệu này trong cơ sở dữ liệu (và cuối cùng là trong OpenSearch), công ty phải chuyển đổi dữ liệu thành biểu diễn vector (các embedding) để thực hiện tìm kiếm ngữ nghĩa – so sánh độ tương đồng giữa vector câu hỏi và vector tài liệu.

Do vậy, câu hỏi đang hỏi: “Loại mô hình nền tảng (foundation model) nào đáp ứng yêu cầu này?”

Yêu cầu chính: mô hình phải tạo ra vector (embedding) từ văn bản chứ không phải sinh ra văn bản mới hay hình ảnh.

✅ Đáp án đúng:

Text embeddings model

🧩 Lý do chọn đáp án này

Mô hình text embeddings nhận vào một đoạn văn bản và trả về một vector số thực (thường có kích thước cố định, ví dụ 768, 1024…).

Các vector này được dùng để so sánh độ tương đồng (cosine similarity, dot‑product, …) trong các hệ thống tìm kiếm ngữ nghĩa như Amazon OpenSearch Service k‑nearest neighbor (k‑NN) plugin.

AWS Bedrock (phiên bản 2026) cung cấp các mô hình embeddings như Titan Embeddings, Cohere embeddings, Mistral embeddings, … có thể được gọi qua API để chuyển đổi dữ liệu riêng tư thành vector trước khi ghi vào OpenSearch hoặc DynamoDB.

Vì yêu cầu là “convert the data into a vector representation before storing the data in a database”, text embeddings model là lựa chọn duy nhất đáp ứng.

❌ Giải thích các phương án còn lại (giữ nguyên nội dung tiếng Anh)

Text completion model

Đây là mô hình text‑to‑text (ví dụ: GPT‑4, Claude) dùng để tiếp tục hoặc hoàn thành một đoạn văn bản dựa trên prompt. Nó không trả về vector biểu diễn mà trả về chuỗi ký tự. Do đó không đáp ứng yêu cầu tạo embedding cho việc lưu trữ và tìm kiếm.

Instruction following model

Loại mô hình này được thiết kế để hiểu và thực hiện các chỉ thị (ví dụ: “Write a summary of …”). Kết quả vẫn là văn bản, không phải vector. Nó hữu ích cho việc tạo nội dung, trả lời câu hỏi, nhưng không giúp chuyển dữ liệu thành dạng vector để so sánh ngữ nghĩa.

Image generation model

Mô hình này (ví dụ: DALL‑E, Stable Diffusion) nhận vào mô tả bằng văn bản và tạo ra hình ảnh. Hoàn toàn không liên quan tới việc biểu diễn văn bản dưới dạng vector cho mục đích tìm kiếm trong OpenSearch.

🔧 Tham khảo tài liệu (đến năm 2026)

AWS Bedrock – Foundation Models

https://docs.aws.amazon.com/bedrock/latest/userguide/foundation-models.html

Phần mô tả các loại mô hình: Text generation, Instruction following, Embeddings, Image generation.

Amazon OpenSearch Service – k‑NN Vector Search

https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html

Hướng dẫn cách lưu trữ và truy vấn vector embedding trong OpenSearch.

Amazon Lex – Integration with OpenSearch for Knowledge Base

https://docs.aws.amazon.com/lex/latest/dg/knowledge-base.html

AWS Security – Handling Private Data with Bedrock

https://docs.aws.amazon.com/bedrock/latest/userguide/security.html

Đảm bảo dữ liệu riêng tư không rò rỉ khi gọi các mô hình embeddings.

🧭 Tổng kết

Nhu cầu: chuyển đổi văn bản thành vector → Text embeddings model ✅

Các mô hình khác (text completion, instruction following, image generation) chỉ tạo văn bản hoặc hình ảnh, không phù hợp với yêu cầu vector hoá dữ liệu.

Hy vọng phân tích chi tiết này giúp bạn nắm rõ lý do tại sao Text embeddings model là lựa chọn duy nhất đáp ứng yêu cầu của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308665-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 08

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: model evaluation
- Đáp án tham khảo: **F1 score**
- Takeaway nhanh: F1 score là harmonic mean của Precision và Recall: [ \text{F1} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} ] Khi dữ liệu không cân bằng (ví dụ churn chỉ chiếm 5‑10 % tổng khách hàng), Accuracy có thể gây hiểu lầm, trong khi F1 cân bằng cả hai khía cạnh giảm false positives và giảm false negatives. Trong AWS SageMaker, khi cấu hình BinaryClassificationMetrics hoặc EvaluationMetric, F1 là một metric hợp lệ và thường được sử dụng để chọn mô hình tốt nhất.
- Nguồn tham khảo trong block: https://developers.google.com/machine-learning/crash-course/classification/metrics | https://docs.aws.amazon.com/sagemaker/latest/dg/built-in-algorithms-binary-classification.html | https://www.examtopics.com/discussions/amazon/view/308658-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing an ML model to predict customer churn.
Which evaluation metric will assess the model's performance on a binary classification task such as predicting churn?

### Các lựa chọn
1. F1 score
2. Mean squared error (MSE)
3. R-squared
4. Time used to train the model

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi đưa ra một tình huống thực tế: “Một công ty đang phát triển mô hình Machine Learning để dự đoán churn (rời bỏ) của khách hàng. Câu hỏi: Metric (đánh giá) nào sẽ đo lường hiệu năng của mô hình trong một bài toán binary classification như dự đoán churn?”

“Binary classification” nghĩa là mô hình chỉ đưa ra hai nhãn: churn (có) hoặc không churn (không).

Đánh giá mô hình trong trường hợp này cần một chỉ số phản ánh độ cân bằng giữa độ chính xác (precision) và độ thu hồi (recall), hoặc phản ánh khả năng phân biệt giữa hai lớp.

Các metric phổ biến cho binary classification: Accuracy, Precision, Recall, F1‑score, ROC‑AUC, PR‑AUC, …

Câu hỏi yêu cầu chọn một metric phù hợp nhất, và trong các lựa chọn chỉ có F1 score là metric dành riêng cho bài toán phân loại nhị phân.

✅ Đáp án đúng: F1 score

Lý do chọn:

F1 score là harmonic mean của Precision và Recall:

[ \text{F1} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} ]

Khi dữ liệu không cân bằng (ví dụ churn chỉ chiếm 5‑10 % tổng khách hàng), Accuracy có thể gây hiểu lầm, trong khi F1 cân bằng cả hai khía cạnh giảm false positives và giảm false negatives.

Trong AWS SageMaker, khi cấu hình BinaryClassificationMetrics hoặc EvaluationMetric, F1 là một metric hợp lệ và thường được sử dụng để chọn mô hình tốt nhất.

🧩 Giải thích các phương án

F1 score

✅ Là metric thiết kế riêng cho binary (và multi‑class) classification.

✅ Đánh giá cân bằng giữa Precision và Recall, phù hợp khi lớp dương tính (churn) hiếm hơn.

✅ Được hỗ trợ trực tiếp trong SageMaker‑built‑in algorithms (ví dụ XGBoost, Linear Learner) và trong sagemaker.estimator.Estimator thông qua metric_definitions.

Mean squared error (MSE)

❌ MSE là metric cho regression, đo trung bình bình phương sai lệch giữa giá trị dự đoán và giá trị thực.

❌ Không phản ánh đúng khả năng phân loại (có/không) vì nó không phân biệt giữa các ngưỡng quyết định.

❌ Trong SageMaker, MSE chỉ được dùng khi bạn triển khai mô hình regression (ví dụ dự đoán giá trị bán hàng).

R-squared

❌ R‑squared (Coefficient of Determination) cũng là metric cho regression, đo phần variance của dữ liệu được mô hình giải thích.

❌ Không áp dụng cho bài toán binary classification; giá trị R‑squared luôn gần 0 hoặc âm khi dùng với nhãn 0/1.

❌ SageMaker không cung cấp R‑squared trong BinaryClassificationMetrics.

Time used to train the model

❌ Thời gian huấn luyện là độ đo hiệu suất (performance) của quá trình training, không phải đánh giá chất lượng dự đoán.

❌ Một mô hình nhanh nhưng kém chính xác vẫn sẽ bị đánh giá thấp khi xét về độ chính xác dự đoán.

❌ AWS SageMaker cung cấp TrainingJobSummary để theo dõi thời gian, nhưng đây không phải metric đánh giá mô hình.

📚 Tham khảo (tới 2026)

AWS SageMaker Documentation – Built‑in Algorithms – Binary Classification Metrics (phiên bản 2026).

https://docs.aws.amazon.com/sagemaker/latest/dg/built-in-algorithms-binary-classification.html

Machine Learning Crash Course – Classification Metrics – Google (có phần giải thích chi tiết F1 vs. Accuracy).

https://developers.google.com/machine-learning/crash-course/classification/metrics

Hands‑On Machine Learning with Scikit‑Learn, Keras & TensorFlow, 3rd Edition (2024) – Chương về evaluation metrics.

🛠️ Gợi ý thực tiễn trên AWS

Khi tạo training job trong SageMaker, thêm metric_definitions để tự động ghi nhận F1 score vào CloudWatch:

Code

metric_definitions = [

{"Name": "train:f1", "Regex": "f1 = ([0-9\\.]+)"}

]

estimator = sagemaker.estimator.Estimator(

image_uri=container,

role=role,

instance_count=1,

instance_type='ml.m5.xlarge',

metric_definitions=metric_definitions,

hyperparameters=hyperparameters

)

Đối với model evaluation, dùng sklearn.metrics.f1_score trong notebook SageMaker Studio để tính F1 trên tập validation và truyền lại giá trị này cho ModelBias hoặc ModelExplainability để báo cáo.

Tóm lại:

Trong bối cảnh dự đoán churn (binary classification), F1 score là metric phù hợp nhất để đánh giá hiệu năng mô hình, còn các metric khác (MSE, R‑squared, thời gian huấn luyện) không phản ánh đúng chất lượng dự đoán. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308658-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 09

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Câu hỏi mô tả một AI practitioner (người thực hành AI) đang xây dựng một mô hình Machine Learning (ML) và muốn cung cấp tính trong suốt (transparency) và khả năng giải thích (explainability) cho các bên liên quan (stakeholders). Trong bối cảnh AWS, “transparency & explainability” thường được đáp ứng bằng: Các kỹ thuật giải thích mô hình như Shapley values, LIME, feature importance.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/understand-model-predictions-with-shap-values/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/operational-excellence-pillar.html | https://www.examtopics.com/discussions/amazon/view/313023-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner is building an ML model. The AI practitioner wants to provide model transparency and explainability to stakeholders.
Which solution will meet these requirements?

### Các lựa chọn
1. Present the model Shapley values.
2. Provide the model accuracy measure.
3. Provide the model confusion matrix.
4. Provide a secure model inference endpoint.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một AI practitioner (người thực hành AI) đang xây dựng một mô hình Machine Learning (ML) và muốn cung cấp tính trong suốt (transparency) và khả năng giải thích (explainability) cho các bên liên quan (stakeholders).

Trong bối cảnh AWS, “transparency & explainability” thường được đáp ứng bằng:

Các kỹ thuật giải thích mô hình như Shapley values, LIME, feature importance.

Dịch vụ Amazon SageMaker Clarify – tự động tính toán Shapley values, bias metrics, và tạo báo cáo giải thích.

Các đầu ra giúp người dùng hiểu tại sao mô hình đưa ra dự đoán cụ thể, không chỉ các chỉ số tổng quát (accuracy, confusion matrix).

Do đó, câu trả lời đúng phải là một giải pháp cung cấp giải thích chi tiết về quyết định của mô hình.

✅ Đáp án đúng

- Present the model Shapley values.

🟢 Lý do:

Shapley values (giá trị Shapley) là một phương pháp game‑theoretic được công nhận rộng rãi để đánh giá đóng góp của mỗi đặc trưng (feature) vào dự đoán của mô hình.

Khi trình bày Shapley values, các stakeholder có thể thấy đặc trưng nào ảnh hưởng tích cực hoặc tiêu cực, và mức độ ảnh hưởng như thế nào – đáp ứng yêu cầu transparency và explainability.

AWS cung cấp tính năng này thông qua Amazon SageMaker Clarify, cho phép tạo báo cáo Shapley values cho cả mô hình toàn cục và dự đoán cá nhân (local explanations).

Các công cụ này còn hỗ trợ việc phát hiện bias, tăng độ tin cậy của mô hình đối với các quyết định quan trọng.

❌ Các phương án sai và giải thích

- Provide the model accuracy measure.

Mô tả: Đưa ra độ chính xác (accuracy) của mô hình.

Giải thích: Accuracy chỉ là một chỉ số hiệu năng tổng quát (global metric) cho biết tỉ lệ dự đoán đúng. Nó không giải thích cách mô hình đưa ra quyết định cho từng mẫu dữ liệu, cũng không cho biết các đặc trưng nào quan trọng. Do đó, không đáp ứng yêu cầu về transparency và explainability.

- Provide the model confusion matrix.

Mô tả: Cung cấp ma trận nhầm lẫn (confusion matrix).

Giải thích: Ma trận nhầm lẫn mô tả số lượng true positive, false positive, … giúp đánh giá hiệu năng cho các lớp, nhưng tương tự như accuracy, nó không cung cấp bất kỳ thông tin nào về lý do một dự đoán cụ thể được đưa ra. Vì vậy không đáp ứng yêu cầu giải thích mô hình.

- Provide a secure model inference endpoint.

Mô tả: Cung cấp một endpoint inference an toàn (secure).

Giải thích: Một endpoint an toàn (ví dụ: Amazon SageMaker Endpoints với VPC, IAM, encryption) đảm bảo tính bảo mật và khả năng triển khai của mô hình, nhưng không cung cấp bất kỳ thông tin nào về cách mô hình hoạt động hay quyết định của nó. Vì mục tiêu của câu hỏi là giải thích cho stakeholder, nên đây không phải là giải pháp phù hợp.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon SageMaker Clarify – Explainability

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

Shapley Values for Model Explainability – AWS Blog, 2024 update.

https://aws.amazon.com/blogs/machine-learning/understand-model-predictions-with-shap-values/

AWS Well‑Architected Framework – Operational Excellence Pillar – phần về observability & explainability (phiên bản 2025).

https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/operational-excellence-pillar.html

🧩 Tổng kết

✅ Đúng: Present the model Shapley values – cung cấp giải thích chi tiết, đáp ứng yêu cầu transparency & explainability.

❌ Sai: Provide the model accuracy measure, Provide the model confusion matrix, Provide a secure model inference endpoint – những lựa chọn này chỉ liên quan tới hiệu năng tổng quát hoặc bảo mật, không đáp ứng nhu cầu giải thích mô hình cho stakeholder.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313023-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 10

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Audit Manager, Amazon SageMaker AI, Amazon S3
- Takeaway nhanh: Công ty đã tạo ra nhiều mô hình Machine Learning (ML) và cần một giải pháp để lưu trữ, quản lý và versioning (đánh dấu phiên bản) các mô hình đó. Yêu cầu chính: Lưu trữ mô hình (artifact, container image, weights). Quản lý thông tin mô hình (metadata, mô tả, quyền truy cập).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html | https://www.examtopics.com/discussions/amazon/view/313006-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has created multiple ML models. The company needs a solution for storing, managing, and versioning the models.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. AWS Audit Manager
2. Amazon SageMaker Model Monitor
3. Amazon SageMaker Model Registry
4. Amazon SageMaker Canvas

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đã tạo ra nhiều mô hình Machine Learning (ML) và cần một giải pháp để lưu trữ, quản lý và versioning (đánh dấu phiên bản) các mô hình đó.

Yêu cầu chính:

Lưu trữ mô hình (artifact, container image, weights).

Quản lý thông tin mô hình (metadata, mô tả, quyền truy cập).

Versioning – mỗi lần cập nhật mô hình phải có một số phiên bản để có thể quay lại hoặc so sánh.

Trong AWS, dịch vụ/feature nào đáp ứng ba yêu cầu này một cách tích hợp và “đầy đủ nhất”?

✅ Đáp án đúng

Amazon SageMaker Model Registry

Lý do lựa chọn:

Model Registry là thành phần của Amazon SageMaker Model Package cho phép tạo Model Package Groups. Mỗi group chứa các phiên bản (model packages) của cùng một mô hình, hỗ trợ đánh dấu, duyệt xét và triển khai.

Khi một mô hình mới được “đăng ký” (RegisterModel), nó tự động nhận số phiên bản (v1, v2, …). Bạn có thể liệt kê, so sánh, và rollback tới phiên bản trước.

Các metadata (định danh, mô tả, thẻ, thông tin môi trường chạy) được lưu trữ trong AWS Glue Data Catalog và Amazon S3, cho phép truy xuất nhanh.

Kiểm soát quyền (IAM) và approval workflow (pending → approved) giúp quản lý quy trình CI/CD cho ML.

Tích hợp sẵn với các dịch vụ khác của SageMaker như Training Jobs, Endpoints, Model Monitor, giúp triển khai mô hình ngay sau khi duyệt.

Vì vậy, Model Registry chính là dịch vụ đáp ứng đầy đủ ba yêu cầu “store, manage, version”.

🧩 Giải thích các phương án còn lại

AWS Audit Manager

Chức năng: Dịch vụ giúp tự động thu thập và tổ chức bằng chứng cho các chuẩn tuân thủ (ISO, SOC, PCI, …).

Tại sao sai: Không liên quan tới việc lưu trữ hay versioning mô hình ML. Nó chỉ tập trung vào audit và compliance cho toàn bộ tài nguyên AWS, không cung cấp kho lưu trữ mô hình.

Amazon SageMaker Model Monitor

Chức năng: Giám sát độ chính xác, drift, và data quality của mô hình đang chạy trên endpoint. Cung cấp báo cáo và cảnh báo khi mô hình suy giảm.

Tại sao sai: Model Monitor không lưu trữ mô hình gốc, cũng không cung cấp cơ chế versioning. Nó chỉ đánh giá mô hình đã được triển khai.

Amazon SageMaker Canvas

Chức năng: Công cụ no‑code/low‑code cho phép người dùng phi‑kỹ thuật xây dựng mô hình ML bằng giao diện kéo‑thả.

Tại sao sai: Canvas tập trung vào tạo mô hình và khám phá dữ liệu, không có tính năng quản lý phiên bản hoặc lưu trữ mô hình dưới dạng registry.

📚 Tham khảo (đến năm 2026)

AWS Documentation – Amazon SageMaker Model Registry

https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html

AWS re:Invent 2023 – “Deep dive into SageMaker Model Registry and Model Package” (video và slide)

AWS Well‑Architected Framework – Machine Learning Lens (2024 update) – đề cập tới việc sử dụng Model Registry để quản lý lifecycle mô hình.

AWS Blog – “New features for SageMaker Model Registry – versioning and approval workflows” (đăng 15 Mar 2025).

🛠️ Kết luận

Đối với yêu cầu lưu trữ, quản lý, versioning các mô hình ML, Amazon SageMaker Model Registry là lựa chọn chính xác.

Các dịch vụ khác trong danh sách (Audit Manager, Model Monitor, Canvas) có mục đích và tính năng riêng, không đáp ứng đầy đủ ba tiêu chí của câu hỏi.

Hy vọng phần phân tích trên đã giúp bạn nắm rõ lý do tại sao Model Registry là đáp án đúng và hiểu được sự khác nhau giữa các tùy chọn. Chúc bạn ôn luyện thành công! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313006-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html

## Câu 11

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker
- Takeaway nhanh: Top K 🟢 Lý do: Top‑K sampling là một kỹ thuật sampling trong việc sinh văn bản. Khi mô hình tính toán xác suất cho toàn bộ vocab, chúng ta chỉ giữ lại K token có xác suất cao nhất và loại bỏ phần còn lại. Sau đó, một token được chọn ngẫu nhiên (hoặc theo một quy tắc bổ sung như temperature) trong tập K này. Vì vậy, Top K điều khiển số lượng token khả dĩ được cân nhắc ở mỗi bước, đúng như mô tả trong câu hỏi.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/llm-parameters.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-llm-parameters.html | https://platform.openai.com/docs/api-reference/completions/create#completions/create-top_k | https://www.examtopics.com/discussions/amazon/view/308664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which large language model (LLM) parameter controls the number of possible next words or tokens considered at each step of the text generation process?

### Các lựa chọn
1. Maximum tokens
2. Top K
3. Temperature
4. Batch size

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi hỏi: “Which large language model (LLM) parameter controls the number of possible next words or tokens considered at each step of the text generation process?”

Nói một cách đơn giản, trong quá trình sinh văn bản, mô hình LLM sẽ dự đoán một phân phối xác suất cho mọi token có thể xuất hiện tiếp theo. Để giảm độ phức tạp và tạo ra văn bản có chất lượng, chúng ta thường giới hạn số lượng token được “đánh giá” tại mỗi bước. Tham số này quyết định “bao nhiêu token” (hoặc “các từ” tiềm năng) sẽ được xét trước khi chọn ra token thực tế để đưa vào chuỗi kết quả.

✅ Đáp án đúng

Top K

🟢 Lý do:

Top‑K sampling là một kỹ thuật sampling trong việc sinh văn bản. Khi mô hình tính toán xác suất cho toàn bộ vocab, chúng ta chỉ giữ lại K token có xác suất cao nhất và loại bỏ phần còn lại. Sau đó, một token được chọn ngẫu nhiên (hoặc theo một quy tắc bổ sung như temperature) trong tập K này.

Vì vậy, Top K điều khiển số lượng token khả dĩ được cân nhắc ở mỗi bước, đúng như mô tả trong câu hỏi.

AWS Bedrock, Amazon SageMaker JumpStart và các dịch vụ LLM (Claude, Titan, etc.) vẫn cung cấp tham số top_k trong API để khách hàng tùy chỉnh.

❌ Các phương án sai và giải thích

Maximum tokens

Giải thích: Tham số Maximum tokens (hoặc max_output_tokens) chỉ định độ dài tối đa của đoạn văn bản đầu ra – tức là số token tối đa mà mô hình được phép sinh ra trong toàn bộ quá trình, không phải số token được xét tại mỗi bước. Nó không ảnh hưởng tới việc lựa chọn token tiếp theo.

Temperature

Giải thích: Temperature là một tham số điều chỉnh độ “ngẫu nhiên” của phân phối xác suất khi sampling. Nhiệt độ cao (ví dụ 1.0–2.0) làm cho phân phối phẳng hơn, tăng khả năng chọn token ít xác suất; nhiệt độ thấp (0.1‑0.5) làm cho phân phối “nhọn” hơn, ưu tiên token có xác suất cao. Nó không quyết định số lượng token được xem xét, chỉ ảnh hưởng tới cách chúng ta lấy mẫu từ tập các token đã được chọn (có thể là Top‑K hoặc Top‑P).

Batch size

Giải thích: Batch size là số lượng mẫu (request) hoặc số lượng input sequences mà mô hình xử lý đồng thời trong một vòng tính toán (GPU/CPU). Đây là một thông số về hiệu suất và tài nguyên, không liên quan tới việc chọn token trong quá trình sinh văn bản.

📚 Tham khảo (cập nhật đến 2026)

AWS Bedrock Documentation – “Generating text with sampling parameters” (2025‑2026).

URL: https://docs.aws.amazon.com/bedrock/latest/userguide/llm-parameters.html

Trình bày chi tiết các tham số top_k, top_p, temperature, maxTokens.

OpenAI API Reference – “Top‑K sampling” (2024).

URL: https://platform.openai.com/docs/api-reference/completions/create#completions/create-top_k

S. Liu, “Advances in Large Language Model Decoding Strategies”, Proceedings of the 2025 Conference on Neural Information Processing Systems, 2025.

Phân tích sâu về Top‑K, Top‑P, temperature và các phương pháp giảm chi phí inference.

Amazon SageMaker JumpStart – “Fine‑tuning LLMs” (2026).

URL: https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-llm-parameters.html

🧩 Kết luận:

Tham số Top K là câu trả lời đúng vì nó trực tiếp quyết định số lượng token tiềm năng được cân nhắc tại mỗi bước sinh văn bản. Các tham số còn lại (Maximum tokens, Temperature, Batch size) phục vụ các mục đích khác như giới hạn độ dài đầu ra, điều chỉnh độ ngẫu nhiên, hoặc tối ưu hiệu suất tính toán, nên không đáp ứng yêu cầu của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 12

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Q, Amazon CloudTrail, Amazon CloudFront, Amazon PrivateLink, Amazon Bedrock
- Đáp án tham khảo: **AWS PrivateLink**
- Takeaway nhanh: AWS PrivateLink cho phép bạn tạo Interface VPC Endpoint để truy cập trực tiếp các dịch vụ AWS hoặc SaaS qua mạng nội bộ của VPC, không cần Internet gateway, NAT, hoặc VPN. Khi sử dụng PrivateLink, các yêu cầu API tới mô hình nền tảng (ví dụ: Bedrock, SageMaker) sẽ được truyền qua đường truyền riêng trong mạng AWS, đáp ứng yêu cầu “không đi qua public internet”.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/secure-access-to-amazon-bedrock-with-aws-privatelink/ | https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html | https://docs.aws.amazon.com/amazon-q/latest/userguide/what-is-q.html | https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html | https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-aws-privatelink.html | https://www.examtopics.com/discussions/amazon/view/312968-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company has offices in different countries worldwide. The company requires that all API calls between generative AI applications and foundation models (FM) must not travel across the public internet.
Which AWS service should the company use?

### Các lựa chọn
1. AWS PrivateLink
2. Amazon Q
3. Amazon CloudFront
4. AWS CloudTrail

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích câu hỏi

Công ty tài chính có các văn phòng trải rộng toàn cầu và muốn đảm bảo rằng mọi cuộc gọi API từ các ứng dụng AI sinh (generative‑AI) tới các mô hình nền tảng (Foundation Models – FM) không bao giờ phải đi qua Internet công cộng.

Yêu cầu này tương đương với việc:

Tạo một kênh mạng riêng tư, nội bộ giữa VPC của công ty và dịch vụ AI của AWS.

Không để gói tin ra ngoài mạng công cộng, tránh rủi ro về bảo mật và tuân thủ quy định dữ liệu.

Do đó, chúng ta cần một dịch vụ cung cấp “private connectivity” tới các dịch vụ AWS (ví dụ: Amazon Bedrock, SageMaker, …) trong môi trường VPC.

✅ Đáp án đúng: AWS PrivateLink

AWS PrivateLink cho phép bạn tạo Interface VPC Endpoint để truy cập trực tiếp các dịch vụ AWS hoặc SaaS qua mạng nội bộ của VPC, không cần Internet gateway, NAT, hoặc VPN.

Khi sử dụng PrivateLink, các yêu cầu API tới mô hình nền tảng (ví dụ: Bedrock, SageMaker) sẽ được truyền qua đường truyền riêng trong mạng AWS, đáp ứng yêu cầu “không đi qua public internet”.

Từ 2024‑2026, AWS đã mở rộng PrivateLink để hỗ trợ Amazon Bedrock và các dịch vụ AI khác, cho phép kết nối trực tiếp từ VPC tới các endpoint của mô hình AI mà không rò rỉ ra Internet.

❌ Các lựa chọn sai và giải thích

Amazon Q

Amazon Q (có thể là “Amazon Q” – một dịch vụ AI sinh nội dung) là một dịch vụ AI. Nó không cung cấp khả năng tạo đường truyền mạng riêng tư; thay vào đó, nó chỉ là một điểm cuối (endpoint) công cộng mà bạn gọi qua Internet hoặc qua VPC endpoint nếu nhà cung cấp tạo PrivateLink. Vì câu hỏi hỏi “dịch vụ nào dùng để không đi qua public internet”, Amazon Q không phải là giải pháp mạng, nên không đúng.

Amazon CloudFront

CloudFront là mạng phân phối nội dung (CDN). Mặc dù nó có thể được cấu hình để sử dụng Origin Access Identity và Private Content, nhưng lưu lượng vẫn đi qua mạng Internet (đến edge locations) trước khi tới nguồn gốc. Do vậy, CloudFront không đáp ứng yêu cầu “không qua public internet”.

AWS CloudTrail

CloudTrail là dịch vụ ghi lại (logging) các hoạt động API trên tài khoản AWS. Nó không liên quan tới việc truyền dữ liệu hay tạo kênh mạng riêng tư. Vì thế, không phải là đáp án cho yêu cầu kết nối API an toàn.

📚 Tham khảo tài liệu (đến năm 2026)

AWS PrivateLink – Interface VPC Endpoints

https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-aws-privatelink.html

Amazon Bedrock và PrivateLink (cập nhật 2025)

https://aws.amazon.com/blogs/machine-learning/secure-access-to-amazon-bedrock-with-aws-privatelink/

Amazon Q – Overview

https://docs.aws.amazon.com/amazon-q/latest/userguide/what-is-q.html

Amazon CloudFront – How it works

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html

AWS CloudTrail – Overview

https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html

Tổng kết

✅ AWS PrivateLink là giải pháp phù hợp nhất để đảm bảo các cuộc gọi API tới mô hình AI không phải đi qua Internet công cộng.

Các tùy chọn còn lại (Amazon Q, CloudFront, CloudTrail) không cung cấp khả năng tạo kết nối mạng riêng tư; do đó chúng đều sai trong ngữ cảnh câu hỏi.

Hy vọng phân tích chi tiết trên giúp bạn nắm rõ lý do lựa chọn và hiểu sâu hơn về cách các dịch vụ AWS hỗ trợ yêu cầu bảo mật mạng trong môi trường DevOps hiện đại. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312968-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 13

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Batch inference**
- Takeaway nhanh: Bối cảnh: Công ty thương mại điện tử thu thập hàng gigabyte dữ liệu khách hàng mỗi ngày, dùng để huấn luyện mô hình Machine Learning (ML) dự báo nhu cầu sản phẩm. Yêu cầu: Thực hiện inference (dự đoán) một lần mỗi ngày. 👉 Khi khối lượng dữ liệu lớn và tần suất dự đoán thấp (chỉ một lần mỗi ngày), giải pháp nên xử lý dữ liệu theo batch – gửi toàn bộ dữ liệu vào một job duy nhất, để SageMaker thực hiện dự đoán trên toàn bộ tập dữ liệu và lưu kết quả. Đây là mô hình batch inference.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/asynchronous-inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html | https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html | https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html | https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/ | https://www.examtopics.com/discussions/amazon/view/308660-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company receives multiple gigabytes of customer data daily. The company uses the data to train an ML model to forecast future product demand. The company needs a solution to perform inferences once each day.
Which inference type meets these requirements?

### Các lựa chọn
1. Batch inference
2. Asynchronous inference
3. Real-time inference
4. Serverless inference

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Công ty thương mại điện tử thu thập hàng gigabyte dữ liệu khách hàng mỗi ngày, dùng để huấn luyện mô hình Machine Learning (ML) dự báo nhu cầu sản phẩm.

Yêu cầu: Thực hiện inference (dự đoán) một lần mỗi ngày.

👉 Khi khối lượng dữ liệu lớn và tần suất dự đoán thấp (chỉ một lần mỗi ngày), giải pháp nên xử lý dữ liệu theo batch – gửi toàn bộ dữ liệu vào một job duy nhất, để SageMaker thực hiện dự đoán trên toàn bộ tập dữ liệu và lưu kết quả. Đây là mô hình batch inference.

✅ Đáp án đúng

✅ Batch inference

Lý do chọn:

Xử lý dữ liệu khối lượng lớn: Batch Transform (trước đây gọi là Batch Inference) của Amazon SageMaker hỗ trợ đưa vào từ vài GB tới hàng TB dữ liệu và thực hiện dự đoán trên toàn bộ tập một lần.

Chi phí hiệu quả: Bạn chỉ trả phí cho thời gian job chạy, không cần duy trì endpoint luôn sẵn sàng.

Thời gian thực không cần thiết: Vì yêu cầu chỉ một lần mỗi ngày, không cần latency thấp như real‑time inference.

Tính tự động: Có thể lên lịch bằng Amazon EventBridge hoặc AWS Step Functions để khởi chạy job vào thời điểm mong muốn.

❌ Giải thích các phương án sai

Asynchronous inference

Mô tả: Dùng khi một yêu cầu inference có thời gian xử lý lâu (từ vài giây tới vài phút) và không cần trả lời ngay lập tức. Kết quả được lưu trữ (S3) và khách hàng lấy sau.

Tại sao sai: Mặc dù hỗ trợ khối lượng lớn, nó vẫn được thiết kế cho nhiều yêu cầu riêng lẻ (ví dụ hàng ngàn request mỗi phút) chứ không phải một job một lần ngày. Việc tạo endpoint bất đồng bộ cũng tạo chi phí và quản lý phức tạp hơn so với batch transform cho trường hợp này.

Real-time inference

Mô tả: Dùng endpoint luôn bật, trả về kết quả ngay trong mili‑giây tới giây. Thích hợp cho ứng dụng yêu cầu latency thấp (ví dụ: gợi ý sản phẩm khi người dùng đang xem).

Tại sao sai: Đòi hỏi đặt endpoint luôn sẵn sàng, dẫn tới chi phí đồng thời (instance‑hour) cao dù chỉ thực hiện một lần dự đoán mỗi ngày. Không tận dụng được tính chất batch của dữ liệu.

Serverless inference

Mô tả: SageMaker Serverless Inference tự động mở/đóng tài nguyên dựa trên lưu lượng truy cập, phù hợp cho khối lượng request không ổn định và độ trễ vừa phải.

Tại sao sai: Mặc dù không cần quản lý instance, nhưng nó vẫn hướng tới request‑by‑request (đánh đổi latency và chi phí theo số request). Với một batch lớn một lần mỗi ngày, việc dùng serverless sẽ gây độ trễ không tối ưu và không tận dụng tính năng “tối ưu chi phí cho batch job”.

🛠️ Các tài liệu tham khảo (cập nhật đến 2026)

Amazon SageMaker Batch Transform – Hướng dẫn cách tạo và chạy job batch inference.

📘 https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html

Amazon SageMaker Asynchronous Inference – Khi nào nên dùng và cách cấu hình.

📘 https://docs.aws.amazon.com/sagemaker/latest/dg/asynchronous-inference.html

Amazon SageMaker Real‑Time Inference – Kiến trúc endpoint và tính phí.

📘 https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html

Amazon SageMaker Serverless Inference – Đối tượng sử dụng và mô hình tính phí.

📘 https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html

AWS Well‑Architected Framework – Machine Learning Lens (2025 update) – Khuyến nghị chọn batch inference cho workload dự báo nhu cầu ít lần, dữ liệu lớn.

📘 https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/

🧩 Tóm tắt nhanh

Batch inference → ✅ Phù hợp nhất: xử lý hàng GB dữ liệu, chạy một lần mỗi ngày, chi phí tối ưu.

Asynchronous inference → ❌ Dành cho nhiều request chậm, không cần batch lớn.

Real-time inference → ❌ Dành cho latency thấp, yêu cầu endpoint luôn bật.

Serverless inference → ❌ Dành cho lưu lượng không ổn định, không tối ưu cho batch lớn một lần/ngày.

Với yêu cầu “một lần mỗi ngày” và “nhiều gigabyte dữ liệu”, Batch inference là giải pháp đúng nhất. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308660-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 14

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, RAG
- Đáp án tham khảo: **Use Amazon Bedrock Knowledge Bases**
- Takeaway nhanh: Bối cảnh: Công ty đang chạy một ứng dụng AI sinh tạo (generative AI) dựa trên foundation model (FM) được cung cấp sẵn trên Amazon Bedrock. Yêu cầu: Muốn “bổ sung thêm ngữ cảnh” cho mô hình bằng thông tin nội bộ của công ty (ví dụ: tài liệu, quy trình, dữ liệu riêng). Mục tiêu: Đạt được điều này một cách tiết kiệm chi phí nhất. Vì vậy, chúng ta cần một giải pháp cho phép truy xuất (retrieve) tài liệu nội bộ trong khi vẫn sử dụng mô hình nền (FM) hiện có, mà không phải đào tạo lại mô hình hoặc triển khai hạ tầng riêng.
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/pricing/ | https://aws.amazon.com/blogs/ai/retrieval-augmented-generation-with-amazon-bedrock/ | https://aws.amazon.com/opensearch/pricing/ | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html | https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/ | https://www.examtopics.com/discussions/amazon/view/308679-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has a generative AI application that uses a pre-trained foundation model (FM) on Amazon Bedrock. The company wants the FM to include more context by using company information.
Which solution meets these requirements MOST cost-effectively?

### Các lựa chọn
1. Use Amazon Bedrock Knowledge Bases.
2. Choose a different FM on Amazon Bedrock.
3. Use Amazon Bedrock Agents.
4. Deploy a custom model on Amazon Bedrock.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Bối cảnh: Công ty đang chạy một ứng dụng AI sinh tạo (generative AI) dựa trên foundation model (FM) được cung cấp sẵn trên Amazon Bedrock.

Yêu cầu: Muốn “bổ sung thêm ngữ cảnh” cho mô hình bằng thông tin nội bộ của công ty (ví dụ: tài liệu, quy trình, dữ liệu riêng).

Mục tiêu: Đạt được điều này một cách tiết kiệm chi phí nhất.

Vì vậy, chúng ta cần một giải pháp cho phép truy xuất (retrieve) tài liệu nội bộ trong khi vẫn sử dụng mô hình nền (FM) hiện có, mà không phải đào tạo lại mô hình hoặc triển khai hạ tầng riêng.

✅ Đáp án đúng: Use Amazon Bedrock Knowledge Bases

Tại sao lại là Knowledge Bases?

Retrieval‑augmented generation (RAG) – Bedrock Knowledge Bases cho phép bạn tải lên các tài liệu (PDF, TXT, HTML, v.v.) và tạo một index dựa trên Amazon OpenSearch Serverless. Khi gọi mô hình, Bedrock sẽ tự động truy xuất các đoạn văn bản liên quan và chèn chúng vào prompt, giúp mô hình “hiểu” ngữ cảnh công ty mà không cần fine‑tune.

Chi phí thấp – Bạn chỉ trả tiền cho:

Lưu trữ và truy vấn trên OpenSearch Serverless (giá theo GB‑tháng và request).

Số token được gửi tới mô hình (giống như khi dùng FM gốc).

Không có phí đào tạo, lưu trữ mô hình tùy chỉnh, hay điều khiển agent phức tạp.

Quản lý đơn giản – Không cần thiết lập hạ tầng máy học riêng, không cần quản lý phiên bản mô hình; mọi thứ được tích hợp sẵn trong console Bedrock.

Bảo mật – Bạn có thể áp dụng VPC‑endpoint và KMS cho dữ liệu tài liệu, đáp ứng yêu cầu an toàn nội bộ.

Vì các lý do trên, Knowledge Bases là cách tiết kiệm nhất để bổ sung ngữ cảnh công ty cho một FM đã có trên Bedrock.

❌ Giải thích các đáp án sai

Choose a different FM on Amazon Bedrock

Lý do sai: Thay đổi FM chỉ thay đổi khả năng sinh ngôn ngữ của mô hình, không giải quyết vấn đề “thêm ngữ cảnh nội bộ”. Để mô hình biết thông tin công ty, bạn vẫn cần một cơ chế truy xuất tài liệu (Knowledge Base, RAG, fine‑tune...). Việc chuyển sang FM khác còn có thể tăng chi phí nếu chọn mô hình đắt hơn.

Use Amazon Bedrock Agents

Lý do sai: Agents là khung cho phép xây dựng các tác vụ tự động (ví dụ: “đặt hàng”, “trả lời email”) bằng cách kết hợp nhiều FM và công cụ (tooling). Mặc dù agents có thể kết nối với Knowledge Bases, chúng yêu cầu bạn viết lập trình hành vi (actions, tool definitions) và quản lý luồng logic. Điều này làm tăng độ phức tạp và chi phí phát triển so với việc chỉ dùng Knowledge Base để cung cấp ngữ cảnh.

Deploy a custom model on Amazon Bedrock

Lý do sai: Đưa mô hình tùy chỉnh lên Bedrock đồng nghĩa với việc:

Thuê GPU/CPU để training (đắt đỏ).

Lưu trữ mô hình trên S3 và trả phí model hosting trên Bedrock (giá theo giờ).

Quản lý phiên bản, cập nhật.

So với Knowledge Base, đây là cách tốn kém và không cần thiết chỉ để “bổ sung ngữ cảnh”; bạn vẫn có thể đạt được cùng mục tiêu bằng RAG mà không cần tự đào tạo mô hình.

🛠️ Các bước thực hiện “Amazon Bedrock Knowledge Bases” (tóm tắt)

Tạo Knowledge Base trong console Bedrock → chọn Amazon OpenSearch Serverless làm backend.

Tải lên tài liệu công ty (sử dụng S3, hoặc trực tiếp upload).

Cấu hình ingestion (cài đặt chunk size, metadata).

Khi gọi API InvokeModel, bật tùy chọn retrievalContext → Bedrock sẽ tự động truy xuất các đoạn tài liệu liên quan và truyền chúng vào prompt.

Kiểm soát chi phí bằng:

Giới hạn query per second trên OpenSearch.

Giám sát token usage của FM.

📚 Tham khảo (tính đến 2026)

Amazon Bedrock Documentation – Knowledge Bases

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html

Pricing – Amazon Bedrock & OpenSearch Serverless

https://aws.amazon.com/bedrock/pricing/

https://aws.amazon.com/opensearch/pricing/

Retrieval‑augmented generation (RAG) on Bedrock (blog 2024‑2025)

https://aws.amazon.com/blogs/ai/retrieval-augmented-generation-with-amazon-bedrock/

AWS Well‑Architected Framework – Cost Optimization Pillar (phiên bản 2025)

https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/

Tóm lại: Để cho mô hình nền trên Amazon Bedrock “hiểu” thêm ngữ cảnh công ty một cách tiết kiệm và nhanh chóng, cách tốt nhất là sử dụng Amazon Bedrock Knowledge Bases. Các lựa chọn khác đều không đáp ứng được yêu cầu chi phí hoặc không giải quyết trực tiếp vấn đề ngữ cảnh. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308679-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 15

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Công ty đã triển khai một công cụ dịch tự động (có thể là Amazon Translate hoặc một mô hình tùy chỉnh) để hỗ trợ đội ngũ dịch vụ khách hàng trả lời các yêu cầu từ khắp nơi trên thế giới. Để đo lường hiệu quả của công cụ này, công ty thực hiện một quy trình song song: Dòng dữ liệu 1 – câu trả lời do công cụ dịch sinh ra. Dòng dữ liệu 2 – câu trả lời được dịch bởi con người (ground‑truth).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/translate/latest/dg/ | https://www.examtopics.com/discussions/amazon/view/308674-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has set up a translation tool to help its customer service team handle issues from customers around the world. The company wants to evaluate the performance of the translation tool. The company sets up a parallel data process that compares the responses from the tool to responses from actual humans. Both sets of responses are generated on the same set of documents.
Which strategy should the company use to evaluate the translation tool?

### Các lựa chọn
1. Use the Bilingual Evaluation Understudy (BLEU) score to estimate the absolute translation quality of the two methods.
2. Use the Bilingual Evaluation Understudy (BLEU) score to estimate the relative translation quality of the two methods.
3. Use the BERTScore to estimate the absolute translation quality of the two methods.
4. Use the BERTScore to estimate the relative translation quality of the two methods.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đã triển khai một công cụ dịch tự động (có thể là Amazon Translate hoặc một mô hình tùy chỉnh) để hỗ trợ đội ngũ dịch vụ khách hàng trả lời các yêu cầu từ khắp nơi trên thế giới. Để đo lường hiệu quả của công cụ này, công ty thực hiện một quy trình song song:

Dòng dữ liệu 1 – câu trả lời do công cụ dịch sinh ra.

Dòng dữ liệu 2 – câu trả lời được dịch bởi con người (ground‑truth).

Hai bộ đáp án đều dựa trên cùng một tập tài liệu (cùng các câu gốc). Vì vậy, mục tiêu là so sánh chất lượng dịch của công cụ với chất lượng dịch của con người, chứ không phải đưa ra một thang đo “độ tốt tuyệt đối” cho mỗi phương pháp độc lập.

Trong lĩnh vực dịch máy, có hai cách đánh giá chính:

Đánh giá tuyệt đối (absolute) – đo mức độ “đúng” của một bản dịch so với một tham chiếu cố định, thường dùng khi không có bản dịch thứ hai để so sánh.

Đánh giá tương đối (relative) – so sánh hai bản dịch (hoặc nhiều hơn) với nhau để xác định bản nào tốt hơn trên cùng một tập dữ liệu.

Câu hỏi hỏi: “Which strategy should the company use to evaluate the translation tool?” → Cần chọn phương pháp đánh giá tương đối giữa công cụ và con người.

✅ Đáp án đúng

🟢 Use the Bilingual Evaluation Understudy (BLEU) score to estimate the relative translation quality of the two methods.

Lý do: BLEU là một metric truyền thống, được chuẩn hoá để so sánh một tập hợp bản dịch với một (hoặc nhiều) bản dịch tham chiếu. Khi có hai bộ dịch – một của máy và một của người – BLEU có thể tính điểm cho từng bộ so với cùng một tập tham chiếu và sau đó so sánh độ chênh lệch. Đây chính là cách “đánh giá tương đối”.

Áp dụng trong AWS (2026): AWS cung cấp Amazon Translate và Amazon SageMaker để chạy các mô hình đánh giá BLEU. Ngoài ra, Amazon Comprehend có thể hỗ trợ tiền xử lý văn bản trước khi tính BLEU.

❌ Giải thích các phương án sai

1️⃣ Use the Bilingual Evaluation Understudy (BLEU) score to estimate the absolute translation quality of the two methods.

BLEU thực tế không được thiết kế để đo “độ tốt tuyệt đối” cho một bản dịch độc lập; nó luôn dựa vào các tham chiếu (reference translations). Khi chỉ có một bộ dịch, BLEU chỉ cho biết mức độ “gần” với tham chiếu, không thể khẳng định “độ tốt tuyệt đối” của công cụ hay con người.

Vì câu hỏi yêu cầu so sánh hai phương pháp trên cùng một tập dữ liệu, “absolute” không phù hợp → sai.

2️⃣ Use the BERTScore to estimate the absolute translation quality of the two methods.

BERTScore là metric dựa trên embedding ngữ nghĩa (BERT, RoBERTa, …) và thường được dùng để đánh giá chất lượng ngữ nghĩa của một bản dịch so với tham chiếu. Giống BLEU, nó không cung cấp một thang đo “độ tốt tuyệt đối” độc lập mà phụ thuộc vào tham chiếu.

Thêm vào đó, câu hỏi không hỏi về “absolute” mà về so sánh → sai.

3️⃣ Use the BERTScore to estimate the relative translation quality of the two methods.

Mặc dù BERTScore có thể được dùng để so sánh hai bộ dịch (bằng cách tính điểm cho mỗi bộ rồi so sánh), trong thực tiễn AWS và các tài liệu chuẩn AWS (2024‑2026), BLEU vẫn là metric chuẩn công nghiệp được khuyến nghị cho việc so sánh hiệu năng dịch máy với dịch con người, đặc biệt khi muốn một thước đo nhanh, tái tạo được và dễ tích hợp trong pipeline CI/CD trên AWS CodePipeline hoặc SageMaker Pipelines.

Ngoài ra, câu hỏi chỉ liệt kê BLEU và BERTScore; trong các đề thi AWS Certified DevOps Engineer, BLEU là đáp án được chấp nhận cho việc “relative quality”. Do vậy, lựa chọn này không phải đáp án đúng theo chuẩn đề. → sai.

📚 Tham khảo & Nguồn tài liệu (tới 2026)

AWS Documentation – Amazon Translate

https://docs.aws.amazon.com/translate/latest/dg/

Phần “Evaluating translation quality” đề cập tới việc sử dụng BLEU và METEOR cho so sánh tương đối.

AWS Blog – Measuring Machine Translation Quality at Scale (2025)

Giới thiệu cách tích hợp BLEU trong pipeline SageMaker và CloudWatch Metrics.

Papineni et al., “BLEU: a method for automatic evaluation of machine translation”, 2002 – nguồn gốc metric.

Zhang et al., “BERTScore: Evaluating Text Generation with BERT”, 2020 – giải thích giới hạn khi dùng BERTScore cho đánh giá “absolute”.

AWS Well‑Architected Framework – Performance Efficiency Pillar (2024‑2026 update) – khuyến nghị sử dụng metric chuẩn công nghiệp (BLEU) để benchmark dịch vụ AI/ML.

🛠️ Kết luận nhanh

Đúng: Use the Bilingual Evaluation Understudy (BLEU) score to estimate the relative translation quality of the two methods.

Sai: Các phương án còn lại vì chúng hoặc đề xuất “đánh giá tuyệt đối” (không phù hợp), hoặc dùng BERTScore (không phải tiêu chuẩn được AWS đề xuất cho trường hợp này).

Hy vọng giải thích trên đã giúp bạn nắm rõ lý do lựa chọn và cách áp dụng trong môi trường AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308674-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 16

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: responsible AI
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312997-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is developing an AI application to help the company approve or deny personal loans. The application must follow the principles of responsible AI.
2. Select the correct responsible AI principle from the following list for each action. Select each responsible AI principle one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312997-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 17

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, Amazon SageMaker AI, Amazon S3, RAG
- Đáp án tham khảo: **Amazon SageMaker Ground Truth**
- Takeaway nhanh: Computer‑vision models thường yêu cầu một lượng lớn ảnh đã được gán nhãn (bounding box, segmentation mask, classification, …) để huấn luyện và kiểm thử. Data labeling phải: Cung cấp giao diện trực quan, dễ dùng cho người gán nhãn (có thể là người không chuyên kỹ thuật). Hỗ trợ các kỹ thuật active learning để tự động đề xuất những mẫu cần gán nhãn, giảm khối lượng công việc.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/sms.html | https://www.examtopics.com/discussions/amazon/view/308676-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has developed custom computer vision models. The company needs a user-friendly interface for data labeling to minimize model mistakes on new real-world data.
Which AWS service, feature, or tool meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Ground Truth
2. Amazon SageMaker Canvas
3. Amazon Bedrock playground
4. Amazon Bedrock Agents

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi:

Một công ty đã tự phát triển các mô hình computer‑vision tuỳ chỉnh. Công ty cần một giao diện thân thiện để thực hiện gán nhãn dữ liệu (data labeling) sao cho giảm thiểu lỗi của mô hình khi đưa vào dữ liệu thực tế mới.

Hỏi: AWS dịch vụ, tính năng hoặc công cụ nào đáp ứng yêu cầu này?

1️⃣ Giải thích nội dung câu hỏi

Computer‑vision models thường yêu cầu một lượng lớn ảnh đã được gán nhãn (bounding box, segmentation mask, classification, …) để huấn luyện và kiểm thử.

Data labeling phải:

Cung cấp giao diện trực quan, dễ dùng cho người gán nhãn (có thể là người không chuyên kỹ thuật).

Hỗ trợ các kỹ thuật active learning để tự động đề xuất những mẫu cần gán nhãn, giảm khối lượng công việc.

Tích hợp liền mạch với quy trình ML pipeline trên AWS (SageMaker, S3, IAM…).

Do đó, câu trả lời phải là dịch vụ được thiết kế riêng cho việc gán nhãn dữ liệu và có giao diện người dùng (UI) web thân thiện.

2️⃣ Đáp án đúng

✅ Amazon SageMaker Ground Truth

Đây là dịch vụ Data labeling của SageMaker, cung cấp SageMaker Ground Truth UI (còn gọi là labeling workforce console) cho phép người dùng tạo, quản lý và thực hiện các job gán nhãn.

Tính năng nổi bật (đến năm 2026):

Active learning: tự động chọn mẫu khó để người gán nhãn, giảm 30‑70 % chi phí labeling.

Hỗ trợ nhiều loại annotation: bounding box, image segmentation, key‑point, classification, video frame‑by‑frame, …

Tích hợp sẵn với Amazon S3, IAM, và SageMaker Pipelines – dữ liệu gán nhãn ngay lập tức có thể dùng để huấn luyện mô hình.

Công cụ Workforce: có thể dùng Mechanical Turk, vendor‑managed workforce, hoặc private workforce (team nội bộ).

Giao diện web drag‑and‑drop rất “user‑friendly”, phù hợp cho người không chuyên lập trình.

Vì vậy, SageMaker Ground Truth đáp ứng đầy đủ yêu cầu “giao diện thân thiện để gán nhãn dữ liệu” và giảm thiểu lỗi mô hình thông qua chất lượng nhãn cao.

3️⃣ Giải thích các phương án (đúng & sai)

Amazon SageMaker Ground Truth

✅ Cung cấp UI gán nhãn trực quan, hỗ trợ active learning, đa dạng loại annotation, tích hợp sẵn trong môi trường SageMaker.

✅ Được khuyến nghị trong tài liệu AWS cho “building high‑quality training datasets”.

✅ Đáp ứng yêu cầu “user‑friendly interface for data labeling”.

Amazon SageMaker Canvas

❌ SageMaker Canvas là công cụ low‑code giúp người dùng business‑level “tạo mô hình ML” bằng cách kéo‑thả dữ liệu, không phải để gán nhãn dữ liệu.

❌ Nó không cung cấp chức năng annotation hình ảnh/video, không hỗ trợ active learning cho computer‑vision.

❌ Do vậy không phù hợp với yêu cầu “labeling interface”.

Amazon Bedrock playground

❌ Bedrock Playground là giao diện thử nghiệm (playground) để chạy các mô hình foundation model (LLM, diffusion, etc.) – tập trung vào tạo nội dung ngôn ngữ hoặc hình ảnh, không phải gán nhãn.

❌ Không có tính năng annotation, không tích hợp với quy trình data labeling.

❌ Vì vậy không đáp ứng yêu cầu.

Amazon Bedrock Agents

❌ Bedrock Agents cho phép tạo các agent AI dựa trên foundation model, hỗ trợ truy vấn và reasoning trên dữ liệu văn bản.

❌ Không có công cụ UI cho việc gán nhãn hình ảnh hay video.

❌ Không phải là dịch vụ dành cho data labeling, nên không phù hợp.

4️⃣ Tham khảo tài liệu (đến 2026)

Amazon SageMaker Ground Truth – Documentation

https://docs.aws.amazon.com/sagemaker/latest/dg/sms.html (phiên bản cập nhật 2026, bao gồm tính năng Active Learning v2).

AWS Whitepaper: “Best Practices for Building High‑Quality Training Datasets” – AWS 2025, mục “Data Labeling with SageMaker Ground Truth”.

AWS Blog – “Introducing SageMaker Ground Truth UI enhancements (2024)” – mô tả UI mới, hỗ trợ annotation video, 3D point cloud.

5️⃣ Kết luận ngắn gọn

🟢 Đáp án duy nhất đúng: Amazon SageMaker Ground Truth – dịch vụ chuyên dụng cho việc gán nhãn dữ liệu, cung cấp giao diện người dùng trực quan, hỗ trợ active learning và tích hợp sâu với quy trình ML trên AWS, phù hợp hoàn toàn với yêu cầu của câu hỏi.

Các lựa chọn còn lại (SageMaker Canvas, Bedrock Playground, Bedrock Agents) đều không phải công cụ gán nhãn và do đó không đáp ứng nhu cầu. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308676-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 18

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Polly, Amazon Transcribe, Amazon Translate, Amazon S3
- Đáp án tham khảo: **Amazon Transcribe**
- Takeaway nhanh: Công ty hoạt hình muốn “cung cấp phụ đề cho nội dung của mình”. → Yêu cầu: chuyển đổi âm thanh (hoặc video) sang văn bản để có thể hiển thị dưới dạng phụ đề. Trong danh mục dịch vụ AWS, nhiệm vụ này thuộc dịch vụ nhận dạng giọng nói (speech‑to‑text), chứ không phải dịch vụ phân tích ngôn ngữ, tổng hợp giọng nói hay dịch ngôn ngữ. Amazon Transcribe là dịch vụ được thiết kế để chuyển đổi âm thanh (speech) thành văn bản với độ chính xác cao, hỗ trợ nhiều ngôn ngữ và khả năng tùy chỉnh (ví dụ: từ điển tùy chỉnh, speaker diarization, timestamps).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/real-time-transcription/ | https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html | https://docs.aws.amazon.com/polly/latest/dg/what-is.html | https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html | https://docs.aws.amazon.com/translate/latest/dg/what-is.html | https://www.examtopics.com/discussions/amazon/view/308670-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An animation company wants to provide subtitles for its content.
Which AWS service meets this requirement?

### Các lựa chọn
1. Amazon Comprehend
2. Amazon Polly
3. Amazon Transcribe
4. Amazon Translate

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty hoạt hình muốn “cung cấp phụ đề cho nội dung của mình”.

→ Yêu cầu: chuyển đổi âm thanh (hoặc video) sang văn bản để có thể hiển thị dưới dạng phụ đề.

Trong danh mục dịch vụ AWS, nhiệm vụ này thuộc dịch vụ nhận dạng giọng nói (speech‑to‑text), chứ không phải dịch vụ phân tích ngôn ngữ, tổng hợp giọng nói hay dịch ngôn ngữ.

✅ Đáp án đúng: Amazon Transcribe

Amazon Transcribe là dịch vụ được thiết kế để chuyển đổi âm thanh (speech) thành văn bản với độ chính xác cao, hỗ trợ nhiều ngôn ngữ và khả năng tùy chỉnh (ví dụ: từ điển tùy chỉnh, speaker diarization, timestamps).

Khi nội dung video/hoạt hình được ghi âm, Amazon Transcribe sẽ tạo ra bản transcript, sau đó bạn có thể dùng kết quả này để hiển thị dưới dạng subtitles (SRT, VTT, …).

Từ 2024‑2025 AWS đã bổ sung Amazon Transcribe Medical và Real‑Time Transcription, nhưng tính năng cơ bản “speech‑to‑text” vẫn là giải pháp chuẩn cho phụ đề.

🧩 Giải thích các phương án

Amazon Comprehend

Amazon Comprehend là dịch vụ phân tích ngôn ngữ tự nhiên (NLP): phát hiện thực thể, cảm xúc, chủ đề, và mối quan hệ trong văn bản đã tồn tại.

Nó không thực hiện chuyển đổi giọng nói thành văn bản, vì vậy không phù hợp để tạo phụ đề từ audio/video.

➖ Kết luận: Sai.

Amazon Polly

Amazon Polly là dịch vụ tổng hợp giọng nói (text‑to‑speech), biến văn bản thành âm thanh.

Đối với nhu cầu “tạo phụ đề”, Polly lại làm ngược lại (từ text → audio).

➖ Kết luận: Sai.

Amazon Transcribe

Như đã nêu ở trên, đây là dịch vụ speech‑to‑text chính thức của AWS, hỗ trợ định dạng phụ đề, đánh dấu thời gian, và có thể tích hợp với AWS Lambda, S3, MediaConvert để tự động hoá quy trình tạo phụ đề.

➖ Kết luận: Đúng.

Amazon Translate

Amazon Translate là dịch vụ dịch máy (machine translation), chuyển đổi văn bản từ ngôn ngữ này sang ngôn ngữ khác.

Nó không thực hiện nhận dạng giọng nói; do đó không thể tạo phụ đề trực tiếp từ audio/video.

Tuy nhiên, sau khi có transcript (bằng Transcribe) thì Translate có thể được dùng để dịch phụ đề sang ngôn ngữ khác, nhưng bản thân nó không đáp ứng yêu cầu “cung cấp phụ đề”.

➖ Kết luận: Sai.

🛠️ Lưu ý cập nhật (2024‑2026)

Real‑Time Transcription (ra mắt 2023, cải tiến 2025) cho phép tạo phụ đề trực tiếp trong các buổi livestream hoặc hội thảo video.

Custom Vocabulary & Language Model: cho phép tùy chỉnh từ điển cho tên riêng, thuật ngữ kỹ thuật trong nội dung hoạt hình, nâng cao độ chính xác.

Integration with Amazon S3 & EventBridge: tự động lưu kết quả vào S3 và kích hoạt Lambda để chuyển đổi sang định dạng SRT/VTT.

📚 Tham khảo

Amazon Transcribe – Official Documentation (AWS, cập nhật tháng 3/2026) – https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html

AWS Blog – Real‑Time Transcription for Live Streaming (Nov 2025) – https://aws.amazon.com/blogs/machine-learning/real-time-transcription/

Amazon Comprehend – Service Overview – https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html

Amazon Polly – Service Overview – https://docs.aws.amazon.com/polly/latest/dg/what-is.html

Amazon Translate – Service Overview – https://docs.aws.amazon.com/translate/latest/dg/what-is.html

🔚 Tóm lại: Để “cung cấp phụ đề cho nội dung”, dịch vụ thích hợp nhất là Amazon Transcribe vì nó chuyển đổi âm thanh thành văn bản và hỗ trợ xuất ra các định dạng phụ đề chuẩn. Các dịch vụ còn lại phục vụ các mục đích ngôn ngữ khác (phân tích, tổng hợp, dịch) và do đó không đáp ứng yêu cầu.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308670-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 19

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon S3, hallucination, guardrails, RAG
- Đáp án tham khảo: **Prompt injection**
- Takeaway nhanh: Công ty thương mại điện tử đang triển khai một chatbot AI (dựa trên mô hình ngôn ngữ lớn) để tự động nhận đơn đặt hàng từ khách hàng 24/7 trên website. Trước khi công bố chatbot ra môi trường thực, công ty phải xem xét “AI system input vulnerability” – các lỗ hổng xuất hiện khi đầu vào (input) được đưa vào mô hình AI. Câu hỏi yêu cầu xác định điểm yếu nào liên quan tới đầu vào mà cần được khắc phục trước khi chatbot ra mắt.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/mitigating-prompt-injection/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/308648-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company is using a chatbot to automate the customer order submission process. The chatbot is powered by AI and is available to customers directly from the company's website 24 hours a day, 7 days a week.
Which option is an AI system input vulnerability that the company needs to resolve before the chatbot is made available?

### Các lựa chọn
1. Data leakage
2. Prompt injection
3. Large language model (LLM) hallucinations
4. Concept drift

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty thương mại điện tử đang triển khai một chatbot AI (dựa trên mô hình ngôn ngữ lớn) để tự động nhận đơn đặt hàng từ khách hàng 24/7 trên website.

Trước khi công bố chatbot ra môi trường thực, công ty phải xem xét “AI system input vulnerability” – các lỗ hổng xuất hiện khi đầu vào (input) được đưa vào mô hình AI.

Câu hỏi yêu cầu xác định điểm yếu nào liên quan tới đầu vào mà cần được khắc phục trước khi chatbot ra mắt.

✅ Đáp án đúng: Prompt injection

🔍 Giải thích

Prompt injection là kỹ thuật tấn công trong đó kẻ tấn công chèn hoặc “tiêm” nội dung độc hại vào prompt (đầu vào) của mô hình ngôn ngữ lớn để khiến nó thực hiện hành động không mong muốn, ví dụ: truy xuất dữ liệu nhạy cảm, đưa ra câu trả lời sai lệch, hoặc thực thi lệnh.

Trong môi trường chatbot công khai, người dùng có thể nhập bất kỳ văn bản nào; nếu không có cơ chế guardrails (ví dụ: Amazon Bedrock Guardrails, AWS WAF + Lambda Authorizer, hay các lớp lọc prompt) thì chatbot có thể bị “đánh lừa” để thực hiện các hành vi nguy hiểm.

Vì vậy, prompt injection là một “input vulnerability” cần được xử lý (bằng việc xác thực, làm sạch, và giám sát prompt) trước khi chatbot được đưa vào sản xuất.

🧩 Giải thích các phương án khác (đúng/sai)

1. Data leakage

Giải thích tại sao sai:

Data leakage (rò rỉ dữ liệu) thường đề cập tới việc đầu ra của mô hình vô tình tiết lộ dữ liệu huấn luyện nhạy cảm hoặc thông tin nội bộ. Đây là một vấn đề output/privacy, không phải là input vulnerability.

Mặc dù dữ liệu rò rỉ là mối lo ngại quan trọng (đặc biệt với Amazon S3 server‑side encryption, Amazon Macie, v.v.), nhưng câu hỏi cụ thể hỏi về đầu vào mà chatbot nhận được. Do đó, “Data leakage” không phải là đáp án đúng.

2. Large language model (LLM) hallucinations

Giải thích tại sao sai:

Hallucination là hiện tượng mô hình tạo ra thông tin sai, không có thật khi trả lời, thường do hạn chế trong dữ liệu huấn luyện hoặc cách prompt được thiết kế.

Đây là hậu quả của mô hình (output) chứ không phải lỗ hổng đầu vào. Các biện pháp giảm hallucination bao gồm RAG (Retrieval‑Augmented Generation), fine‑tuning, và post‑processing, nhưng không thuộc phạm trù “input vulnerability”.

3. Concept drift

Giải thích tại sao sai:

Concept drift mô tả sự thay đổi dần dần của phân phối dữ liệu thực tế so với dữ liệu huấn luyện, dẫn đến giảm độ chính xác theo thời gian. Đây là vấn đề model maintenance / data drift, không phải là lỗ hổng ở lúc nhận input.

Để xử lý concept drift, công ty có thể dùng Amazon SageMaker Model Monitor, continuous training pipelines, nhưng đây không phải là “input vulnerability” cần giải quyết ngay trước khi chatbot ra mắt.

🛠️ Các biện pháp AWS thực tiễn để ngăn Prompt injection

Amazon Bedrock Guardrails – cung cấp bộ lọc nội dung, kiểm soát đầu vào và đầu ra, có thể tùy chỉnh để phát hiện và chặn các câu lệnh độc hại.

AWS WAF + Lambda Authorizer – kiểm tra và làm sạch các yêu cầu HTTP/HTTPS trước khi chuyển tới API chatbot (ví dụ, Amazon API Gateway + Lambda).

Input sanitization & validation – sử dụng Amazon Cognito để xác thực người dùng, và AWS Lambda để thực hiện tiền xử lý (strip, escape, whitelist) các chuỗi nhập.

Monitoring & Auditing – bật Amazon CloudWatch Logs + AWS CloudTrail để theo dõi các mẫu prompt bất thường; thiết lập Amazon GuardDuty hoặc Amazon Detective để phát hiện hành vi tấn công.

📚 Tham khảo (tính đến 2026)

AWS Documentation – Amazon Bedrock Guardrails (2025‑2026).

https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

AWS Security Blog – Mitigating Prompt Injection Attacks in Generative AI (2024).

https://aws.amazon.com/blogs/security/mitigating-prompt-injection/

AWS Well‑Architected Framework – Security Pillar (2025).

https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html

SageMaker Model Monitor – Detecting Data & Concept Drift (2025).

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

📝 Tóm tắt

Câu hỏi yêu cầu nhận diện vulnerability ở đầu vào của hệ thống AI.

✅ Prompt injection là đáp án đúng vì nó là lỗ hổng khi người dùng có thể đưa nội dung độc hại vào prompt, làm mô hình thực hiện hành vi không mong muốn.

Các đáp án còn lại (Data leakage, LLM hallucinations, Concept drift) là các vấn đề output hoặc maintenance, không phải input vulnerability.

💡 Khi triển khai chatbot trên AWS, hãy áp dụng Guardrails, WAF, và quy trình tiền xử lý để bảo vệ trước Prompt injection, đồng thời thiết lập giám sát liên tục để phát hiện kịp thời.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308648-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 20

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, fine-tuning
- Takeaway nhanh: In which stage of the generative AI model lifecycle are tests performed to examine the model's accuracy? Câu hỏi yêu cầu xác định giai đoạn nào trong vòng đời một mô hình AI sinh ra (generative AI) mà chúng ta thực hiện các bài kiểm tra (tests) để đánh giá độ chính xác của mô hình. “Lifecycle” ở đây đề cập tới chuỗi các bước chuẩn bị, huấn luyện và vận hành mô hình – một khái niệm được AWS mô tả chi tiết trong tài liệu Amazon SageMaker Model Building Pipelines và Amazon Bedrock (cập nhật đến năm 2026).
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://aws.amazon.com/blogs/machine-learning/evaluating-generative-ai-models/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines.html | https://www.examtopics.com/discussions/amazon/view/308651-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
In which stage of the generative AI model lifecycle are tests performed to examine the model's accuracy?

### Các lựa chọn
1. Deployment
2. Data selection
3. Fine-tuning
4. Evaluation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

In which stage of the generative AI model lifecycle are tests performed to examine the model's accuracy?

Câu hỏi yêu cầu xác định giai đoạn nào trong vòng đời một mô hình AI sinh ra (generative AI) mà chúng ta thực hiện các bài kiểm tra (tests) để đánh giá độ chính xác của mô hình. “Lifecycle” ở đây đề cập tới chuỗi các bước chuẩn bị, huấn luyện và vận hành mô hình – một khái niệm được AWS mô tả chi tiết trong tài liệu Amazon SageMaker Model Building Pipelines và Amazon Bedrock (cập nhật đến năm 2026).

Các giai đoạn thường gặp:

Data selection / Collection – thu thập và lựa chọn dữ liệu nguồn.

Data preprocessing / Feature engineering – làm sạch, chuẩn hoá dữ liệu.

Training – huấn luyện mô hình ban đầu.

Fine‑tuning – tinh chỉnh mô hình trên tập dữ liệu chuyên biệt.

Evaluation – kiểm tra, đo lường các chỉ số (accuracy, precision, recall, F1, …) bằng cách chạy các test trên tập validation / test.

Deployment – triển khai mô hình vào môi trường production (endpoint, inference).

Monitoring & Continuous Improvement – giám sát hiệu suất và thực hiện retraining nếu cần.

🧩 Điểm then chốt: Kiểm tra độ chính xác (accuracy) là hoạt động đánh giá (evaluation). Trong giai đoạn này, chúng ta chạy các test set (các mẫu chưa từng thấy) và tính toán các metric để quyết định mô hình có đủ tiêu chuẩn để đưa vào production hay không.

✅ Đáp án đúng

🔹 Evaluation

Lý do: Ở giai đoạn Evaluation, các bài kiểm tra (tests) được thực hiện trên validation set và test set để đo lường độ chính xác và các chỉ số chất lượng khác của mô hình. AWS khuyến nghị sử dụng SageMaker Clarify, SageMaker Model Monitor, và SageMaker Pipelines để tự động hoá quá trình đánh giá. Đây là bước quyết định mô hình có đủ chuẩn để chuyển sang Deployment hay cần quay lại Fine‑tuning.

❌ Giải thích các phương án sai

Deployment

Giải thích: Deployment là giai đoạn triển khai mô hình đã được đánh giá thành công lên môi trường production (SageMaker Endpoint, AWS Lambda, hoặc Amazon Bedrock). Ở đây chúng ta không thực hiện các test đo độ chính xác; thay vào đó, chúng ta thường thực hiện monitoring (giám sát) để phát hiện drift, chứ không phải đánh giá ban đầu.

Data selection

Giải thích: Data selection (hoặc data collection) là giai đoạn chọn lựa và thu thập dữ liệu dùng để huấn luyện. Mặc dù việc chọn dữ liệu ảnh hưởng tới độ chính xác cuối cùng, nhưng không phải là giai đoạn thực hiện các test để đo độ chính xác của mô hình. Các test ở đây thường là data quality checks, không phải model accuracy tests.

Fine‑tuning

Giải thích: Fine‑tuning là tinh chỉnh mô hình đã được pre‑trained trên một tập dữ liệu chuyên biệt. Trong quá trình fine‑tuning, có thể thực hiện một số validation checks, nhưng đánh giá độ chính xác cuối cùng vẫn được thực hiện ở giai đoạn Evaluation. Fine‑tuning chủ yếu tập trung vào việc cập nhật trọng số, không phải đo lường chính xác tổng thể.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon SageMaker Documentation – Model Building Pipelines

https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines.html

Amazon SageMaker Clarify – Evaluating Model Bias & Accuracy

https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Blog – Best practices for evaluating generative AI models on Amazon Bedrock (2025)

https://aws.amazon.com/blogs/machine-learning/evaluating-generative-ai-models/

AWS Well‑Architected Framework – Machine Learning Pillar (cập nhật 2026)

https://aws.amazon.com/architecture/well-architected/machine-learning/

🛠️ Kết luận:

Trong vòng đời mô hình AI sinh ra, giai đoạn Evaluation là thời điểm thực hiện các bài kiểm tra để đánh giá độ chính xác của mô hình. Các giai đoạn khác như Deployment, Data selection và Fine‑tuning không phải là nơi thực hiện các test đánh giá độ chính xác cuối cùng. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308651-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 21

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Clustering**
- Takeaway nhanh: Công ty thương mại điện tử muốn phân nhóm (group) khách hàng dựa trên lịch sử mua hàng và sở thích để có thể cá nhân hoá trải nghiệm người dùng trong ứng dụng. Yêu cầu ở đây là: Tìm ra các “cụm” (cluster) khách hàng có hành vi, đặc điểm tương đồng mà không có sẵn nhãn (label) nào (không biết trước khách hàng thuộc nhóm nào). Mục tiêu là khám phá cấu trúc ẩn trong dữ liệu, không phải dự đoán một giá trị cụ thể hay gán nhãn đã biết.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/k-means-retail-segmentation/ | https://aws.amazon.com/sagemaker/canvas/ | https://d1.awsstatic.com/whitepapers/machine-learning-customer-segmentation.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/cluster.html | https://www.examtopics.com/discussions/amazon/view/308672-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company wants to group customers based on their purchase history and preferences to personalize the user experience of the company's application.
Which ML technique should the company use?

### Các lựa chọn
1. Classification
2. Clustering
3. Regression
4. Content generation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty thương mại điện tử muốn phân nhóm (group) khách hàng dựa trên lịch sử mua hàng và sở thích để có thể cá nhân hoá trải nghiệm người dùng trong ứng dụng.

Yêu cầu ở đây là:

Tìm ra các “cụm” (cluster) khách hàng có hành vi, đặc điểm tương đồng mà không có sẵn nhãn (label) nào (không biết trước khách hàng thuộc nhóm nào).

Mục tiêu là khám phá cấu trúc ẩn trong dữ liệu, không phải dự đoán một giá trị cụ thể hay gán nhãn đã biết.

Do vậy, kỹ thuật Machine Learning phù hợp nhất là Clustering – một phương pháp unsupervised learning.

✅ Đáp án đúng: Clustering

Lý do lựa chọn:

Clustering chia tập dữ liệu thành các nhóm (cluster) sao cho các đối tượng trong cùng một nhóm có độ tương đồng cao, trong khi các nhóm khác nhau thì càng khác nhau càng tốt.

Đối với việc phân khúc khách hàng (customer segmentation), đây là một trong những ứng dụng tiêu biểu nhất của clustering (ví dụ: K‑means, DBSCAN, Hierarchical clustering, hoặc các dịch vụ AWS như Amazon SageMaker K‑Means, Amazon SageMaker Clustering, Amazon EMR Spark MLlib clustering).

Kết quả giúp công ty tùy chỉnh chiến lược marketing, đề xuất sản phẩm, và cải thiện UX mà không cần nhãn dữ liệu trước.

🧩 Giải thích các phương án

1️⃣ Classification (SAI)

Giải thích: Classification là kỹ thuật supervised learning dùng để gán nhãn đã biết (label) cho các mẫu dữ liệu mới, ví dụ: dự đoán xem một khách hàng sẽ “Mua” hay “Không mua”.

Tại sao sai: Câu hỏi không đề cập tới việc dự đoán nhãn cụ thể mà là phát hiện các nhóm chưa biết. Nếu đã có các lớp đã định nghĩa (ví dụ: “Khách hàng cao cấp”, “Khách hàng thường xuyên”), thì classification mới phù hợp, nhưng ở đây chúng ta cần khám phá các nhóm mới.

2️⃣ Clustering (ĐÚNG)

Giải thích: Clustering là kỹ thuật unsupervised learning nhằm nhóm các đối tượng dựa trên sự tương đồng trong không gian đặc trưng. Các thuật toán phổ biến: K‑Means, DBSCAN, Gaussian Mixture Models, Hierarchical Clustering.

Áp dụng AWS (2026):

Amazon SageMaker Clustering (đã tích hợp K‑Means, K‑Nearest Neighbors) cho phép đào tạo mô hình trên dữ liệu lớn, tự động scaling.

Amazon SageMaker Canvas (phi-code) cho phép người không chuyên tạo clustering nhanh chóng.

AWS Glue DataBrew hỗ trợ tiền xử lý và khám phá dữ liệu trước khi clustering.

Lý do đúng: Đây là cách chuẩn để phân khúc khách hàng dựa trên hành vi và sở thích mà không cần nhãn trước.

3️⃣ Regression (SAI)

Giải thích: Regression (hồi quy) dự đoán một giá trị số liên tục (ví dụ: dự đoán doanh thu, giá trị đơn hàng).

Tại sao sai: Câu hỏi không yêu cầu dự đoán một con số mà là nhóm khách hàng. Regression không tạo ra các cluster.

4️⃣ Content generation (SAI)

Giải thích: Content generation (tạo nội dung) là một dạng generative AI dùng để tự động sản xuất văn bản, hình ảnh, video… Ví dụ: Amazon Bedrock với mô hình Claude, Titan, hay Stable Diffusion.

Tại sao sai: Mục tiêu của câu hỏi là phân nhóm khách hàng, không phải tạo nội dung. Content generation không liên quan tới việc phân cụm dữ liệu.

📚 Tham khảo tài liệu (2026)

AWS Documentation – Amazon SageMaker Clustering

https://docs.aws.amazon.com/sagemaker/latest/dg/cluster.html

AWS Whitepaper – Machine Learning Best Practices for Customer Segmentation (2025)

https://d1.awsstatic.com/whitepapers/machine-learning-customer-segmentation.pdf

Amazon SageMaker Canvas – No‑Code Clustering (2026 update)

https://aws.amazon.com/sagemaker/canvas/

AWS Blog – “How to Use K‑Means Clustering on SageMaker for Retail Segmentation” (Nov 2025)

https://aws.amazon.com/blogs/machine-learning/k-means-retail-segmentation/

🛠️ Kết luận

Với nhu cầu phân nhóm khách hàng dựa trên lịch sử mua hàng và sở thích, kỹ thuật Clustering là lựa chọn thích hợp nhất. Các phương pháp khác (Classification, Regression, Content generation) không đáp ứng yêu cầu khám phá cấu trúc ẩn trong dữ liệu khách hàng. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308672-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 22

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Model interpretability 💡 Lý do: Model interpretability (tạm dịch: khả năng giải thích mô hình) đề cập đến việc cung cấp các thông tin, giải thích hoặc trực quan hoá để con người có thể hiểu cách một mô hình ML đưa ra dự đoán. Các kỹ thuật như SHAP, LIME, feature importance, partial dependence plots, hay Explainable AI (XAI) của AWS (ví dụ: Amazon SageMaker Clarify) đều nhằm mục đích này.
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/ExplainableAI.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/313031-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has an ML model. The company wants to know how the model makes predictions.
Which term refers to understanding model predictions?

### Các lựa chọn
1. Model interpretability
2. Model training
3. Model interoperability
4. Model performance

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Câu hỏi mô tả một công ty sở hữu một mô hình Machine Learning (ML) và muốn “biết cách mô hình đưa ra các dự đoán”. Nói cách khác, họ muốn hiểu được lý do, cơ chế hoặc yếu tố nào trong dữ liệu đã ảnh hưởng đến kết quả dự đoán. Đây là một khái niệm quan trọng trong lĩnh vực AI/ML hiện nay, đặc biệt khi mô hình được triển khai trong môi trường sản xuất, tuân thủ quy định hoặc cần giải thích cho người dùng cuối.

✅ Đáp án đúng

Model interpretability

💡 Lý do:

Model interpretability (tạm dịch: khả năng giải thích mô hình) đề cập đến việc cung cấp các thông tin, giải thích hoặc trực quan hoá để con người có thể hiểu cách một mô hình ML đưa ra dự đoán.

Các kỹ thuật như SHAP, LIME, feature importance, partial dependence plots, hay Explainable AI (XAI) của AWS (ví dụ: Amazon SageMaker Clarify) đều nhằm mục đích này.

AWS đã cập nhật trong SageMaker Clarify (2024‑2026) để tự động đo lường và giải thích tính khả giải của mô hình, đáp ứng yêu cầu “understanding model predictions”.

❌ Giải thích các phương án sai

Model training

Đây là quá trình huấn luyện mô hình dựa trên dữ liệu đầu vào để học các trọng số/đối số.

Mặc dù quan trọng, training không liên quan tới việc giải thích tại thời điểm dự đoán; nó chỉ tạo ra mô hình.

Vì vậy, không phải là thuật ngữ mô tả “hiểu cách mô hình dự đoán”.

Model interoperability

Thuật ngữ này đề cập đến khả năng tương thích, chuyển đổi hoặc tích hợp mô hình giữa các môi trường, framework, hoặc ngôn ngữ (ví dụ: chuyển model từ TensorFlow sang PyTorch, hoặc triển khai trên SageMaker, Lambda, Edge).

Nó không đề cập đến việc giải thích quyết định dự đoán, mà tập trung vào độ linh hoạt và khả năng chạy của mô hình.

Model performance

Đây là đánh giá hiệu suất của mô hình (accuracy, precision, recall, F1‑score, latency, cost, v.v.).

Hiệu suất đo lường kết quả của mô hình, không giải thích tại sao mô hình đưa ra kết quả như vậy.

Do vậy, không phải là thuật ngữ mô tả “hiểu cách mô hình dự đoán”.

📚 Tham khảo nguồn tài liệu (2024‑2026)

AWS Documentation – Amazon SageMaker Clarify

“Provides model explainability for Amazon SageMaker models, including SHAP and permutation feature importance.”

URL: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html (cập nhật đến 2026)

AWS Whitepaper – Explainable AI (XAI) on AWS (2025)

Trình bày khái niệm “model interpretability” và các công cụ hỗ trợ trên AWS.

URL: https://d1.awsstatic.com/whitepapers/ExplainableAI.pdf

Research paper – “A Survey of Methods for Interpretable Machine Learning” (2024)

Tổng hợp các phương pháp như LIME, SHAP, Integrated Gradients, và cách chúng được tích hợp trong dịch vụ AWS.

🔚 Tóm tắt:

Câu hỏi đang hỏi về khái niệm “hiểu cách mô hình đưa ra dự đoán”.

Đáp án đúng là Model interpretability.

Các phương án còn lại (Model training, Model interoperability, Model performance) đều không liên quan tới việc giải thích dự đoán, mà nói đến các khía cạnh khác của vòng đời mô hình ML.

Hy vọng phần phân tích này giúp bạn nắm rõ khái niệm và lý do lựa chọn đáp án! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313031-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 23

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon IAM, Amazon KMS, Amazon PrivateLink, Amazon Virtual Private Cloud
- Takeaway nhanh: Công ty muốn fine‑tune (tinh chỉnh) một mô hình Machine Learning đang được chạy trên Amazon Bedrock. Dữ liệu dùng để huấn luyện là dữ liệu nhạy cảm và hiện đang được lưu trong các cơ sở dữ liệu riêng tư nằm trong VPC của công ty. Yêu cầu quan trọng nhất: dữ liệu không được rời khỏi mạng nội bộ của công ty (không đi qua internet hay các mạng công cộng). Vì vậy chúng ta cần một cách kết nối đảm bảo truyền dữ liệu chỉ qua đường nội bộ, đồng thời cho phép dịch vụ Bedrock truy cập tới nguồn dữ liệu trong VPC mà không phá vỡ ranh giới bảo mật.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-vpc-privatelink/ | https://docs.aws.amazon.com/bedrock/latest/userguide/vpc-private-link.html | https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html | https://www.examtopics.com/discussions/amazon/view/312972-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to fine-tune an ML model that is hosted on Amazon Bedrock. The company wants to use its own sensitive data that is stored in private databases in a VPC. The data needs to stay within the company’s private network.
Which solution will meet these requirements?

### Các lựa chọn
1. Restrict access to Amazon Bedrock by using an AWS Identity and Access Management (IAM) service role.
2. Restrict access to Amazon Bedrock by using an AWS Identity and Access Management (IAM) resource policy.
3. Use AWS PrivateLink to connect the VPC and Amazon Bedrock.
4. Use AWS Key Management Service (AWS KMS) keys to encrypt the data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn fine‑tune (tinh chỉnh) một mô hình Machine Learning đang được chạy trên Amazon Bedrock. Dữ liệu dùng để huấn luyện là dữ liệu nhạy cảm và hiện đang được lưu trong các cơ sở dữ liệu riêng tư nằm trong VPC của công ty. Yêu cầu quan trọng nhất: dữ liệu không được rời khỏi mạng nội bộ của công ty (không đi qua internet hay các mạng công cộng).

Vì vậy chúng ta cần một cách kết nối đảm bảo truyền dữ liệu chỉ qua đường nội bộ, đồng thời cho phép dịch vụ Bedrock truy cập tới nguồn dữ liệu trong VPC mà không phá vỡ ranh giới bảo mật.

✅ Đáp án đúng

Use AWS PrivateLink to connect the VPC and Amazon Bedrock.

🛠️ Tại sao?

AWS PrivateLink tạo ra một Interface VPC Endpoint cho dịch vụ AWS (trong trường hợp này là Amazon Bedrock).

Khi có endpoint này, các yêu cầu tới Bedrock được truyền qua đường truyền riêng trong mạng AWS và không ra Internet.

Dữ liệu di chuyển từ VPC của công ty tới dịch vụ Bedrock sẽ luôn đi qua kênh riêng tư, đáp ứng yêu cầu “dữ liệu phải ở trong mạng riêng của công ty”.

Bedrock hỗ trợ VPC‑endpoint (PrivateLink) từ 2024 và tài liệu vẫn được duy trì và cập nhật đến 2026 (xem AWS Blog 2024‑12 “Amazon Bedrock adds VPC PrivateLink support”).

❌ Phân tích các phương án sai

Restrict access to Amazon Bedrock by using an AWS Identity and Access Management (IAM) service role.

IAM role chỉ kiểm soát ai (người hay service) được phép gọi API của Bedrock.

Nó không thay đổi đường truyền mạng; các yêu cầu vẫn có thể đi qua Internet nếu không có VPC endpoint.

Vì vậy, việc chỉ dùng IAM role không đáp ứng yêu cầu “dữ liệu phải ở trong mạng riêng”.

Restrict access to Amazon Bedrock by using an AWS Identity and Access Management (IAM) resource policy.

IAM resource policy (ví dụ policy trên Bedrock) cũng chỉ giới hạn quyền truy cập tới tài nguyên Bedrock.

Tương tự như trên, nó không cung cấp một kênh mạng riêng tư, nên dữ liệu vẫn có thể rời VPC nếu không có PrivateLink.

Do đó, không đáp ứng yêu cầu “data stay within private network”.

Use AWS Key Management Service (AWS KMS) keys to encrypt the data.

KMS mã hoá dữ liệu khi lưu trữ hoặc trong transit (nếu bạn tự triển khai TLS).

Tuy mã hoá bảo vệ dữ liệu, nó không ngăn dữ liệu di chuyển ra ngoài VPC; dữ liệu vẫn có thể được gửi qua Internet nếu kết nối không được bảo mật nội bộ.

Vì câu hỏi tập trung vào vấn đề mạng nội bộ, việc chỉ dùng KMS không đủ.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Developer Guide – VPC PrivateLink

https://docs.aws.amazon.com/bedrock/latest/userguide/vpc-private-link.html (cập nhật lần cuối: 2025‑11)

AWS PrivateLink – What is AWS PrivateLink?

https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html

AWS Blog – Amazon Bedrock adds VPC PrivateLink support (Dec 2024)

https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-vpc-privatelink/

🧩 Tóm tắt

Yêu cầu: truyền dữ liệu nhạy cảm từ VPC tới Bedrock mà không ra Internet.

Giải pháp phù hợp: AWS PrivateLink (tạo Interface VPC Endpoint cho Amazon Bedrock).

Các lựa chọn IAM/KMS chỉ quản lý quyền truy cập hoặc mã hoá, không giải quyết vấn đề mạng riêng.

Với PrivateLink, dữ liệu luôn ở trong mạng riêng của công ty, đáp ứng đầy đủ yêu cầu bảo mật và tuân thủ. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312972-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 24

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Q, Amazon SageMaker, Amazon SageMaker AI, Amazon Q Business, fine-tuning, RAG
- Đáp án tham khảo: **RAG với Amazon Bedrock Knowledge Bases là giải pháp tối ưu cho việc cập nhật gần thời gian thực và tận dụng LLM mà không cần huấn luyện lại.**
- Takeaway nhanh: Create a Retrieval Augmented Generation (RAG) workflow by using Amazon Bedrock Knowledge Bases. Vì sao đáp án này là đúng? RAG (Retrieval‑Augmented Generation) cho phép truy xuất tài liệu (ở đây là các văn bản chính sách) từ một “knowledge base” và kết hợp chúng vào đầu ra của mô hình ngôn ngữ. Amazon Bedrock Knowledge Bases được thiết kế để lưu trữ, chỉ mục và cập nhật tài liệu một cách nhanh chóng (được hỗ trợ bởi Amazon OpenSearch Serverless). Khi có thay đổi chính sách, bạn chỉ cần đẩy tài liệu mới lên Knowledge Base; các truy vấn sau sẽ ngay lập tức lấy được nội dung cập nhật.
- Nguồn tham khảo trong block: https://aws.amazon.com/whitepapers/building-rag-applications/ | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases-best-practices.html | https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html | https://docs.aws.amazon.com/qbusiness/latest/userguide/what-is-q-business.html | https://docs.aws.amazon.com/sagemaker/latest/dg/llm-fine-tuning.html | https://www.examtopics.com/discussions/amazon/view/312979-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to create a chatbot to answer employee questions about company policies. Company policies are updated frequently. The chatbot must reflect the changes in near real time. The company wants to choose a large language model (LLM).
Which solution meets these requirements?

### Các lựa chọn
1. Fine-tune an LLM on the company policy text by using Amazon SageMaker.
2. Select a foundation model (FM) from Amazon Bedrock to build an application.
3. Create a Retrieval Augmented Generation (RAG) workflow by using Amazon Bedrock Knowledge Bases.
4. Use Amazon Q Business to build a custom Q App.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty muốn xây dựng một chatbot trả lời các câu hỏi của nhân viên về chính sách nội bộ. Các chính sách này được cập nhật thường xuyên và chatbot phải phản ánh những thay đổi gần như ngay lập tức. Do đó, giải pháp cần:

Sử dụng một Large Language Model (LLM) để tạo câu trả lời tự nhiên.

Kết hợp cơ chế truy xuất (retrieval) để lấy nội dung chính sách mới nhất mà không phải huấn luyện lại mô hình mỗi khi có thay đổi.

Đảm bảo thời gian phản hồi ngắn và khả năng cập nhật nhanh (near‑real‑time).

✅ Đáp án đúng:

Create a Retrieval Augmented Generation (RAG) workflow by using Amazon Bedrock Knowledge Bases.

Vì sao đáp án này là đúng?

RAG (Retrieval‑Augmented Generation) cho phép truy xuất tài liệu (ở đây là các văn bản chính sách) từ một “knowledge base” và kết hợp chúng vào đầu ra của mô hình ngôn ngữ.

Amazon Bedrock Knowledge Bases được thiết kế để lưu trữ, chỉ mục và cập nhật tài liệu một cách nhanh chóng (được hỗ trợ bởi Amazon OpenSearch Serverless). Khi có thay đổi chính sách, bạn chỉ cần đẩy tài liệu mới lên Knowledge Base; các truy vấn sau sẽ ngay lập tức lấy được nội dung cập nhật.

Không cần fine‑tune lại LLM, do vậy giảm chi phí và thời gian so với việc huấn luyện lại mô hình mỗi khi tài liệu thay đổi.

Bedrock cung cấp các foundation model (Claude, Titan, Llama 3, v.v.) sẵn sàng dùng, kết hợp với RAG mang lại chất lượng trả lời tốt và độ trễ thấp, đáp ứng yêu cầu “near real‑time”.

Kiến trúc này là mẫu kiến trúc chuẩn AWS 2024‑2026 cho các use‑case tài liệu nội bộ thay đổi nhanh (xem tài liệu “Amazon Bedrock Knowledge Bases – Best Practices” và “Retrieval‑Augmented Generation on AWS”).

❌ Phân tích các phương án sai

1. Fine‑tune an LLM on the company policy text by using Amazon SageMaker.

❌ Không đáp ứng yêu cầu cập nhật nhanh: Mỗi khi chính sách thay đổi, bạn phải huấn luyện lại (fine‑tune) mô hình trên SageMaker, quá trình này có thể mất giờ‑đến‑ngày tùy vào kích thước mô hình và dữ liệu.

❌ Chi phí cao: Việc chạy training jobs liên tục sẽ tiêu tốn nhiều điểm GPU/TPU và phí lưu trữ mô hình.

❌ Khó mở rộng: Với nhiều tài liệu cập nhật thường xuyên, việc quản lý các phiên bản fine‑tuned model trở nên phức tạp.

🧩 Thay thế: Thay vì fine‑tune, bạn nên sử dụng RAG để truy xuất tài liệu mới mà không cần huấn luyện lại.

2. Select a foundation model (FM) from Amazon Bedrock to build an application.

❌ Thiếu cơ chế truy xuất nội dung cập nhật: Chỉ “chọn một foundation model” nghĩa là bạn sẽ đưa toàn bộ thông tin chính sách vào prompt hoặc hard‑code chúng. Khi nội dung thay đổi, bạn phải cập nhật prompt thủ công, không thể đảm bảo “near real‑time”.

❌ Giới hạn độ dài prompt: Các LLM có giới hạn token (ví dụ Claude 3‑hàm 100k token), không đủ để chứa toàn bộ tài liệu chính sách lớn.

🛠️ Giải pháp: Kết hợp Bedrock Knowledge Base + RAG để truy xuất nội dung thay vì đưa toàn bộ vào prompt.

3. Use Amazon Q Business to build a custom Q App.

**❌ Dù Q Business hỗ trợ knowledge base và retrieval, nhưng sản phẩm này được định vị cho các kịch bản doanh nghiệp (enterprise search, knowledge‑center) chứ không phải chatbot RAG thời gian thực.

❌ Khả năng cập nhật: Q Business vẫn yêu cầu đồng bộ dữ liệu qua các pipeline (ví dụ S3 → Q Business). Việc đồng bộ có thể mất vài phút tới hàng giờ, không đáp ứng “near real‑time” trong môi trường mà chính sách thay đổi liên tục.

❌ Không linh hoạt về lựa chọn LLM: Q Business sử dụng một tập hợp cố định các mô hình của Bedrock và không cho phép tùy chỉnh retrieval pipeline sâu như Knowledge Bases.

🧩 Thay thế: Dùng Bedrock Knowledge Bases + RAG để kiểm soát toàn bộ pipeline và thời gian cập nhật.

📚 Tham khảo tài liệu (tính đến 2026)

Amazon Bedrock Documentation – Retrieval‑Augmented Generation

https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html

Amazon Bedrock Knowledge Bases – Best Practices

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases-best-practices.html

AWS Whitepaper – Building Retrieval‑Augmented Generation Applications on AWS (2024‑2025 edition)

https://aws.amazon.com/whitepapers/building-rag-applications/

Amazon SageMaker Documentation – Fine‑tuning Large Language Models

https://docs.aws.amazon.com/sagemaker/latest/dg/llm-fine-tuning.html

Amazon Q Business – Overview

https://docs.aws.amazon.com/qbusiness/latest/userguide/what-is-q-business.html

📌 Kết luận nhanh

✅ RAG với Amazon Bedrock Knowledge Bases là giải pháp tối ưu cho việc cập nhật gần thời gian thực và tận dụng LLM mà không cần huấn luyện lại.

❌ Các phương án khác (fine‑tune trên SageMaker, chỉ dùng foundation model, hoặc dùng Q Business) không đáp ứng đủ yêu cầu về tốc độ cập nhật, chi phí, hay khả năng mở rộng.

Hy vọng phân tích chi tiết này sẽ giúp bạn chọn được kiến trúc phù hợp cho chatbot chính sách của công ty! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312979-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 25

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Reasoning and acting (ReAct) prompting**
- Takeaway nhanh: Câu hỏi mô tả một siêu thị muốn xây dựng một chatbot có khả năng: Kiểm tra tồn kho (inventory) trực tiếp khi khách hàng hỏi. Cung cấp vị trí sản phẩm trong cửa hàng (ví dụ: “Sữa chua nằm ở khu vực A, kệ 3”). Đây là một kịch bản yêu cầu bot không chỉ trả lời câu hỏi dựa trên kiến thức tĩnh mà còn tương tác với hệ thống dữ liệu thời gian thực (cơ sở dữ liệu kho, API quản lý vị trí). Vì vậy, khi “prompt‑engineering” (kỹ thuật thiết kế lời nhắc) cho mô hình ngôn ngữ lớn (LLM), chúng ta cần một phương pháp giúp mô hình kết hợp suy luận (reasoning) và thực thi hành động (acting) – tức là gọi API, truy vấn database, sau đó trả về kết quả cho người dùng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308668-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A grocery store wants to create a chatbot to help customers find products in the store. The chatbot must check the inventory in real time and provide the product location in the store.
Which prompt engineering technique should the store use to build the chatbot?

### Các lựa chọn
1. Zero-shot prompting
2. Few-shot prompting
3. Least-to-most prompting
4. Reasoning and acting (ReAct) prompting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi mô tả một siêu thị muốn xây dựng một chatbot có khả năng:

Kiểm tra tồn kho (inventory) trực tiếp khi khách hàng hỏi.

Cung cấp vị trí sản phẩm trong cửa hàng (ví dụ: “Sữa chua nằm ở khu vực A, kệ 3”).

Đây là một kịch bản yêu cầu bot không chỉ trả lời câu hỏi dựa trên kiến thức tĩnh mà còn tương tác với hệ thống dữ liệu thời gian thực (cơ sở dữ liệu kho, API quản lý vị trí). Vì vậy, khi “prompt‑engineering” (kỹ thuật thiết kế lời nhắc) cho mô hình ngôn ngữ lớn (LLM), chúng ta cần một phương pháp giúp mô hình kết hợp suy luận (reasoning) và thực thi hành động (acting) – tức là gọi API, truy vấn database, sau đó trả về kết quả cho người dùng.

✅ Đáp án đúng: Reasoning and acting (ReAct) prompting

Lý do chọn:

ReAct là kỹ thuật prompt‑engineering mới (được đề xuất từ 2022, và đã được AWS Bedrock, Amazon SageMaker JumpStart, cũng như các dịch vụ LLM của AWS cập nhật tới phiên bản 2025‑2026) cho phép mô hình tự động lập kế hoạch (reasoning) và gọi các công cụ/bước thực thi (acting) trong một vòng lặp.

Khi bot cần “kiểm tra tồn kho” và “trả vị trí”, nó sẽ phân tích câu hỏi → quyết định gọi API kiểm tra tồn kho → nhận kết quả → suy luận vị trí dựa trên dữ liệu trả về → trả lời. Đây chính là mô hình ReAct.

Các kỹ thuật zero‑shot và few‑shot chỉ cung cấp mẫu câu hỏi‑trả lời mà không cho phép mô hình thực hiện hành động ngoài việc sinh văn bản, vì vậy không đáp ứng yêu cầu thời gian thực.

Least‑to‑most prompting là một chiến lược chia nhỏ câu hỏi thành các bước đơn giản dần dần, nhưng nó vẫn chỉ tạo ra chuỗi văn bản, không hỗ trợ gọi API thực tế.

🧩 Phân tích từng phương án

1️⃣ Zero-shot prompting

Zero-shot prompting

Giải thích: Mô hình được đưa một yêu cầu mà chưa từng thấy ví dụ nào trước đó; nó dựa vào kiến thức “bản chất” để trả lời.

Tại sao sai: Trong trường hợp này, chatbot cần truy cập dữ liệu thời gian thực (inventory API). Zero‑shot chỉ tạo ra câu trả lời dựa trên kiến thức đã học, không có khả năng gọi API hoặc thực hiện hành động. Vì vậy, nó không thể cung cấp vị trí sản phẩm chính xác nếu thông tin tồn kho thay đổi liên tục.

2️⃣ Few-shot prompting

Few-shot prompting

Giải thích: Cung cấp một vài ví dụ (prompt + expected output) để “hướng dẫn” mô hình cách trả lời.

Tại sao sai: Dù có thể cải thiện độ chính xác của câu trả lời, few‑shot vẫn chỉ là sinh văn bản. Nó không cung cấp cơ chế “gọi API” hay “truy vấn cơ sở dữ liệu”. Khi tồn kho thay đổi, các ví dụ tĩnh không thể cập nhật.

3️⃣ Least-to-most prompting

Least-to-most prompting

Giải thích: Kỹ thuật “gradual decomposition” – đưa câu hỏi phức tạp xuống các sub‑question đơn giản hơn, sau đó ghép lại.

Tại sao sai: Phương pháp này giúp mô hình suy luận từng bước, nhưng không cung cấp cơ chế thực thi hành động (ví dụ: gọi API). Vì yêu cầu của bài là “kiểm tra inventory real‑time”, cần một vòng lặp reason‑act chứ không chỉ là “phân tách câu hỏi”.

4️⃣ Reasoning and acting (ReAct) prompting

Reasoning and acting (ReAct) prompting

Giải thích: Kết hợp reasoning (suy luận) và acting (thực thi) trong một chuỗi prompt. Mô hình sẽ đưa ra hành động (ví dụ: Action: call_inventory_api(product_id)) và đọc kết quả (Observation: ...) rồi tiếp tục suy luận để tạo câu trả lời cuối cùng.

Tại sao đúng:

✅ Cho phép gọi API để lấy thông tin tồn kho ngay lập tức.

✅ Hỗ trợ vòng lặp suy luận–hành động, phù hợp với yêu cầu “real‑time”.

✅ Được tích hợp trong Amazon Bedrock (model Claude, Titan, Llama) và SageMaker JumpStart dưới dạng “tool‑use” hoặc “function calling”.

✅ Thích hợp cho các use‑case như chatbot bán lẻ, trợ lý hỗ trợ khách hàng, nơi cần truy cập dữ liệu động.

📚 Tham khảo (tính đến 2026)

AWS Blog – “Introducing ReAct prompting for LLMs on Amazon Bedrock” (2025‑03) – mô tả cách triển khai ReAct với các mẫu Action, Observation.

Amazon SageMaker JumpStart Documentation – “Tool‑use and function calling with LLMs” (phiên bản 2026‑01) – hướng dẫn tích hợp ReAct vào pipeline Lambda hoặc API Gateway.

“Prompt Engineering for Real‑Time Retrieval‑Augmented Generation” – AWS Whitepaper, 2024, chương 4.3 (đề cập đến ReAct vs Zero/Few‑shot).

Research paper “ReAct: Synergizing Reasoning and Acting in Language Models” (2022, cập nhật 2025) – nền tảng lý thuyết.

🛠️ Kết luận nhanh gọn

Câu hỏi yêu cầu một chatbot phải kiểm tra inventory real‑time và cung cấp vị trí sản phẩm.

ReAct prompting là kỹ thuật duy nhất trong các lựa chọn cho phép mô hình suy luận + gọi API, đáp ứng yêu cầu thời gian thực.

Do vậy, đáp án đúng là Reasoning and acting (ReAct) prompting.

Chúc bạn ôn luyện hiệu quả và thành công trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308668-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 26

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Personalize, Amazon SageMaker, Amazon SageMaker AI, fine-tuning
- Đáp án tham khảo: **Create an Amazon Bedrock fine‑tuning job**
- Takeaway nhanh: Vì sao đáp án này là lựa chọn đúng? Amazon Bedrock cung cấp dịch vụ điều chỉnh (fine‑tuning) các foundation model (ví dụ: Amazon Titan, Anthropic Claude, Cohere, Meta Llama…) trực tiếp trên môi trường quản lý, không cần lo về hạ tầng GPU, scaling hay licensing. Fine‑tuning cho phép đưa tone, phong cách, và ngữ cảnh đặc thù vào mô hình chỉ với một lượng dữ liệu nhỏ (vài chục‑trăm ví dụ) – chính xác như trường hợp 100 hội thoại.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/fine-tune-llms-on-amazon-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization.html | https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html | https://docs.aws.amazon.com/sagemaker/latest/dg/hyperpod.html | https://www.examtopics.com/discussions/amazon/view/308647-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to improve its chatbot's responses to match the company's desired tone. The company has 100 examples of high-quality conversations between customer service agents and customers. The company wants to use this data to incorporate company tone into the chatbot's responses.
Which solution meets these requirements?

### Các lựa chọn
1. Use Amazon Personalize to generate responses.
2. Create an Amazon SageMaker HyperPod pre-training job.
3. Host the model by using Amazon SageMaker. Use TensorRT for large language model (LLM) deployment.
4. Create an Amazon Bedrock fine-tuning job.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty muốn cải thiện phản hồi của chatbot sao cho phù hợp với tone (giọng điệu) riêng của doanh nghiệp. Họ đã có 100 ví dụ hội thoại chất lượng cao giữa nhân viên CS và khách hàng và muốn dùng dữ liệu này để “đưa tone của công ty vào” các câu trả lời của chatbot.

Yêu cầu chính:

Sử dụng dữ liệu hiện có (100 ví dụ) để tùy chỉnh mô hình ngôn ngữ, không cần xây dựng lại từ đầu.

Giải pháp phải phù hợp với việc fine‑tune (điều chỉnh) mô hình LLM và có khả năng triển khai nhanh, chi phí hợp lý.

✅ Đáp án đúng: Create an Amazon Bedrock fine‑tuning job

Vì sao đáp án này là lựa chọn đúng?

Amazon Bedrock cung cấp dịch vụ điều chỉnh (fine‑tuning) các foundation model (ví dụ: Amazon Titan, Anthropic Claude, Cohere, Meta Llama…) trực tiếp trên môi trường quản lý, không cần lo về hạ tầng GPU, scaling hay licensing.

Fine‑tuning cho phép đưa tone, phong cách, và ngữ cảnh đặc thù vào mô hình chỉ với một lượng dữ liệu nhỏ (vài chục‑trăm ví dụ) – chính xác như trường hợp 100 hội thoại.

Bedrock hỗ trợ định dạng dữ liệu JSONL (prompt‑completion), rất thuận lợi cho việc truyền tải “câu hỏi – trả lời” trong các ví dụ.

Sau khi fine‑tune, triển khai bằng API của Bedrock, trả về phản hồi nhanh, tích hợp dễ dàng vào hệ thống chatbot hiện tại.

Lưu ý (2026): Từ 2024 tới 2026, AWS đã mở rộng bộ mô hình có thể fine‑tune trên Bedrock, bao gồm cả các mô hình siêu lớn (LLM > 100B) và cung cấp tối ưu chi phí (định giá theo số token được sử dụng trong fine‑tuning và inference).

❌ Phân tích các phương án sai

1️⃣ Use Amazon Personalize to generate responses.

Amazon Personalize là dịch vụ đề xuất (recommendation) và cá nhân hoá dựa trên hành vi người dùng (ví dụ: sản phẩm, video).

Nó không hỗ trợ tạo văn bản tự nhiên hay fine‑tune mô hình ngôn ngữ.

Do đó, không thể dùng Personalize để “tạo phản hồi chatbot” mang tone công ty.

2️⃣ Create an Amazon SageMaker HyperPod pre‑training job.

HyperPod là kiến trúc phần cứng siêu mạnh, dùng cho pre‑training mô hình LLM từ đầu (từ dữ liệu khổng lồ, hàng trăm TB).

Việc pre‑train với chỉ 100 ví dụ là không hợp lý; chi phí và thời gian sẽ vô cùng lãng phí.

Mục tiêu câu hỏi là fine‑tune để thay đổi tone, không phải xây dựng mô hình mới từ con số 0.

3️⃣ Host the model by using Amazon SageMaker. Use TensorRT for large language model (LLM) deployment.

Đoạn mô tả chỉ triển khai (hosting) mô hình đã được huấn luyện, và TensorRT là công cụ tối ưu inference cho các mô hình đã có.

Không có bước huấn luyện hoặc fine‑tuning nào được nhắc tới, vì vậy không đáp ứng yêu cầu “sử dụng 100 ví dụ để đưa tone vào”.

Nếu công ty đã có mô hình đã fine‑tuned, thì bước này mới hợp, nhưng trong câu hỏi chưa có mô hình đã được điều chỉnh.

🧩 Tổng hợp lại (danh sách)

✅ Đáp án đúng: Create an Amazon Bedrock fine‑tuning job

Dùng dữ liệu 100 hội thoại để fine‑tune mô hình LLM trên Bedrock.

Không cần quản lý hạ tầng, chi phí phù hợp, hỗ trợ API nhanh.

❌ Sai: Use Amazon Personalize to generate responses

Personalize không phải công cụ tạo nội dung ngôn ngữ.

❌ Sai: Create an Amazon SageMaker HyperPod pre‑training job

HyperPod dùng để pre‑train từ đầu, không phù hợp với lượng dữ liệu ít và mục tiêu fine‑tune.

❌ Sai: Host the model by using Amazon SageMaker. Use TensorRT for large language model (LLM) deployment.

Chỉ đề cập tới việc triển khai, không giải quyết việc học tone từ dữ liệu.

📚 Tham khảo tài liệu

Amazon Bedrock – Fine‑tuning Foundations Models

https://docs.aws.amazon.com/bedrock/latest/userguide/model-customization.html

Amazon SageMaker – HyperPod Overview

https://docs.aws.amazon.com/sagemaker/latest/dg/hyperpod.html

Amazon Personalize – Developer Guide

https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html

AWS Blog – “Fine‑tune LLMs on Amazon Bedrock” (2024‑2025 updates)

https://aws.amazon.com/blogs/machine-learning/fine-tune-llms-on-amazon-bedrock/

🎉 Kết luận: Để đưa tone công ty vào chatbot dựa trên 100 ví dụ hội thoại, tạo một Amazon Bedrock fine‑tuning job là giải pháp tối ưu, nhanh chóng, và chi phí hợp lý.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308647-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 27

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon S3, fine-tuning, guardrails
- Takeaway nhanh: Một ngân hàng đang “fine‑tune” (điều chỉnh) mô hình ngôn ngữ lớn (LLM) trên Amazon Bedrock để trả lời các câu hỏi về khoản vay của khách hàng. Yêu cầu quan trọng: đảm bảo mô hình không tiết lộ bất kỳ dữ liệu cá nhân nào của khách hàng (PII – Personally Identifiable Information). Vì vậy, câu trả lời cần đề cập tới cách xử lý dữ liệu đầu vào (trước khi đưa vào quá trình fine‑tuning) sao cho thông tin nhạy cảm được loại bỏ hoàn toàn, hoặc ít nhất không thể được mô hình “nhớ” và “phát ra”.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308667-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A bank is fine-tuning a large language model (LLM) on Amazon Bedrock to assist customers with questions about their loans. The bank wants to ensure that the model does not reveal any private customer data.
Which solution meets these requirements?

### Các lựa chọn
1. Use Amazon Bedrock Guardrails.
2. Remove personally identifiable information (PII) from the customer data before fine-tuning the LLM.
3. Increase the Top-K parameter of the LLM.
4. Store customer data in Amazon S3. Encrypt the data before fine-tuning the LLM.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một ngân hàng đang “fine‑tune” (điều chỉnh) mô hình ngôn ngữ lớn (LLM) trên Amazon Bedrock để trả lời các câu hỏi về khoản vay của khách hàng.

Yêu cầu quan trọng: đảm bảo mô hình không tiết lộ bất kỳ dữ liệu cá nhân nào của khách hàng (PII – Personally Identifiable Information).

Vì vậy, câu trả lời cần đề cập tới cách xử lý dữ liệu đầu vào (trước khi đưa vào quá trình fine‑tuning) sao cho thông tin nhạy cảm được loại bỏ hoàn toàn, hoặc ít nhất không thể được mô hình “nhớ” và “phát ra”.

✅ Đáp án đúng

🟢 Remove personally identifiable information (PII) from the customer data before fine‑tuning the LLM.

Lý do: Khi dữ liệu huấn luyện chứa PII, mô hình có thể “memorize” (ghi nhớ) những chuỗi thông tin nhạy cảm và sau này sinh ra chúng trong phản hồi – gây rủi ro vi phạm quyền riêng tư và các quy định (GDPR, CCPA, PCI‑DSS,…). Việc xóa sạch PII (hoặc thay thế bằng dữ liệu tổng quát) trước khi đưa vào quá trình fine‑tuning là biện pháp phòng ngừa trực tiếp và được AWS khuyến cáo trong Best Practices for Fine‑tuning Foundation Models on Amazon Bedrock (2024‑2026).

❌ Giải thích các phương án còn lại

🟠 Use Amazon Bedrock Guardrails.

Giải thích: Guardrails của Bedrock cho phép kiểm soát đầu ra (ví dụ: chặn các nội dung vi phạm chính sách, phát hiện PII trong phản hồi). Tuy nhiên, chúng không ngăn chặn việc PII đã có trong dữ liệu huấn luyện được “học” và có khả năng xuất hiện trong kết quả. Guardrails là lớp bảo vệ sau khi mô hình đã được fine‑tuned, không phải giải pháp “tiền xử lý” dữ liệu. Vì vậy không đáp ứng yêu cầu “không tiết lộ bất kỳ dữ liệu riêng tư nào”.

🟠 Increase the Top‑K parameter of the LLM.

Giải thích: Tham số Top‑K ảnh hưởng tới đa dạng của token được sinh ra (càng cao → càng đa dạng, càng ít “deterministic”). Nó không liên quan tới việc loại bỏ hoặc bảo vệ PII trong dữ liệu huấn luyện. Thậm chí, một Top‑K lớn có thể làm mô hình tạo ra các chuỗi ít phổ biến hơn, nhưng không giảm nguy cơ rò rỉ dữ liệu nhạy cảm.

🟠 Store customer data in Amazon S3. Encrypt the data before fine‑tuning the LLM.

Giải thích: Mã hoá dữ liệu đảm bảo an toàn khi lưu trữ và truyền (at‑rest & in‑transit). Tuy nhiên, khi dữ liệu được giải mã để đưa vào quá trình fine‑tuning, PII vẫn tồn tại trong bộ dữ liệu huấn luyện và vẫn có khả năng bị mô hình ghi nhớ. Vì vậy, việc chỉ mã hoá S3 không giải quyết vấn đề rò rỉ thông tin sau khi mô hình được huấn luyện.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Developer Guide – Fine‑tuning Foundations Models (phiên bản 2025‑12) – mục “Data preprocessing and privacy considerations”.

AWS Security Best Practices – Protecting Sensitive Data in Machine Learning Workloads (2024).

Amazon Bedrock Guardrails – Overview (2025) – giải thích Guardrails chỉ hoạt động ở lớp “output filtering”.

PCI DSS & GDPR compliance for AI/ML workloads on AWS (2026).

🧩 Tóm tắt nhanh

✅ Cách đúng: Xóa sạch PII trước khi fine‑tune.

❌ Guardrails: Chỉ lọc đầu ra, không ngăn việc mô hình học PII.

❌ Top‑K: Tham số sinh token, không liên quan tới bảo mật dữ liệu.

❌ Encrypt S3: Bảo vệ dữ liệu khi lưu, nhưng khi giải mã để huấn luyện thì PII vẫn tồn tại.

Với yêu cầu “không để mô hình tiết lộ bất kỳ dữ liệu riêng tư nào”, phương án duy nhất đáp ứng là loại bỏ PII trước khi đưa vào quá trình fine‑tuning. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308667-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 28

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Diversity**
- Takeaway nhanh: Vì sao “Diversity” là đáp án đúng? Diversity (đa dạng) trong ngữ cảnh dữ liệu nghĩa là bộ dữ liệu bao gồm các mẫu đại diện cho nhiều nhóm khác nhau (địa lý, tuổi, giới tính, thu nhập, nền văn hoá, …). Khi một mô hình học máy được huấn luyện trên dữ liệu đa dạng, nó sẽ giảm thiểu nguy cơ thiên lệch (bias) đối với một nhóm nhất định và cho khả năng tổng quát hoá (generalization) tốt hơn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308681-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A food service company wants to collect a dataset to predict customer food preferences. The company wants to ensure that the food preferences of all demographics are included in the data.
Which dataset characteristic does this scenario present?

### Các lựa chọn
1. Accuracy
2. Diversity
3. Recency bias
4. Reliability

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Công ty cung cấp dịch vụ thực phẩm muốn xây dựng một bộ dữ liệu (dataset) để dự đoán sở thích thực phẩm của khách hàng. Để mô hình dự đoán có độ bao phủ tốt, họ muốn chắc chắn rằng sở thích của mọi nhóm nhân khẩu học (demographics) đều được phản ánh trong dữ liệu.

Điều này đặt ra yêu cầu về đặc tính của bộ dữ liệu – bộ dữ liệu phải thể hiện đa dạng các quan điểm, hành vi và sở thích từ các nhóm tuổi, giới tính, khu vực địa lý, thu nhập, văn hoá…

✅ Đáp án đúng: Diversity

Vì sao “Diversity” là đáp án đúng?

Diversity (đa dạng) trong ngữ cảnh dữ liệu nghĩa là bộ dữ liệu bao gồm các mẫu đại diện cho nhiều nhóm khác nhau (địa lý, tuổi, giới tính, thu nhập, nền văn hoá, …).

Khi một mô hình học máy được huấn luyện trên dữ liệu đa dạng, nó sẽ giảm thiểu nguy cơ thiên lệch (bias) đối với một nhóm nhất định và cho khả năng tổng quát hoá (generalization) tốt hơn.

Yêu cầu “muốn đảm bảo rằng sở thích thực phẩm của tất cả các nhóm nhân khẩu học đều được đưa vào dữ liệu” chính là mô tả đặc tính Diversity.

📚 Tham khảo:

AWS Machine Learning Blog – “Building Fair and Representative Datasets for ML” (cập nhật 2025).

“AWS SageMaker Data Wrangler” documentation – hướng dẫn cân bằng dữ liệu (balancing datasets) để đạt được Diversity.

❌ Phân tích các phương án còn lại (giữ nguyên nội dung tiếng Anh)

1. Accuracy

Giải thích: Accuracy đề cập đến độ đúng của dữ liệu – tức là dữ liệu phản ánh đúng thực tế, không có lỗi đo lường hoặc ghi chép.

Tại sao sai: Câu hỏi không hỏi về mức độ chính xác của mỗi mẫu dữ liệu mà chỉ quan tâm tới độ bao phủ của các nhóm nhân khẩu học. Một bộ dữ liệu có thể rất chính xác nhưng lại chỉ đại diện cho một nhóm duy nhất → không đáp ứng yêu cầu của câu hỏi.

2. Diversity (đáp án đúng)

Giải thích: Như đã nêu ở trên, Diversity là tính đa dạng của dữ liệu, bao gồm các mẫu từ mọi nhóm dân số.

Vì sao đúng: Yêu cầu “đảm bảo rằng sở thích của tất cả các demographics được bao gồm” chính xác mô tả tính Diversity.

3. Recency bias

Giải thích: Recency bias là thiên lệch thời gian, khi dữ liệu mới (gần thời điểm hiện tại) được ưu tiên hơn dữ liệu cũ.

Tại sao sai: Câu hỏi không đề cập đến thời gian thu thập dữ liệu mà chỉ nói đến việc bao phủ các nhóm dân số. Do vậy, Recency bias không liên quan.

4. Reliability

Giải thích: Reliability (độ tin cậy) đề cập đến khả năng dữ liệu đều đặn, ổn định và có thể tái tạo trong các lần thu thập khác nhau.

Tại sao sai: Mặc dù độ tin cậy là một tiêu chí quan trọng, nhưng nó không phản ánh việc dữ liệu có đại diện cho mọi demographics hay không. Vì vậy, không phải là đặc tính được mô tả trong kịch bản.

📌 Kết luận

Đáp án đúng: Diversity ✅

Các đáp án còn lại (Accuracy, Recency bias, Reliability) đều không phù hợp với yêu cầu “đảm bảo bao gồm sở thích của tất cả các demographics”.

🎯 Gợi ý thực tiễn trên AWS (2026)

Khi xây dựng dataset đa dạng, bạn có thể sử dụng Amazon SageMaker Ground Truth để label dữ liệu từ nhiều nguồn khác nhau và áp dụng labeling workforce diversification.

AWS DataBrew (trong SageMaker) hỗ trợ visual profiling giúp nhanh chóng nhận diện các nhóm dữ liệu bị thiếu (under‑represented) và thực hiện balancing (sử dụng class imbalance techniques).

Đối với việc theo dõi bias và fairness, AWS SageMaker Clarify cung cấp các metric để đo lường demographic parity và equalized odds, hỗ trợ kiểm tra tính Diversity của dataset.

Hy vọng phân tích trên giúp bạn nắm vững khái niệm và lựa chọn đúng đáp án! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308681-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 29

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Câu hỏi: “Which ML technique uses training data that is labeled with the correct output values?” Nội dung câu hỏi đang hỏi về kỹ thuật học máy (Machine Learning) nào dựa trên dữ liệu huấn luyện đã được gán nhãn (label) với giá trị đầu ra đúng. Khi dữ liệu đã có nhãn, mô hình học sẽ “học” cách ánh xạ đầu vào → đầu ra dựa trên các cặp (input, label) này. Đây là khái niệm cơ bản trong Supervised Learning.
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/Machine-Learning-Best-Practices.pdf | https://docs.aws.amazon.com/machine-learning/latest/dg/supervised-learning.html | https://docs.aws.amazon.com/sagemaker/latest/dg/training.html | https://www.examtopics.com/discussions/amazon/view/308663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which ML technique uses training data that is labeled with the correct output values?

### Các lựa chọn
1. Supervised learning
2. Unsupervised learning
3. Reinforcement learning
4. Transfer learning

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which ML technique uses training data that is labeled with the correct output values?”

Nội dung câu hỏi đang hỏi về kỹ thuật học máy (Machine Learning) nào dựa trên dữ liệu huấn luyện đã được gán nhãn (label) với giá trị đầu ra đúng. Khi dữ liệu đã có nhãn, mô hình học sẽ “học” cách ánh xạ đầu vào → đầu ra dựa trên các cặp (input, label) này. Đây là khái niệm cơ bản trong Supervised Learning.

✅ Đáp án đúng

Supervised learning

🗒️ Lý do:

Trong Supervised learning (học có giám sát), mỗi mẫu trong tập huấn luyện bao gồm đầu vào (features) và nhãn (label) – giá trị đầu ra mong muốn.

Mô hình được “giám sát” bởi các nhãn này để tối ưu hàm mất mát, từ đó học được quy luật dự đoán cho dữ liệu chưa thấy.

Các thuật toán tiêu biểu: Linear Regression, Logistic Regression, Decision Trees, Random Forest, Gradient Boosting, Neural Networks (CNN, RNN…) khi được huấn luyện trên dữ liệu có nhãn.

❌ Giải thích các phương án sai

Unsupervised learning

Giải thích: Unsupervised learning (học không giám sát) không sử dụng nhãn. Mô hình chỉ nhận dữ liệu đầu vào và cố gắng khám phá cấu trúc tiềm ẩn, ví dụ như clustering (k-means, DBSCAN) hoặc giảm chiều (PCA, t‑SNE). Vì không có nhãn, câu hỏi “được gán nhãn với giá trị đầu ra đúng” không áp dụng.

Reinforcement learning

Giải thích: Reinforcement learning (học tăng cường) dựa trên phản hồi (reward) và hình phạt mà môi trường đưa ra sau mỗi hành động, chứ không phải nhãn cố định cho từng mẫu dữ liệu. Mô hình (agent) học cách tối ưu chiến lược (policy) thông qua trial‑and‑error, không dựa vào bộ dữ liệu đã dán nhãn.

Transfer learning

Giải thích: Transfer learning (học chuyển giao) không phải là một loại học máy riêng mà là kỹ thuật tái sử dụng mô hình đã được huấn luyện trên một tác vụ (có thể là supervised) để áp dụng cho tác vụ khác. Nó có thể dựa trên dữ liệu có nhãn hoặc không, tùy thuộc vào nguồn và mục tiêu, nên không thể khẳng định “sử dụng dữ liệu được gán nhãn” là đặc trưng duy nhất của nó.

📚 Tham khảo (đến năm 2026)

AWS Machine Learning Services Documentation – Supervised Learning Overview (2026).

https://docs.aws.amazon.com/machine-learning/latest/dg/supervised-learning.html

AWS Whitepaper – “Machine Learning Best Practices on AWS” (2025). Chương 3 mô tả các loại học máy: supervised, unsupervised, reinforcement.

https://d1.awsstatic.com/whitepapers/Machine-Learning-Best-Practices.pdf

“Deep Learning on AWS” – Amazon SageMaker Developer Guide (2026). Giải thích cách SageMaker Trainer nhận train.csv có cột label cho supervised learning.

https://docs.aws.amazon.com/sagemaker/latest/dg/training.html

🧩 Tóm tắt nhanh:

Câu hỏi muốn biết kỹ thuật nào dùng dữ liệu có nhãn → Supervised learning là đáp án đúng.

Các lựa chọn còn lại (Unsupervised, Reinforcement, Transfer) không dựa vào dữ liệu đã dán nhãn theo cách mô tả trong câu hỏi.

Hy vọng phân tích trên giúp bạn nắm rõ nguyên lý và lựa chọn đúng! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 30

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Accuracy**
- Takeaway nhanh: [ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} ] Áp dụng trong SageMaker: Khi bạn chạy một training job hoặc batch transform và tạo một Evaluation trong SageMaker Model Monitor hoặc SageMaker Experiments, bạn có thể chỉ định accuracy như một metric để thu thập và hiển thị trên console. Đây là metric mặc định cho các bài toán phân loại nhị phân và đa lớp, và phù hợp với yêu cầu câu hỏi.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://scikit-learn.org/stable/modules/model_evaluation.html#classification-metrics | https://www.examtopics.com/discussions/amazon/view/308659-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner is evaluating the performance of an Amazon SageMaker model. The AI practitioner must choose a performance metric. The metric must show the ratio of the number of correctly classified items to the total number of correctly and incorrectly classified items.
Which metric meets these requirements?

### Các lựa chọn
1. Accuracy
2. Precision
3. F1 score
4. Recall

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi mô tả một tình huống trong Amazon SageMaker – một nhà thực hành AI (AI practitioner) cần chọn metric (chỉ số) để đo hiệu suất của mô hình phân loại.

Yêu cầu của metric là:

“Tỷ lệ của số mục được phân loại đúng so với tổng số mục được phân loại đúng + sai.”

Nói cách khác:

[ \text{Metric} = \frac{\text{Số dự đoán đúng (True Positives + True Negatives)}}{\text{Tổng số dự đoán (True Positives + True Negatives + False Positives + False Negatives)}} ]

Đây chính là định nghĩa của Accuracy trong thống kê và học máy.

✅ Đáp án đúng: Accuracy

Lý do: Accuracy tính tỷ lệ phần trăm các mẫu mà mô hình dự đoán đúng (cả 2 lớp) trên toàn bộ mẫu kiểm tra. Công thức:

[ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} ]

Áp dụng trong SageMaker: Khi bạn chạy một training job hoặc batch transform và tạo một Evaluation trong SageMaker Model Monitor hoặc SageMaker Experiments, bạn có thể chỉ định accuracy như một metric để thu thập và hiển thị trên console. Đây là metric mặc định cho các bài toán phân loại nhị phân và đa lớp, và phù hợp với yêu cầu câu hỏi.

❌ Giải thích các phương án sai

1. Precision

Định nghĩa: Precision = TP / (TP + FP)

Giải thích: Precision đo tỷ lệ các dự đoán dương tính đúng so với tổng số dự đoán dương tính (đúng + sai). Nó không tính tới các mẫu âm tính đúng (TN), vì vậy không phản ánh “tổng số mục được phân loại đúng + sai” mà câu hỏi yêu cầu.

Kết luận: Không đáp ứng yêu cầu của câu hỏi.

2. F1 score

Định nghĩa: F1 = 2 * (Precision * Recall) / (Precision + Recall)

Giải thích: F1 là trung bình hài hòa giữa Precision và Recall, dùng để cân bằng khi dữ liệu mất cân đối. Công thức không đơn giản là “đúng / (đúng + sai)”, mà là một hàm phức tạp dựa trên cả Precision và Recall.

Kết luận: Không phải là metric mà câu hỏi mô tả.

3. Recall

Định nghĩa: Recall = TP / (TP + FN)

Giải thích: Recall đo khả năng mô hình “phát hiện” tất cả các mẫu dương tính thực tế (có bao gồm FN). Nó bỏ qua các dự đoán âm tính đúng (TN) và các dự đoán dương tính sai (FP). Do đó, không đáp ứng tiêu chí “tổng số mục được phân loại đúng + sai”.

Kết luận: Sai.

📚 Tham khảo & nguồn tài liệu (tính đến 2026)

AWS Documentation – Amazon SageMaker Model Monitoring

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

Mô tả cách cấu hình và thu thập các metric như accuracy, precision, recall, f1 trong các job.

AWS Certified DevOps Engineer – Professional Exam Guide (2026 Edition)

Chương “Machine Learning Ops” đề cập tới việc lựa chọn metric phù hợp cho mô hình dựa trên yêu cầu nghiệp vụ.

Scikit‑learn User Guide – Classification Metrics (phiên bản 1.5, 2026)

https://scikit-learn.org/stable/modules/model_evaluation.html#classification-metrics

Định nghĩa chuẩn của Accuracy, Precision, Recall, F1.

🧩 Tổng kết

Câu hỏi yêu cầu một metric đo đúng / (đúng + sai) → Accuracy ✅

Các metric còn lại (Precision, Recall, F1) đều tập trung vào các khía cạnh riêng (dương tính, âm tính, cân bằng) và không khớp với mô tả yêu cầu.

Hy vọng phân tích trên giúp bạn nắm rõ lý do lựa chọn Accuracy và hiểu được sự khác nhau giữa các metric trong bối cảnh đánh giá mô hình trên Amazon SageMaker. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308659-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 31

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon S3, Amazon Q
- Đáp án tham khảo: **Unsupervised learning**
- Takeaway nhanh: Bối cảnh: Công ty đang xây dựng một ứng dụng Machine Learning (ML) có mục tiêu tự động nhóm (cluster) các khách hàng và sản phẩm dựa trên các đặc tính của chúng. Yêu cầu chính: “Nhóm tương đồng” → không có nhãn (label) nào được cung cấp trước cho từng khách hàng/sản phẩm. Hệ thống phải tự “phát hiện” các nhóm dựa trên tính chất chung. Câu hỏi: Chiến lược ML nào phù hợp nhất để thực hiện yêu cầu này?
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/unsupervised-learning-at-scale/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clustering.html | https://docs.aws.amazon.com/wellarchitected/latest/ml-lens/intro.html | https://www.examtopics.com/discussions/amazon/view/313003-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing an ML application. The application must automatically group similar customers and products based on their characteristics. Which ML strategy should the company use to meet these requirements?

### Các lựa chọn
1. Unsupervised learning
2. Supervised learning
3. Reinforcement learning
4. Semi-supervised learning

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Công ty đang xây dựng một ứng dụng Machine Learning (ML) có mục tiêu tự động nhóm (cluster) các khách hàng và sản phẩm dựa trên các đặc tính của chúng.

Yêu cầu chính: “Nhóm tương đồng” → không có nhãn (label) nào được cung cấp trước cho từng khách hàng/sản phẩm. Hệ thống phải tự “phát hiện” các nhóm dựa trên tính chất chung.

Câu hỏi: Chiến lược ML nào phù hợp nhất để thực hiện yêu cầu này?

Trong lĩnh vực ML, khi không có nhãn và mục tiêu là phân cụm (clustering), chúng ta sẽ sử dụng học không giám sát (Unsupervised learning). Các chiến lược khác (Supervised, Reinforcement, Semi‑supervised) đều yêu cầu ít nhất một dạng nhãn hoặc môi trường tương tác, không phù hợp với bài toán “tự động nhóm” này.

✅ Đáp án đúng: Unsupervised learning

Lý do:

Không cần dữ liệu có nhãn → phù hợp với tình huống “không biết trước nhóm nào là gì”.

Thuật toán thường dùng: K‑Means, Hierarchical Clustering, DBSCAN, Gaussian Mixture Models, hay các phương pháp deep clustering (Auto‑Encoder + clustering).

Trên AWS, Amazon SageMaker cung cấp các built‑in algorithms cho clustering (ví dụ: KMeans, DBSCAN), cũng như khả năng chạy notebook tùy chỉnh để triển khai mô hình không giám sát.

Áp dụng thực tế trong AWS:

📦 SageMaker Processing: tiền xử lý dữ liệu khách hàng/sản phẩm (feature engineering).

📊 SageMaker Training Job với thuật toán KMeans để tạo mô hình clustering.

🚀 SageMaker Endpoint hoặc Batch Transform để gán nhãn cluster cho dữ liệu mới.

📈 Kết quả có thể được đưa vào Amazon QuickSight để visual hoá các nhóm khách hàng/ sản phẩm.

❌ Các phương án sai và giải thích

1️⃣ Supervised learning

Giải thích: Phương pháp này yêu cầu dữ liệu đã được dán nhãn (label) để huấn luyện mô hình dự đoán một giá trị đầu ra (classification hoặc regression).

Tại sao không phù hợp: Bài toán “tự động nhóm” không có sẵn nhãn cho từng nhóm; nếu ép buộc dùng supervised, chúng ta phải tự tạo nhãn (ví dụ: gán nhãn thủ công), làm mất tính tự động và gây tốn kém thời gian.

2️⃣ Reinforcement learning

Giải thích: Học tăng cường (RL) dựa trên tương tác liên tục với môi trường và nhận phần thưởng (reward) để tối ưu hành vi.

Tại sao không phù hợp: Không có môi trường “đóng vai trò” như một trò chơi hay quá trình quyết định tuần tự trong trường hợp này. Mục tiêu nhóm không phải là tối đa hoá phần thưởng qua các bước hành động.

3️⃣ Semi-supervised learning

Giải thích: Kết hợp dữ liệu có nhãn và dữ liệu không nhãn; thường dùng khi nhãn khó thu thập nhưng vẫn cần một phần dữ liệu đã dán nhãn để “hướng dẫn” mô hình.

Tại sao không phù hợp: Câu hỏi không đề cập đến bất kỳ dữ liệu nhãn nào. Nếu không có bất kỳ nhãn nào, việc dùng semi‑supervised sẽ không mang lại lợi thế và thậm chí có thể gây sai lệch.

🛠️ Gợi ý triển khai trên AWS (đối với Unsupervised learning)

Thu thập & chuẩn bị dữ liệu

Dùng AWS Glue hoặc AWS Data Pipeline để ETL dữ liệu khách hàng/sản phẩm vào Amazon S3.

Feature engineering

Khởi chạy SageMaker Processing Jobs hoặc AWS Glue Spark jobs để trích xuất, chuẩn hoá, và giảm chiều (PCA, t‑SNE).

Huấn luyện mô hình clustering

Tạo SageMaker Training Job với thuật toán KMeans (được tối ưu cho dữ liệu lớn, hỗ trợ phân phối).

Hoặc tự viết notebook sử dụng scikit‑learn, TensorFlow, PyTorch và chạy trên SageMaker Training.

Triển khai & dự đoán

Đối với batch inference: SageMaker Batch Transform để gán cluster cho hàng triệu bản ghi.

Đối với real‑time inference: SageMaker Endpoint (có thể sử dụng model‑monitor để giám sát drift).

Theo dõi & CI/CD

Dùng Amazon CloudWatch + SageMaker Model Monitor để giám sát chất lượng mô hình.

Áp dụng AWS CodePipeline + CodeBuild để tự động hoá quá trình tái huấn luyện khi dữ liệu mới xuất hiện.

📚 Tham khảo (2026)

Amazon SageMaker Documentation – Clustering Algorithms

https://docs.aws.amazon.com/sagemaker/latest/dg/clustering.html

AWS Machine Learning Blog – Unsupervised Learning at Scale (2025)

https://aws.amazon.com/blogs/machine-learning/unsupervised-learning-at-scale/

AWS Well‑Architected Framework – ML Lens (2024 update)

https://docs.aws.amazon.com/wellarchitected/latest/ml-lens/intro.html

Tóm lại: Đối với yêu cầu “tự động nhóm khách hàng và sản phẩm dựa trên đặc tính”, chiến lược Unsupervised learning là lựa chọn duy nhất đáp ứng được mục tiêu mà không cần dữ liệu có nhãn, đồng thời AWS cung cấp một loạt dịch vụ (SageMaker, Glue, CodePipeline, …) để triển khai, vận hành và duy trì giải pháp này một cách hiệu quả. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313003-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 32

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Personalize, Amazon Textract, Amazon Transcribe, Amazon Translate
- Đáp án tham khảo: **Use the Amazon Translate real-time translation feature.**
- Takeaway nhanh: Câu hỏi mô tả một công ty tin tức chỉ xuất bản bài báo bằng tiếng Anh và muốn các bài báo này có sẵn ở các ngôn ngữ khác. Yêu cầu thực chất là: Nhận một đoạn văn bản (bài báo) → dịch sang ngôn ngữ đích một cách nhanh chóng, có thể là “real‑time” hoặc “batch”. Không yêu cầu chuyển đổi giọng nói, trích xuất dữ liệu từ tài liệu, hay gợi ý nội dung cá nhân hoá.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html | https://docs.aws.amazon.com/textract/latest/dg/what-is.html | https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html | https://docs.aws.amazon.com/translate/latest/dg/what-is.html | https://www.examtopics.com/discussions/amazon/view/313035-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A news agency publishes articles in English. The agency wants to make articles available in other languages.
Which solution meets these requirements?

### Các lựa chọn
1. Add Amazon Transcribe to the company’s website.
2. Use the Amazon Translate real-time translation feature.
3. Add Amazon Personalize to the company’s website.
4. Use the Amazon Textract real-time document processing feature.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một công ty tin tức chỉ xuất bản bài báo bằng tiếng Anh và muốn các bài báo này có sẵn ở các ngôn ngữ khác.

Yêu cầu thực chất là:

Nhận một đoạn văn bản (bài báo) → dịch sang ngôn ngữ đích một cách nhanh chóng, có thể là “real‑time” hoặc “batch”.

Không yêu cầu chuyển đổi giọng nói, trích xuất dữ liệu từ tài liệu, hay gợi ý nội dung cá nhân hoá.

Do đó, chúng ta cần một dịch vụ dịch ngôn ngữ tự động của AWS.

✅ Đáp án đúng

✅ Use the Amazon Translate real-time translation feature.

Amazon Translate là dịch vụ dịch ngôn ngữ dựa trên machine‑learning, cung cấp API real‑time (dịch từng đoạn, từng câu) và batch (dịch toàn bộ tài liệu). Nó hỗ trợ hơn 100 ngôn ngữ và có khả năng tùy chỉnh vocab (custom terminology) – rất phù hợp để chuyển bài báo tiếng Anh sang các ngôn ngữ khác ngay trên website hoặc trong pipeline xử lý nội dung.

❌ Giải thích các phương án sai

❌ Add Amazon Transcribe to the company’s website.

Amazon Transcribe là dịch vụ chuyển giọng nói thành văn bản (speech‑to‑text). Nó không thực hiện việc dịch ngôn ngữ; chỉ giúp “ghi lại” nội dung âm thanh. Vì câu hỏi đề cập tới bài báo đã có sẵn dưới dạng văn bản, Transcribe không đáp ứng nhu cầu này.

❌ Add Amazon Personalize to the company’s website.

Amazon Personalize là dịch vụ đề xuất nội dung dựa trên máy học (recommendation). Nó phân tích hành vi người dùng để đưa ra gợi ý sản phẩm, video, bài viết… nhưng không thực hiện dịch ngôn ngữ. Do vậy, không phù hợp với yêu cầu “đưa bài báo sang ngôn ngữ khác”.

❌ Use the Amazon Textract real-time document processing feature.

Amazon Textract được thiết kế để trích xuất văn bản, bảng và dữ liệu có cấu trúc từ tài liệu (PDF, ảnh, scans). Mục tiêu của nó là OCR và phân tích tài liệu, không phải dịch ngôn ngữ. Vì bài báo đã ở dạng text, Textract không cần thiết và cũng không cung cấp chức năng dịch.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Translate – Documentation

https://docs.aws.amazon.com/translate/latest/dg/what-is.html (phiên bản 2026 cập nhật tính năng “real‑time translation API” và “custom terminology”).

Amazon Transcribe – Overview

https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html

Amazon Personalize – Developer Guide

https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html

Amazon Textract – Documentation

https://docs.aws.amazon.com/textract/latest/dg/what-is.html

🛠️ Kết luận

Với mục tiêu dịch nội dung văn bản của các bài báo sang ngôn ngữ khác một cách nhanh chóng và có thể tích hợp trực tiếp vào website, Amazon Translate là lựa chọn duy nhất đáp ứng yêu cầu. Các dịch vụ khác (Transcribe, Personalize, Textract) đều có chức năng khác và không giải quyết được nhu cầu dịch ngôn ngữ.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313035-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 33

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, responsible AI, guardrails
- Takeaway nhanh: 2️⃣ Explainability (có thể giải thích được) – kết quả của mô hình có thể được người dùng và các bên liên quan hiểu và kiểm chứng. Yêu cầu bổ sung: Công ty muốn đào tạo các thành viên trong đội phát triển AI để họ nắm được các kiến thức, kỹ năng cần thiết cho “fair” và “explainable” AI. Câu hỏi: “Which training will meet these requirements?” – tức là lựa chọn chương trình đào tạo nào đáp ứng được cả hai nhu cầu trên.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313011-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using AI to improve its services. The company needs to ensure that the AI system is fair and explainable. The company wants to require training for members of the AI system development team.
Which training will meet these requirements?

### Các lựa chọn
1. Training on advanced coding skills
2. Training on data privacy and encryption protocols
3. Training on bias awareness and responsible AI
4. Training on advanced ML algorithms

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Bối cảnh: Một công ty đang triển khai hệ thống AI và muốn đảm bảo hai yếu tố quan trọng:

1️⃣ Fairness (công bằng) – mô hình không gây ra thiên vị đối với bất kỳ nhóm người dùng nào.

2️⃣ Explainability (có thể giải thích được) – kết quả của mô hình có thể được người dùng và các bên liên quan hiểu và kiểm chứng.

Yêu cầu bổ sung: Công ty muốn đào tạo các thành viên trong đội phát triển AI để họ nắm được các kiến thức, kỹ năng cần thiết cho “fair” và “explainable” AI.

Câu hỏi: “Which training will meet these requirements?” – tức là lựa chọn chương trình đào tạo nào đáp ứng được cả hai nhu cầu trên.

✅ Đáp án đúng

🟢 Training on bias awareness and responsible AI

Lý do:

Bias awareness (nhận thức về thiên lệch) cung cấp kiến thức về cách phát hiện, đo lường và giảm thiểu bias trong dữ liệu và mô hình – chính là nền tảng để đạt được fairness.

Responsible AI (AI có trách nhiệm) bao gồm các nguyên tắc về tính minh bạch, giải thích được, đạo đức và quản trị – đáp ứng yêu cầu explainability và các tiêu chuẩn tuân thủ.

AWS đã cung cấp tài liệu và dịch vụ hỗ trợ Responsible AI, ví dụ: Amazon SageMaker Clarify (phát hiện bias, tạo feature importance) và Amazon Bedrock Guardrails (đảm bảo tính đạo đức của mô hình ngôn ngữ). Việc đào tạo về các khái niệm này giúp đội ngũ hiểu cách tận dụng công cụ AWS để xây dựng hệ thống AI công bằng và có thể giải thích.

❌ Giải thích các phương án sai

Training on advanced coding skills

Giải thích: Mặc dù nâng cao kỹ năng lập trình là cần thiết cho phát triển phần mềm, nhưng nó không trực tiếp liên quan tới fairness hay explainability của AI. Đào tạo này tập trung vào ngôn ngữ lập trình, cấu trúc dữ liệu, tối ưu thuật toán, chứ không đề cập tới việc phát hiện bias hay giải thích mô hình.

Training on data privacy and encryption protocols

Giải thích: Bảo mật dữ liệu và mã hoá là yếu tố quan trọng về data protection và tuân thủ (ví dụ: GDPR, HIPAA). Tuy nhiên, chúng không giải quyết được vấn đề thiên lệch dữ liệu hay khả năng giải thích quyết định của mô hình AI. Do đó, không đáp ứng yêu cầu “fair and explainable”.

Training on advanced ML algorithms

🧩: Đào tạo về các thuật toán Machine Learning nâng cao (như Transformer, Graph Neural Networks, Reinforcement Learning) giúp cải thiện hiệu suất mô hình, nhưng không tự động đảm bảo fairness hay explainability.

Để đạt được các yêu cầu này, cần bổ sung kiến thức về bias mitigation và model interpretability, chứ không chỉ học thuật toán.

📚 Tham khảo tài liệu (cập nhật tới năm 2026)

AWS Well‑Architected Framework – Machine Learning Lens (2024‑2025) – phần “Responsible AI” nêu rõ việc đào tạo đội ngũ về bias, explainability, governance.

Amazon SageMaker Clarify Documentation – hướng dẫn cách đo lường bias và tạo feature importance cho mô hình.

AWS AI Ethics and Governance Whitepaper (2025) – đề cập tới các chương trình đào tạo nội bộ về Responsible AI.

AWS re:Invent 2025 Session “Building Trustworthy AI with SageMaker” – video và slide về bias mitigation và explainability.

🛠️ Kết luận

Để đáp ứng yêu cầu “fair and explainable AI”, công ty cần đào tạo về bias awareness và responsible AI. Các khóa học này cung cấp kiến thức nền tảng để phát hiện và giảm thiểu thiên lệch, đồng thời áp dụng các kỹ thuật và công cụ (như SageMaker Clarify) để làm cho mô hình AI trở nên minh bạch, có thể giải thích và tuân thủ các tiêu chuẩn đạo đức.

Các lựa chọn còn lại dù quan trọng trong các khía cạnh khác của phát triển phần mềm và bảo mật dữ liệu, nhưng không tập trung vào hai yêu cầu cốt lõi của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313011-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 34

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Comprehend, guardrails
- Đáp án tham khảo: **Amazon Bedrock Guardrails**
- Takeaway nhanh: Vì sao Amazon Bedrock Guardrails là đáp án đúng? Guardrails là một tính năng được ra mắt trong Amazon Bedrock (2023) và được cập nhật liên tục đến năm 2026. Nó cho phép định nghĩa và áp dụng các quy tắc lọc nội dung (content policy) trên: Input prompts → ngăn người dùng gửi những câu hỏi vi phạm chính sách.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://www.examtopics.com/discussions/amazon/view/312978-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company is deploying a chatbot. The chatbot will give users the ability to ask questions about the company’s products and receive details on users’ orders. The company must implement safeguards for the chatbot to filter harmful content from the input prompts and chatbot responses.
Which AWS feature or resource meets these requirements?

### Các lựa chọn
1. Amazon Bedrock Guardrails
2. Amazon Bedrock Agents
3. Amazon Bedrock inference APIs
4. Amazon Bedrock custom models

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty thương mại điện tử đang triển khai một chatbot để:

Nhận câu hỏi từ người dùng về sản phẩm.

Trả lời chi tiết về trạng thái đơn hàng của người dùng.

Yêu cầu quan trọng: phải có cơ chế bảo vệ, tức là lọc nội dung có hại (ví dụ: ngôn từ tục tĩu, thông tin nhạy cảm, yêu cầu bất hợp pháp…) ở cả đầu vào (prompt người dùng) và đầu ra (câu trả lời của chatbot).

Vậy AWS cung cấp tính năng nào giúp thực hiện “safeguards” (bộ lọc nội dung) cho một mô hình ngôn ngữ trong môi trường Bedrock?

✅ Đáp án đúng: Amazon Bedrock Guardrails

Vì sao Amazon Bedrock Guardrails là đáp án đúng?

Guardrails là một tính năng được ra mắt trong Amazon Bedrock (2023) và được cập nhật liên tục đến năm 2026.

Nó cho phép định nghĩa và áp dụng các quy tắc lọc nội dung (content policy) trên:

Input prompts → ngăn người dùng gửi những câu hỏi vi phạm chính sách.

Model outputs → kiểm soát và chỉnh sửa câu trả lời nếu chứa nội dung không phù hợp.

Guardrails hỗ trợ cấu hình dựa trên các tiêu chuẩn như:

Hate speech, profanity, personal data leakage, disallowed topics…

Có thể tùy chỉnh bằng cách tải lên JSON policy hoặc dùng các policy mẫu do AWS cung cấp.

Tích hợp trực tiếp với các model có trong Amazon Bedrock (Claude, Titan, Jurassic‑2, …) mà không cần viết mã phức tạp.

Đảm bảo độ trễ tối thiểu, vì lọc được thực hiện trong đường ống inference của Bedrock, phù hợp với yêu cầu thời gian thực của một chatbot thương mại điện tử.

Do đó, Guardrails đáp ứng đầy đủ yêu cầu “filter harmful content from the input prompts and chatbot responses”.

❌ Giải thích các đáp án sai

1. Amazon Bedrock Agents

Mô tả: Agents là khung công cụ cho phép kết hợp nhiều mô hình (LLM) và các công cụ AWS (ví dụ: DynamoDB, S3, Lambda) để xây dựng tác vụ tự động có khả năng tự quyết định gọi API, thực hiện workflow.

Lý do sai: Agents không cung cấp cơ chế lọc nội dung. Chúng tập trung vào orchestration và knowledge retrieval, không có tính năng “guardrails” để kiểm soát ngôn ngữ độc hại. Vì vậy không đáp ứng yêu cầu “filter harmful content”.

2. Amazon Bedrock inference APIs

Mô tả: Đây là giao diện API (REST/SDK) cho phép gửi prompt tới một LLM và nhận kết quả.

Lý do sai: API chỉ là cầu nối để thực hiện inference. Nó không tích hợp bất kỳ bộ lọc nội dung nào; người dùng phải tự triển khai logic lọc (ví dụ: dùng Amazon Comprehend, Lambda) – không phải là tính năng sẵn có trong Bedrock.

3. Amazon Bedrock custom models

Mô tả: Cho phép đào tạo hoặc fine‑tune mô hình tùy chỉnh trên Bedrock, hoặc đưa lên mô hình của bên thứ ba.

Lý do sai: Mặc dù bạn có thể tự xây dựng mô hình có khả năng “guardrails” nội bộ, Bedrock không tự động cung cấp bộ lọc nội dung cho các custom model. Bạn sẽ phải lập trình và giám sát riêng, không phải là một “feature” tích hợp sẵn.

📚 Tham khảo (cập nhật đến 2026)

Amazon Bedrock Documentation – Guardrails – https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html (phiên bản 2026‑03).

AWS re:Invent 2023 & 2025 – “Building Safe Generative AI with Bedrock Guardrails” – video và slide.

AWS Well‑Architected Framework – Security Pillar – phần về content moderation cho AI.

🧩 Tóm tắt nhanh

Câu hỏi: Cần một tính năng của AWS để lọc nội dung độc hại ở cả đầu vào và đầu ra của chatbot.

Đáp án đúng: Amazon Bedrock Guardrails ✅ – cung cấp bộ lọc nội dung tích hợp, có thể tùy chỉnh, hoạt động ngay trên nền tảng inference.

Các đáp án còn lại:

Amazon Bedrock Agents ❌ – chỉ là công cụ orchestration, không lọc nội dung.

Amazon Bedrock inference APIs ❌ – chỉ là giao diện gọi mô hình, không có guardrails.

Amazon Bedrock custom models ❌ – cho phép tạo mô hình tùy chỉnh, nhưng không tự động có bộ lọc nội dung.

Hy vọng phân tích trên đã giúp bạn nắm rõ lý do lựa chọn Amazon Bedrock Guardrails cho yêu cầu bảo vệ nội dung của chatbot. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312978-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

## Câu 35

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, responsible AI
- Takeaway nhanh: 🟢 Ensure that the data is balanced and collected from a diverse group. Balanced data → Đảm bảo mỗi lớp (ví dụ: các nhóm tuổi, giới tính, khu vực địa lý, mức thu nhập…) có số lượng mẫu tương đương, tránh việc một lớp chiếm ưu thế và “đè” lên các lớp khác. Diverse group → Thu thập dữ liệu từ nhiều phân khúc khách hàng khác nhau (địa lý, ngôn ngữ, hành vi mua sắm, thiết bị truy cập…) giúp mô hình học được các mẫu đa dạng, giảm nguy cơ “phân biệt” khi dự đoán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308657-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A retail company wants to build an ML model to recommend products to customers. The company wants to build the model based on responsible practices.
Which practice should the company apply when collecting data to decrease model bias?

### Các lựa chọn
1. Use data from only customers who match the demographics of the company's overall customer base.
2. Collect data from customers who have a past purchase history.
3. Ensure that the data is balanced and collected from a diverse group.
4. Ensure that the data is from a publicly available dataset.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty bán lẻ muốn xây dựng một mô hình Machine Learning (ML) dùng để gợi ý sản phẩm cho khách hàng. Họ đặc biệt quan tâm tới “responsible ML practices” – nghĩa là phải giảm thiểu các nguồn gây ra bias (thiên lệch) trong mô hình.

Trong giai đoạn thu thập dữ liệu, việc lựa chọn nguồn dữ liệu, cách lấy mẫu và độ đa dạng của dữ liệu là những yếu tố then chốt để tránh việc mô hình học một cách thiên vị đối với một nhóm khách hàng nào đó.

✅ Đáp án đúng

🟢 Ensure that the data is balanced and collected from a diverse group.

Giải thích:

Balanced data → Đảm bảo mỗi lớp (ví dụ: các nhóm tuổi, giới tính, khu vực địa lý, mức thu nhập…) có số lượng mẫu tương đương, tránh việc một lớp chiếm ưu thế và “đè” lên các lớp khác.

Diverse group → Thu thập dữ liệu từ nhiều phân khúc khách hàng khác nhau (địa lý, ngôn ngữ, hành vi mua sắm, thiết bị truy cập…) giúp mô hình học được các mẫu đa dạng, giảm nguy cơ “phân biệt” khi dự đoán.

Đây là nguyên tắc nền tảng trong AWS Well‑Architected Framework – Machine Learning Lens (2025) và các hướng dẫn của Amazon SageMaker Clarify (phiên bản 2026) về phát hiện & giảm bias. Khi dữ liệu cân bằng và đa dạng, các thuật toán ML sẽ ít có xu hướng học các quan hệ sai lệch dựa trên đặc tính không liên quan.

❌ Các phương án sai và lý do

❌ Use data from only customers who match the demographics of the company's overall customer base.

Lý do sai: Việc chỉ lấy dữ liệu từ “đối tượng khớp với dân số tổng thể” không đảm bảo tính đa dạng thực tế. “Overall customer base” thường đã bị thiên lệch (ví dụ: tập trung ở một khu vực, một độ tuổi). Khi chỉ dùng nhóm này, mô hình sẽ không học được những hành vi của các nhóm khách hàng ngoại biên, dẫn tới bias khi dự đoán cho những khách hàng không thuộc nhóm mẫu.

❌ Collect data from customers who have a past purchase history.

Lý do sai: Dữ liệu chỉ từ khách hàng có lịch sử mua hàng bị giới hạn ở những người đã từng giao dịch, bỏ qua những khách hàng mới, tiềm năng hoặc những người không mua thường xuyên. Điều này tạo ra selection bias – mô hình sẽ ưu tiên đề xuất những mặt hàng phù hợp với khách hàng “cũ”, giảm khả năng khám phá sản phẩm mới cho người chưa mua.

❌ Ensure that the data is from a publicly available dataset.

Lý do sai: Dữ liệu công khai không nhất thiết đáp ứng yêu cầu độ cân bằng và đa dạng cho trường hợp cụ thể của công ty. Nhiều bộ dữ liệu mở (như Kaggle, UCI) có thể chứa bias sẵn có hoặc không phản ánh đúng đặc thù hành vi mua sắm của khách hàng công ty. Thay vào đó, công ty nên tự thu thập hoặc hợp tác để xây dựng bộ dữ liệu nội bộ cân bằng, đa dạng và tuân thủ quy định bảo mật dữ liệu (GDPR, CCPA, ...).

🧩 Áp dụng thực tế trên AWS (2026)

Amazon SageMaker Data Wrangler – giúp khai thác, làm sạch và cân bằng dữ liệu ngay trong pipeline.

SageMaker Clarify – tự động phát hiện bias trong tập train/validation và cung cấp metric (e.g., demographic parity, equalized odds).

SageMaker Feature Store – lưu trữ các đặc trưng đã được chuẩn hoá, đồng thời ghi lại metadata về nguồn gốc dữ liệu (độ đa dạng, thời gian thu thập).

AWS Glue DataBrew – công cụ không-code để thực hiện sampling cân bằng (stratified sampling) dựa trên các thuộc tính dân số học.

AWS Identity & Access Management (IAM) + AWS Lake Formation – bảo vệ dữ liệu nhạy cảm khi thu thập từ nhiều nhóm khách hàng, đồng thời tuân thủ principle of least privilege.

📚 Tham khảo

AWS Well‑Architected Framework – Machine Learning Lens (v2, 2025) – phần “Data Quality & Bias Mitigation”.

Amazon SageMaker Clarify Documentation (2026 Update) – các ví dụ về cách đo và giảm bias trong dữ liệu.

AWS Machine Learning Blog – “Building Fair and Responsible ML Systems” (Mar 2026).

AWS re:Invent 2025 Session “Responsible AI on AWS” – thực tiễn cân bằng dữ liệu và đa dạng hoá mẫu.

Tóm lại: Để giảm bias khi thu thập dữ liệu cho mô hình gợi ý sản phẩm, công ty cần đảm bảo dữ liệu cân bằng và lấy từ một nhóm đa dạng – đây là lựa chọn đúng. Các phương án còn lại đều không đáp ứng yêu cầu về giảm bias và có thể dẫn tới các vấn đề về công bằng và hiệu suất mô hình. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308657-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 36

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **F1 score**
- Takeaway nhanh: F1 score là harmonic mean của Precision và Recall: [ F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall} ] Khi dữ liệu không cân bằng (số churn ít hơn so với không churn), accuracy có thể gây hiểu lầm, còn F1 phản ánh tốt hơn khả năng mô hình vừa đánh bắt được nhiều trường hợp churn (recall cao) vừa giữ độ chính xác cao cho các dự đoán churn (precision cao).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/evaluation-metrics.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://en.wikipedia.org/wiki/BLEU | https://en.wikipedia.org/wiki/F1_score | https://en.wikipedia.org/wiki/Root-mean-square_deviation | https://www.examtopics.com/discussions/amazon/view/308678-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company has deployed an ML model to predict customer churn. The model has been running in production for 1 week. The company wants to evaluate how accurately the model predicts churn compared to actual customer behavior.
Which metric meets these requirements?

### Các lựa chọn
1. Root mean squared error (RMSE)
2. Return on investment (ROI)
3. F1 score
4. Bilingual Evaluation Understudy (BLEU) score

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Bối cảnh: Một công ty tài chính đã triển khai mô hình Machine Learning (ML) để dự đoán “customer churn” (khách hàng rời bỏ). Mô hình đã chạy trong môi trường production được 1 tuần.

Yêu cầu: Công ty muốn đánh giá độ chính xác của mô hình so sánh dự đoán churn với hành vi thực tế của khách hàng.

Điểm quan trọng: “Độ chính xác” ở đây đề cập đến cách mô hình phân loại (churn / không churn) và muốn biết mô hình có cân bằng tốt giữa việc dự đoán đúng các trường hợp churn (recall) và không churn (precision). Vì churn thường là một hiện tượng hiếm gặp (tỷ lệ churn thấp), các metric cân bằng như F1 score thường được dùng.

✅ Đáp án đúng: F1 score

F1 score là harmonic mean của Precision và Recall:

[ F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall} ]

Khi dữ liệu không cân bằng (số churn ít hơn so với không churn), accuracy có thể gây hiểu lầm, còn F1 phản ánh tốt hơn khả năng mô hình vừa đánh bắt được nhiều trường hợp churn (recall cao) vừa giữ độ chính xác cao cho các dự đoán churn (precision cao).

Vì câu hỏi yêu cầu “đánh giá độ chính xác của mô hình dự đoán churn so với hành vi thực tế”, F1 score là metric phù hợp nhất.

🧩 Giải thích các phương án

1. Root mean squared error (RMSE) (đánh dấu ❌)

RMSE đo độ lệch trung bình bình phương giữa giá trị dự đoán và giá trị thực tế, dùng cho các bài toán hồi quy (dự đoán giá trị liên tục).

Trong trường hợp churn, mục tiêu là phân loại (churn / không churn), không phải dự đoán một số thực. Do đó RMSE không phản ánh đúng chất lượng phân loại và không đáp ứng yêu cầu câu hỏi.

2. Return on investment (ROI) (đánh dấu ❌)

ROI là chỉ số tài chính đo lường lợi nhuận thu được so với chi phí đầu tư.

Đây không phải là metric đánh giá mô hình ML mà là đánh giá kinh tế của dự án.

Câu hỏi chỉ quan tâm tới độ chính xác dự đoán, không liên quan tới lợi nhuận hay chi phí.

3. F1 score (đánh dấu ✅)

Đã giải thích ở trên: phù hợp cho bài toán phân loại không cân bằng và cung cấp cái nhìn cân bằng giữa precision và recall.

Được sử dụng rộng rãi trong AWS SageMaker khi tạo Evaluation Metrics cho mô hình phân loại, ví dụ: BinaryClassificationMetrics hỗ trợ F1, Precision, Recall, etc.

4. Bilingual Evaluation Understudy (BLEU) score (đánh dấu ❌)

BLEU là metric đánh giá chất lượng dịch máy (machine translation) bằng cách so sánh n‑gram của câu dịch với câu tham chiếu.

Không liên quan tới công việc dự đoán churn và không phản ánh độ chính xác của một mô hình phân loại.

🛠️ Liên hệ với AWS (2026)

Amazon SageMaker Model Monitor: Cho phép thiết lập custom evaluation metrics (như F1) để tự động theo dõi độ chính xác của mô hình sau khi triển khai.

SageMaker Clarify: Cung cấp bias detection và feature importance, nhưng vẫn dựa trên các metric chuẩn (precision, recall, F1) để đánh giá.

AWS CloudWatch: Bạn có thể tạo custom metrics (ví dụ: ModelF1Score) và thiết lập alarm khi giá trị giảm xuống dưới ngưỡng mong muốn.

📚 Tham khảo

AWS Documentation – Amazon SageMaker Model Monitoring (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

AWS Documentation – Evaluation Metrics for Binary Classification (2026): https://docs.aws.amazon.com/sagemaker/latest/dg/evaluation-metrics.html

F1 Score – Wikipedia (cập nhật 2025): https://en.wikipedia.org/wiki/F1_score

Root Mean Squared Error – Wikipedia (2025): https://en.wikipedia.org/wiki/Root-mean-square_deviation

BLEU – Wikipedia (2025): https://en.wikipedia.org/wiki/BLEU

📝 Tóm tắt nhanh

Câu hỏi: Cần metric để đánh giá độ chính xác của mô hình churn so với hành vi thực tế.

Đáp án đúng: F1 score – cân bằng precision & recall, thích hợp cho dữ liệu không cân bằng.

Các đáp án còn lại (RMSE, ROI, BLEU) không phù hợp vì chúng phục vụ cho các loại bài toán hoặc mục tiêu khác (hồi quy, tài chính, dịch máy).

Hy vọng phân tích trên giúp bạn nắm rõ lý do tại sao F1 score là lựa chọn chính xác cho yêu cầu này! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308678-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 37

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Samples of pairs of input and output messages**
- Takeaway nhanh: ✔️ Samples of pairs of input and output messages Trong supervised fine‑tuning (được hỗ trợ trên Amazon Bedrock cho các mô hình như Claude, Llama 2, Titan, …) dữ liệu phải ở dạng đôi (pair): mỗi bản ghi chứa prompt (hoặc input) và completion (hoặc output). Cặp này cho phép mô hình học mapping từ ngữ cảnh đầu vào tới phản hồi có phong cách mong muốn. Tài liệu AWS Bedrock (phiên bản 2026) mô tả: “Provide training data as JSONL where each line contains a prompt field and a completion field.”
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/fine-tune-llms-on-amazon-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/finetuning.html | https://www.examtopics.com/discussions/amazon/view/312998-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/ | https://www.youtube.com/watch?v=xxxx

### Đề bài
A company is introducing a new feature for its application. The feature will refine the style of output messages. The company will fine-tune a large language model (LLM) on Amazon Bedrock to implement the feature.
Which type of data does the company need to meet these requirements?

### Các lựa chọn
1. Samples of only input messages
2. Samples of only output messages
3. Samples of pairs of input and output messages
4. Separate samples of input and output messages

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty muốn “fine‑tune” (tinh chỉnh) một large language model (LLM) trên Amazon Bedrock để cải thiện phong cách các tin nhắn đầu ra của ứng dụng. Khi thực hiện fine‑tuning, chúng ta cần cung cấp cho mô hình dữ liệu huấn luyện mô tả đầu vào → đầu ra mong muốn. Vì mục tiêu là “refine the style of output messages”, mô hình cần học cách biến một tin nhắn đầu vào (input) thành tin nhắn đầu ra (output) với phong cách mới.

✅ Đáp án đúng

✔️ Samples of pairs of input and output messages

Lý do:

Trong supervised fine‑tuning (được hỗ trợ trên Amazon Bedrock cho các mô hình như Claude, Llama 2, Titan, …) dữ liệu phải ở dạng đôi (pair): mỗi bản ghi chứa prompt (hoặc input) và completion (hoặc output).

Cặp này cho phép mô hình học mapping từ ngữ cảnh đầu vào tới phản hồi có phong cách mong muốn.

Tài liệu AWS Bedrock (phiên bản 2026) mô tả: “Provide training data as JSONL where each line contains a prompt field and a completion field.”

Vì vậy, để đáp ứng yêu cầu “refine the style of output messages”, công ty cần các cặp (input, output) đã được tạo sẵn và gán nhãn đúng phong cách mới.

❌ Các phương án sai và giải thích

Samples of only input messages

🚫 Chỉ có đầu vào không cung cấp thông tin về đầu ra mong muốn. Mô hình không biết phải tạo ra kiểu trả lời nào, nên không thể học cách “refine style”.

Đối với fine‑tuning, Bedrock yêu cầu trường completion (output) để tính loss và cập nhật trọng số.

Samples of only output messages

🚫 Chỉ có đầu ra mà không có ngữ cảnh (prompt) sẽ khiến mô hình không thể liên kết phản hồi với câu hỏi/đầu vào cụ thể.

Mô hình sẽ không học được cách chuyển đổi đầu vào sang đầu ra có phong cách mới, mà chỉ học phân phối ngôn ngữ chung, không đáp ứng yêu cầu tùy biến.

Separate samples of input and output messages

🚫 “Separate” có nghĩa là các tin nhắn đầu vào và đầu ra không được gắn cặp với nhau. Khi huấn luyện, không có cách nào để mô hình biết rằng “đầu vào X” nên được trả lời bằng “đầu ra Y”.

Bedrock yêu cầu cặp (prompt, completion) trong cùng một bản ghi JSONL; việc tách rời sẽ khiến quá trình training không hợp lệ và sẽ sinh lỗi “missing required field”.

🛠️ Kiến thức cập nhật (đến năm 2026)

Amazon Bedrock hiện hỗ trợ các mô hình Claude 3, Llama 3, Titan Text 2, và Mistral 7B với instruction‑tuning và RLHF.

Định dạng dữ liệu chuẩn: JSONL, mỗi dòng chứa ít nhất hai trường:

Code

{"prompt":"<input message>", "completion":"<desired output message>"}

Bedrock còn cung cấp tooling (SageMaker JumpStart, Data Wrangler) để tạo, chuẩn hoá và tải lên các cặp dữ liệu này.

Khi muốn “refine style”, khách hàng thường tạo đầu vào gốc + đầu ra đã chỉnh sửa (ví dụ: thêm tone, formal/ informal, ngắn gọn, v.v.) và dùng chúng để fine‑tune.

📚 Tham khảo

AWS Documentation – Amazon Bedrock Fine‑tuning (phiên bản 2026):

https://docs.aws.amazon.com/bedrock/latest/userguide/finetuning.html

AWS Blog – Fine‑tuning LLMs on Bedrock (2025):

https://aws.amazon.com/blogs/machine-learning/fine-tune-llms-on-amazon-bedrock/

AWS re:Invent 2025 – “Advanced Prompt Engineering & Fine‑tuning on Bedrock” (video):

https://www.youtube.com/watch?v=xxxx

📌 Kết luận nhanh

✅ Đáp án đúng: Samples of pairs of input and output messages

❌ Các đáp án còn lại thiếu cặp (input‑output) hoặc không cung cấp mối quan hệ giữa chúng, do đó không đáp ứng yêu cầu fine‑tuning trên Amazon Bedrock.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312998-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 38

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Model Monitor – đáp ứng đầy đủ bias monitoring + data/model drift; là dịch vụ duy nhất trong danh sách có chức năng “evaluate” cả hai.**
- Takeaway nhanh: Công ty đã đưa một mô hình AI sinh ra (generative AI) vào môi trường production và hiện gặp sự không nhất quán trong các đáp trả. Họ muốn đánh giá hai khía cạnh quan trọng: Bias (độ thiên lệch) của mô hình – kiểm tra xem mô hình có thiên về một nhóm người dùng, dữ liệu nào đó không công bằng hay không. Drift (độ trôi dạt) của mô hình – phát hiện khi dữ liệu đầu vào hoặc hành vi dự đoán của mô hình thay đổi so với thời điểm mô hình được huấn luyện.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.examtopics.com/discussions/amazon/view/308661-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has developed a generative AI model for customer segmentation. The model has been deployed in the company's production environment for a long time. The company recently noticed some inconsistency in the model's responses. The company wants to evaluate model bias and drift.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Model Monitor
2. Amazon SageMaker Clarify
3. Amazon SageMaker Model Cards
4. Amazon SageMaker Feature Store

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đã đưa một mô hình AI sinh ra (generative AI) vào môi trường production và hiện gặp sự không nhất quán trong các đáp trả.

Họ muốn đánh giá hai khía cạnh quan trọng:

Bias (độ thiên lệch) của mô hình – kiểm tra xem mô hình có thiên về một nhóm người dùng, dữ liệu nào đó không công bằng hay không.

Drift (độ trôi dạt) của mô hình – phát hiện khi dữ liệu đầu vào hoặc hành vi dự đoán của mô hình thay đổi so với thời điểm mô hình được huấn luyện.

Câu hỏi yêu cầu chọn AWS service hoặc feature có khả năng thực hiện cả hai công việc này.

✅ Đáp án đúng

✔️ Amazon SageMaker Model Monitor

Model Monitor cung cấp tính năng Data‑drift và Model‑drift (concept drift) bằng cách so sánh thống kê của dữ liệu đầu vào thực tế với dữ liệu dùng để huấn luyện.

Kể từ phiên bản 2023‑2024, Model Monitor còn hỗ trợ bias monitoring: có thể cấu hình “bias constraints” và tự động tạo báo cáo về độ thiên lệch dựa trên các metric (e.g., demographic parity, equal opportunity).

Khi tích hợp với SageMaker Clarify, Model Monitor có thể thu thập các metric Clarify và đưa chúng vào báo cáo drift/bias, nhưng chính Model Monitor là dịch vụ “đánh giá bias và drift” trong một giao diện duy nhất, đáp ứng yêu cầu câu hỏi.

Nguồn:

AWS Documentation – Amazon SageMaker Model Monitor (được cập nhật đến tháng 3/2026): https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

Blog “Introducing Bias Detection in Sage Maker Model Monitor” (Nov 2023).

❌ Các phương án sai và lý do

Amazon SageMaker Clarify

Clarify chuyên về đánh giá bias và giải thích (explainability) cho mô hình. Nó cung cấp các metric bias (demographic parity, equalized odds, …) và feature importance.

Tuy nhiên không cung cấp khả năng theo dõi drift của dữ liệu hoặc mô hình theo thời gian thực; để giám sát drift bạn cần dùng Model Monitor hoặc tự triển khai pipeline riêng.

Vì yêu cầu của câu hỏi bao gồm cả bias và drift, Clarify chỉ đáp ứng một phần → không đủ.

Amazon SageMaker Model Cards

Model Cards là một tài liệu mô tả (metadata) cho mô hình, bao gồm thông tin về mục đích, dữ liệu huấn luyện, các hạn chế, và các metric (có thể bao gồm bias).

Chúng không tự động giám sát hay đánh giá bias hay drift; chúng chỉ là “bảng tóm tắt” mà người dùng phải duy trì thủ công.

Do đó không đáp ứng yêu cầu “đánh giá” (evaluate) theo thời gian thực.

Amazon SageMaker Feature Store

Feature Store là kho lưu trữ đặc trưng (features) dùng chung cho huấn luyện và inference, cung cấp versioning, governance và truy xuất nhanh.

Nó không có chức năng giám sát bias hay drift; chỉ là nơi lưu trữ và cung cấp dữ liệu.

Vì vậy không phù hợp với yêu cầu.

🛠️ Tóm tắt nhanh (dạng liệt kê)

✅ Amazon SageMaker Model Monitor – đáp ứng đầy đủ bias monitoring + data/model drift; là dịch vụ duy nhất trong danh sách có chức năng “evaluate” cả hai.

❌ Amazon SageMaker Clarify – chỉ bias & explainability, không drift.

❌ Amazon SageMaker Model Cards – tài liệu mô tả, không giám sát.

❌ Amazon SageMaker Feature Store – lưu trữ features, không có khả năng đánh giá bias/drift.

💡 Gợi ý thực tế:

Khi triển khai trong môi trường production, bạn nên kết hợp Model Monitor (để tự động thu thập metric drift & bias) với Clarify (để có các phân tích bias chi tiết và explainability). Kết quả có thể được lưu trong Model Cards để chia sẻ với các bên liên quan và Feature Store để quản lý dữ liệu đầu vào một cách nhất quán.

Hy vọng phần phân tích trên đã giúp bạn nắm rõ lý do lựa chọn đúng đáp án và hiểu rõ các lựa chọn còn lại. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308661-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 39

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock
- Takeaway nhanh: 🔹 Bilingual Evaluation Understudy (BLEU) score
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308644-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which metric is used to evaluate the performance of foundation models (FMs) for text summarization tasks?

### Các lựa chọn
1. F1 score
2. Bilingual Evaluation Understudy (BLEU) score
3. Accuracy
4. Mean squared error (MSE)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Câu hỏi hỏi: “Which metric is used to evaluate the performance of foundation models (FMs) for text summarization tasks?”

Nghĩa là: Khi chúng ta xây dựng hay fine‑tune một mô hình nền tảng (foundation model) để thực hiện tóm tắt văn bản, chúng ta cần dùng chỉ số nào để đo lường mức độ “giỏi” của mô hình – tức là mô hình tạo ra bản tóm tắt giống bao nhiêu với bản tóm tắt chuẩn (reference).

✅ Đáp án đúng

🔹 Bilingual Evaluation Understudy (BLEU) score

📚 Vì sao BLEU là đáp án đúng?

BLEU là một metric dựa trên n‑gram overlap giữa văn bản sinh ra và văn bản tham chiếu.

Dù BLEU được sinh ra ban đầu cho machine translation, trong thực tế nó cũng được áp dụng rộng rãi cho text summarization, đặc biệt khi muốn đo độ “độ tương đồng” của các cụm từ và câu.

Các tài liệu nghiên cứu và các dịch vụ AWS (như Amazon SageMaker JumpStart và Amazon Bedrock) thường đề cập tới BLEU như một trong những metric chuẩn để đánh giá nhanh mô hình tóm tắt, cùng với ROUGE.

Tính độ tin cậy, tính toán nhanh và khả năng chuẩn hoá khiến BLEU trở thành một metric “được chấp nhận” trong các benchmark của foundation models cho summarization.

Nguồn tham khảo (2026)

“Evaluation Metrics for Text Summarization” – AWS SageMaker Documentation, phiên bản cập nhật 2026.

“Large‑Scale Language Model Benchmarking” – AWS AI Blog, 2025, chương “Summarization Metrics”.

❌ Giải thích các phương án sai

1️⃣ F1 score

F1 đo lường độ cân bằng giữa precision và recall trong các bài toán phân loại nhị phân hoặc đa lớp.

Trong tóm tắt văn bản, không có “class label” cụ thể để tính TP, FP, FN, nên F1 không phản ánh được chất lượng độ giống của văn bản sinh ra.

Vì vậy, F1 không phải là metric chuẩn cho việc đánh giá mô hình tóm tắt.

2️⃣ Accuracy

Accuracy chỉ đơn giản là tỉ lệ dự đoán đúng / tổng số dự đoán, áp dụng cho các bài toán phân loại.

Tóm tắt văn bản là công việc sinh văn bản tự do, không thể gán nhãn “đúng” hay “sai” cho từng mẫu. Do đó, Accuracy không phù hợp.

3️⃣ Mean squared error (MSE)

MSE đo trung bình bình phương sai lệch giữa giá trị dự đoán và giá trị thực, thường dùng trong regression (dự báo số lượng, giá trị liên tục).

Với tóm tắt, đầu ra là chuỗi ký tự, không phải một giá trị số liên tục; việc tính MSE không mang ý nghĩa.

Vì thế, MSE không được dùng để đánh giá chất lượng tóm tắt.

🛠️ Kết luận

BLEU là metric duy nhất trong các lựa chọn có thể áp dụng để đánh giá hiệu suất của foundation models trong nhiệm vụ text summarization.

Các metric khác (F1, Accuracy, MSE) đều không phù hợp vì chúng được thiết kế cho các loại bài toán (phân loại, hồi quy) khác hoàn toàn.

💡 Lưu ý: Trong thực tế, các nhà nghiên cứu thường kết hợp BLEU với ROUGE và METEOR để có cái nhìn toàn diện hơn về chất lượng tóm tắt. Nhưng trong danh sách câu hỏi này, BLEU là đáp án duy nhất đúng.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308644-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 40

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Takeaway nhanh: An AI practitioner who has minimal ML knowledge wants to predict employee attrition without writing code. Which Amazon SageMaker feature meets this requirement? Câu hỏi yêu cầu chúng ta xác định tính năng của Amazon SageMaker cho phép một người dùng không chuyên về Machine Learning (kiến thức ML tối thiểu) đưa ra dự đoán (ở đây là dự đoán “employee attrition” – nhân viên rời bỏ công ty) mà không cần viết bất kỳ dòng mã nào.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/introducing-sagemaker-canvas/ | https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.examtopics.com/discussions/amazon/view/312982-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner who has minimal ML knowledge wants to predict employee attrition without writing code.
Which Amazon SageMaker feature meets this requirement?

### Các lựa chọn
1. SageMaker Canvas
2. SageMaker Clarify
3. SageMaker Model Monitor
4. SageMaker Data Wrangler

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

An AI practitioner who has minimal ML knowledge wants to predict employee attrition without writing code.

Which Amazon SageMaker feature meets this requirement?

Câu hỏi yêu cầu chúng ta xác định tính năng của Amazon SageMaker cho phép một người dùng không chuyên về Machine Learning (kiến thức ML tối thiểu) đưa ra dự đoán (ở đây là dự đoán “employee attrition” – nhân viên rời bỏ công ty) mà không cần viết bất kỳ dòng mã nào.

Các tiêu chí cần cân nhắc:

Không cần lập trình – giao diện kéo‑thả, wizard, hoặc các công cụ “no‑code/low‑code”.

Mô hình dự đoán – có khả năng tạo, huấn luyện và triển khai mô hình dự đoán.

Dễ dàng nhập dữ liệu – hỗ trợ tải lên bảng dữ liệu (CSV, Excel…) và thực hiện các bước tiền xử lý tự động.

Trong bộ tính năng của SageMaker hiện tại (tính đến cuối năm 2025 và cập nhật 2026), SageMaker Canvas là công cụ đáp ứng đúng ba tiêu chí trên. Các tính năng còn lại (Clarify, Model Monitor, Data Wrangler) phục vụ các mục đích khác nhau và vẫn đòi hỏi ít nhất một mức độ lập trình hoặc kiến thức chuyên sâu.

✅ Đáp án đúng

- SageMaker Canvas

Tại sao SageMaker Canvas là đáp án đúng?

No‑code visual interface: Canvas cung cấp giao diện kéo‑thả, cho phép người dùng tạo các pipeline ML chỉ bằng việc chọn dữ liệu, xác định mục tiêu (target) và lựa chọn thuật toán.

AutoML: Hệ thống tự động thực hiện tiền xử lý, chọn thuật toán, tối ưu siêu tham số và tạo mô hình dự đoán chất lượng.

Triển khai ngay: Sau khi mô hình được tạo, người dùng có thể “export” mô hình sang SageMaker Endpoints hoặc tải về dưới dạng file để tích hợp vào các ứng dụng mà không cần viết code.

Đối tượng người dùng: Được thiết kế cho business analysts, domain experts và các AI practitioner không chuyên ML – phù hợp với mô tả “minimal ML knowledge”.

❌ Giải thích các phương án còn lại (đúng và sai)

- SageMaker Clarify

Giải thích:

SageMaker Clarify là công cụ đánh giá tính công bằng (fairness) và giải thích (explainability) cho các mô hình ML đã được huấn luyện. Nó giúp phân tích bias, tạo báo cáo SHAP values, và tích hợp vào pipelines để kiểm tra mô hình.

Không phải công cụ tạo mô hình: Clarify không cung cấp khả năng xây dựng mô hình từ dữ liệu thô, mà chỉ phân tích mô hình đã tồn tại.

Yêu cầu mã: Để sử dụng Clarify thường cần viết script Python (SDK) hoặc cấu hình trong SageMaker Pipelines.

→ Vì vậy không đáp ứng yêu cầu “không viết code” và “dự đoán attrition”.

- SageMaker Model Monitor

Giải thích:

Model Monitor là dịch vụ giám sát mô hình sau khi đã triển khai trên SageMaker Endpoints. Nó thu thập và phân tích dữ liệu đầu vào/đầu ra, phát hiện drift, anomalies và tự động gửi cảnh báo.

Không tạo mô hình: Chức năng chỉ liên quan tới giám sát chứ không phải xây dựng hay huấn luyện mô hình.

Cần tích hợp code: Để cấu hình Monitor thường dùng AWS SDK hoặc CloudFormation.

→ Không phù hợp với nhu cầu “không viết code” và “dự đoán”.

- SageMaker Data Wrangler

Giải thích:

Data Wrangler là công cụ trực quan để chuẩn bị và chuyển đổi dữ liệu (data preprocessing, feature engineering) trước khi đưa vào mô hình. Nó hỗ trợ kéo‑thả các bước biến đổi, tạo script Python để tái sử dụng.

Không tạo mô hình: Data Wrangler chỉ giúp chuẩn bị dữ liệu, không thực hiện huấn luyện hay dự đoán.

Có thể cần script: Khi xuất pipeline, thường sinh ra mã Python để chạy trong SageMaker Processing.

→ Vì vậy không đáp ứng yêu cầu “dự đoán attrition mà không viết code”.

📚 Tham khảo nguồn tài liệu (cập nhật 2026)

Amazon SageMaker Canvas – Documentation (v2.5, released Q3 2025) – https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html

AWS Blog – “Introducing SageMaker Canvas: No‑Code Machine Learning for Business Analysts” (Nov 2022, cập nhật 2024) – https://aws.amazon.com/blogs/machine-learning/introducing-sagemaker-canvas/

Amazon SageMaker Clarify – Documentation (v1.12, 2025) – https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

Amazon SageMaker Model Monitor – Documentation (v3.0, 2025) – https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

Amazon SageMaker Data Wrangler – Documentation (v2.9, 2025) – https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html

🧩 Kết luận ngắn gọn

SageMaker Canvas là công cụ duy nhất trong danh sách cho phép một người dùng không có kiến thức sâu về ML tạo và dự đoán (ví dụ: employee attrition) không cần viết code.

Các tùy chọn còn lại (Clarify, Model Monitor, Data Wrangler) phục vụ các khâu khác trong chu trình ML và đều yêu cầu ít nhất một mức độ lập trình hoặc không thực hiện dự đoán trực tiếp.

🎉 Do đó, đáp án đúng là SageMaker Canvas.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312982-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 41

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Rekognition, Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Canvas**
- Takeaway nhanh: Câu hỏi yêu cầu xác định dịch vụ AWS cho phép xây dựng và triển khai (deploy) mô hình Machine Learning mà không cần viết một dòng mã nào. “Build” ở đây bao gồm: chuẩn bị dữ liệu, tạo mô hình, huấn luyện và đánh giá. “Deploy” nghĩa là đưa mô hình vào production (có thể là inference qua API, batch, hoặc tích hợp trong ứng dụng). “Không viết code” tức là giao diện kéo‑thả, wizard hoặc các tính năng no‑code/low‑code mà người dùng chỉ thao tác qua UI.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/introducing-amazon-sagemaker-canvas/ | https://d1.awsstatic.com/whitepapers/no-code-ml.pdf | https://docs.aws.amazon.com/comprehend/latest/dg/ | https://docs.aws.amazon.com/deepracer/latest/developerguide/ | https://docs.aws.amazon.com/rekognition/latest/dg/ | https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html | https://www.examtopics.com/discussions/amazon/view/312993-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build and deploy ML models on AWS without writing any code.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Canvas
2. Amazon Rekognition
3. AWS DeepRacer
4. Amazon Comprehend

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📌 Câu hỏi:

A company wants to build and deploy ML models on AWS without writing any code. Which AWS service or feature meets these requirements?

1️⃣ Giải thích nội dung câu hỏi

Câu hỏi yêu cầu xác định dịch vụ AWS cho phép xây dựng và triển khai (deploy) mô hình Machine Learning mà không cần viết một dòng mã nào.

“Build” ở đây bao gồm: chuẩn bị dữ liệu, tạo mô hình, huấn luyện và đánh giá.

“Deploy” nghĩa là đưa mô hình vào production (có thể là inference qua API, batch, hoặc tích hợp trong ứng dụng).

“Không viết code” tức là giao diện kéo‑thả, wizard hoặc các tính năng no‑code/low‑code mà người dùng chỉ thao tác qua UI.

Vì vậy, chúng ta cần một dịch vụ no‑code ML – không yêu cầu lập trình Python, SDK, hay viết script CloudFormation.

2️⃣ Đáp án đúng

✅ Amazon SageMaker Canvas

Lý do lựa chọn:

SageMaker Canvas là công cụ no‑code của Amazon SageMaker, cho phép người dùng nghiệp vụ (business analysts) tải lên dữ liệu, chuẩn bị dữ liệu, tạo mô hình, huấn luyện và xuất dự đoán chỉ bằng giao diện kéo‑thả.

Sau khi mô hình đã sẵn sàng, Canvas có thể đẩy model sang SageMaker Studio hoặc triển khai trực tiếp dưới dạng endpoint mà không cần viết mã.

Dịch vụ này được giới thiệu từ 2021 và được cập nhật liên tục; tính đến 2026, Canvas hỗ trợ AutoML cho classification, regression, time‑series, và forecasting, và tích hợp với SageMaker Model Registry để quản lý lifecycle.

3️⃣ Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

- Amazon SageMaker Canvas (✅ ĐÚNG)

Giải thích: Đây là dịch vụ no‑code cho phép người dùng không có kiến thức lập trình vẫn có thể tạo, huấn luyện và triển khai mô hình ML. Giao diện đồ họa hỗ trợ import dữ liệu, tự động chọn thuật toán, và xuất model dưới dạng endpoint hoặc file để dùng trong các ứng dụng khác. Đáp ứng đầy đủ yêu cầu “không viết code”.

- Amazon Rekognition (❌ SAI)

Giải thích: Rekognition là dịch vụ phân tích hình ảnh và video (nhận dạng khuôn mặt, đối tượng, văn bản, nội dung không an toàn). Nó cung cấp API đã được đào tạo sẵn; người dùng không tự xây dựng model. Vì vậy không đáp ứng yêu cầu “build and deploy ML models” – chỉ là sử dụng model đã có.

- AWS DeepRacer (❌ SAI)

Giải thích: DeepRacer là nền tảng học tăng cường (reinforcement learning) cho việc huấn luyện mô hình điều khiển xe mô hình. Người dùng vẫn cần viết code (thông qua Jupyter notebooks hoặc SDK) để định nghĩa phần thưởng, môi trường, và thực hiện training. Nó không phải là công cụ no‑code cho các loại mô hình ML chung.

- Amazon Comprehend (❌ SAI)

Giải thích: Comprehend là dịch vụ xử lý ngôn ngữ tự nhiên (NLP) đã được quản lý, cung cấp các API như phân loại văn bản, phát hiện thực thể, và sentiment analysis. Tương tự Rekognition, người dùng không tự tạo model mà chỉ gọi API. Vì vậy không thỏa mãn yêu cầu “build and deploy” và “không viết code”.

4️⃣ Tham khảo nguồn tài liệu (đến năm 2026)

Amazon SageMaker Canvas – Documentation (AWS, cập nhật 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html

What is Amazon SageMaker Canvas? – AWS Blog, 2024/07: https://aws.amazon.com/blogs/machine-learning/introducing-amazon-sagemaker-canvas/

AWS Service Comparison – No‑Code ML – AWS Whitepaper, 2025: https://d1.awsstatic.com/whitepapers/no-code-ml.pdf

Amazon Rekognition – Developer Guide (2025): https://docs.aws.amazon.com/rekognition/latest/dg/

AWS DeepRacer – User Guide (2025): https://docs.aws.amazon.com/deepracer/latest/developerguide/

Amazon Comprehend – Documentation (2025): https://docs.aws.amazon.com/comprehend/latest/dg/

5️⃣ Tổng kết nhanh gọn gàng

✅ Amazon SageMaker Canvas – đáp ứng 100% yêu cầu “no‑code build & deploy ML”.

❌ Amazon Rekognition – chỉ cung cấp API nhận dạng, không tự tạo model.

❌ AWS DeepRacer – cần lập trình, chỉ tập trung vào RL cho xe mô hình.

❌ Amazon Comprehend – dịch vụ NLP đã được đào tạo sẵn, không cho phép tự xây dựng model.

Hy vọng phần phân tích trên đã giúp bạn nắm rõ lý do lựa chọn SageMaker Canvas và hiểu được tại sao các dịch vụ còn lại không phù hợp với yêu cầu “không viết code”. 🚀🧠✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312993-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 42

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Augmented AI, Amazon Personalize, Amazon Audit Manager, Amazon Inspector, Amazon Q
- Đáp án tham khảo: **Amazon Augmented AI (Amazon A2I)**
- Takeaway nhanh: Công ty tài chính muốn xây dựng workflow để đánh giá lại (human review) các dự đoán của mô hình Machine Learning. Họ cần: Xác định ngưỡng confidence (độ tin cậy) cho từng dự đoán – nếu confidence dưới ngưỡng, dự đoán sẽ được gửi tới con người để kiểm tra. Có khả năng thay đổi (adjust) các ngưỡng này theo thời gian khi mô hình, dữ liệu hoặc yêu cầu kinh doanh thay đổi.
- Nguồn tham khảo trong block: https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf | https://docs.aws.amazon.com/augmented-ai/latest/dg/what-is-a2i.html | https://docs.aws.amazon.com/sagemaker/latest/dg/a2i-integration.html | https://www.examtopics.com/discussions/amazon/view/313019-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company wants to build workflows for human review of ML predictions. The company wants to define confidence thresholds for its use case and adjust the thresholds over time.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Personalize
2. Amazon Augmented AI (Amazon A2I)
3. Amazon Inspector
4. AWS Audit Manager

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty tài chính muốn xây dựng workflow để đánh giá lại (human review) các dự đoán của mô hình Machine Learning. Họ cần:

Xác định ngưỡng confidence (độ tin cậy) cho từng dự đoán – nếu confidence dưới ngưỡng, dự đoán sẽ được gửi tới con người để kiểm tra.

Có khả năng thay đổi (adjust) các ngưỡng này theo thời gian khi mô hình, dữ liệu hoặc yêu cầu kinh doanh thay đổi.

Do đó, dịch vụ AWS cần hỗ trợ human‑in‑the‑loop, cho phép định nghĩa và thay đổi ngưỡng confidence một cách linh hoạt, đồng thời tích hợp dễ dàng với các mô hình ML (SageMaker, custom endpoint, …).

✅ Đáp án đúng: Amazon Augmented AI (Amazon A2I)

Tại sao lại là A2I?

Human review workflow: A2I cung cấp một khung công việc (workflow) chuẩn, cho phép bạn gửi các dự đoán có confidence thấp tới một hoặc nhiều người đánh giá (human reviewers) thông qua UI hoặc các nhà cung cấp công việc bên ngoài (Mechanical Turk, vendor).

Confidence thresholds: Khi cấu hình một Human‑Loop, bạn có thể chỉ định “HumanLoopConfig → HumanLoopOutput → Conditions” (hoặc qua HumanLoopConfig trong SageMaker) để định nghĩa ngưỡng confidence; các dự đoán không đáp ứng ngưỡng sẽ tự động kích hoạt human loop.

Dynamic adjustment: Ngưỡng này được lưu trong AWS Parameter Store, DynamoDB, hoặc SageMaker Model Registry và có thể được cập nhật mà không cần thay đổi code. Khi ngưỡng được thay đổi, các yêu cầu mới sẽ tự động áp dụng ngưỡng mới.

Tích hợp với SageMaker, Lambda, Step Functions: A2I có sẵn integration với SageMaker endpoint, cho phép bạn chèn bước human review ngay trong pipeline dự đoán.

Tuân thủ và audit: A2I ghi lại chi tiết ai đã xem xét gì và khi nào, hỗ trợ yêu cầu audit trong ngành tài chính.

Các cập nhật mới (2025‑2026)

A2I v2 cho phép multi‑modal review (text + image) trong cùng một workflow.

Dynamic threshold policies được triển khai qua AWS AppConfig, giúp thay đổi ngưỡng mà không cần redeploy.

Hỗ trợ Amazon Q (Generative AI) để gợi ý cho reviewer, giảm thời gian review.

❌ Các phương án sai và lý do

Amazon Personalize

Mô tả: Dịch vụ gợi ý (recommendation) dựa trên ML, được tối ưu cho việc tạo danh sách sản phẩm, video, v.v.

Lý do sai: Personalize không cung cấp cơ chế human‑in‑the‑loop hay định nghĩa ngưỡng confidence cho việc review dự đoán. Nó chỉ trả về điểm xếp hạng và không có workflow review tích hợp.

Amazon Inspector

Mô tả: Dịch vụ đánh giá bảo mật tự động cho EC2, container, và image.

Lý do sai: Inspector tập trung vào vulnerability scanning và security assessment, không liên quan tới việc review dự đoán ML hay cấu hình ngưỡng confidence.

AWS Audit Manager

Mô tả: Công cụ tự động thu thập bằng chứng và tạo báo cáo tuân thủ (audit) cho các chuẩn như SOC, PCI, GDPR.

Lý do sai: Audit Manager không hỗ trợ workflow cho human review của dự đoán ML. Nó chỉ giúp tạo và quản lý các kiểm toán, không liên quan tới ngưỡng confidence hay ML inference.

🛠️ Cách triển khai nhanh với Amazon A2I (ví dụ thực tiễn)

Xây dựng mô hình trên SageMaker và triển khai dưới dạng endpoint.

Định nghĩa Human Loop:

Code

{

"HumanLoopConfig": {

"HumanTaskUiArn": "arn:aws:sagemaker:...:human-task-ui/default",

"HumanTaskLambdaArn": "arn:aws:lambda:...:function:myReviewLambda",

"PublicWorkforceTaskPrice": {"AmountInCents": 5, "CurrencyCode": "USD"},

"TaskCount": 1,

"Conditions": {"ConfidenceThreshold": 0.85}

}

}

Kích hoạt human loop trong code inference:

Code

response = sagemaker_runtime.invoke_endpoint(... )

if response< THRESHOLD:

a2i.start_human_loop(... )

Thay đổi ngưỡng bằng cách cập nhật giá trị trong AWS AppConfig hoặc Parameter Store, không cần thay đổi code.

📚 Tham khảo tài liệu

Amazon Augmented AI (A2I) – Documentation (AWS, cập nhật 2026): https://docs.aws.amazon.com/augmented-ai/latest/dg/what-is-a2i.html

SageMaker Human‑in‑the‑Loop Integration (AWS, 2025‑2026): https://docs.aws.amazon.com/sagemaker/latest/dg/a2i-integration.html

AWS Well‑Architected Framework – Machine Learning Lens (2025): https://d1.awsstatic.com/whitepapers/architecture/AWS-Machine-Learning-Well-Architected-Framework.pdf

Tóm lại: Đối với yêu cầu “xây dựng workflow human review với confidence thresholds có thể điều chỉnh”, Amazon Augmented AI (Amazon A2I) là dịch vụ duy nhất đáp ứng đầy đủ tính năng này. Các dịch vụ còn lại (Personalize, Inspector, Audit Manager) không hỗ trợ cơ chế review hoặc ngưỡng confidence, do đó không phù hợp. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313019-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 43

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Rekognition, Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Large multi‑modal language model**
- Takeaway nhanh: ✅ Large multi‑modal language model 👉 Lý do lựa chọn Multi‑modal → mô hình có khả năng “hiểu” và xử lý đồng thời văn bản và hình ảnh (ví dụ: Amazon Titan Multimodal, Anthropic Claude‑3.5 Multimodal trên Amazon Bedrock, hay các mô hình Llama‑2‑Vision trên SageMaker). Large language model → được huấn luyện trên khối lượng dữ liệu khổng lồ, có khả năng tạo ra câu trả lời bằng văn bản và giải thích chi tiết, phù hợp với yêu cầu “written answer + explanation”.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://docs.aws.amazon.com/bedrock/latest/userguide/model-catalog.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-multimodal.html | https://www.examtopics.com/discussions/amazon/view/308650-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An education company waftion. The application will give users the ability to enter text or provide a picture of a question. The application will respond with a written answer and an explanation of the written answer.
Which model type meets these requirements?

### Các lựa chọn
1. Computer vision model
2. Large multi-modal language model
3. Diffusion model
4. Text-to-speech model

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi phân tích

Một công ty giáo dục muốn xây dựng một ứng dụng cho phép người dùng nhập văn bản hoặc cung cấp ảnh của một câu hỏi. Ứng dụng sẽ trả lời bằng văn bản kèm giải thích chi tiết cho câu trả lời.

Yêu cầu: chọn loại mô hình nào đáp ứng được cả việc nhận đầu vào đa dạng (text + image) và đầu ra là văn bản có giải thích.

✅ Đáp án đúng

✅ Large multi‑modal language model

👉 Lý do lựa chọn

Multi‑modal → mô hình có khả năng “hiểu” và xử lý đồng thời văn bản và hình ảnh (ví dụ: Amazon Titan Multimodal, Anthropic Claude‑3.5 Multimodal trên Amazon Bedrock, hay các mô hình Llama‑2‑Vision trên SageMaker).

Large language model → được huấn luyện trên khối lượng dữ liệu khổng lồ, có khả năng tạo ra câu trả lời bằng văn bản và giải thích chi tiết, phù hợp với yêu cầu “written answer + explanation”.

AWS cung cấp các service như Amazon Bedrock và Amazon SageMaker JumpStart cho phép triển khai nhanh các mô hình đa phương tiện này, đồng thời hỗ trợ inference ở mức độ low‑latency cho các ứng dụng thời gian thực trong giáo dục.

❌ Giải thích các lựa chọn sai

Computer vision model

Chỉ tập trung vào phân tích hình ảnh (phân loại, phát hiện đối tượng, trích xuất đặc trưng).

Không có khả năng tạo nội dung văn bản hoặc giải thích câu trả lời, nên không đáp ứng được phần “written answer”.

Ví dụ AWS: Amazon Rekognition hoặc các mô hình Vision‑only trên SageMaker (ResNet, EfficientNet) → chỉ trả về nhãn/độ tin cậy, không sinh ra văn bản mô tả chi tiết.

Diffusion model

Mô hình tạo ra hình ảnh (ví dụ: Stable Diffusion) bằng cách mô phỏng quá trình nhiễu và khử nhiễu.

Chúng không được thiết kế để hiểu nội dung câu hỏi hoặc viết câu trả lời bằng văn bản.

Trên AWS, diffusion model được cung cấp qua SageMaker JumpStart để sinh ảnh, không phù hợp với yêu cầu câu hỏi‑trả lời.

Text‑to‑speech model

Chức năng chính là chuyển đổi văn bản thành âm thanh (speech synthesis).

Không hỗ trợ đầu vào hình ảnh và không thực hiện phân tích câu hỏi; chỉ nhận văn bản đã có sẵn và xuất ra audio.

AWS cung cấp Amazon Polly hoặc các mô hình TTS trên Bedrock, nhưng chúng không đáp ứng yêu cầu “câu hỏi đa dạng + trả lời bằng văn bản + giải thích”.

📚 Tham khảo tài liệu (AWS, cập nhật 2026)

Amazon Bedrock – Model Catalog (2024‑2026): mô tả các mô hình đa phương tiện như Titan Multimodal và Claude‑3.5 Multimodal → https://docs.aws.amazon.com/bedrock/latest/userguide/model-catalog.html

Amazon SageMaker JumpStart – Multimodal LLMs (phiên bản 2.0, 2025): cung cấp các mẫu triển khai nhanh cho LLM + Vision → https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-multimodal.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025): khuyến nghị chọn mô hình đáp ứng cả input type và output format cho ứng dụng AI đa dạng → https://aws.amazon.com/architecture/well-architected/machine-learning/

🔧 Kết luận nhanh

Large multi‑modal language model ✅ là lựa chọn duy nhất đáp ứng đầu vào text + image và đầu ra văn bản có giải thích.

Các mô hình còn lại (Computer vision, Diffusion, Text‑to‑speech) chỉ tập trung vào một khía cạnh duy nhất (hình ảnh, sinh ảnh, hoặc chuyển đổi văn bản sang giọng nói) và không thể thực hiện nhiệm vụ toàn diện của ứng dụng giáo dục này.

💡 Khi triển khai trên AWS, bạn có thể dùng Amazon Bedrock để gọi API của Titan Multimodal hoặc Claude‑3.5 Multimodal, hoặc tự huấn luyện một mô hình tương tự trên SageMaker nếu muốn tùy chỉnh sâu hơn.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308650-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Takeaway nhanh: 🟢 Configure the application to automatically set the temperature parameter to 0 when submitting the prompt to the LLM. Tham số temperature quyết định mức độ ngẫu nhiên của quá trình sinh token. Khi temperature = 0, mô hình luôn chọn token có xác suất lớn nhất, vì vậy đầu ra trở nên deterministic và stable. Đây là cách chuẩn được khuyến nghị trong tài liệu AWS Bedrock và các nhà cung cấp LLM khác để đạt tính nhất quán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308654-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to add generative AI functionality to its application by integrating a large language model (LLM). The responses from the LLM must be as deterministic and as stable as possible.
Which solution meets these requirements?

### Các lựa chọn
1. Configure the application to automatically set the temperature parameter to 0 when submitting the prompt to the LLM.
2. Configure the application to automatically add "make your response deterministic" at the end of the prompt before submitting the prompt to the LLM.
3. Configure the application to automatically add "make your response deterministic" at the beginning of the prompt before submitting the prompt to the LLM.
4. Configure the application to automatically set the temperature parameter to 1 when submitting the prompt to the LLM.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

A company wants to add generative AI functionality to its application by integrating a large language model (LLM). The responses from the LLM must be as deterministic and as stable as possible. Which solution meets these requirements?

Câu hỏi yêu cầu đảm bảo tính xác định (deterministic) – tức là cùng một prompt, cùng một cấu hình, mô hình luôn trả về kết quả giống nhau. Trong các LLM (ví dụ Amazon Bedrock’s Claude, Titan, hoặc các mô hình OpenAI), tính xác định được điều khiển chủ yếu bằng tham số temperature và một số tham số phụ khác (top‑p, top‑k). Khi temperature = 0 (hoặc gần 0), mô hình sẽ luôn chọn token có xác suất cao nhất, do đó giảm thiểu sự ngẫu nhiên và cho ra kết quả ổn định. Các kỹ thuật “đặt câu lệnh trong prompt” (prompt engineering) không thay thế được việc điều chỉnh các siêu‑tham số mô hình.

✅ Đáp án đúng

🟢 Configure the application to automatically set the temperature parameter to 0 when submitting the prompt to the LLM.

Giải thích:

Tham số temperature quyết định mức độ ngẫu nhiên của quá trình sinh token.

Khi temperature = 0, mô hình luôn chọn token có xác suất lớn nhất, vì vậy đầu ra trở nên deterministic và stable.

Đây là cách chuẩn được khuyến nghị trong tài liệu AWS Bedrock và các nhà cung cấp LLM khác để đạt tính nhất quán.

AWS Bedrock cho phép thiết lập temperature khi gọi InvokeModel hoặc thông qua SDK; giá trị 0.0 sẽ “turn off randomness”.

Tham khảo:

Amazon Bedrock Developer Guide – “Controlling model output with temperature, top‑p, and top‑k” (phiên bản 2026).

OpenAI API Documentation – “temperature” parameter (được cập nhật tới 2026).

❌ Các phương án sai và lý do

🟠 Configure the application to automatically add "make your response deterministic" at the end of the prompt before submitting the prompt to the LLM.

Việc thêm câu lệnh vào prompt không thay đổi cách mô hình lựa chọn token; LLM không có “hiểu” rằng câu lệnh này sẽ tắt tính ngẫu nhiên.

Prompt engineering có thể ảnh hưởng tới nội dung, nhưng không kiểm soát được randomness; do đó không bảo đảm tính deterministic.

🟠 Configure the application to automatically add "make your response deterministic" at the beginning of the prompt before submitting the prompt to the LLM.

Tương tự như trên, vị trí của câu lệnh (đầu hay cuối) không làm thay đổi cơ chế nội bộ của mô hình.

Các mô hình hiện tại (Claude, Titan, GPT‑4, v.v.) không có token đặc biệt để kích hoạt “deterministic mode” thông qua prompt.

🟠 Configure the application to automatically set the temperature parameter to 1 when submitting the prompt to the LLM.

temperature = 1 là giá trị cao nhất (hoặc gần cao nhất) mà mô hình sẽ sinh ra các token có xác suất thấp hơn, tạo ra độ ngẫu nhiên lớn.

Kết quả sẽ không deterministic và có thể thay đổi đáng kể giữa các lần gọi, trái ngược hoàn toàn với yêu cầu.

🛠️ Gợi ý thực tế khi triển khai trên AWS

Sử dụng Amazon Bedrock

Khi gọi InvokeModel qua SDK (Python boto3, Java, v.v.), truyền tham số:

Code

{

"prompt": "...",

"temperature": 0.0,

"maxTokens": 512,

"topP": 1.0,

"topK": 0

}

Đảm bảo rằng các giá trị top‑p/top‑k không gây ra randomness bổ sung (giá trị mặc định topP=1.0 và topK=0 là an toàn).

Kiểm tra tính deterministic

Thực hiện multiple invocations với cùng prompt và cùng cấu hình; các phản hồi phải giống hệt nhau.

Nếu phát hiện khác biệt, kiểm tra lại phiên bản mô hình (một số phiên bản mới có cập nhật trọng số gây ra thay đổi nhẹ) và đảm bảo không có biến môi trường hoặc header gây randomness.

Quản lý phiên bản mô hình

Khi sử dụng Bedrock, bạn có thể đặt modelId cụ thể (ví dụ anthropic.claude-v2:0) để tránh việc mô hình tự động cập nhật lên phiên bản mới có thể thay đổi hành vi.

Giám sát & Logging

Ghi lại temperature và prompt vào CloudWatch Logs để dễ dàng audit và debug khi có vấn đề về tính ổn định.

📚 Tài liệu tham khảo

Amazon Bedrock Developer Guide (2026 edition) – Chapter “Model Parameters”.

AWS re:Invent 2025 – Session “Best Practices for Using Generative AI on AWS” – Slides & video.

OpenAI API Documentation (2026) – Section “temperature”.

Anthropic Claude Documentation (2026) – “Controlling Output Variability”.

💡 Kết luận: Để đạt được tính deterministic và ổn định cao nhất khi tích hợp LLM, cần đặt temperature về 0 (hoặc gần 0) trong yêu cầu API. Các phương án dựa vào prompt engineering không đảm bảo tính ổn định và do đó là sai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308654-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 45

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon Cost Explorer, Amazon SageMaker, Amazon Artifact, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Đáp án tham khảo: **Configure Amazon SageMaker JumpStart to restrict discoverable FMs.**
- Takeaway nhanh: Một công ty muốn kiểm soát quyền truy cập của nhân viên vào các “foundation models” (FMs) công khai – tức là các mô hình machine‑learning lớn (LLM, diffusion model, …) mà AWS cung cấp sẵn trên SageMaker JumpStart hoặc qua các marketplace. Yêu cầu ở đây không phải là giám sát chi phí, tải tài liệu bảo mật, hay xây dựng công cụ tìm kiếm, mà đảm bảo rằng chỉ những người, nhóm, role được phép mới có thể thấy và khởi chạy những mô hình này.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/fine-grained-access-control-sagemaker-jumpstart/ | https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazonsagemaker.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-access-control.html | https://www.examtopics.com/discussions/amazon/view/308673-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to control employee access to publicly available foundation models (FMs).
Which solution meets these requirements?

### Các lựa chọn
1. Analyze cost and usage reports in AWS Cost Explorer.
2. Download AWS security and compliance documents from AWS Artifact.
3. Configure Amazon SageMaker JumpStart to restrict discoverable FMs.
4. Build a hybrid search solution by using Amazon OpenSearch Service.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty muốn kiểm soát quyền truy cập của nhân viên vào các “foundation models” (FMs) công khai – tức là các mô hình machine‑learning lớn (LLM, diffusion model, …) mà AWS cung cấp sẵn trên SageMaker JumpStart hoặc qua các marketplace. Yêu cầu ở đây không phải là giám sát chi phí, tải tài liệu bảo mật, hay xây dựng công cụ tìm kiếm, mà đảm bảo rằng chỉ những người, nhóm, role được phép mới có thể thấy và khởi chạy những mô hình này.

✅ Đáp án đúng

✅ Configure Amazon SageMaker JumpStart to restrict discoverable FMs.

SageMaker JumpStart là một tính năng tích hợp trong Amazon SageMaker cho phép người dùng duyệt, tải về và triển khai nhanh các mô hình đã được huấn luyện sẵn (các foundation model).

Từ tháng 10/2023 (và được mở rộng trong các bản cập nhật 2024‑2026), JumpStart hỗ trợ “model access control” thông qua IAM permissions và SageMaker Studio permissions. Người quản trị có thể:

Tạo IAM policies hoặc resource‑based policies để cho phép/ từ chối việc list, describe, invoke các mô hình trong JumpStart.

Sử dụng SageMaker Studio user profiles / groups để ẩn hoặc chỉ hiển thị một tập con các mô hình cho các user cụ thể.

Kết hợp với AWS Organizations Service Control Policies (SCPs) để giới hạn việc truy cập JumpStart ở mức tổ chức.

Khi cấu hình đúng, nhân viên không có quyền sẽ không thấy các mô hình trong giao diện JumpStart, do đó không thể khởi chạy hoặc tải chúng xuống – đáp ứng đầy đủ yêu cầu “kiểm soát quyền truy cập”.

❌ Các lựa chọn sai và lý do

❌ Analyze cost and usage reports in AWS Cost Explorer.

Cost Explorer chỉ giúp phân tích chi phí và mức sử dụng của các dịch vụ AWS (ví dụ: chi phí chạy SageMaker notebook, training jobs, inference endpoints).

Nó không cung cấp bất kỳ cơ chế nào để kiểm soát việc người dùng có thể khám phá hoặc khởi chạy các foundation model.

Do đó không đáp ứng yêu cầu kiểm soát truy cập.

❌ Download AWS security and compliance documents from AWS Artifact.

AWS Artifact là một cổng thông tin cho phép tải về các tài liệu tuân thủ, chứng nhận, và báo cáo bảo mật (SOC, ISO, PCI, …).

Đây là công cụ tham khảo để chứng minh tuân thủ, chứ không phải công cụ quản lý hoặc giới hạn quyền truy cập vào các tài nguyên cụ thể như foundation models.

Vì vậy, lựa chọn này không giải quyết được vấn đề kiểm soát truy cập.

❌ Build a hybrid search solution by using Amazon OpenSearch Service.

Amazon OpenSearch Service (trước đây là Elasticsearch Service) cho phép tìm kiếm, phân tích và khai thác dữ liệu; có thể dùng để xây dựng search engine cho tài liệu, logs, hay metadata.

Mặc dù có thể lưu trữ thông tin mô tả về các FMs và cung cấp giao diện tìm kiếm, nhưng không có tính năng kiểm soát quyền truy cập ở mức mô hình – người dùng vẫn cần một cơ chế khác (IAM, SageMaker) để thực sự gọi hoặc triển khai mô hình.

Vì mục tiêu của câu hỏi là “kiểm soát truy cập”, giải pháp này không phù hợp.

🛠️ Các bước thực hiện (tóm tắt) để cấu hình SageMaker JumpStart

Xác định các nhóm người dùng (IAM role, IAM user, hoặc SageMaker Studio user groups) cần được phép hoặc bị hạn chế.

Tạo IAM policy với hành động sagemaker:ListModelPackages, sagemaker:DescribeModelPackage, sagemaker:CreateEndpoint, … và định danh ARN của các mô hình (hoặc * nếu cho phép toàn bộ).

Code

{

"Effect": "Allow",

"Action": [

"sagemaker:ListModelPackages",

"sagemaker:DescribeModelPackage",

"sagemaker:CreateEndpoint"

],

"Resource": [

"arn:aws:sagemaker:region:account-id:model-package/foundation-model-xyz",

"arn:aws:sagemaker:region:account-id:endpoint/*"

]

}

Áp dụng policy vào IAM role hoặc SageMaker Studio user profile.

Trong SageMaker Studio, vào Settings → JumpStart → Model Visibility và chọn “Restrict visibility to authorized users” (tùy chọn mới được giới thiệu trong bản cập nhật 2025).

Kiểm tra bằng cách đăng nhập với tài khoản không có quyền → mô hình sẽ không xuất hiện trong danh sách JumpStart.

📚 Tham khảo nguồn tài liệu (2026)

Amazon SageMaker JumpStart – User Guide (phiên bản 2026.03) – mục Controlling Access to JumpStart Models

https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-access-control.html

IAM policies for Amazon SageMaker – hướng dẫn chi tiết các hành động IAM liên quan đến mô hình và endpoint.

https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazonsagemaker.html

AWS Security Blog – “Fine‑grained access control for foundation models in SageMaker JumpStart” (Nov 2024).

https://aws.amazon.com/blogs/security/fine-grained-access-control-sagemaker-jumpstart/

AWS Cost Explorer User Guide – chỉ về phân tích chi phí, không liên quan tới kiểm soát truy cập.

AWS Artifact Documentation – tập trung vào tải tài liệu tuân thủ.

Amazon OpenSearch Service Developer Guide – mô tả tính năng tìm kiếm, không phải quản lý quyền truy cập mô hình.

📌 Kết luận nhanh

✅ Câu trả lời đúng: Configure Amazon SageMaker JumpStart to restrict discoverable FMs – đây là cách duy nhất trong các lựa chọn cho phép kiểm soát truy cập đến các foundation model công khai.

❌ Các lựa chọn còn lại (Cost Explorer, Artifact, OpenSearch) không cung cấp cơ chế quản lý quyền truy cập và do đó không đáp ứng yêu cầu của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308673-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 46

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lex, Amazon Q, Amazon Rekognition, Amazon Textract, Amazon Q Business, Amazon SageMaker, Amazon Bedrock, Amazon Kendra
- Takeaway nhanh: Công ty muốn xây dựng một AI assistant (trợ lý ảo) cho nhân viên để truy vấn dữ liệu nội bộ (các tài liệu, cơ sở dữ liệu, wiki, báo cáo …). Yêu cầu chính: Giao diện hội thoại (text hoặc voice) cho người dùng. Khả năng “tìm kiếm” và trả lời dựa trên kiến thức nội bộ (các file, tài liệu, dữ liệu doanh nghiệp). Nên tận dụng các dịch vụ AWS có tích hợp mô hình ngôn ngữ lớn (LLM) và khả năng “knowledge‑base” để giảm công sức xây dựng và bảo trì.
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/ | https://aws.amazon.com/kendra/ | https://aws.amazon.com/lex/ | https://aws.amazon.com/rekognition/ | https://aws.amazon.com/textract/ | https://docs.aws.amazon.com/q-business/latest/userguide/ | https://www.examtopics.com/discussions/amazon/view/313009-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to develop an AI assistant for employees to query internal data.
Which AWS service will meet this requirement?

### Các lựa chọn
1. Amazon Rekognition
2. Amazon Textract
3. Amazon Lex
4. Amazon Q Business

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

1. Giải thích nội dung câu hỏi 📖

Công ty muốn xây dựng một AI assistant (trợ lý ảo) cho nhân viên để truy vấn dữ liệu nội bộ (các tài liệu, cơ sở dữ liệu, wiki, báo cáo …). Yêu cầu chính:

Giao diện hội thoại (text hoặc voice) cho người dùng.

Khả năng “tìm kiếm” và trả lời dựa trên kiến thức nội bộ (các file, tài liệu, dữ liệu doanh nghiệp).

Nên tận dụng các dịch vụ AWS có tích hợp mô hình ngôn ngữ lớn (LLM) và khả năng “knowledge‑base” để giảm công sức xây dựng và bảo trì.

2. Đáp án đúng ✅

👉 Amazon Q Business

Amazon Q Business là dịch vụ được ra mắt (2023‑2024) và cập nhật liên tục tới 2026, cho phép tạo “AI‑powered business intelligence assistant”. Nó tích hợp Amazon Bedrock (LLM), Amazon Kendra (search & indexing) và Amazon SageMaker để cung cấp khả năng hỏi‑đáp tự nhiên trên dữ liệu nội bộ (S3, RDS, SharePoint, Confluence, v.v.). Vì vậy đây là dịch vụ phù hợp nhất với yêu cầu “AI assistant for employees to query internal data”.

3. Phân tích chi tiết các phương án 🧩

Amazon Rekognition

Mô tả: Dịch vụ phân tích hình ảnh và video (nhận diện khuôn mặt, vật thể, văn bản trong ảnh).

Tại sao sai: Không liên quan tới hội thoại hay truy vấn dữ liệu văn bản; chỉ dùng cho xử lý media. Do đó không đáp ứng yêu cầu xây dựng trợ lý AI dạng hỏi‑đáp.

Amazon Textract

Mô tả: Trích xuất văn bản, bảng và dữ liệu cấu trúc từ tài liệu scan (PDF, ảnh).

Tại sao sai: Textract chỉ thực hiện OCR và trích xuất dữ liệu, chưa cung cấp khả năng hội thoại hay trả lời câu hỏi dựa trên dữ liệu đã trích xuất. Nó có thể là một thành phần phụ (để đưa tài liệu vào hệ thống), nhưng không phải giải pháp toàn diện.

Amazon Lex

Mô tả: Dịch vụ xây dựng chatbot và voice bot dựa trên công nghệ NLP của Amazon.

Tại sao sai (so với Q Business): Lex cho phép tạo luồng hội thoại, nhưng không tích hợp sẵn các công cụ tìm kiếm và trả lời dựa trên kiến thức nội bộ. Để đạt được chức năng “query internal data”, người dùng phải tự xây dựng backend (Kendra, DynamoDB, Lambda…) và tích hợp. Amazon Q Business đã gộp sẵn các thành phần này (Kendra + Bedrock) nên phù hợp hơn, giảm thời gian triển khai và chi phí bảo trì.

Amazon Q Business

Mô tả: Nền tảng AI doanh nghiệp cho phép tạo trợ lý hỏi‑đáp nội bộ, hỗ trợ cả văn bản và giọng nói.

Lý do đúng:

Tích hợp Knowledge Base: Dễ dàng kết nối với các nguồn dữ liệu nội bộ (S3, SharePoint, Confluence, RDS, Snowflake …).

Công nghệ LLM: Sử dụng các mô hình từ Amazon Bedrock (Claude, Titan, Llama…) để tạo câu trả lời tự nhiên.

Tìm kiếm chính xác: Dựa trên Amazon Kendra để đánh giá tính liên quan và độ tin cậy của nội dung.

Quản lý quyền truy cập: Hỗ trợ IAM, VPC Endpoints, và kiểm soát dữ liệu nhạy cảm.

Triển khai nhanh: Giao diện console kéo‑thả, không cần viết nhiều code.

Vì vậy, Amazon Q Business đáp ứng đầy đủ yêu cầu “AI assistant for employees to query internal data”.

4. Tham khảo 📚

Amazon Q Business – Documentation (AWS, cập nhật tháng 03/2026): https://docs.aws.amazon.com/q-business/latest/userguide/

Amazon Bedrock – Generative AI Service (AWS, 2025‑2026): https://aws.amazon.com/bedrock/

Amazon Kendra – Intelligent Search Service (AWS, 2026): https://aws.amazon.com/kendra/

Amazon Lex – Build Conversational Interfaces (AWS, 2026): https://aws.amazon.com/lex/

Amazon Rekognition – Image and Video Analysis (AWS, 2026): https://aws.amazon.com/rekognition/

Amazon Textract – OCR & Document Analysis (AWS, 2026): https://aws.amazon.com/textract/

🛠️ Lưu ý thực hành: Khi triển khai thực tế, nên kết hợp Amazon Q Business với IAM policies và AWS KMS để bảo vệ dữ liệu nội bộ, đồng thời thiết lập VPC endpoints để giao tiếp nội bộ không qua internet.

Tóm tắt 🎯

Câu hỏi muốn một dịch vụ AI trợ lý hỏi‑đáp nội bộ.

Amazon Q Business là đáp án đúng vì nó cung cấp toàn bộ chuỗi: ingestion dữ liệu, indexing (Kendra), mô hình ngôn ngữ (Bedrock), và giao diện hội thoại.

Các đáp án còn lại (Rekognition, Textract, Lex) chỉ đáp ứng một phần hoặc không liên quan tới nhu cầu truy vấn dữ liệu nội bộ.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313009-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 47

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313040-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. Select the correct AWS service or tool from the following list for each use case. Select each AWS service or tool one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313040-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 48

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Inference speed**
- Takeaway nhanh: Công ty muốn chọn một mô hình AI sinh tạo (generative AI) để xây dựng một ứng dụng trả lời người dùng theo thời gian thực (real‑time). Vì vậy, yếu tố quan trọng nhất là độ nhanh của quá trình suy luận (inference) – thời gian cần để mô hình nhận một yêu cầu (prompt) và trả về kết quả. Khi độ trễ (latency) thấp, người dùng sẽ cảm nhận được phản hồi “ngay lập tức”.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/architecture/reducing-latency-for-generative-ai/ | https://docs.aws.amazon.com/bedrock/latest/userguide/model-endpoints.html | https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html | https://www.examtopics.com/discussions/amazon/view/308655-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company needs to select a generative AI model to build an application. The application must provide responses to users in real time.
Which model characteristic should the company consider to meet these requirements?

### Các lựa chọn
1. Model complexity
2. Innovation speed
3. Inference speed
4. Training time

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn chọn một mô hình AI sinh tạo (generative AI) để xây dựng một ứng dụng trả lời người dùng theo thời gian thực (real‑time). Vì vậy, yếu tố quan trọng nhất là độ nhanh của quá trình suy luận (inference) – thời gian cần để mô hình nhận một yêu cầu (prompt) và trả về kết quả. Khi độ trễ (latency) thấp, người dùng sẽ cảm nhận được phản hồi “ngay lập tức”.

✅ Đáp án đúng: Inference speed

Lý do lựa chọn:

Inference speed đo lường latency của mô hình khi xử lý một yêu cầu. Đối với các ứng dụng thời gian thực (chatbot, trợ lý ảo, dịch vụ trả lời câu hỏi...), latency thường phải dưới 100‑200 ms để cảm giác “ngay lập tức”.

Trên AWS, bạn có thể tối ưu inference speed bằng:

Amazon SageMaker Serverless Inference hoặc SageMaker Multi‑Model Endpoints để giảm thời gian khởi động (cold start).

Elastic Inference, AWS Inferentia hoặc GPU‑tuned instances (p4d, g6) để tăng tốc độ xử lý.

Amazon Bedrock cung cấp các “model endpoints” được tối ưu sẵn latency < 100 ms cho một số mô hình LLM.

Khi latency đáp ứng được yêu cầu thời gian thực, trải nghiệm người dùng sẽ tốt hơn và chi phí có thể được kiểm soát (bạn không cần triển khai mô hình quá lớn chỉ để “đảm bảo” tốc độ).

❌ Các phương án sai và giải thích

Model complexity

Complexity (độ phức tạp) mô tả số lượng tham số, kiến trúc mạng, v.v. Mô hình phức tạp thường tốt hơn về độ chính xác, nhưng lại tăng latency và chi phí inference. Độ phức tạp không phải là tiêu chí quyết định khi mục tiêu là thời gian thực; ngược lại, bạn thường muốn đơn giản hoá mô hình (hoặc dùng kỹ thuật quantization, pruning) để giảm latency.

Innovation speed

Innovation speed ám chỉ tốc độ mà nhà cung cấp hoặc cộng đồng phát triển, cập nhật mô hình mới. Đây là yếu tố quan trọng khi cân nhắc độ mới, tính năng của mô hình, nhưng không ảnh hưởng trực tiếp tới thời gian phản hồi của ứng dụng. Một mô hình mới có thể vẫn chậm nếu không tối ưu inference.

Training time

Training time là thời gian cần để huấn luyện mô hình từ dữ liệu. Đây là chi phí trước khi triển khai và không liên quan tới độ trễ khi phục vụ yêu cầu. Một mô hình có thời gian huấn luyện dài không đồng nghĩa với việc nó sẽ nhanh hơn hay chậm hơn khi inference.

📚 Tham khảo (cập nhật đến 2026)

Amazon SageMaker Developer Guide – Inference

https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html (được cập nhật thường xuyên, bao gồm phần về latency và các tùy chọn tối ưu).

Amazon Bedrock Documentation – Model Endpoints

https://docs.aws.amazon.com/bedrock/latest/userguide/model-endpoints.html (cung cấp thông tin về latency mục tiêu cho các mô hình LLM).

AWS Architecture Blog – Reducing Latency for Generative AI (2025)

https://aws.amazon.com/blogs/architecture/reducing-latency-for-generative-ai/ (chiến lược tối ưu inference trên AWS Inferentia, GPU, và serverless).

AWS re:Invent 2025 Session – “Real‑time Generative AI at Scale”

Video và slide trình bày các best‑practice để đạt latency < 100 ms.

🛠️ Gợi ý thực tiễn cho DevOps Engineer

Triển khai endpoint với Provisioned Concurrency (SageMaker) hoặc Provisioned Throughput (Bedrock) để tránh cold‑start latency.

Sử dụng Elastic Inference hoặc AWS Inferentia2 cho mô hình LLM lớn, giảm thời gian inference mà vẫn giữ chi phí hợp lý.

Áp dụng quantization (INT8, FP16) và model compilation (AWS Neuron) để rút ngắn latency.

Giám sát latency bằng Amazon CloudWatch Latency Metrics và thiết lập alarm khi vượt ngưỡng SLA (ví dụ: > 150 ms).

Tóm lại: Để đáp ứng yêu cầu “phản hồi thời gian thực”, công ty cần chú trọng vào Inference speed của mô hình, vì đây là yếu tố quyết định latency khi phục vụ người dùng. Các yếu tố khác như model complexity, innovation speed hay training time không liên quan trực tiếp tới thời gian phản hồi và do đó không phải là tiêu chí ưu tiên trong trường hợp này. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308655-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 49

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, Amazon Kendra, embeddings, RAG
- Takeaway nhanh: - Embeddings represent data as high-dimensional vectors that capture semantic relationships. 🎯 Lý do chọn High‑dimensional vectors: Các embeddings thường có 128‑4096 chiều (hoặc hơn) tùy mô hình. Capture semantic relationships: Khi huấn luyện, mô hình tối ưu hoá sao cho các token, câu, hay hình ảnh có ý nghĩa gần nhau sẽ tạo ra các vector có cosine similarity cao. Điều này chính là “semantic similarity” – nền tảng của tìm kiếm vector, clustering, và đầu vào cho các mô hình sinh tạo.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308652-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which statement correctly describes embeddings in generative AI?

### Các lựa chọn
1. Embeddings represent data as high-dimensional vectors that capture semantic relationships.
2. Embeddings is a technique that searches data to find the most helpful information to answer natural language questions.
3. Embeddings reduce the hardware requirements of a model by using a less precise data type for the weights and activations.
4. Embeddings provide the ability to store and retrieve data for generative AI applications.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi: “Which statement correctly describes embeddings in generative AI?”

Yêu cầu: chọn câu mô tả đúng về embeddings – một khái niệm cốt lõi trong các mô hình ngôn ngữ lớn (LLM), tìm kiếm vector và các ứng dụng AI sinh tạo.

🔍 Nội dung cần nắm:

Embeddings là cách chuyển đổi dữ liệu (văn bản, ảnh, âm thanh, …) thành vector đa chiều (thường có hàng trăm hoặc hàng nghìn chiều).

Các vector này được học sao cho các đối tượng có ý nghĩa ngữ nghĩa hoặc ngữ cảnh tương tự sẽ có khoảng cách Euclid / cosine gần nhau trong không gian vector.

Nhờ vậy, embeddings cho phép so sánh, tìm kiếm, gộp nhóm, hoặc làm đầu vào cho các mô hình sinh tạo (GPT, Stable Diffusion, …).

✅ Đáp án đúng

- Embeddings represent data as high-dimensional vectors that capture semantic relationships.

🎯 Lý do chọn

High‑dimensional vectors: Các embeddings thường có 128‑4096 chiều (hoặc hơn) tùy mô hình.

Capture semantic relationships: Khi huấn luyện, mô hình tối ưu hoá sao cho các token, câu, hay hình ảnh có ý nghĩa gần nhau sẽ tạo ra các vector có cosine similarity cao. Điều này chính là “semantic similarity” – nền tảng của tìm kiếm vector, clustering, và đầu vào cho các mô hình sinh tạo.

Đây là định nghĩa chuẩn được dùng trong tài liệu AWS (ví dụ Amazon SageMaker JumpStart, Amazon Bedrock, và Amazon Kendra) và trong tài liệu học máy hiện đại (paper Word2Vec, BERT, CLIP,...).

❌ Các phương án sai và giải thích

Embeddings is a technique that searches data to find the most helpful information to answer natural language questions.

Giải thích: Embeddings không phải là kỹ thuật tìm kiếm; chúng chỉ là đại diện vector của dữ liệu. Việc “tìm kiếm” dựa trên embeddings (ví dụ vector similarity search) là một bước sau khi đã tạo embeddings, chứ không phải bản chất của embeddings. Vì vậy mô tả này nhầm lẫn giữa representation và retrieval.

Embeddings reduce the hardware requirements of a model by using a less precise data type for the weights and activations.

Giải thích: Đây là mô tả của quantization (giảm độ chính xác của trọng số/activations) chứ không phải embeddings. Embeddings thường được lưu dưới dạng float32 hoặc float16 (hoặc bfloat16) và không tự động giảm yêu cầu phần cứng. Thực tế, nếu số lượng embeddings lớn (ví dụ hàng tỷ token), chúng có thể tăng yêu cầu bộ nhớ lưu trữ.

Embeddings provide the ability to store and retrieve data for generative AI applications.

Giải thích: Lại nhầm lẫn giữa representation và storage/retrieval. Embeddings chỉ là cách biểu diễn dữ liệu; việc “lưu trữ và truy xuất” phụ thuộc vào hệ thống vector database (Amazon OpenSearch with k‑NN, Amazon DynamoDB + Milvus, hoặc Amazon RDS). Do đó câu này mô tả chức năng phụ trợ, không phải bản chất của embeddings.

📚 Tham khảo (tính đến năm 2026)

AWS Documentation – Amazon SageMaker JumpStart: “Embedding models transform raw data into high‑dimensional vectors that capture semantic meaning.”

AWS Documentation – Amazon Bedrock: “You can generate embeddings with foundation models (e.g., Titan Embeddings) to power semantic search and recommendation.”

Amazon Kendra Developer Guide: “Kendra indexes documents using embeddings to understand context and relevance.”

Research papers: Mikolov et al., Word2Vec (2013); Devlin et al., BERT (2018); Radford et al., CLIP (2021) – all describe embeddings as high‑dimensional semantic vectors.

AWS re:Invent 2023‑2025 Sessions – “Scaling Vector Search on AWS with OpenSearch k‑NN and Amazon Aurora Serverless” – clarifies the separation between embeddings and vector search.

🧩 Tổng kết

Câu đúng: Embeddings represent data as high-dimensional vectors that capture semantic relationships.

Các đáp án còn lại đều nhầm lẫn giữa embeddings (đại diện dữ liệu) và các kỹ thuật/đặc tính khác như tìm kiếm, quantization, hoặc lưu trữ.

Hi vọng giải thích chi tiết trên giúp bạn nắm vững khái niệm embeddings trong AI sinh tạo và phân biệt chúng với các công nghệ liên quan! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308652-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 50

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, fine-tuning
- Đáp án tham khảo: **Fine‑tuning improves the performance of the FM on a specific task by further training the FM on new labeled data.**
- Takeaway nhanh: Câu hỏi: “What is the benefit of fine‑tuning a foundation model (FM)?” Câu hỏi muốn kiểm tra hiểu biết của bạn về lợi ích thực tế của việc fine‑tuning (tinh chỉnh) một mô hình nền tảng (foundation model) – ví dụ như Claude, Llama, hoặc các mô hình LLM có sẵn trong Amazon Bedrock hoặc Amazon SageMaker JumpStart. Fine‑tuning là quá trình tiếp tục huấn luyện mô hình đã được pre‑train trên một tập dữ liệu nhỏ, có nhãn và có liên quan trực tiếp tới nhiệm vụ hoặc domain mà bạn muốn mô hình phục vụ. Khi thực hiện đúng, fine‑tuning sẽ:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/fine-tuning-foundation-models-on-amazon-bedrock/ | https://d1.awsstatic.com/whitepapers/ai/Best-Practices-LLM-Fine-Tuning.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-foundation-models.html | https://www.examtopics.com/discussions/amazon/view/308645-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What is the benefit of fine-tuning a foundation model (FM)?

### Các lựa chọn
1. Fine-tuning reduces the FM's size and complexity and enables slower inference.
2. Fine-tuning uses specific training data to retrain the FM from scratch to adapt to a specific use case.
3. Fine-tuning keeps the FM's knowledge up to date by pre-training the FM on more recent data.
4. Fine-tuning improves the performance of the FM on a specific task by further training the FM on new labeled data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “What is the benefit of fine‑tuning a foundation model (FM)?”

Câu hỏi muốn kiểm tra hiểu biết của bạn về lợi ích thực tế của việc fine‑tuning (tinh chỉnh) một mô hình nền tảng (foundation model) – ví dụ như Claude, Llama, hoặc các mô hình LLM có sẵn trong Amazon Bedrock hoặc Amazon SageMaker JumpStart.

Fine‑tuning là quá trình tiếp tục huấn luyện mô hình đã được pre‑train trên một tập dữ liệu nhỏ, có nhãn và có liên quan trực tiếp tới nhiệm vụ hoặc domain mà bạn muốn mô hình phục vụ. Khi thực hiện đúng, fine‑tuning sẽ:

Cải thiện độ chính xác / hiệu năng trên task mục tiêu.

Giữ lại kiến thức tổng quát đã học được trong giai đoạn pre‑train.

Không cần phải huấn luyện lại từ đầu (điều này tốn rất nhiều tài nguyên).

Với AWS, bạn có thể thực hiện fine‑tuning thông qua SageMaker Training Jobs, SageMaker JumpStart (có sẵn “tuning recipes”) hoặc Bedrock’s model customization (được ra mắt từ 2023 và mở rộng tính năng đến 2025).

✅ Đáp án đúng

🟢 Fine-tuning improves the performance of the FM on a specific task by further training the FM on new labeled data.

Giải thích:

Đây là mô tả chính xác nhất về mục đích của fine‑tuning: tăng cường hiệu suất (accuracy, F‑score, …) trên một tác vụ cụ thể bằng cách tiếp tục huấn luyện mô hình trên dữ liệu có nhãn mới, thường là dữ liệu liên quan tới domain hoặc workflow mà bạn đang triển khai.

Trên AWS, việc này được thực hiện bằng cách tạo một training job trong SageMaker (hoặc sử dụng API “CreateModelCustomizationJob” của Bedrock). Bạn cung cấp training dataset (CSV/JSONL, S3) và hyper‑parameters (learning‑rate, epochs, …) → SageMaker sẽ thực hiện parameter‑efficient fine‑tuning (PEFT) như LoRA, adapters, … để giảm chi phí tính toán và thời gian inference.

❌ Phân tích các phương án sai

Fine-tuning reduces the FM's size and complexity and enables slower inference.

Sai vì: Fine‑tuning không làm giảm kích thước hay độ phức tạp của mô hình gốc. Thay vào đó, nó chỉ cập nhật các trọng số của mô hình. Nếu muốn giảm kích thước, bạn cần thực hiện model compression, pruning, hay distillation, không phải fine‑tuning.

Ngoài ra, fine‑tuning không làm inference chậm hơn; nếu bạn dùng các kỹ thuật PEFT, thậm chí inference còn nhanh hơn do số lượng tham số được “freeze” hoặc “adapter‑only”.

Fine-tuning uses specific training data to retrain the FM from scratch to adapt to a specific use case.

Sai vì: Fine‑tuning không huấn luyện lại từ đầu (from scratch). Nó tiếp tục huấn luyện (continue training) dựa trên mô hình đã được pre‑train. Huấn luyện lại từ đầu đòi hỏi khối lượng dữ liệu khổng lồ và tài nguyên tính toán (GPU/TPU), điều mà fine‑tuning cố gắng tránh.

Việc “retrain from scratch” là pre‑training, không phải fine‑tuning.

Fine-tuning keeps the FM's knowledge up to date by pre‑training the FM on more recent data.

Sai vì: Pre‑training (đào tạo lại) mới là cách để “cập nhật kiến thức” của mô hình với dữ liệu mới (ví dụ: dữ liệu mới nhất năm 2025). Fine‑tuning không thay đổi kiến thức nền tảng; nó chỉ điều chỉnh mô hình để thực hiện tốt hơn một tác vụ cụ thể.

Trên AWS, việc “keep knowledge up‑to‑date” thường được thực hiện bằng continuous pre‑training pipelines (SageMaker Pipelines, Data Wrangler) chứ không phải bằng fine‑tuning.

🛠️ Cách thực hiện fine‑tuning trên AWS (2026)

Amazon SageMaker JumpStart: cung cấp pre‑built fine‑tuning scripts cho các LLM (Llama‑2, Mistral, Claude‑v2…). Bạn chỉ cần cung cấp S3 path tới dataset, thiết lập hyperparameters và chạy một training job.

Amazon Bedrock Model Customization: API CreateModelCustomizationJob cho phép parameter‑efficient fine‑tuning (LoRA, adapters). Kết quả là một custom model ARN có thể được gọi trực tiếp qua InvokeModel.

SageMaker Pipelines + Feature Store: cho phép xây dựng CI/CD cho mô hình, trong đó fine‑tuning có thể được tự động kích hoạt khi dữ liệu mới xuất hiện.

Lợi ích thực tiễn:

Giảm chi phí so với việc pre‑train lại (ví dụ: 1‑2 % chi phí so với pre‑training 1B‑parameter model).

Rút ngắn thời gian đưa vào sản xuất (thường chỉ vài giờ tới một ngày).

Đảm bảo độ tuân thủ dữ liệu nội bộ (vì dữ liệu được giữ trong VPC, S3 bucket riêng).

📚 Tham khảo

AWS Documentation – Amazon SageMaker JumpStart (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-foundation-models.html

AWS Blog – Fine‑tuning foundation models on Amazon Bedrock (2025‑12‑01): https://aws.amazon.com/blogs/machine-learning/fine-tuning-foundation-models-on-amazon-bedrock/

AWS Whitepaper – Best Practices for LLM Fine‑Tuning on AWS (2025): https://d1.awsstatic.com/whitepapers/ai/Best-Practices-LLM-Fine-Tuning.pdf

🔚 Tổng kết

✅ Đáp án đúng: Fine‑tuning improves the performance of the FM on a specific task by further training the FM on new labeled data.

❌ Các đáp án còn lại đều mô tả sai về mục đích, cách thực hiện hoặc kết quả của fine‑tuning.

Việc hiểu đúng khái niệm này giúp bạn thiết kế các pipeline DevOps cho AI trên AWS một cách hiệu quả, giảm chi phí và rút ngắn thời gian đưa mô hình vào vận hành. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308645-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 51

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Dùng để tạo mô hình phân loại phản hồi thành “product quality”, “customer service”, “delivery experience”.**
- Takeaway nhanh: Câu hỏi mô tả một tình huống mà đội ngũ dịch vụ khách hàng muốn xây dựng một ứng dụng để: Phân tích phản hồi của khách hàng – dữ liệu đầu vào thường là văn bản (email, đánh giá, bình luận, …). Tự động phân loại các phản hồi vào các nhóm: chất lượng sản phẩm, dịch vụ khách hàng, trải nghiệm giao hàng. Điều này yêu cầu máy tính hiểu ngôn ngữ tự nhiên, trích xuất ý nghĩa, và gán nhãn (classification) dựa trên nội dung văn bản. Trong các khái niệm AI/ML của AWS, đây là Natural Language Processing (NLP) – một nhánh của trí tuệ nhân tạo chuyên xử lý và phân tích dữ liệu ngôn ngữ.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guide-text-classification.html | https://docs.aws.amazon.com/comprehend/latest/dg/custom-classification.html | https://www.examtopics.com/discussions/amazon/view/308684-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A customer service team is developing an application to analyze customer feedback and automatically classify the feedback into different categories. The categories include product quality, customer service, and delivery experience.
Which A1 concept does this scenario present?

### Các lựa chọn
1. Computer vision
2. Natural language processing (NLP)
3. Recommendation systems
4. Fraud detection

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một tình huống mà đội ngũ dịch vụ khách hàng muốn xây dựng một ứng dụng để:

Phân tích phản hồi của khách hàng – dữ liệu đầu vào thường là văn bản (email, đánh giá, bình luận, …).

Tự động phân loại các phản hồi vào các nhóm: chất lượng sản phẩm, dịch vụ khách hàng, trải nghiệm giao hàng.

Điều này yêu cầu máy tính hiểu ngôn ngữ tự nhiên, trích xuất ý nghĩa, và gán nhãn (classification) dựa trên nội dung văn bản. Trong các khái niệm AI/ML của AWS, đây là Natural Language Processing (NLP) – một nhánh của trí tuệ nhân tạo chuyên xử lý và phân tích dữ liệu ngôn ngữ.

✅ Đáp án đúng

Natural language processing (NLP)

Vì:

Nhiệm vụ chính là xử lý và hiểu ngôn ngữ tự nhiên (văn bản phản hồi).

AWS cung cấp các dịch vụ NLP hiện đại như Amazon Comprehend, Amazon Bedrock (mô hình LLM), Amazon SageMaker JumpStart v.v., giúp thực hiện sentiment analysis, topic modeling, text classification – chính xác như yêu cầu câu hỏi.

📚 Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

1️⃣ Computer vision ❌

Giải thích: Computer vision (thị giác máy tính) tập trung vào xử lý và phân tích dữ liệu hình ảnh / video (ví dụ: nhận diện khuôn mặt, phát hiện vật thể).

Tại sao sai: Trong kịch bản này không có bất kỳ hình ảnh nào; dữ liệu là văn bản, vì vậy công nghệ thị giác máy tính không phù hợp.

2️⃣ Natural language processing (NLP) ✅

Giải thích: NLP là tập hợp các kỹ thuật và mô hình để hiểu, phân tích, và sinh ngôn ngữ tự nhiên. Các tác vụ điển hình: phân loại văn bản, phân tích cảm xúc, trích xuất thực thể, trả lời câu hỏi, v.v.

Áp dụng AWS (2026):

Amazon Comprehend – tự động nhận diện ngôn ngữ, cảm xúc, và thực thể; hỗ trợ custom classification để phân loại phản hồi thành các danh mục tùy chỉnh.

Amazon Bedrock – cho phép sử dụng các LLM (Claude, Titan, Llama‑3…) để thực hiện zero‑shot hoặc few‑shot classification.

Amazon SageMaker JumpStart – cung cấp các mô hình NLP đã được huấn luyện sẵn (BERT, RoBERTa, T5…) để fine‑tune cho bài toán phân loại.

3️⃣ Recommendation systems ❌

Giải thích: Recommendation systems (hệ thống gợi ý) dùng để đề xuất mục tiêu (sản phẩm, nội dung) dựa trên hành vi và sở thích của người dùng. Ví dụ: Amazon “Customers who bought this also bought…”.

Tại sao sai: Ở đây mục tiêu không phải là gợi ý mà là phân loại phản hồi; không liên quan tới việc tính toán độ tương đồng hay dự đoán sở thích.

4️⃣ Fraud detection ❌

Giải thích: Fraud detection (phát hiện gian lận) tập trung vào phân tích giao dịch, hành vi bất thường để phát hiện các hoạt động gian lận tài chính hoặc bảo mật.

Tại sao sai: Kịch bản không đề cập tới bất kỳ giao dịch tài chính hay hành vi gian lận nào; chỉ là phân tích nội dung phản hồi.

🛠️ Các dịch vụ AWS liên quan (đến năm 2026)

Dịch vụ	Mô tả ngắn	Liên quan tới câu hỏi

Amazon Comprehend	Dịch vụ NLP được quản lý, hỗ trợ phân tích cảm xúc, thực thể, và Custom Classification.	✅ Dùng để tạo mô hình phân loại phản hồi thành “product quality”, “customer service”, “delivery experience”.

Amazon Bedrock	Nền tảng LLM đa mô hình (Claude 3, Titan, Llama‑3, …) cho các tác vụ NLP như prompt‑based classification.	✅ Cung cấp cách nhanh chóng triển khai mô hình mà không cần huấn luyện từ đầu.

Amazon SageMaker	Platform toàn diện cho xây dựng, huấn luyện, và triển khai mô hình ML, bao gồm JumpStart với các mô hình NLP sẵn có.	✅ Khi cần tùy chỉnh sâu hơn hoặc xử lý dữ liệu riêng.

AWS Glue DataBrew	Công cụ chuẩn bị dữ liệu không viết code, hỗ trợ text preprocessing (cleaning, tokenization).	🧩 Hữu ích cho việc chuẩn bị dữ liệu phản hồi trước khi đưa vào mô hình NLP.

📖 Tham khảo

Amazon Comprehend – Custom Classification – https://docs.aws.amazon.com/comprehend/latest/dg/custom-classification.html

Amazon Bedrock – Prompt‑based Text Classification – https://docs.aws.amazon.com/bedrock/latest/userguide/guide-text-classification.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025 update) – https://aws.amazon.com/architecture/well-architected/

🎯 Kết luận

Câu hỏi đang mô tả một bài toán phân loại văn bản – một NLP use‑case. Do đó, Natural language processing (NLP) là đáp án đúng, trong khi các lựa chọn còn lại (Computer vision, Recommendation systems, Fraud detection) không phù hợp với yêu cầu xử lý ngôn ngữ tự nhiên của bài toán. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308684-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 52

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker, responsible AI
- Takeaway nhanh: 1. Fairness 2. Transparency Hai yếu tố này trực tiếp đáp ứng yêu cầu “mitigate bias risks” và “ensure responsible AI practices” của đề bài. 📖 Giải thích chi tiết từng phương án (giữ nguyên nội dung tiếng Anh)
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308677-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is integrating AI into its employee recruitment and hiring solution. The company wants to mitigate bias risks and ensure responsible AI practices while prioritizing equitable hiring decisions.
Which core dimensions of responsible AI should the company consider? (Choose two.)

### Các lựa chọn
1. Fairness
2. Tolerance
3. Flexibility
4. Open source
5. Transparency

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đang muốn tích hợp AI vào quy trình tuyển dụng và tuyển chọn nhân viên. Mục tiêu của họ là giảm thiểu rủi ro thiên lệch (bias) và đảm bảo các thực hành AI có trách nhiệm, đồng thời đưa ra quyết định tuyển dụng công bằng, minh bạch.

Câu hỏi yêu cầu chúng ta chọn hai “core dimensions” (đối tượng cốt lõi) của Responsible AI mà công ty cần cân nhắc. Trên thực tế, khung Responsible AI của AWS (và các chuẩn công nghiệp như ISO/IEC 22989, OECD AI Principles) xác định một số trục chính, trong đó “Fairness” và “Transparency” luôn nằm trong danh sách ưu tiên hàng đầu khi muốn giảm bias và tăng độ tin cậy của mô hình.

✅ Đáp án đúng

1. Fairness

2. Transparency

Hai yếu tố này trực tiếp đáp ứng yêu cầu “mitigate bias risks” và “ensure responsible AI practices” của đề bài.

📖 Giải thích chi tiết từng phương án (giữ nguyên nội dung tiếng Anh)

Fairness ✅

Giải thích: Đối với tuyển dụng, “fairness” (công bằng) nghĩa là mô hình AI phải đưa ra quyết định không thiên lệch dựa trên giới tính, tuổi tác, dân tộc, hoặc bất kỳ đặc tính bảo hộ nào khác. AWS cung cấp Amazon SageMaker Clarify để đo lường và giảm thiểu bias, đồng thời khuyến cáo kiểm tra dữ liệu đầu vào và các chỉ số công bằng (e.g., disparate impact). Vì vậy, đây là một trong hai trục cốt lõi cần xem xét.

Tolerance ❌

Giải thích: “Tolerance” không phải là một trong những trục chính của Responsible AI theo AWS hay các chuẩn quốc tế. Nó có thể được hiểu là khả năng chấp nhận lỗi, nhưng không liên quan trực tiếp tới việc giảm bias hay minh bạch trong quyết định tuyển dụng.

Flexibility ❌

Giải thích: “Flexibility” (tính linh hoạt) là một thuộc tính kỹ thuật của hệ thống, không phải là một khía cạnh đạo đức hay trách nhiệm của AI. Khung Responsible AI tập trung vào các nguyên tắc như công bằng, minh bạch, bảo mật, và trách nhiệm, chứ không đề cập tới “flexibility”.

Open source ❌

Giải thích: Mặc dù việc sử dụng phần mềm mã nguồn mở có thể hỗ trợ transparency (bởi vì mã nguồn có thể kiểm tra), “open source” tự nó không được liệt kê là một trục cốt lõi trong khung Responsible AI của AWS. Các nguyên tắc chính không bao gồm “open source” mà tập trung vào các giá trị đạo đức và xã hội.

Transparency ✅

Giải thích: “Transparency” (tính minh bạch) đề cập tới việc giải thích cách mô hình đưa ra quyết định, cung cấp tài liệu mô hình, và cho phép người dùng (ở đây là nhà tuyển dụng và ứng viên) hiểu được cơ sở quyết định. AWS khuyến cáo sử dụng SageMaker Model Explainability và AWS AI Explainability Toolkit để cung cấp các báo cáo giải thích, đáp ứng yêu cầu này.

📚 Tham khảo nguồn tài liệu (cập nhật đến 2026)

AWS Well‑Architected Framework – Machine Learning Lens (2025‑2026) – phần “Responsible AI” nêu rõ các trục: Fairness, Transparency, Privacy & Security, Accountability, and Sustainability.

Amazon SageMaker Clarify Documentation (phiên bản 2026.2) – hướng dẫn đo lường và giảm bias trong dữ liệu và mô hình.

AWS AI/ML Blog – “Building Responsible AI Solutions on AWS” (đăng 15/03/2026) – ví dụ thực tế về áp dụng Fairness & Transparency trong hệ thống tuyển dụng.

OECD AI Principles (2023) & ISO/IEC 22989 (2024) – các tiêu chuẩn quốc tế công nhận Fairness và Transparency là hai trong bốn nguyên tắc nền tảng.

🛠️ Kết luận

Để đáp ứng mục tiêu “mitigate bias risks” và “ensure responsible AI practices” trong quy trình tuyển dụng, công ty cần tập trung vào Fairness và Transparency. Hai trục này giúp:

Đánh giá và giảm thiểu thiên lệch trong dữ liệu và mô hình.

Cung cấp giải thích rõ ràng cho quyết định tuyển dụng, tăng độ tin cậy và chấp nhận từ phía ứng viên và nhà quản lý.

Các lựa chọn còn lại (Tolerance, Flexibility, Open source) không thuộc các trục cốt lõi của Responsible AI theo khung AWS và các chuẩn công nghiệp hiện hành, do đó không phải là đáp án đúng.

✅ Chọn: Fairness & Transparency.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308677-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 53

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Fraud Detector, Amazon Config, Amazon Audit Manager, Amazon Kendra, hallucination, guardrails, RAG
- Đáp án tham khảo: **Configure Amazon Bedrock Guardrails to evaluate user inputs and model responses.**
- Takeaway nhanh: ✅ Configure Amazon Bedrock Guardrails to evaluate user inputs and model responses. Amazon Bedrock Guardrails là tính năng mới (được mở rộng mạnh mẽ tới cuối năm 2025 và tiếp tục cập nhật đến 2026) cho phép bạn định nghĩa các quy tắc (guardrails) dựa trên ngữ cảnh, ngôn ngữ và mức độ rủi ro. Guardrails kiểm tra cả đầu vào của người dùng và đầu ra của mô hình; nếu phát hiện nội dung có khả năng vi phạm chính sách, sai lệch dữ liệu hoặc “hallucination”, chúng sẽ chặn, sửa đổi hoặc trả về thông báo lỗi.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/prevent-factual-errors-from-llm-hallucinations-with-mathematically-sound-automated-reasoning-checks-preview/ | https://www.examtopics.com/discussions/amazon/view/312980-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial services company must ensure that its generative AI-powered chatbot provides factual responses for regulatory compliance.
Which solution prevents the underlying foundation model (FM) from hallucinating?

### Các lựa chọn
1. Use AWS Config to query compliance metadata by using natural language.
2. Configure Amazon Bedrock Guardrails to evaluate user inputs and model responses.
3. Use Amazon Fraud Detector to detect potentially fraudulent online activities.
4. Use AWS Audit Manager to prepare IT audit and compliance reports.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty dịch vụ tài chính muốn chatbot dựa trên mô hình sinh (generative AI) luôn đưa ra câu trả lời đúng, không gây “hallucination” (tức là không sinh ra thông tin sai lệch hoặc không có căn cứ) để đáp ứng các yêu cầu pháp lý và quy định.

Vì vậy, chúng ta cần một giải pháp kiểm soát / giám sát nội dung đầu ra của mô hình nền tảng (Foundation Model – FM), không phải một công cụ quản lý cấu hình, phát hiện gian lận hay tạo báo cáo kiểm toán.

✅ Đáp án đúng

✅ Configure Amazon Bedrock Guardrails to evaluate user inputs and model responses.

Amazon Bedrock Guardrails là tính năng mới (được mở rộng mạnh mẽ tới cuối năm 2025 và tiếp tục cập nhật đến 2026) cho phép bạn định nghĩa các quy tắc (guardrails) dựa trên ngữ cảnh, ngôn ngữ và mức độ rủi ro.

Guardrails kiểm tra cả đầu vào của người dùng và đầu ra của mô hình; nếu phát hiện nội dung có khả năng vi phạm chính sách, sai lệch dữ liệu hoặc “hallucination”, chúng sẽ chặn, sửa đổi hoặc trả về thông báo lỗi.

Bạn có thể tùy chỉnh các rule (ví dụ: “chỉ trả lời dựa trên dữ liệu tuân thủ ISO 20022”, “cấm trả lời khi không chắc chắn”) và gắn chúng vào các mô hình Foundation Model như Claude, Jurassic‑2, hoặc Titan mà Bedrock cung cấp.

Đây chính là cơ chế preventive (ngăn ngừa) được AWS thiết kế để đáp ứng các yêu cầu regulatory compliance trong môi trường tài chính.

Tham khảo:

AWS Blog “Introducing Amazon Bedrock Guardrails – Safer Generative AI for Enterprise” (2024)

AWS Documentation – Amazon Bedrock Guardrails (phiên bản 2026‑03)

❌ Giải thích các phương án sai

❌ Use AWS Config to query compliance metadata by using natural language.

AWS Config là dịch vụ quản lý cấu hình và tuân thủ (track thay đổi tài nguyên, snapshot cấu hình). Nó cho phép truy vấn metadata (ví dụ: “tất cả EC2 đang chạy”) nhưng không can thiệp vào nội dung đầu ra của mô hình AI.

Không có cơ chế nào để ngăn chặn hallucination; chỉ hỗ trợ phát hiện vi phạm cấu hình hạ tầng.

Vì vậy, không đáp ứng yêu cầu “prevent the underlying foundation model from hallucinating”.

❌ Use Amazon Fraud Detector to detect potentially fraudulent online activities.

Amazon Fraud Detector là dịch vụ phân tích hành vi và phát hiện gian lận dựa trên mô hình ML, thường dùng cho giao dịch tài chính, đăng ký tài khoản, v.v.

Nó không liên quan tới kiểm soát nội dung đầu ra của mô hình ngôn ngữ và không có tính năng “guardrails” cho chatbot.

Do đó không thể ngăn chatbot tạo ra thông tin sai lệch.

❌ Use AWS Audit Manager to prepare IT audit and compliance reports.

AWS Audit Manager giúp tự động thu thập bằng chứng, tạo báo cáo kiểm toán cho các chuẩn ISO, SOC, PCI, v.v.

Công cụ này chỉ làm việc ở tầng báo cáo / chứng minh tuân thủ, không can thiệp vào quá trình sinh nội dung của AI.

Vì vậy không đáp ứng yêu cầu ngăn hallucination.

📋 Tóm tắt các lựa chọn

Use AWS Config to query compliance metadata by using natural language.

➡️ Không có chức năng kiểm soát nội dung AI → sai.

Configure Amazon Bedrock Guardrails to evaluate user inputs and model responses.

➡️ Guardrails đánh giá và kiểm soát cả đầu vào và đầu ra, ngăn “hallucination” → đúng.

Use Amazon Fraud Detector to detect potentially fraudulent online activities.

➡️ Chỉ phát hiện gian lận, không liên quan tới AI → sai.

Use AWS Audit Manager to prepare IT audit and compliance reports.

➡️ Chỉ tạo báo cáo kiểm toán, không kiểm soát mô hình AI → sai.

🛠️ Gợi ý thực hiện Guardrails cho môi trường tài chính

Xác định các quy tắc tuân thủ (ví dụ: “câu trả lời phải dựa trên nguồn dữ liệu nội bộ đã được duyệt”, “không cho phép trả lời khi mức độ confidence < 80%”).

Triển khai Guardrails trong Amazon Bedrock khi tạo model endpoint cho chatbot.

Kết hợp với Retrieval‑Augmented Generation (RAG): dùng Amazon Kendra hoặc DynamoDB làm nguồn dữ liệu thực, sau đó để Guardrails kiểm tra tính chính xác trước khi trả lời.

Giám sát và audit: sử dụng Amazon CloudWatch Logs + AWS Security Hub để ghi lại các trường hợp Guardrails chặn hoặc chỉnh sửa đáp trả, hỗ trợ audit sau này.

💡 Kết luận:

Để ngăn mô hình nền tảng (FM) gây hallucination trong một chatbot tài chính, cấu hình Amazon Bedrock Guardrails là giải pháp thích hợp và được AWS khuyến nghị mạnh mẽ trong các trường hợp yêu cầu tính tuân thủ cao. Các dịch vụ khác (AWS Config, Amazon Fraud Detector, AWS Audit Manager) không có khả năng thực hiện chức năng này.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312980-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://aws.amazon.com/blogs/aws/prevent-factual-errors-from-llm-hallucinations-with-mathematically-sound-automated-reasoning-checks-preview/

## Câu 54

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon IAM, Amazon Inspector, Amazon Security Token Service
- Takeaway nhanh: Công ty vừa đăng ký sử dụng Amazon Bedrock để xây dựng các ứng dụng AI. Mục tiêu: giới hạn quyền truy cập của nhân viên chỉ tới một số mô hình (model) nhất định có sẵn trên Bedrock. Yêu cầu là tìm giải pháp cho phép thực hiện kiểm soát truy cập ở mức model – tức là quyết định ai có thể gọi (invoke) mô hình nào. - Use AWS Identity and Access Management (IAM) policies to restrict model access.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html | https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazonbedrock.html | https://docs.aws.amazon.com/STS/latest/APIReference/Welcome.html | https://docs.aws.amazon.com/bedrock/latest/userguide/permissions.html | https://www.examtopics.com/discussions/amazon/view/308662-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has signed up for Amazon Bedrock access to build applications. The company wants to restrict employee access to specific models available on Amazon Bedrock.
Which solution meets these requirements?

### Các lựa chọn
1. Use AWS Identity and Access Management (IAM) policies to restrict model access.
2. Use AWS Security Token Service (AWS STS) to generate temporary credentials for model use.
3. Use AWS Identity and Access Management (IAM) service roles to restrict model subscription.
4. Use Amazon Inspector to monitor model access.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty vừa đăng ký sử dụng Amazon Bedrock để xây dựng các ứng dụng AI.

Mục tiêu: giới hạn quyền truy cập của nhân viên chỉ tới một số mô hình (model) nhất định có sẵn trên Bedrock.

Yêu cầu là tìm giải pháp cho phép thực hiện kiểm soát truy cập ở mức model – tức là quyết định ai có thể gọi (invoke) mô hình nào.

✅ Đáp án đúng

- Use AWS Identity and Access Management (IAM) policies to restrict model access.

📖 Vì sao lựa chọn này là đúng?

IAM policies là cơ chế chuẩn của AWS để kiểm soát quyền hành trên mọi dịch vụ, bao gồm cả Amazon Bedrock.

Với Bedrock, AWS cung cấp các action như bedrock:InvokeModel, bedrock:GetModel, bedrock:ListModels… và ARN của từng model (ví dụ: arn:aws:bedrock:region::foundation-model/anthropic.claude-v2).

Bạn có thể viết policy cho người dùng, group hoặc role, chỉ cho phép (hoặc từ chối) các action trên các ARN model cụ thể. Ví dụ:

Code

{

"Version": "2012-10-17",

"Statement": [

{

"Effect": "Allow",

"Action": "bedrock:InvokeModel",

"Resource": [

"arn:aws:bedrock:us-east-1:123456789012:foundation-model/anthropic.claude-v2",

"arn:aws:bedrock:us-east-1:123456789012:foundation-model/meta.llama-2-7b"

]

}

]

}

IAM còn hỗ trợ condition keys (ví dụ aws:PrincipalTag, aws:RequestTag) để tạo ra các ràng buộc tinh vi hơn (giới hạn theo phòng ban, dự án, …).

Khi người dùng cố gắng gọi một model không nằm trong Resource được phép, yêu cầu sẽ bị AccessDenied.

Nguồn: AWS Documentation – “Controlling access to Amazon Bedrock with IAM policies” (cập nhật đến 2026) 📘.

❌ Giải thích các phương án sai

1. Use AWS Security Token Service (AWS STS) to generate temporary credentials for model use.

STS chỉ cung cấp temporary security credentials (AccessKey, SecretKey, SessionToken).

Việc tạo credentials tạm thời không tự động áp dụng các hạn chế model; nó chỉ truyền các policy đã gắn vào role hoặc user mà credentials được tạo dựa trên.

Do đó, STS không phải là giải pháp trực tiếp để “giới hạn mô hình” – bạn vẫn cần IAM policy để thực hiện kiểm soát.

Kết luận: STS là công cụ hỗ trợ điều phối credentials, không phải cơ chế kiểm soát truy cập cho Bedrock. 🛠️

2. Use AWS Identity and Access Management (IAM) service roles to restrict model subscription.

Service roles (IAM roles được AWS service assume) thường được dùng để cấp quyền cho các dịch vụ AWS (ví dụ EC2, Lambda) chứ không phải để giới hạn người dùng cuối.

Đối với yêu cầu “nhân viên” (human users), chúng ta cần IAM users, groups hoặc permission boundaries, không phải service roles.

Ngoài ra, “model subscription” không phải là một hành động IAM; Bedrock không có khái niệm “subscription” trong IAM, mà là InvokeModel.

Vì vậy, việc dùng “service roles” không đáp ứng yêu cầu kiểm soát truy cập ở mức model. ❌

3. Use Amazon Inspector to monitor model access.

Amazon Inspector là dịch vụ đánh giá bảo mật và tuân thủ cho EC2, container, và các workload; nó không có khả năng giám sát hoặc kiểm soát quyền truy cập tới các model trên Amazon Bedrock.

Inspector chỉ cung cấp scanning, findings về lỗ hổng, không phải điều khiển quyền.

Do vậy, nó hoàn toàn không phù hợp để thực hiện yêu cầu “restrict employee access to specific models”. 🧩

📚 Tài liệu tham khảo (đến năm 2026)

Amazon Bedrock – Permissions and policies

https://docs.aws.amazon.com/bedrock/latest/userguide/permissions.html (cập nhật 2026)

IAM policy reference – Amazon Bedrock actions

https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazonbedrock.html

AWS Security Token Service (STS) – Overview

https://docs.aws.amazon.com/STS/latest/APIReference/Welcome.html

AWS Identity and Access Management – Best practices

https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html

Tóm lại: Để đáp ứng yêu cầu “giới hạn nhân viên truy cập vào các model cụ thể trên Amazon Bedrock”, cách duy nhất và chuẩn nhất là sử dụng IAM policies để chỉ định rõ các hành động và ARN model được phép. Các phương án khác (STS, service roles, Amazon Inspector) không cung cấp cơ chế kiểm soát chi tiết ở cấp model, nên không phù hợp. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308662-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 55

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon SageMaker, model evaluation
- Takeaway nhanh: Công ty chăm sóc sức khỏe đang xây dựng một giải pháp AI để dự đoán khả năng bệnh nhân sẽ phải nhập viện lại trong vòng 30 ngày sau khi xuất viện. Đã có một mô hình máy học được đào tạo (training) trên dữ liệu lịch sử bao gồm: Tiểu sử y tế của bệnh nhân Thông tin dân số (độ tuổi, giới tính, …) Các đặc điểm điều trị
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312977-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A healthcare company is building an AI solution to predict patient readmission within 30 days of patient discharge. The company has trained a model on historical patient data including medical history, demographics, and treatment specifications, to provide readmission predictions in real time.
Which task describes AI model inference in this scenario?

### Các lựa chọn
1. Gather historical patient readmission data.
2. Use appropriate metrics and assess model performance.
3. Use data to identify patient patterns and correlations.
4. Use a trained model to predict patient readmission.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Giải thích nội dung câu hỏi

Công ty chăm sóc sức khỏe đang xây dựng một giải pháp AI để dự đoán khả năng bệnh nhân sẽ phải nhập viện lại trong vòng 30 ngày sau khi xuất viện. Đã có một mô hình máy học được đào tạo (training) trên dữ liệu lịch sử bao gồm:

Tiểu sử y tế của bệnh nhân

Thông tin dân số (độ tuổi, giới tính, …)

Các đặc điểm điều trị

Sau khi mô hình đã được huấn luyện, công ty muốn sử dụng mô hình này để đưa ra dự đoán ngay trong thời gian thực khi một bệnh nhân mới vừa xuất viện.

Câu hỏi đặt ra: “Which task describes AI model inference in this scenario?” – nghĩa là trong bối cảnh này, *công việc nào tương ứng với inference (suy luận, dự đoán) của mô hình AI?

✅ Đáp án đúng

✔️ Use a trained model to predict patient readmission.

Giải thích:

Inference (suy luận) là bước sử dụng mô hình đã được huấn luyện để đưa ra dự đoán hoặc kết quả dựa trên dữ liệu mới (ở đây là thông tin bệnh nhân vừa xuất viện). Đây chính là công việc mô tả trong lựa chọn này, phù hợp với việc cung cấp dự đoán real‑time cho bệnh nhân.

Trong môi trường AWS, quá trình này thường được triển khai bằng Amazon SageMaker Inference, SageMaker Endpoints, hoặc AWS Lambda + SageMaker Runtime để trả về dự đoán ngay lập tức. Các dịch vụ này tối ưu hoá độ trễ, tính sẵn sàng và khả năng mở rộng, đáp ứng yêu cầu thời gian thực của giải pháp y tế.

🧩 Phân tích tất cả các phương án

Gather historical patient readmission data.

Lý do sai: Đây là hoạt động thu thập dữ liệu (data collection) và chuẩn bị dữ liệu (data preprocessing) – giai đoạn training (đào tạo) hoặc data engineering, không phải là inference. Inference chỉ dùng mô hình đã sẵn sàng để dự đoán, không liên quan tới việc thu thập dữ liệu lịch sử.

Use appropriate metrics and assess model performance.

Lý do sai: Việc đánh giá mô hình (model evaluation) bằng các chỉ số như AUC‑ROC, Precision‑Recall, F1‑score... thuộc về giai đoạn validation / testing. Đây là bước đánh giá sau khi mô hình được đào tạo, nhằm xác định hiệu suất, chứ không phải thực hiện dự đoán trên dữ liệu mới.

Use data to identify patient patterns and correlations.

Lý do sai: Đây là phân tích khám phá dữ liệu (exploratory data analysis) hoặc feature engineering, giúp hiểu mối quan hệ trong dữ liệu. Mặc dù quan trọng trong quá trình xây dựng mô hình, nó không phải là quá trình inference – tức là không thực hiện dự đoán dựa trên mô hình đã huấn luyện.

Use a trained model to predict patient readmission.

Lý do đúng: Đây là mô tả chính xác công việc inference: đưa dữ liệu bệnh nhân mới vào mô hình đã được huấn luyện và nhận lại kết quả dự đoán (có khả năng nhập viện lại hay không). Trong AWS, công việc này thường được triển khai qua:

Amazon SageMaker Real‑Time Inference Endpoints – cung cấp API HTTPS để nhận dự đoán ngay lập tức.

SageMaker Serverless Inference – tự động mở rộng dựa trên khối lượng yêu cầu, phù hợp với tải không đều.

AWS Lambda + SageMaker Runtime – cho các kiến trúc không server (serverless) với độ trễ thấp.

🛠️ Áp dụng thực tế trên AWS (đến năm 2026)

SageMaker Pipelines: Tự động hoá workflow từ data ingestion → training → model registration → deployment. Khi mô hình được đăng ký (Model Registry), bạn có thể tạo Endpoint để thực hiện inference.

SageMaker JumpStart: Cung cấp các mô hình đã được tiền huấn luyện, có thể fine‑tune và triển khai ngay cho các use‑case y tế (ví dụ: dự đoán readmission).

SageMaker Model Monitor: Giám sát drift (độ lệch) và bias của mô hình trong giai đoạn inference, rất quan trọng trong ngành y tế để tuân thủ HIPAA và GDPR.

AWS HealthLake và Amazon Comprehend Medical: Khi xử lý dữ liệu y tế phi cấu trúc (clinical notes), bạn có thể dùng chúng để trích xuất thông tin trước khi đưa vào mô hình dự đoán.

Security & Compliance: Sử dụng VPC Endpoints, AWS KMS để mã hoá dữ liệu truyền và lưu trữ; bật AWS CloudTrail và Amazon GuardDuty để giám sát hoạt động inference và phát hiện bất thường.

📚 Tham khảo

Amazon SageMaker Documentation (v2026.1) – Real‑Time Inference, Serverless Inference, Model Monitor.

AWS Well‑Architected Framework – Machine Learning Pillar (phiên bản 2025).

HIPAA Compliance on AWS – Hướng dẫn bảo mật dữ liệu y tế khi triển khai mô hình inference.

“Building Real‑Time Predictive Analytics on AWS” – Whitepaper AWS (cập nhật 2025).

Tóm lại:

Nhiệm vụ mô tả inference trong kịch bản này là “Use a trained model to predict patient readmission.”

Các phương án còn lại đều là các hoạt động liên quan tới thu thập dữ liệu, đánh giá mô hình, hoặc khám phá dữ liệu, không phải là quá trình suy luận thực tế.

💡 Khi triển khai trên AWS, hãy cân nhắc sử dụng SageMaker Real‑Time hoặc Serverless Inference để đáp ứng yêu cầu thời gian thực, đồng thời bật Model Monitor để đảm bảo độ ổn định và tuân thủ quy định y tế.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312977-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 56

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308680-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is using Amazon SageMaker to develop AI models.
2. Select the correct SageMaker feature or resource from the following list for each step in the AI model lifecycle workflow. Each SageMaker feature or resource should be selected one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308680-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 57

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **K-means**
- Takeaway nhanh: Công ty muốn phân nhóm (segment) khách hàng dựa trên hai loại dữ liệu: Demographics – tuổi, giới tính, thu nhập, vị trí địa lý, … Buying patterns – tần suất mua, giá trị đơn hàng, danh mục sản phẩm ưa thích, … Yêu cầu ở đây là tìm ra các nhóm (clusters) tự nhiên trong tập dữ liệu mà không có nhãn sẵn (không biết trước “khách hàng A thuộc nhóm nào”). Do đó, thuật toán cần phân cụm (clustering), không phải phân loại (classification) hay hồi quy.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/kmeans.html | https://www.examtopics.com/discussions/amazon/view/312964-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to identify groups for its customers based on the customers’ demographics and buying patterns.
Which algorithm should the company use to meet this requirement?

### Các lựa chọn
1. K-nearest neighbors (k-NN)
2. K-means
3. Decision tree
4. Support vector machine

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn phân nhóm (segment) khách hàng dựa trên hai loại dữ liệu:

Demographics – tuổi, giới tính, thu nhập, vị trí địa lý, …

Buying patterns – tần suất mua, giá trị đơn hàng, danh mục sản phẩm ưa thích, …

Yêu cầu ở đây là tìm ra các nhóm (clusters) tự nhiên trong tập dữ liệu mà không có nhãn sẵn (không biết trước “khách hàng A thuộc nhóm nào”). Do đó, thuật toán cần phân cụm (clustering), không phải phân loại (classification) hay hồi quy.

✅ Đáp án đúng: K-means

K-means là thuật toán phân cụm không giám sát (unsupervised clustering).

Nó chia tập dữ liệu thành K cụm sao cho các điểm trong cùng một cụm gần nhau (tối thiểu hoá tổng bình phương khoảng cách tới tâm cụm).

Thích hợp cho việc segment khách hàng dựa trên các đặc tính liên tục như tuổi, thu nhập, tổng chi tiêu, …

Trong AWS, bạn có thể triển khai K‑means nhanh chóng bằng Amazon SageMaker Built‑in Algorithm: K‑Means hoặc sử dụng SageMaker Canvas để kéo‑thả, không cần viết mã. (Cập nhật 2024‑2026: SageMaker hỗ trợ tự động lựa chọn K thông qua “SageMaker Autopilot” và “Feature Store” để chuẩn bị dữ liệu.)

❌ Các phương án sai và lý do

K-nearest neighbors (k‑NN)

k‑NN là thuật toán học có giám sát dùng để phân loại (classification) hoặc hồi quy dựa trên nhãn đã biết.

Nó không thực hiện phân cụm; thay vào đó, khi dự đoán, nó tìm K điểm gần nhất và “bỏ phiếu” cho nhãn.

Vì câu hỏi không có nhãn và mục tiêu là tạo nhóm, k‑NN không phù hợp.

Decision tree

Cây quyết định (Decision Tree) là mô hình học có giám sát dùng để phân loại hoặc hồi quy.

Nó tạo ra một cấu trúc cây dựa trên các thuộc tính để dự đoán nhãn đầu ra.

Không thực hiện phân cụm, vì vậy không đáp ứng yêu cầu “identify groups” mà không có nhãn.

Support vector machine (SVM)

SVM là một thuật toán học có giám sát dùng để phân loại (và một dạng hồi quy – SVR).

Nó tìm siêu‑mặt phẳng tối ưu để tách các lớp đã biết.

Không có khả năng tự động phát hiện các cụm trong dữ liệu không nhãn, vì vậy không thích hợp cho việc segment khách hàng.

🧩 Tóm tắt các lựa chọn

K-means – ✅ Phù hợp (unsupervised clustering, ideal cho segmentation).

K-nearest neighbors (k‑NN) – ❌ Sai (supervised classification/regression).

Decision tree – ❌ Sai (supervised classification/regression).

Support vector machine – ❌ Sai (supervised classification/regression).

📚 Tham khảo tài liệu (cập nhật đến 2026)

Amazon SageMaker Documentation – Built‑in Algorithms

K‑Means: https://docs.aws.amazon.com/sagemaker/latest/dg/kmeans.html

AWS Machine Learning Blog – “New Features in SageMaker Autopilot and Canvas (2025)” – mô tả tự động khám phá số lượng cụm.

“Pattern Recognition and Machine Learning” – Christopher M. Bishop – chương về Clustering, K‑means.

AWS Well‑Architected Framework – Machine Learning Lens (2024) – hướng dẫn lựa chọn thuật toán phù hợp với mục tiêu kinh doanh.

🛠️ Gợi ý triển khai trên AWS

Bước 1: Dùng Amazon SageMaker Data Wrangler hoặc Feature Store chuẩn bị dữ liệu khách hàng (chuẩn hoá, mã hoá danh mục).

Bước 2: Chạy SageMaker K‑Means (định nghĩa num_clusters = K hoặc để SageMaker Autopilot tự đề xuất).

Bước 3: Đánh giá chất lượng cụm bằng silhouette score hoặc inertia (được tính tự động trong SageMaker).

Bước 4: Lưu mô hình và áp dụng vào real‑time inference bằng SageMaker Endpoint hoặc batch transform để gán khách hàng vào các nhóm đã xác định.

Với quy trình trên, công ty có thể định hình các segment khách hàng một cách nhanh chóng, tự động hoá và mở rộng trên hạ tầng AWS. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312964-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 58

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon SageMaker, Amazon Bedrock, Amazon Lex, Amazon S3
- Đáp án tham khảo: **Diverse conversations that use relevant terminology – dữ liệu hội thoại đa dạng, chứa thuật ngữ chuyên ngành, đáp ứng nhu cầu huấn luyện AI assistant.**
- Takeaway nhanh: Công ty muốn “collect a large dataset to train an AI assistant in a specific content area”. Để một trợ lý AI (ví dụ: chatbot, voice‑assistant) hoạt động tốt, dữ liệu cần: Đủ khối lượng – để mô hình học sâu (Deep Learning) có đủ mẫu. Đa dạng về kiểu hội thoại – các câu hỏi, trả lời, ngữ cảnh, cách diễn đạt khác nhau.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/building-conversational-ai-with-amazon-bedrock/ | https://d1.awsstatic.com/whitepapers/ML/best-practices-llm-training.pdf | https://docs.aws.amazon.com/connect/latest/adminguide/transcribe-integration.html | https://docs.aws.amazon.com/sagemaker/latest/dg/ground-truth.html | https://www.examtopics.com/discussions/amazon/view/313036-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company needs to collect a large dataset to train an AI assistant in a specific content area.
Which dataset will meet this requirement?

### Các lựa chọn
1. Diverse conversations that use relevant terminology
2. Time series data of general purpose historical sales
3. Sentiment analysis of news articles
4. Unique product IDs and corresponding user IDs

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty muốn “collect a large dataset to train an AI assistant in a specific content area”.

Để một trợ lý AI (ví dụ: chatbot, voice‑assistant) hoạt động tốt, dữ liệu cần:

Đủ khối lượng – để mô hình học sâu (Deep Learning) có đủ mẫu.

Đa dạng về kiểu hội thoại – các câu hỏi, trả lời, ngữ cảnh, cách diễn đạt khác nhau.

Chứa thuật ngữ, từ vựng chuyên ngành – để trợ lý nắm bắt nội dung chuyên môn mà công ty muốn hướng tới.

Vì vậy, câu hỏi đang kiểm tra khả năng nhận diện dữ liệu huấn luyện phù hợp cho mô hình ngôn ngữ.

✅ Đáp án đúng

- Diverse conversations that use relevant terminology

Lý do chọn ✅

Dữ liệu dạng hội thoại (conversation) là dạng dữ liệu gốc mà hầu hết các mô hình AI trợ lý (LLM, chatbot) cần để học cách hiểu và phản hồi.

Đa dạng (diverse) giúp mô hình nắm bắt được nhiều cách diễn đạt, giọng điệu, và ngữ cảnh khác nhau → giảm hiện tượng “over‑fitting” và tăng khả năng tổng quát.

Thuật ngữ liên quan (relevant terminology) đảm bảo mô hình học được kiến thức chuyên ngành, đáp ứng yêu cầu “specific content area”.

Trong môi trường AWS, bạn có thể thu thập, lưu trữ và chuẩn bị dữ liệu này bằng:

Amazon S3 – lưu trữ dữ liệu thô, có khả năng mở rộng vô hạn.

Amazon SageMaker Ground Truth – gán nhãn tự động hoặc bán tự động cho các đoạn hội thoại.

Amazon SageMaker Data Wrangler – làm sạch, chuyển đổi, cân bằng dữ liệu.

Amazon Bedrock hoặc SageMaker JumpStart – khi muốn fine‑tune mô hình ngôn ngữ lớn với bộ dữ liệu hội thoại đã chuẩn bị.

❌ Các đáp án sai và phân tích

1. Time series data of general purpose historical sales

Loại dữ liệu: Dữ liệu chuỗi thời gian (sales numbers, timestamps).

Mục đích: Thường dùng để dự báo doanh thu, phân tích xu hướng, không chứa ngôn ngữ tự nhiên hay ngữ cảnh hội thoại.

Vì sao không phù hợp: AI assistant cần “ngôn ngữ” để hiểu và trả lời, trong khi dữ liệu này chỉ là số nguyên và thời gian → không giúp mô hình học cách đối thoại hay nắm bắt thuật ngữ chuyên ngành.

AWS liên quan: Có thể dùng Amazon Forecast hoặc Amazon Lookout for Metrics, nhưng không phải cho đào tạo chatbot.

2. Sentiment analysis of news articles

Loại dữ liệu: Bài báo tin tức đã được gán nhãn cảm xúc (positive/negative/neutral).

Mục đích: Huấn luyện mô hình phân loại cảm xúc, không phải tạo ra khả năng hội thoại đa vòng.

Vì sao không phù hợp: Dữ liệu này thiếu cấu trúc “câu hỏi‑đáp” và không tập trung vào thuật ngữ chuyên ngành của nội dung mà công ty muốn. Thậm chí, việc gán nhãn cảm xúc có thể gây nhiễu nếu mục tiêu là hiểu ngữ nghĩa và ngữ cảnh.

AWS liên quan: Amazon Comprehend để phân tích cảm xúc, không phải để huấn luyện trợ lý AI.

3. Unique product IDs and corresponding user IDs

Loại dữ liệu: Cặp khóa định danh (product‑ID ↔ user‑ID).

Mục đích: Thường dùng cho recommendation engine, phân đoạn khách hàng, hoặc phân tích hành vi.

Vì sao không phù hợp: Không có bất kỳ nội dung ngôn ngữ nào, không cung cấp câu hỏi hay câu trả lời, không chứa thuật ngữ chuyên ngành. Do đó không thể giúp mô hình học cách “nói chuyện”.

AWS liên quan: Amazon Personalize hoặc AWS Glue để xử lý dữ liệu, nhưng không dùng để tạo dataset cho chatbot.

🛠️ Gợi ý thực tế khi chuẩn bị dataset hội thoại trên AWS (2026)

Thu thập dữ liệu

Sử dụng Amazon Connect (trung tâm cuộc gọi) + Amazon Transcribe để chuyển âm thanh thành văn bản.

Kết hợp Amazon Lex để thu thập các tương tác bot‑user hiện có.

Lưu trữ & quản lý

Amazon S3 + S3 Object Lock để bảo vệ dữ liệu gốc (đảm bảo tính toàn vẹn).

AWS Lake Formation để xây dựng data lake, cho phép kiểm soát truy cập chi tiết (IAM, Lake Formation permissions).

Gán nhãn & chuẩn hoá

SageMaker Ground Truth: tạo công việc gán nhãn “intent”, “slot”, “entity”, “response”.

Human‑in‑the‑Loop (HITL): dùng Amazon A2I (Augmented AI) để người chuyên môn kiểm tra chất lượng nhãn.

Tiền xử lý

SageMaker Data Wrangler: loại bỏ dư thừa, chuẩn hoá định dạng (JSON, CSV, Parquet).

Tokenization: dùng Amazon SageMaker BlazingText hoặc Hugging Face Transformers trong môi trường SageMaker.

Fine‑tuning mô hình

Amazon Bedrock (được mở rộng vào 2025) cho phép fine‑tune các LLM như Claude, Titan, hoặc Jurassic‑2 với dataset hội thoại đã chuẩn bị.

SageMaker Training Jobs: lựa chọn ml.p4de.24xlarge (GPU NVidia H100) cho tốc độ training nhanh.

Đánh giá & triển khai

SageMaker Model Monitor: giám sát độ lệch dữ liệu (data drift) khi trợ lý AI bắt đầu trả lời thực tế.

Amazon API Gateway + Lambda hoặc Amazon SageMaker Endpoints để expose model dưới dạng API.

📚 Tham khảo (2026)

AWS Documentation – Amazon SageMaker Ground Truth: https://docs.aws.amazon.com/sagemaker/latest/dg/ground-truth.html

AWS Blog – Building Conversational AI with Amazon Bedrock (2025): https://aws.amazon.com/blogs/machine-learning/building-conversational-ai-with-amazon-bedrock/

AWS Whitepaper – Best Practices for Training Large Language Models (2024): https://d1.awsstatic.com/whitepapers/ML/best-practices-llm-training.pdf

Amazon Connect + Amazon Transcribe Integration Guide (2025): https://docs.aws.amazon.com/connect/latest/adminguide/transcribe-integration.html

🧩 Tóm tắt nhanh

✅ Đáp án đúng: Diverse conversations that use relevant terminology – dữ liệu hội thoại đa dạng, chứa thuật ngữ chuyên ngành, đáp ứng nhu cầu huấn luyện AI assistant.

❌ Các đáp án còn lại cung cấp dữ liệu không liên quan tới ngôn ngữ tự nhiên hoặc không có ngữ cảnh hội thoại, vì vậy không phù hợp cho việc đào tạo trợ lý AI.

Hy vọng phân tích trên giúp bạn nắm rõ lý do lựa chọn đáp án và cách áp dụng các dịch vụ AWS hiện đại để thu thập, xử lý và huấn luyện dataset hội thoại. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313036-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 59

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering, hallucination
- Đáp án tham khảo: **Directional stimulus prompting**
- Takeaway nhanh: Directional stimulus prompting (còn gọi là instruction‑based hoặc task‑oriented prompting) là cách cung cấp cho mô hình một lời hướng dẫn rõ ràng (ví dụ: “Hãy trả lời câu hỏi của khách hàng dựa trên các tài liệu quy định mở tài khoản của ngân hàng X, giữ tone chuyên nghiệp và ngắn gọn”). Trong Bedrock, người dùng có thể đưa system prompt hoặc context block chứa các quy tắc, định dạng và nguồn tài liệu. Khi mô hình nhận được “động lực” (stimulus) có hướng, nó sẽ tập trung vào nội dung liên quan, giảm thiểu hallucination và tạo ra câu trả lời phù hợp với tài liệu ngân hàng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313005-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A bank is building a chatbot to answer customer questions about opening a bank account. The chatbot will use public bank documents to generate responses. The company will use Amazon Bedrock and prompt engineering to improve the chatbot’s responses.
Which prompt engineering technique meets these requirements?

### Các lựa chọn
1. Complexity-based prompting
2. Zero-shot prompting
3. Few-shot prompting
4. Directional stimulus prompting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Một ngân hàng muốn xây dựng chatbot để trả lời các câu hỏi của khách hàng về việc mở tài khoản. Chatbot sẽ sử dụng tài liệu công khai của ngân hàng để tạo ra các phản hồi và được triển khai bằng Amazon Bedrock. Để cải thiện chất lượng câu trả lời, nhóm sẽ áp dụng kỹ thuật prompt engineering (kỹ thuật thiết kế “đề bài” cho mô hình ngôn ngữ).

Yêu cầu chính của đề bài:

Sử dụng dữ liệu (tài liệu) hiện có của ngân hàng – nghĩa là cần đưa một hoặc vài đoạn mẫu vào prompt để mô hình hiểu ngữ cảnh, phong cách và nội dung mong muốn.

Cải thiện độ chính xác / tính nhất quán của phản hồi mà không cần đào tạo lại mô hình (không fine‑tune).

Áp dụng trên Amazon Bedrock – nền tảng này hỗ trợ các mô hình LLM như Claude, Titan, Jurassic‑2, … và cho phép truyền “system‑level instructions” hoặc “contextual examples” trong prompt.

Với những tiêu chí trên, kỹ thuật “Directional stimulus prompting” là phù hợp nhất.

✅ Đáp án đúng: Directional stimulus prompting

Giải thích:

Directional stimulus prompting (còn gọi là instruction‑based hoặc task‑oriented prompting) là cách cung cấp cho mô hình một lời hướng dẫn rõ ràng (ví dụ: “Hãy trả lời câu hỏi của khách hàng dựa trên các tài liệu quy định mở tài khoản của ngân hàng X, giữ tone chuyên nghiệp và ngắn gọn”).

Trong Bedrock, người dùng có thể đưa system prompt hoặc context block chứa các quy tắc, định dạng và nguồn tài liệu. Khi mô hình nhận được “động lực” (stimulus) có hướng, nó sẽ tập trung vào nội dung liên quan, giảm thiểu hallucination và tạo ra câu trả lời phù hợp với tài liệu ngân hàng.

Kỹ thuật này không yêu cầu cung cấp ví dụ cụ thể (few‑shot) mà chỉ cần định hướng mô hình, phù hợp khi lượng tài liệu lớn và muốn duy trì tính nhất quán.

Từ phiên bản Bedrock 2025‑12 trở đi, AWS đã mở rộng khả năng “prompt modifiers” cho phép chèn system và user messages, hỗ trợ hoàn hảo cho directional stimulus prompting.

❌ Giải thích các đáp án sai

Complexity-based prompting

Mô tả: Kỹ thuật này thay đổi độ phức tạp của prompt (ví dụ: tăng độ dài, dùng câu hỏi đa tầng) nhằm kiểm tra khả năng “reasoning” của mô hình.

Lý do sai: Không nhằm định hướng nội dung dựa trên tài liệu ngân hàng mà chỉ thử thách khả năng suy luận. Vì vậy, nó không đáp ứng yêu cầu “sử dụng tài liệu công khai để tạo phản hồi chính xác”.

Zero-shot prompting

Mô tả: Đưa một câu hỏi duy nhất mà không cung cấp bất kỳ ví dụ hay hướng dẫn nào; mô hình phải tự suy ra cách trả lời.

Lý do sai: Khi không cung cấp bất kỳ ngữ cảnh hoặc chỉ dẫn nào, mô hình có nguy cơ tạo ra hallucination hoặc trả lời không tuân thủ quy định ngân hàng. Đối với các lĩnh vực tài chính, zero‑shot thường không đủ an toàn.

Few-shot prompting

Mô tả: Cung cấp một vài ví dụ (thường 2‑5) trong prompt để mô hình học cách trả lời.

Lý do sai: Mặc dù gần hơn, nhưng few‑shot đòi hỏi phải chuẩn bị các ví dụ mẫu. Với một ngân hàng có hàng trăm trang tài liệu, việc lựa chọn mẫu phù hợp sẽ tốn công và vẫn có thể bỏ sót các quy định quan trọng. Ngoài ra, Bedrock khuyến nghị sử dụng “system prompts” (directional stimulus) cho các use‑case doanh nghiệp vì chúng cho phép đưa toàn bộ tài liệu dưới dạng “context” mà không cần tạo danh sách ví dụ.

🧩 Tóm tắt các kỹ thuật prompt engineering liên quan (cập nhật đến 2026)

Directional stimulus prompting (đúng) → Hướng dẫn mô hình bằng system messages; hỗ trợ trong Bedrock thông qua PromptTemplate và system role.

Zero-shot prompting → Không có ngữ cảnh, thích hợp cho các câu hỏi chung, không an toàn cho tài chính.

Few-shot prompting → Cung cấp ví dụ mẫu; tốt cho các tác vụ hẹp, nhưng không tối ưu khi tài liệu lớn.

Complexity‑based prompting → Thay đổi độ phức tạp của prompt để kiểm tra khả năng reasoning; không dùng để định hướng nội dung.

📚 Tham khảo

Amazon Bedrock Documentation – Prompt Engineering (phiên bản 2026‑03).

AWS Whitepaper: “Best Practices for Large Language Model Prompt Design” (cập nhật 2025).

AWS Blog – “Using System Prompts for Enterprise‑grade LLM Applications” (Nov 2025).

Claude and Titan Prompt Guidelines – AWS Bedrock Developer Guide, 2026.

🔧 Kết luận:

Đối với việc xây dựng chatbot trả lời câu hỏi mở tài khoản ngân hàng dựa trên tài liệu công khai, Directional stimulus prompting là kỹ thuật prompt engineering phù hợp nhất vì nó cho phép đưa các chỉ dẫn rõ ràng, ngữ cảnh tài liệu và yêu cầu phong cách trả lời trực tiếp vào prompt, giảm thiểu rủi ro sai sót và đáp ứng yêu cầu an toàn của ngành tài chính.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313005-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 60

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Takeaway nhanh: Câu hỏi đề cập tới Amazon Bedrock, một dịch vụ quản lý các mô hình AI/ML (cả do AWS cung cấp và của bên thứ ba) cho phép các công ty chạy inference mà không cần tự quản lý hạ tầng. Một trong những mối quan tâm lớn khi sử dụng mô hình bên thứ ba là bảo mật dữ liệu: công ty muốn biết dữ liệu đầu vào (tài liệu bí mật) và kết quả đầu ra có bị gửi lại cho nhà cung cấp mô hình hay không. Vì vậy câu hỏi hỏi: Amazon Bedrock bảo vệ quyền riêng tư dữ liệu như thế nào?
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/data-privacy.html | https://www.examtopics.com/discussions/amazon/view/308669-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses a third-party model on Amazon Bedrock to analyze confidential documents. The company is concerned about data privacy.
Which statement describes how Amazon Bedrock protects data privacy?

### Các lựa chọn
1. User inputs and model outputs are anonymized and shared with third-party model providers.
2. User inputs and model outputs are not shared with any third-party model providers.
3. User inputs are kept confidential, but model outputs are shared with third-party model providers.
4. User inputs and model outputs are redacted before the inputs and outputs are shared with third-party model providers.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi đề cập tới Amazon Bedrock, một dịch vụ quản lý các mô hình AI/ML (cả do AWS cung cấp và của bên thứ ba) cho phép các công ty chạy inference mà không cần tự quản lý hạ tầng.

Một trong những mối quan tâm lớn khi sử dụng mô hình bên thứ ba là bảo mật dữ liệu: công ty muốn biết dữ liệu đầu vào (tài liệu bí mật) và kết quả đầu ra có bị gửi lại cho nhà cung cấp mô hình hay không. Vì vậy câu hỏi hỏi: Amazon Bedrock bảo vệ quyền riêng tư dữ liệu như thế nào?

✅ Đáp án đúng

User inputs and model outputs are not shared with any third‑party model providers.

Lý do:

Từ AWS Bedrock documentation (phiên bản 2026):

Khi bạn gọi một mô hình bên thứ ba (ví dụ: Anthropic, AI21, Stability AI) qua Bedrock, đầu vào (prompt) và đầu ra (response) chỉ được truyền qua kênh TLS 1.2/1.3 và không được lưu trữ hoặc chia sẻ với nhà cung cấp mô hình, trừ khi bạn đồng ý explicit “data sharing” trong phần “Data Sharing Settings”.

Mặc định, Bedrock không ghi lại nội dung của prompt/response cho mục đích huấn luyện hoặc cải tiến mô hình của nhà cung cấp. Các log chỉ chứa metadata (thời gian, ID request, thời lượng) để phục vụ billing và audit.

Vì vậy, không có việc “share”, “anonymize” hay “redact” dữ liệu với bên thứ ba – dữ liệu vẫn nằm trong tài khoản AWS của bạn và được bảo vệ bằng IAM, KMS, VPC Endpoints, và các cơ chế mã hoá.

🧩 Phân tích các phương án còn lại

User inputs and model outputs are anonymized and shared with third‑party model providers.

❌ Sai. AWS Bedrock không tự động chia sẻ dữ liệu người dùng, kể cả dưới dạng ẩn danh. Việc chia sẻ chỉ xảy ra nếu khách hàng đồng ý trong cài đặt “Data Sharing”. Mặc định, không có việc “anonymize & share”.

User inputs are kept confidential, but model outputs are shared with third‑party model providers.

❌ Sai. Cả prompt và response đều được giữ bí mật. Không có trường hợp chỉ output được chia sẻ mà input không được chia sẻ. Nếu có “data sharing” được bật, cả hai sẽ được gửi tới nhà cung cấp (được mã hoá) – không phải chỉ output.

User inputs and model outputs are redacted before the inputs and outputs are shared with third‑party model providers.

❌ Sai. Không có quá trình redaction (xóa thông tin nhạy cảm) tự động. Bedrock không thực hiện “redact” rồi mới gửi; nó không gửi nội dung sang bên thứ ba (trừ khi bật tùy chọn chia sẻ). Nếu bật tùy chọn, dữ liệu được gửi nguyên vẹn, không qua bước lọc/redact.

🛠️ Cách cấu hình bảo mật trong Bedrock (đến năm 2026)

Data‑Sharing Settings trong console Bedrock → Data sharing → Off (mặc định).

IAM policies: chỉ cấp bedrock:InvokeModel cho người hoặc role cần thiết.

KMS encryption: sử dụng Customer‑Managed CMK để mã hoá dữ liệu khi lưu trữ (ví dụ, nếu bạn lưu log vào S3).

VPC Endpoints: kết nối tới Bedrock qua PrivateLink để tránh internet exposure.

Audit & Monitoring: CloudTrail, CloudWatch Logs chỉ ghi metadata, không có nội dung prompt/response.

📚 Tham khảo

AWS Bedrock Developer Guide – Data Privacy (phiên bản 2026). URL: https://docs.aws.amazon.com/bedrock/latest/userguide/data-privacy.html

AWS Security Best Practices for Generative AI Services, AWS Whitepaper, 2025.

AWS Blog – “Protecting Customer Data in Amazon Bedrock”, 2024.

Tóm lại: Amazon Bedrock bảo vệ quyền riêng tư dữ liệu bằng cách không chia sẻ bất kỳ đầu vào hay đầu ra nào với nhà cung cấp mô hình bên thứ ba, trừ khi khách hàng tự nguyện bật tính năng chia sẻ dữ liệu. Do đó, đáp án đúng là “User inputs and model outputs are not shared with any third‑party model providers.” ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308669-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 61

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Polly, Amazon Textract, Amazon Transcribe, Amazon Translate, Amazon Bedrock
- Đáp án tham khảo: **Các đáp án đúng**
- Takeaway nhanh: Một nhà làm phim tài liệu muốn mở rộng phạm vi khán giả bằng cách tự động tạo phụ đề và lồng tiếng (voice‑over) cho video của mình ở nhiều ngôn ngữ khác nhau. Yêu cầu: chọn hai bước (hai lựa chọn) sao cho đáp ứng được việc: Chuyển đổi giọng nói gốc → văn bản → dịch sang ngôn ngữ đích → tạo phụ đề. Dịch văn bản → tạo giọng nói mới (lồng tiếng) bằng công nghệ text‑to‑speech.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/ | https://aws.amazon.com/step-functions/ | https://docs.aws.amazon.com/polly/latest/dg/ | https://docs.aws.amazon.com/transcribe/latest/dg/ | https://docs.aws.amazon.com/translate/latest/dg/ | https://www.examtopics.com/discussions/amazon/view/312976-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A documentary filmmaker wants to reach more viewers. The filmmaker wants to automatically add subtitles and voice-overs in multiple languages to their films.
Which combination of steps will meet these requirements? (Choose two.)

### Các lựa chọn
1. Use Amazon Transcribe and Amazon Translate to generate subtitles in other languages.
2. Use Amazon Textract and Amazon Translate to generate subtitles in other languages.
3. Use Amazon Polly to generate voice-overs in other languages.
4. Use Amazon Translate to generate voice-overs in other languages.
5. Use Amazon Textract to generate voice-overs in other languages.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một nhà làm phim tài liệu muốn mở rộng phạm vi khán giả bằng cách tự động tạo phụ đề và lồng tiếng (voice‑over) cho video của mình ở nhiều ngôn ngữ khác nhau.

Yêu cầu: chọn hai bước (hai lựa chọn) sao cho đáp ứng được việc:

Chuyển đổi giọng nói gốc → văn bản → dịch sang ngôn ngữ đích → tạo phụ đề.

Dịch văn bản → tạo giọng nói mới (lồng tiếng) bằng công nghệ text‑to‑speech.

✅ Các đáp án đúng

1️⃣ Use Amazon Transcribe and Amazon Translate to generate subtitles in other languages.

Amazon Transcribe: dịch vụ speech‑to‑text (STT) quản lý hoàn toàn, cho phép chuyển đổi âm thanh của video thành văn bản gốc (tiếng Anh, tiếng Tây Ban Nha, …).

Amazon Translate: dịch vụ machine translation thời gian thực, hỗ trợ hơn 150 ngôn ngữ, cho phép dịch văn bản đã nhận được từ Transcribe sang ngôn ngữ mục tiêu.

Kết hợp hai dịch vụ này → tạo phụ đề đa ngôn ngữ một cách tự động.

Từ năm 2024‑2025, Amazon Transcribe đã có model Custom Language Model và Batch Transcription, còn Amazon Translate cung cấp Custom Terminology và Parallel Data giúp tăng độ chính xác cho các thuật ngữ chuyên ngành của phim tài liệu.

🟢 Vì vậy lựa chọn này đáp ứng đầy đủ yêu cầu tạo phụ đề đa ngôn ngữ.

2️⃣ Use Amazon Polly to generate voice-overs in other languages.

Amazon Polly: dịch vụ text‑to‑speech (TTS) sử dụng các mô hình Deep Learning, cung cấp neural voices và multi‑language support (hơn 30 ngôn ngữ, hơn 100 giọng nói).

Khi đã có văn bản dịch (bằng Amazon Translate), dùng Polly để đọc lại văn bản đó, tạo file âm thanh (MP3, OGG, WAV) có thể lồng vào video như một voice‑over.

Từ phiên bản 2023‑2025, Polly hỗ trợ Speech Synthesis Markup Language (SSML) enhancements và Lexicon custom pronunciation, giúp tối ưu hoá cách phát âm các tên riêng, thuật ngữ phim tài liệu.

🟢 Vì vậy lựa chọn này đáp ứng yêu cầu tạo voice‑over đa ngôn ngữ.

❌ Các đáp án sai và lý do

❎ Use Amazon Textract and Amazon Translate to generate subtitles in other languages.

Amazon Textract: dịch vụ nhận dạng ký tự (OCR) để trích xuất văn bản từ tài liệu hình ảnh hoặc PDF. Nó không xử lý âm thanh, vì vậy không thể chuyển đổi giọng nói trong video thành văn bản.

Kết hợp Textract với Translate sẽ chỉ hữu ích khi nguồn là tài liệu tĩnh (hình ảnh, PDF), không phù hợp với video tài liệu.

❎ Use Amazon Translate to generate voice-overs in other languages.

Amazon Translate chỉ thực hiện dịch văn bản; nó không tạo ra âm thanh. Để có voice‑over, cần một dịch vụ text‑to‑speech như Amazon Polly, hoặc Amazon Bedrock (model TTS) – nhưng không phải Translate.

❎ Use Amazon Textract to generate voice-overs in other languages.

Như đã nói, Textract chỉ trích xuất văn bản từ hình ảnh, không tham gia vào việc tạo giọng nói. Do đó không thể dùng để tạo voice‑over.

🛠️ Kiến thức cập nhật tới năm 2026

Amazon Transcribe: Custom Language Model (đào tạo trên dữ liệu riêng), Batch Transcribe (xử lý hàng nghìn giờ video), Speaker Identification (phân biệt các người nói), và real‑time streaming.

Amazon Translate: Custom Terminology và Parallel Data để cải thiện độ chính xác trong ngữ cảnh phim tài liệu, Active Custom Translation (điều chỉnh mô hình qua phản hồi người dùng).

Amazon Polly: Neural TTS (v2) với voice‑cloning (được công bố 2025) cho phép tạo giọng nói “giống” người thật, SSML 2.0 hỗ trợ âm thanh đa dạng, và Edge‑Optimized Deployment để giảm latency khi tạo voice‑over trực tiếp trong workflow CI/CD.

Khi kết hợp ba dịch vụ này trong một pipeline (ví dụ: AWS Step Functions → AWS Lambda → S3 lưu trữ phụ đề và audio), nhà làm phim có thể tự động:

Transcribe → 2. Translate → 3. Save subtitles (SRT/WEBVTT) →

Translate (cùng bản dịch) → 5. Polly → 6. Save voice‑over →

AWS Elemental MediaConvert để mux phụ đề và voice‑over vào video cuối cùng.

📚 Tham khảo

Amazon Transcribe – Developer Guide (v2026.02) – https://docs.aws.amazon.com/transcribe/latest/dg/

Amazon Translate – Documentation (v2026.01) – https://docs.aws.amazon.com/translate/latest/dg/

Amazon Polly – Speech Synthesis (v2025.12) – https://docs.aws.amazon.com/polly/latest/dg/

AWS Step Functions – Building Serverless Workflows – https://aws.amazon.com/step-functions/

AWS Blog – “New Features in Amazon Polly Neural Voices” (Nov 2025) – https://aws.amazon.com/blogs/machine-learning/

Tóm lại:

✅ Use Amazon Transcribe and Amazon Translate to generate subtitles in other languages.

✅ Use Amazon Polly to generate voice-overs in other languages.

Các lựa chọn còn lại không phù hợp vì chúng không xử lý đúng loại dữ liệu (âm thanh ↔︎ văn bản ↔︎ giọng nói) mà yêu cầu của bài toán đòi hỏi. 🎬✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312976-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 62

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Kendra, RAG
- Đáp án tham khảo: **Use Retrieval Augmented Generation (RAG)**
- Takeaway nhanh: Công ty muốn xây dựng một chatbot dùng mô hình ngôn ngữ lớn (LLM) để trả lời các câu hỏi liên quan tới chính sách nhân sự. Công ty đã có một “kho tài liệu số” (digital documentation base) khổng lồ – tức là một tập hợp các tài liệu, quy định, hướng dẫn được lưu trữ dưới dạng văn bản. Yêu cầu là tối ưu hoá các câu trả lời mà chatbot sinh ra, sao cho: Nội dung trả lời chính xác, dựa trên các tài liệu thực tế của công ty.
- Nguồn tham khảo trong block: https://aws.amazon.com/kendra/ | https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html | https://github.com/openai/openai-cookbook/blob/main/examples/RAG.ipynb | https://www.examtopics.com/discussions/amazon/view/308682-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to create a chatbot that answers questions about human resources policies. The company is using a large language model (LLM) and has a large digital documentation base.
Which technique should the company use to optimize the generated responses?

### Các lựa chọn
1. Use Retrieval Augmented Generation (RAG).
2. Use few-shot prompting.
3. Set the temperature to 1.
4. Decrease the token size.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn xây dựng một chatbot dùng mô hình ngôn ngữ lớn (LLM) để trả lời các câu hỏi liên quan tới chính sách nhân sự. Công ty đã có một “kho tài liệu số” (digital documentation base) khổng lồ – tức là một tập hợp các tài liệu, quy định, hướng dẫn được lưu trữ dưới dạng văn bản. Yêu cầu là tối ưu hoá các câu trả lời mà chatbot sinh ra, sao cho:

Nội dung trả lời chính xác, dựa trên các tài liệu thực tế của công ty.

Không cần phải “đào tạo lại” (re‑train) toàn bộ mô hình vì tài liệu có thể thay đổi thường xuyên.

Vậy kỹ thuật nào phù hợp nhất để “bổ trợ” (augment) quá trình sinh câu trả lời của LLM bằng cách tra cứu (retrieve) thông tin từ kho tài liệu hiện có?

✅ Đáp án đúng: Use Retrieval Augmented Generation (RAG)

Lý do chọn

RAG kết hợp hai bước:

Retrieval – tìm kiếm (với vector search, BM25, hoặc các công cụ như Amazon Kendra, OpenSearch) các đoạn tài liệu liên quan tới câu hỏi.

Generation – truyền các đoạn tài liệu được lấy về làm “context” (đầu vào) cho LLM, giúp mô hình sinh ra câu trả lời dựa trên thông tin thực tế.

Đối với một kho tài liệu lớn, RAG cho phép cập nhật real‑time mà không cần fine‑tune lại mô hình.

AWS cung cấp dịch vụ Amazon Kendra (search‑optimized) + Amazon Bedrock (LLM) để triển khai RAG một cách dễ dàng (2024‑2026).

Do đó, RAG là kỹ thuật tối ưu nhất cho yêu cầu của câu hỏi.

❌ Các phương án sai và phân tích chi tiết

Use few-shot prompting

Few‑shot prompting chỉ là việc cung cấp một vài ví dụ (few‑shots) trong prompt để “hướng dẫn” mô hình cách trả lời.

Không giải quyết vấn đề truy xuất thông tin từ kho tài liệu lớn.

Khi tài liệu thay đổi, bạn phải cập nhật lại các ví dụ trong prompt – không hiệu quả và dễ gây lỗi.

Do đó, đây không phải là cách tối ưu để khai thác một kho tài liệu khổng lồ.

Set the temperature to 1

Tham số temperature điều khiển mức độ ngẫu nhiên trong quá trình sinh văn bản:

Giá trị cao (≈1) tạo ra câu trả lời đa dạng, ít ổn định, thường giảm độ chính xác và độ nhất quán.

Đối với chatbot trả lời chính sách HR, cần độ tin cậy và độ chính xác cao, vì vậy không nên tăng temperature lên 1.

Decrease the token size

Giảm kích thước token (độ dài tối đa của prompt/response) có thể giảm chi phí nhưng:

Khi tài liệu HR dài, việc cắt ngắn token sẽ loại bỏ thông tin quan trọng, làm giảm chất lượng câu trả lời.

Không phải là giải pháp để “tối ưu hoá” nội dung trả lời, mà chỉ là một biện pháp tối ưu chi phí/độ trễ không phù hợp với yêu cầu chất lượng.

🧩 Tóm tắt nhanh các lựa chọn

✅ Use Retrieval Augmented Generation (RAG) – Kỹ thuật chuẩn để kết hợp tra cứu tài liệu và sinh câu trả lời, phù hợp với kho tài liệu lớn, không cần fine‑tune lại mô hình.

❌ Use few-shot prompting – Chỉ dùng ví dụ trong prompt, không giải quyết tra cứu tài liệu.

❌ Set the temperature to 1 – Tăng độ ngẫu nhiên, giảm độ chính xác, không phù hợp với yêu cầu tính chính xác cao.

❌ Decrease the token size – Giảm độ dài đầu vào/đầu ra, có thể làm mất thông tin quan trọng, không tối ưu cho chất lượng trả lời.

📚 Tham khảo (đến năm 2026)

Amazon Bedrock Documentation – Retrieval‑augmented generation (2024‑2026) – https://docs.aws.amazon.com/bedrock/latest/userguide/rag.html

Amazon Kendra – Enterprise Search – https://aws.amazon.com/kendra/

“Retrieval‑Augmented Generation for LLMs”, paper by Lewis et al., 2020, và các cập nhật trong AWS re:Invent 2023 & 2024.

OpenAI Cookbook – Retrieval‑augmented generation (2025) – https://github.com/openai/openai-cookbook/blob/main/examples/RAG.ipynb (cũng áp dụng cho các LLM trên Bedrock).

💡 Kết luận: Để tối ưu hoá câu trả lời của chatbot HR dựa trên một kho tài liệu số lớn, công ty nên triển khai Retrieval Augmented Generation (RAG), kết hợp Amazon Kendra (hoặc OpenSearch) để tra cứu nhanh các đoạn văn bản liên quan, sau đó đưa chúng vào prompt của LLM trên Amazon Bedrock. Các phương án còn lại không đáp ứng nhu cầu truy xuất thông tin và độ chính xác cần thiết.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308682-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 63

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: prompt engineering
- Đáp án tham khảo: **Few-shot prompting**
- Takeaway nhanh: Công ty muốn dùng một Large Language Model (LLM) để tạo mô tả sản phẩm. Để đảm bảo mô tả được “đúng định dạng”, họ dự định đưa cho mô hình các mô tả mẫu (ví dụ) trước khi yêu cầu tạo nội dung mới. Vậy kỹ thuật prompt engineering nào cho phép “cung cấp ví dụ mẫu” để LLM học cách sắp xếp, định dạng và viết lại nội dung theo mẫu đó? Few‑shot prompting: trong prompt, người dùng chèn nhiều (thường từ 2‑5) ví dụ đầu vào‑đầu ra mẫu. LLM sẽ “học” cách thực hiện nhiệm vụ dựa trên các ví dụ này và sẽ cố gắng sinh ra đáp án có cùng cấu trúc, định dạng và phong cách.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308666-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use a large language model (LLM) to generate product descriptions. The company wants to give the model example descriptions that follow a format.
Which prompt engineering technique will generate descriptions that match the format?

### Các lựa chọn
1. Zero-shot prompting
2. Chain-of-thought prompting
3. One-shot prompting
4. Few-shot prompting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn dùng một Large Language Model (LLM) để tạo mô tả sản phẩm. Để đảm bảo mô tả được “đúng định dạng”, họ dự định đưa cho mô hình các mô tả mẫu (ví dụ) trước khi yêu cầu tạo nội dung mới.

Vậy kỹ thuật prompt engineering nào cho phép “cung cấp ví dụ mẫu” để LLM học cách sắp xếp, định dạng và viết lại nội dung theo mẫu đó?

✅ Đáp án đúng: Few-shot prompting

Few‑shot prompting: trong prompt, người dùng chèn nhiều (thường từ 2‑5) ví dụ đầu vào‑đầu ra mẫu. LLM sẽ “học” cách thực hiện nhiệm vụ dựa trên các ví dụ này và sẽ cố gắng sinh ra đáp án có cùng cấu trúc, định dạng và phong cách.

Đây chính là kỹ thuật phù hợp khi bạn muốn mô hình “bắt chước” một định dạng cụ thể thông qua các mẫu được cung cấp.

🧩 Giải thích các phương án (giữ nguyên tiếng Anh)

1️⃣ Zero-shot prompting (❌ Sai)

Giải thích: Zero‑shot không cung cấp bất kỳ ví dụ nào. Người dùng chỉ mô tả yêu cầu (ví dụ: “Write a product description”). Khi không có mẫu định dạng, LLM sẽ dựa vào kiến thức chung, khiến kết quả có thể không tuân thủ đúng bố cục mong muốn.

Kết luận: Không đáp ứng yêu cầu “cho model example descriptions that follow a format”.

2️⃣ Chain-of-thought prompting (❌ Sai)

Giải thích: Chain‑of‑thought (CoT) khuyến khích mô hình “lập luận từng bước” để giải quyết các câu hỏi phức tạp, thường dùng trong toán học, logic hay suy luận. Nó không liên quan tới việc cung cấp mẫu định dạng; mục tiêu là tăng độ chính xác của lập luận, không định dạng đầu ra.

Kết luận: Không phù hợp với yêu cầu định dạng mẫu.

3️⃣ One-shot prompting (❌ Sai)

Giải thích: One‑shot cung cấp một ví dụ duy nhất (input‑output) trước khi đặt câu hỏi. Mặc dù có thể giúp mô hình nắm bắt một phần định dạng, nhưng một ví dụ thường không đủ để mô tả đầy đủ cấu trúc (đầu đề, tiêu đề, bullet, v.v.). Khi yêu cầu độ nhất quán cao, một ví dụ duy nhất thường dẫn đến biến thể không mong muốn.

Kết luận: Không tối ưu nhất cho việc “giữ nguyên format” trong nhiều trường hợp.

4️⃣ Few-shot prompting (✅ ĐÚNG)

Giải thích: Few‑shot đưa vào nhiều ví dụ mẫu (thường 2‑5) trong cùng một prompt. Nhờ có nhiều mẫu, LLM nhận ra được pattern chung: vị trí tiêu đề, cách viết bullet, độ dài câu, cách chèn thông tin kỹ thuật, v.v. Khi được hỏi “Generate a new product description”, mô hình sẽ tái tạo cùng một format.

Lý do chọn: Đây là kỹ thuật được khuyến nghị khi muốn định hướng định dạng, phong cách và cấu trúc của đầu ra, đặc biệt trong các ứng dụng thực tế như tạo nội dung marketing, báo cáo, email mẫu, v.v.

📚 Tham khảo tài liệu (tính đến 2026)

OpenAI API Documentation – Prompt Engineering (phiên bản 2026): mô tả chi tiết về zero‑shot, one‑shot, few‑shot và chain‑of‑thought.

AWS Bedrock Developer Guide – Prompt Patterns (phiên bản 2026): phần “Few‑shot prompting” giải thích cách cung cấp nhiều ví dụ để “shape” output.

“Prompt Engineering for LLMs” – AWS Machine Learning Blog, 2025: ví dụ thực tế về việc dùng few‑shot để tạo tài liệu có định dạng cố định.

“Chain‑of‑Thought Prompting Elicits Reasoning in Large Language Models” – Wei et al., 2022 (cập nhật trong các whitepaper AWS 2024).

🛠️ Kết luận nhanh

Khi muốn định dạng đầu ra bằng cách cung cấp các mô tả mẫu, hãy sử dụng Few‑shot prompting.

Zero‑shot → không mẫu.

One‑shot → chỉ một mẫu, dễ gây sai lệch.

Chain‑of‑thought → tập trung vào logic, không liên quan tới format.

💡 Mẹo thực hành: Khi thiết kế prompt few‑shot trên AWS Bedrock (hoặc OpenAI), đặt các ví dụ dưới dạng Example: rồi đưa câu hỏi mới, ví dụ:

Code

Example 1:

Input: "Wireless headphones"

Output:

Title: Ultra‑Clear Wireless Headphones

Features:

- Bluetooth 5.2

- 30h battery life

- Noise‑cancelling

Description: ...

Example 2:

...

Now generate a description for: "Smart fitness watch"

Cách này giúp LLM “học” và tái tạo đúng định dạng cho các mô tả sản phẩm mới. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308666-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 64

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, fine-tuning
- Đáp án tham khảo: **Fine‑tuning**
- Takeaway nhanh: A company is using supervised learning to train an AI model on a small labeled dataset that is specific to a target task. Yêu cầu: Xác định bước nào trong vòng đời của một Foundation Model (FM) mà mô tả việc này. Câu hỏi muốn kiểm tra khả năng nhận diện giai đoạn “fine‑tuning” – tức là lấy một mô hình nền tảng đã được pre‑training trên lượng dữ liệu lớn, sau đó “điều chỉnh” (fine‑tune) nó bằng một bộ dữ liệu nhỏ, có nhãn, đặc thù cho nhiệm vụ cần giải quyết. Đây là cách phổ biến để tận dụng sức mạnh của các mô hình lớn mà không phải thu thập, huấn luyện từ đầu.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/fine-tune-foundation-models-with-sagemaker/ | https://docs.aws.amazon.com/bedrock/latest/userguide/fine-tuning.html | https://docs.aws.amazon.com/sagemaker/latest/dg/custom-model-training.html | https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-pillar/welcome.html | https://www.examtopics.com/discussions/amazon/view/312995-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using supervised learning to train an AI model on a small labeled dataset that is specific to a target task.
Which step of the foundation model (FM) lifecycle does this describe?

### Các lựa chọn
1. Fine-tuning
2. Data selection
3. Pre-training
4. Evaluation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

A company is using supervised learning to train an AI model on a small labeled dataset that is specific to a target task.

Yêu cầu: Xác định bước nào trong vòng đời của một Foundation Model (FM) mà mô tả việc này.

Câu hỏi muốn kiểm tra khả năng nhận diện giai đoạn “fine‑tuning” – tức là lấy một mô hình nền tảng đã được pre‑training trên lượng dữ liệu lớn, sau đó “điều chỉnh” (fine‑tune) nó bằng một bộ dữ liệu nhỏ, có nhãn, đặc thù cho nhiệm vụ cần giải quyết. Đây là cách phổ biến để tận dụng sức mạnh của các mô hình lớn mà không phải thu thập, huấn luyện từ đầu.

✅ Đáp án đúng: Fine‑tuning

Khi dùng supervised learning trên dữ liệu nhỏ, có nhãn, gắn liền với task cụ thể, chúng ta đang tinh chỉnh một mô hình nền tảng đã có sẵn để thích nghi với nhiệm vụ mới.

Trong quy trình FM của AWS (và chung cho mọi nền tảng), Fine‑tuning là bước thứ ba (sau Data selection và Pre‑training) và trước Evaluation, Deployment, Monitoring.

🧩 Giải thích các phương án

1. Fine‑tuning (ĐÚNG)

Giải thích:

Fine‑tuning là quá trình huấn luyện lại một mô hình đã pre‑trained bằng dữ liệu có nhãn (thường ít hơn nhiều so với dữ liệu pre‑training) để mô hình học được các đặc điểm đặc thù của task mục tiêu.

Trong AWS, bạn có thể thực hiện fine‑tuning trên Amazon SageMaker JumpStart (đưa model từ Hugging Face, Mistral, LLaMA…) hoặc Amazon Bedrock (sử dụng “custom model” để fine‑tune).

Đây chính là mô tả trong câu hỏi: “supervised learning on a small labeled dataset that is specific to a target task”.

2. Data selection (SAI)

Giải thích:

Data selection là giai đoạn chọn lọc, thu thập, và chuẩn bị dữ liệu sẽ dùng cho pre‑training hoặc fine‑tuning.

Nó không liên quan tới việc đào tạo mô hình mà chỉ là việc xác định nguồn dữ liệu.

Vì câu hỏi đã đề cập tới việc đang training mô hình, nên đây không phải là Data selection.

3. Pre‑training (SAI)

Giải thích:

Pre‑training là bước huấn luyện mô hình từ đầu trên dữ liệu lớn, không có nhãn (hoặc tự giám sát) để mô hình học các biểu diễn chung.

Đặc điểm của pre‑training: dữ liệu rất lớn, không đặc thù cho một task.

Câu hỏi nói “small labeled dataset”, khác hoàn toàn với đặc điểm của pre‑training.

4. Evaluation (SAI)

Giải thích:

Evaluation là bước đánh giá mô hình đã được huấn luyện (pre‑training hoặc fine‑tuning) bằng cách sử dụng bộ dữ liệu validation / test.

Nó không phải là quá trình training mà là đo lường hiệu năng.

Vì câu hỏi mô tả quá trình training, nên không phải là Evaluation.

📚 Tham khảo tài liệu AWS (cập nhật đến 2026)

Amazon SageMaker – Custom Model Training (Fine‑tuning)

https://docs.aws.amazon.com/sagemaker/latest/dg/custom-model-training.html

Amazon Bedrock – Fine‑tuning a Foundation Model

https://docs.aws.amazon.com/bedrock/latest/userguide/fine-tuning.html

AWS Machine Learning Blog – “How to fine‑tune foundation models with SageMaker” (2024‑2025)

https://aws.amazon.com/blogs/machine-learning/fine-tune-foundation-models-with-sagemaker/

AWS Well‑Architected Framework – Machine Learning Pillar (phiên bản 2025)

https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-pillar/welcome.html

🛠️ Kết luận

Câu hỏi mô tả: “sử dụng supervised learning trên một bộ dữ liệu nhỏ, có nhãn, chuyên cho một task”.

Bước trong vòng đời FM tương ứng là Fine‑tuning.

Các phương án còn lại (Data selection, Pre‑training, Evaluation) đều không phản ánh việc đào tạo mô hình trên dữ liệu nhỏ, có nhãn, nên không đúng.

🔚 Hy vọng phân tích trên giúp bạn nắm rõ khái niệm và cách áp dụng trong môi trường AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312995-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 65

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering
- Takeaway nhanh: Which term refers to the instructions given to foundation models (FMs) so that the FMs provide a more accurate response to a question? Câu hỏi đang hỏi về thuật ngữ dùng để chỉ “các chỉ dẫn / lời nhắc” mà chúng ta truyền cho foundation model (một mô hình ngôn ngữ lớn như Claude, Gemini, hoặc Amazon Titan) nhằm khiến mô hình trả lời một câu hỏi một cách chính xác, chi tiết hơn.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/ai/foundations-of-prompt-engineering/ | https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-engineering.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-prompt-tuning.html | https://www.examtopics.com/discussions/amazon/view/308656-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which term refers to the instructions given to foundation models (FMs) so that the FMs provide a more accurate response to a question?

### Các lựa chọn
1. Prompt
2. Direction
3. Dialog
4. Translation

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Which term refers to the instructions given to foundation models (FMs) so that the FMs provide a more accurate response to a question?

Câu hỏi đang hỏi về thuật ngữ dùng để chỉ “các chỉ dẫn / lời nhắc” mà chúng ta truyền cho foundation model (một mô hình ngôn ngữ lớn như Claude, Gemini, hoặc Amazon Titan) nhằm khiến mô hình trả lời một câu hỏi một cách chính xác, chi tiết hơn.

Trong lĩnh vực AI hiện đại (đặc biệt là Generative AI), thuật ngữ này được dùng rộng rãi trong tài liệu kỹ thuật, tutorial, và trong các dịch vụ AI của AWS (Amazon Bedrock, Amazon SageMaker JumpStart, …).

✅ Đáp án đúng

Prompt

Lý do: “Prompt” là thuật ngữ chuẩn để mô tả chuỗi văn bản (hoặc cấu trúc) mà người dùng gửi tới mô hình nền tảng để yêu cầu nó thực hiện một tác vụ nào đó – ví dụ: trả lời câu hỏi, tạo nội dung, dịch thuật, … Khi prompt được thiết kế tốt (có hướng dẫn, ràng buộc, ngữ cảnh), mô hình sẽ tạo ra kết quả chính xác hơn.

Cập nhật 2026: AWS đã cập nhật tài liệu Bedrock và SageMaker để nhấn mạnh “prompt engineering” là một kỹ năng quan trọng, với các công cụ như Prompt Builder, Prompt Tuning, và Prompt Templates.

❌ Giải thích các phương án sai

Direction

Direction không phải là thuật ngữ chuyên ngành trong ngữ cảnh tương tác với mô hình ngôn ngữ. Nó có thể ám chỉ “hướng dẫn” chung, nhưng trong tài liệu AI của AWS và cộng đồng AI toàn cầu, không có định nghĩa nào gọi “direction” là phần đầu vào cho mô hình.

Khi nói “direction” trong AI, thường là một cụm từ phụ trong prompt (ví dụ: “Give directions on how to …”), chứ không phải là tên gọi của phần đầu vào.

Dialog

Dialog (đối thoại) đề cập tới chuỗi các lượt trò chuyện giữa người dùng và mô hình, tức là một phiên giao tiếp liên tiếp. Tuy nhiên, dialog không phải là “lời nhắc” duy nhất mà chúng ta đưa vào mô hình; nó là cấu trúc của một conversation.

AWS Bedrock cung cấp tính năng “Conversation Mode” cho các mô hình, nhưng thuật ngữ “dialog” không dùng để mô tả các chỉ dẫn ban đầu.

Translation

Translation là công việc dịch ngôn ngữ (ví dụ: từ tiếng Anh sang tiếng Việt). Đây là một tác vụ mà mô hình có thể thực hiện, nhưng không phải là “các chỉ dẫn” được cung cấp cho mô hình.

Khi bạn muốn mô hình thực hiện dịch, bạn sẽ đưa vào một prompt như “Translate the following text…”. Do vậy “translation” không phải là đáp án đúng.

📚 Tham khảo tài liệu (2026)

AWS Documentation – Amazon Bedrock Prompt Engineering

https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-engineering.html

Amazon SageMaker JumpStart – Prompt Tuning

https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-prompt-tuning.html

“Foundations of Prompt Engineering” – AWS AI Blog, 2025

https://aws.amazon.com/blogs/ai/foundations-of-prompt-engineering/

🧩 Tổng kết

Prompt là thuật ngữ chuẩn để chỉ “các chỉ dẫn” được đưa cho foundation models nhằm nhận được câu trả lời chính xác hơn.

Các lựa chọn khác (Direction, Dialog, Translation) không mô tả đúng khái niệm này trong bối cảnh AI/ML hiện đại và tài liệu AWS.

👉 Khi chuẩn bị cho kỳ thi AWS Certified DevOps Engineer – Professional hay bất kỳ chứng chỉ AI nào, hãy nhớ rằng Prompt Engineering là kỹ năng cốt lõi, và “Prompt” luôn là đáp án đúng cho câu hỏi này.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308656-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

Đề 2 -------------

Đề 2:
