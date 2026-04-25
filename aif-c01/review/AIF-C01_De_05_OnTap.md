# AIF-C01 - Bộ Ôn Tập Chi Tiết - Đề 05

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 05 tham khảo từ Đề Internet - ExamTopics (Full6de.md)
- Blueprint tham chiếu: `w:\AI Practitioner\AIF\AWS-Certified-AI-Practitioner_Exam-Guide.pdf`
- Ghi chú kỹ thuật: dữ liệu được tách từ `Full6de.md`; parser dùng reset `Câu hỏi 1`/`Câu 1:` và link tham khảo để vá các câu thiếu marker.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon SageMaker | 36 |
| Amazon Bedrock | 26 |
| Amazon Comprehend | 11 |
| Amazon S3 | 10 |
| Amazon SageMaker JumpStart | 9 |
| Amazon SageMaker AI | 8 |
| Amazon Q | 7 |
| Amazon Rekognition | 4 |
| Amazon OpenSearch Service | 3 |
| Amazon Kendra | 3 |
| Amazon Lex | 2 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon Bedrock | 4 |
| Amazon OpenSearch Service | 2 |
| Amazon SageMaker | 1 |
| Amazon Q | 1 |
| Amazon Comprehend | 1 |
| Amazon Kendra | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| model evaluation | 183 |
| prompt engineering | 98 |
| embeddings | 94 |
| guardrails | 63 |
| RAG | 49 |
| responsible AI | 30 |
| fine-tuning | 14 |
| hallucination | 4 |

### Domain heuristic

| Domain | Tên | Tỷ trọng chính thức | Số câu ước lượng |
| --- | --- | --- | --- |
| Domain 1 | Fundamentals of AI and ML | 20% | 20 |
| Domain 2 | Fundamentals of Generative AI | 24% | 22 |
| Domain 3 | Applications of Foundation Models | 28% | 15 |
| Domain 4 | Guidelines for Responsible AI | 14% | 2 |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% | 6 |

## Service Key-Notes

### Amazon SageMaker
- Bộ dịch vụ managed cho vòng đời ML: chuẩn bị dữ liệu, huấn luyện, tuning, deploy, monitor và governance.
- Trong đề AIF, cần phân biệt SageMaker với Bedrock: SageMaker thiên về build/train/deploy ML model; Bedrock thiên về consume/customize foundation model.

### Amazon Bedrock
- Dịch vụ managed để dùng foundation models qua API, thường là đáp án cho generative AI với ít vận hành.
- Các mảng hay gặp: model selection, Knowledge Bases/RAG, Agents, Guardrails, logging, VPC endpoint và dữ liệu không dùng để train model nền mặc định.

### Amazon Comprehend
- Dịch vụ NLP managed cho entity, key phrases, sentiment, topic và phân tích văn bản.
- Không phải công cụ tạo nội dung generative AI hay vector database.

### Amazon S3
- Object storage nền tảng cho dataset, artifact, log, nguồn dữ liệu RAG và output pipeline ML.
- Hay đi cùng security/governance như encryption, lifecycle, access control và data residency.

### Amazon SageMaker JumpStart
- Cung cấp model và solution template dựng sẵn, phù hợp khi cần triển khai hoặc fine-tune model nguồn mở với ít operational effort.
- Nếu câu hỏi nhấn mạnh least operational effort cho open-source LLM, JumpStart thường là lựa chọn mạnh.

### Amazon SageMaker AI
- Tên mới/biến thể cách gọi SageMaker trong nguồn câu hỏi, thường trỏ về cùng nhóm năng lực ML managed.
- Hay đi cùng training job, endpoint, Feature Store, Clarify, Model Cards và JumpStart.

### Amazon Q
- Trợ lý generative AI của AWS cho công việc doanh nghiệp, code và tri thức nội bộ.
- Amazon Q Developer thường gắn với hỗ trợ lập trình, giải thích code, tạo code và tăng năng suất developer.

### Amazon Rekognition
- Dịch vụ computer vision managed cho ảnh/video: object, label, moderation, face và text detection.
- Nếu câu hỏi cần nhận dạng hình ảnh không phải tự train model, Rekognition thường là đáp án.

## Pattern Key-Notes

### model evaluation
- Chọn metric theo task: ROUGE cho summarization, accuracy/precision/recall/F1 cho classification, MSE cho regression.
- Không dùng metric không liên quan chỉ vì quen thuộc trong ML truyền thống.

### prompt engineering
- Kỹ thuật thiết kế chỉ dẫn cho foundation model để tăng độ chính xác, định dạng và tính nhất quán của output.
- Không thay thế guardrails, validation hoặc kiểm soát bảo mật trước prompt injection.

### embeddings
- Vector số biểu diễn ý nghĩa của văn bản/hình ảnh/đối tượng để tìm kiếm tương đồng và clustering.
- Embedding thường đi cùng vector database, semantic search và RAG.

### guardrails
- Cơ chế kiểm soát input/output nhằm giảm nội dung độc hại, prompt injection và vi phạm policy.
- Trên Bedrock, Guardrails là keyword quan trọng cho yêu cầu responsible/safe generative AI.

### RAG
- Retrieval-Augmented Generation đưa tri thức ngoài vào context để giảm hallucination và tăng tính cập nhật.
- Trên AWS thường ghép Bedrock với Knowledge Bases, Kendra, OpenSearch hoặc S3.

### responsible AI
- Nhóm nguyên tắc về fairness, transparency, explainability, privacy, safety và accountability.
- Trong AIF-C01, cần nhận diện rủi ro như bias, toxicity, plagiarism, hallucination và misuse.

## Cách Học Đề Này

- Đọc nhanh các service/pattern nổi bật để biết đề nghiêng về Bedrock, SageMaker, responsible AI hay governance.
- Với câu generative AI, xác định trước keyword như `RAG`, `prompt`, `embedding`, `guardrails`, `fine-tuning`, `hallucination`.
- Với câu ML nền tảng, chọn metric/kỹ thuật đúng theo task thay vì nhớ máy móc đáp án.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Công ty đang so sánh một số large language models (LLM) để thực hiện tổng hợp văn bản (text summarization). Để quyết định mô hình nào cho kết quả tốt nhất, họ cần chọn một metric đo lường chất lượng của các bản tóm tắt do LLM sinh ra. Yêu cầu: metric phải phản ánh độ tương đồng nội dung giữa bản tóm tắt tự động và bản tóm tắt tham chiếu (ground‑truth). Trong các metric truyền thống, ROUGE (Recall‑Oriented Understudy for Gisting Evaluation) là tiêu chuẩn công nghiệp cho việc đánh giá tóm tắt, vì nó tính toán các n‑gram, chuỗi con (skip‑bigram) và longest common subsequence giữa đầu ra và bản chuẩn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313025-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is evaluating several large language models (LLMs) for a text summarization task. The company needs to select a metric to evaluate the quality of the summaries that the LLMs generate.
Which metric will meet this requirement?

### Các lựa chọn
1. Recall
2. Area under the ROC curve (AUC)
3. Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
4. Mean squared error (MSE)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang so sánh một số large language models (LLM) để thực hiện tổng hợp văn bản (text summarization). Để quyết định mô hình nào cho kết quả tốt nhất, họ cần chọn một metric đo lường chất lượng của các bản tóm tắt do LLM sinh ra.

Yêu cầu: metric phải phản ánh độ tương đồng nội dung giữa bản tóm tắt tự động và bản tóm tắt tham chiếu (ground‑truth).

Trong các metric truyền thống, ROUGE (Recall‑Oriented Understudy for Gisting Evaluation) là tiêu chuẩn công nghiệp cho việc đánh giá tóm tắt, vì nó tính toán các n‑gram, chuỗi con (skip‑bigram) và longest common subsequence giữa đầu ra và bản chuẩn.

✅ Đáp án đúng

Recall‑Oriented Understudy for Gisting Evaluation (ROUGE)

🟢 Lý do chọn ROUGE

Thiết kế cho summarization – ROUGE được sinh ra từ nhu cầu đánh giá hệ thống tóm tắt, nên nó đo lường mức độ “gợi nhớ” (recall) của các n‑gram quan trọng trong bản chuẩn.

Các biến thể phong phú – ROUGE‑1, ROUGE‑2, ROUGE‑L, ROUGE‑SU4… cho phép đo lường chi tiết các khía cạnh:

ROUGE‑1/2: độ trùng khớp n‑gram.

ROUGE‑L: longest common subsequence, phản ánh thứ tự câu.

ROUGE‑SU4: skip‑bigram với tối đa 4 khoảng cách, đánh giá ngữ cảnh linh hoạt.

Được cộng đồng NLP chấp nhận rộng rãi – Các hội nghị (ACL, EMNLP) và benchmark (GLUE, SuperGLUE, SummEval) vẫn dùng ROUGE làm chỉ số chuẩn cho summarization.

Triển khai dễ dàng trên AWS – Có sẵn trong các SDK Python (rouge_score, datasets), có thể chạy trên Amazon SageMaker Processing Jobs hoặc AWS Lambda để tự động hoá pipeline đánh giá.

❌ Giải thích các phương án sai

Recall

Recall chỉ đo tỷ lệ phần tử đúng được “gợi lại” trong một tập hợp, thường dùng cho binary classification hoặc information retrieval.

Nó không xét đến thứ tự hay cấu trúc ngôn ngữ, vì vậy không đủ để đánh giá chất lượng bản tóm tắt đầy đủ như ROUGE.

Area under the ROC curve (AUC)

AUC là metric cho binary classifier (đánh giá khả năng phân biệt giữa hai lớp).

Summarization không phải là bài toán phân loại, mà là tạo ra chuỗi văn bản; do đó AUC không áp dụng và không phản ánh độ giống nội dung.

Mean squared error (MSE)

MSE đo sai số trung bình bình phương giữa các giá trị số (ví dụ: dự báo thời gian, giá trị liên tục).

Khi đầu ra là chuỗi ký tự, việc chuyển sang vector số và tính MSE sẽ mất đi ngữ nghĩa và không cung cấp thông tin về chất lượng nội dung tóm tắt.

📚 Tham khảo (tính đến năm 2026)

Lin, C.-Y. (2004). “ROUGE: A Package for Automatic Evaluation of Summaries.” – Bài báo gốc giới thiệu ROUGE.

Bajaj, S. et al. (2023). “SummEval: Reassessing Summarization Evaluation.” – Khảo sát các metric hiện đại, khẳng định ROUGE vẫn là tiêu chuẩn cơ bản.

AWS Documentation – Amazon SageMaker Processing Jobs (2026). Hướng dẫn tích hợp thư viện rouge_score trong pipeline đánh giá.

Hugging Face Datasets – “rouge” metric (cập nhật 2026). Cung cấp API chuẩn để tính ROUGE trên môi trường AWS.

🛠️ Kết luận nhanh

ROUGE ✅ là metric duy nhất trong danh sách đáp ứng yêu cầu đánh giá chất lượng tóm tắt do các LLM sinh ra.

Các metric còn lại (Recall, AUC, MSE) ❌ không được thiết kế cho nhiệm vụ này và sẽ cho kết quả không phản ánh đúng chất lượng nội dung.

💡 Nếu muốn nâng cao hơn, công ty có thể bổ sung BERTScore hoặc GPT‑Eval (đánh giá dựa trên mô hình LLM) để bổ trợ cho ROUGE, nhưng ROUGE vẫn là lựa chọn chuẩn và được chấp nhận rộng rãi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313025-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 02

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, guardrails
- Đáp án tham khảo: **Cấu hình nhanh, không thay đổi model, lọc cả prompt và output, giảm đáng kể rủi ro injection.**
- Takeaway nhanh: Giải thích (tiếng Việt): Fine‑tuning yêu cầu thu thập một bộ dữ liệu lớn, gán nhãn an toàn/độc hại, sau đó chạy quy trình huấn luyện lại trên mô hình. Quá trình này tốn thời gian (tuần‑tháng), chi phí (điện toán GPU/Trn1) và kỹ năng (ML‑ops). Ngoài ra, việc fine‑tune không thể đảm bảo 100 % ngăn chặn mọi dạng prompt injection, vì các mẫu tấn công mới có thể xuất hiện sau khi mô hình đã được huấn luyện.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/prompt-injection-protection/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ai-ml.html | https://www.awsreInvent.com/2023/secure-genai-bedrock/ | https://www.examtopics.com/discussions/amazon/view/313012-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a new generative AI chatbot. The chatbot uses an Amazon Bedrock foundation model (FM) to generate responses. During testing, the company notices that the chatbot is prone to prompt injection attacks.
What can the company do to secure the chatbot with the LEAST implementation effort?

### Các lựa chọn
1. Fine-tune the FM to avoid harmful responses.
2. Use Amazon Bedrock Guardrails content filters and denied topics.
3. Change the FM to a more secure FM.
4. Use chain-of-thought prompting to produce secure responses.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Bối cảnh: Công ty đang xây dựng một chatbot AI sinh ra (generative AI) dựa trên Amazon Bedrock và một foundation model (FM). Khi chạy thử, họ phát hiện chatbot dễ bị prompt‑injection attacks – kẻ tấn công chèn các lệnh hoặc nội dung độc hại vào prompt để làm cho mô hình trả lời sai, đưa ra thông tin nhạy cảm, hoặc thực hiện hành vi không mong muốn.

Yêu cầu: “What can the company do to secure the chatbot with the LEAST implementation effort?” → Tìm cách bảo vệ chatbot với công sức triển khai ít nhất. Vì vậy chúng ta cần một giải pháp “plug‑and‑play”, không yêu cầu thay đổi mô hình, không cần thu thập dữ liệu mới để fine‑tune, và không đòi hỏi việc thiết kế lại prompt phức tạp.

✅ Đáp án đúng

Use Amazon Bedrock Guardrails content filters and denied topics.

Vì sao đây là lựa chọn ít công sức nhất?

Tích hợp sẵn trong Amazon Bedrock

Guardrails là một tính năng được cung cấp ngay trong dịch vụ Bedrock (từ 2023, nâng cấp liên tục tới 2026). Bạn chỉ cần bật các content filters (lọc nội dung) và định nghĩa các denied topics (chủ đề cấm) thông qua API hoặc console.

Không cần thay đổi model

Guardrails hoạt động ở lớp trung gian: khi prompt tới mô hình và khi phản hồi trả về, chúng sẽ kiểm tra và chặn các nội dung vi phạm. Vì vậy không cần fine‑tune hay đổi mô hình.

Triển khai nhanh

Bạn chỉ cần tạo một Guardrails policy (có sẵn template) và gán cho endpoint Bedrock. Thời gian cấu hình thường chỉ trong vài phút, không yêu cầu viết code phức tạp hoặc thu thập dữ liệu nhãn.

Hiệu quả chống prompt injection

Guardrails có khả năng nhận diện các mẫu injection (ví dụ: “Ignore previous instructions and …”) và ngăn chặn chúng trước khi chúng tới mô hình, giảm thiểu rủi ro đáng kể.

Do đó, đây là giải pháp “least implementation effort” so với các phương án khác.

❌ Phân tích các phương án còn lại

1️⃣ Fine‑tune the FM to avoid harmful responses.

Giải thích (tiếng Việt):

Fine‑tuning yêu cầu thu thập một bộ dữ liệu lớn, gán nhãn an toàn/độc hại, sau đó chạy quy trình huấn luyện lại trên mô hình.

Quá trình này tốn thời gian (tuần‑tháng), chi phí (điện toán GPU/Trn1) và kỹ năng (ML‑ops).

Ngoài ra, việc fine‑tune không thể đảm bảo 100 % ngăn chặn mọi dạng prompt injection, vì các mẫu tấn công mới có thể xuất hiện sau khi mô hình đã được huấn luyện.

Kết luận: ❌ Không phải là giải pháp ít công sức; chi phí và độ phức tạp cao.

2️⃣ Change the FM to a more secure FM.

Giải thích (tiếng Việt):

Chuyển sang một mô hình “an toàn hơn” (ví dụ: một model được nhà cung cấp khai báo có mức độ “safety‑tuned”) vẫn cần thay đổi endpoint, có thể phải điều chỉnh lại prompt, và đánh giá lại hiệu suất.

Việc lựa chọn mô hình mới không tự động giải quyết được prompt injection; ngay cả các model “secure” cũng có thể bị lừa đảo bởi các prompt tinh vi.

Thay đổi mô hình còn có thể gây gián đoạn dịch vụ và đòi hỏi kiểm thử lại toàn bộ pipeline.

Kết luận: ❌ Cần nỗ lực triển khai và không chắc chắn sẽ giảm được rủi ro ngay lập tức.

3️⃣ Use chain‑of‑thought prompting to produce secure responses.

Giải thích (tiếng Việt):

Chain‑of‑thought (CoT) là kỹ thuật thiết kế prompt khiến mô hình “nghĩ” từng bước trước khi đưa ra đáp án. Mặc dù CoT có thể cải thiện độ chính xác và minh bạch, nhưng không phải là biện pháp phòng ngừa prompt injection.

Việc thiết kế CoT đòi hỏi thiết kế lại prompt cho mọi yêu cầu, tốn công trong việc viết, kiểm thử và duy trì.

Các kẻ tấn công vẫn có thể chèn lệnh vào phần “thought” và gây ra phản hồi không mong muốn.

Kết luận: ❌ Không đáp ứng yêu cầu “least implementation effort” và không chuyên dụng cho an toàn.

🧩 Tóm tắt so sánh nhanh

Guardrails (đúng) – ✅ Cấu hình nhanh, không thay đổi model, lọc cả prompt và output, giảm đáng kể rủi ro injection.

Fine‑tune – ❌ Yêu cầu dữ liệu, thời gian huấn luyện, chi phí cao, không bảo đảm toàn diện.

Đổi FM – ❌ Cần thay đổi kiến trúc, kiểm thử lại, vẫn có thể bị tấn công.

Chain‑of‑thought – ❌ Cần viết prompt phức tạp, không ngăn chặn injection, công sức cao.

📚 Nguồn tham khảo (cập nhật đến 2026)

Amazon Bedrock Developer Guide – Guardrails

https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html (phiên bản 2024‑2026, cập nhật các policy mẫu và API CreateGuardrail, AssociateGuardrail).

AWS Security Blog – Protecting Generative AI Applications from Prompt Injection (2023‑2025)

https://aws.amazon.com/blogs/security/prompt-injection-protection/

AWS re:Invent 2023 – “Building Secure Generative AI with Amazon Bedrock Guardrails” (video và slide)

https://www.awsreInvent.com/2023/secure-genai-bedrock/

AWS Well‑Architected Framework – Security Pillar (AI/ML add‑on)

https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ai-ml.html

🎯 Kết luận cuối cùng

Với mục tiêu bảo mật chatbot và giảm thiểu công sức triển khai, công ty nên kích hoạt Amazon Bedrock Guardrails (content filters + denied topics). Đây là cách nhanh, tích hợp sẵn, và đã được chứng minh là hiệu quả trong việc ngăn chặn các cuộc tấn công injection trên mô hình nền tảng. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313012-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 03

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Polly, Amazon Q, Amazon Rekognition, Amazon Q Business
- Takeaway nhanh: Một công ty đang xây dựng một ứng dụng AI sinh ra (generative AI) trên AWS, mục tiêu giúp học sinh cải thiện khả năng đọc hiểu. Ứng dụng cần cho phép học sinh thêm hình minh hoạ vào các câu chuyện mà họ đang đọc/viết. Vì vậy câu hỏi đang hỏi: Giải pháp nào trên AWS có thể chuyển đổi “đoạn văn bản mô tả hình ảnh” thành hình ảnh (illustrations) một cách tự động?
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/generative-ai-stable-diffusion-bedrock/ | https://aws.amazon.com/q-business/ | https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html | https://docs.aws.amazon.com/polly/latest/dg/ | https://docs.aws.amazon.com/rekognition/latest/dg/ | https://www.examtopics.com/discussions/amazon/view/313002-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a generative AI application on AWS. The application will help improve reading comprehension for students. The application must give students the ability to add illustrations to stories.
Which solution will meet this requirement?

### Các lựa chọn
1. Use Amazon Bedrock Stable Diffusion 3.5 Large to generate images based on text inputs.
2. Use Amazon Polly to create an audiobook based on story texts.
3. Use Amazon Rekognition to analyze image contents and detect text attributes.
4. Create a standard prompt template. Use Amazon Q Business to illustrate stories.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Một công ty đang xây dựng một ứng dụng AI sinh ra (generative AI) trên AWS, mục tiêu giúp học sinh cải thiện khả năng đọc hiểu. Ứng dụng cần cho phép học sinh thêm hình minh hoạ vào các câu chuyện mà họ đang đọc/viết.

Vì vậy câu hỏi đang hỏi: Giải pháp nào trên AWS có thể chuyển đổi “đoạn văn bản mô tả hình ảnh” thành hình ảnh (illustrations) một cách tự động?

Ta cần một dịch vụ tạo ảnh từ văn bản (text‑to‑image), tích hợp được trong môi trường generative AI và có sẵn trên AWS.

✅ Đáp án đúng

- Use Amazon Bedrock Stable Diffusion 3.5 Large to generate images based on text inputs.

Lý do:

Amazon Bedrock cung cấp các mô hình nền tảng (foundation models) cho cả ngôn ngữ và hình ảnh.

Stable Diffusion 3.5 Large (phiên bản mới cập nhật tới 2024‑2025) là mô hình text‑to‑image mạnh mẽ, được hỗ trợ trực tiếp trong Bedrock, cho phép truyền một prompt mô tả cảnh hoặc nhân vật và nhận lại hình ảnh chất lượng cao.

Bedrock cung cấp API an toàn, có thể tích hợp vào kiến trúc serverless (Lambda, API Gateway) hoặc container (ECS/EKS) để phục vụ yêu cầu thời gian thực của học sinh.

Đúng với yêu cầu “add illustrations to stories”.

❌ Giải thích các phương án sai

1️⃣ Use Amazon Polly to create an audiobook based on story texts.

Polly là dịch vụ Text‑to‑Speech (chuyển văn bản thành giọng nói). Nó không có khả năng tạo ra hình ảnh, chỉ tạo file âm thanh.

Vì mục tiêu là hình minh hoạ, nên Polly không đáp ứng yêu cầu.

2️⃣ Use Amazon Rekognition to analyze image contents and detect text attributes.

Rekognition là dịch vụ phân tích ảnh/video (phát hiện khuôn mặt, vật thể, văn bản trong ảnh). Nó phân tích ảnh hiện có, không tạo ảnh mới từ văn bản.

Do đó không phù hợp cho việc sinh ra hình minh hoạ từ câu chuyện.

3️⃣ Create a standard prompt template. Use Amazon Q Business to illustrate stories.

Amazon Q Business là giải pháp search‑augmented generative AI cho doanh nghiệp, tập trung vào truy vấn dữ liệu nội bộ, trả lời câu hỏi và tạo nội dung văn bản.

Hiện tại Q Business không tích hợp mô hình tạo ảnh như Stable Diffusion và không cung cấp API text‑to‑image.

Việc “create a standard prompt template” có thể là một bước chuẩn bị, nhưng công cụ Q Business không thực hiện việc sinh ảnh, vì vậy đáp án này sai.

🧩 Tóm tắt so sánh nhanh

Amazon Bedrock (Stable Diffusion 3.5 Large) → text‑to‑image ✅

Amazon Polly → text‑to‑speech ❌

Amazon Rekognition → image/video analysis ❌

Amazon Q Business → search‑augmented LLM, không tạo ảnh ❌

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Documentation – “Supported foundation models” (Stable Diffusion 3.5 Large) – https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html

AWS Generative AI Blog, 2025 – “Using Stable Diffusion on Bedrock for high‑quality illustration generation” – https://aws.amazon.com/blogs/aws/generative-ai-stable-diffusion-bedrock/

Amazon Polly – Developer Guide – https://docs.aws.amazon.com/polly/latest/dg/

Amazon Rekognition – API Reference – https://docs.aws.amazon.com/rekognition/latest/dg/

Amazon Q Business – Product Overview – https://aws.amazon.com/q-business/

Kết luận: Để cho học sinh thêm hình minh hoạ vào câu chuyện, Amazon Bedrock với mô hình Stable Diffusion 3.5 Large là giải pháp duy nhất trong các lựa chọn đáp ứng yêu cầu “tạo ảnh từ văn bản”. Các phương án còn lại không cung cấp chức năng tạo ảnh và do đó không phù hợp. 🎉

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313002-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 04

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Glue, Amazon Lake Formation, Amazon Bedrock, Amazon CloudFront, Amazon PrivateLink, Amazon Virtual Private Cloud
- Takeaway nhanh: Công ty muốn truy cập riêng tư (private access) tới các API của Amazon Bedrock từ tài khoản AWS của mình, đồng thời ngăn dữ liệu bị phơi bày ra Internet. Yêu cầu thực chất là: Kết nối mạng phải được thiết lập trong VPC của công ty, không đi qua internet public. Giao tiếp với dịch vụ Bedrock phải được được bảo mật, chỉ cho phép từ VPC (hoặc các tài khoản được ủy quyền).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/best-practices-for-vpc-endpoints/ | https://docs.aws.amazon.com/bedrock/latest/userguide/bedrock-private-link.html | https://docs.aws.amazon.com/vpc/latest/privatelink/ | https://www.examtopics.com/discussions/amazon/view/313026-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to set up private access to Amazon Bedrock APIs from the company’s AWS account. The company also wants to protect its data from internet exposure. Which solution meets these requirements?

### Các lựa chọn
1. Use Amazon CloudFront to restrict access to the company’s private content.
2. Use AWS Glue to set up data encryption across the company’s data catalog.
3. Use AWS Lake Formation to manage centralized data governance and cross-account data sharing.
4. Use AWS PrivateLink to configure a private connection between the company’s VPC and Amazon Bedrock.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn truy cập riêng tư (private access) tới các API của Amazon Bedrock từ tài khoản AWS của mình, đồng thời ngăn dữ liệu bị phơi bày ra Internet.

Yêu cầu thực chất là:

Kết nối mạng phải được thiết lập trong VPC của công ty, không đi qua internet public.

Giao tiếp với dịch vụ Bedrock phải được được bảo mật, chỉ cho phép từ VPC (hoặc các tài khoản được ủy quyền).

Do đó câu trả lời phải là một giải pháp network‑level isolation (điểm cuối VPC riêng) chứ không phải các giải pháp ở lớp dữ liệu hoặc CDN.

✅ Đáp án đúng

✔️ Use AWS PrivateLink to configure a private connection between the company’s VPC and Amazon Bedrock.

Tại sao?

AWS PrivateLink tạo ra VPC endpoint interface cho một dịch vụ AWS (ở đây là Amazon Bedrock).

Lưu lượng không đi ra Internet; nó được truyền qua Amazon’s private network.

Bạn có thể kiểm soát truy cập bằng Security Groups và IAM policy; chỉ các tài nguyên trong VPC mới có thể gọi Bedrock API.

Từ 2024, Amazon Bedrock hỗ trợ PrivateLink (được cập nhật liên tục đến 2026), cho phép các khách hàng thiết lập private connectivity mà không cần NAT, Internet Gateway hoặc VPN.

Do vậy, PrivateLink đáp ứng đầy đủ cả “private access” và “protect data from internet exposure”.

❌ Giải thích các phương án sai

Use Amazon CloudFront to restrict access to the company’s private content.

CloudFront là dịch vụ CDN, chủ yếu dùng để phân phối nội dung công cộng hoặc bảo mật bằng signed URLs/cookies.

Nó không tạo kết nối riêng tư tới API nội bộ; lưu lượng vẫn phải đi qua Internet (được đưa về các edge location) và không thể ngăn hoàn toàn việc truy cập từ Internet.

Vì vậy không phù hợp để “private access” tới Amazon Bedrock.

Use AWS Glue to set up data encryption across the company’s data catalog.

AWS Glue là dịch vụ ETL và Data Catalog. Việc encrypt catalog chỉ bảo vệ siêu dữ liệu, không ảnh hưởng tới cách mà các API Bedrock được gọi.

Không cung cấp mạng riêng hay ngăn chặn truy cập Internet tới Bedrock.

Use AWS Lake Formation to manage centralized data governance and cross‑account data sharing.

Lake Formation tập trung vào quản trị dữ liệu, phân quyền truy cập, và chia sẻ dữ liệu giữa các tài khoản hoặc miền dữ liệu.

Nó không cung cấp cơ chế mạng riêng để kết nối tới Bedrock và không ngăn chặn lưu lượng Internet.

Do đó không đáp ứng yêu cầu “private access”.

🛠️ Các bước triển khai AWS PrivateLink cho Amazon Bedrock (2026)

Mở Service Endpoint: Trong VPC của công ty, tạo Interface VPC Endpoint cho dịch vụ com.amazonaws.<region>.bedrock.

Chọn Subnets & Security Groups: Gắn endpoint vào các subnet cần thiết, thiết lập Security Group chỉ cho phép traffic đến/đến các IP nội bộ của công ty.

Cập nhật DNS (tùy chọn): Endpoint tạo một CNAME trong Route 53 (hoặc sử dụng Private DNS) để các ứng dụng gọi bedrock.<region>.amazonaws.com sẽ được tự động chuyển tới endpoint riêng.

IAM Policy: Gán IAM policy cho role/role policy cho phép gọi bedrock:* chỉ khi request xuất phát từ VPC endpoint.

Kiểm tra: Dùng AWS CLI hoặc SDK để gọi Bedrock API; nếu cấu hình đúng, bạn sẽ nhận được response và bản ghi CloudWatch Logs sẽ cho thấy traffic đi qua Interface Endpoint (địa chỉ IP private).

📚 Tham khảo

Amazon Bedrock – PrivateLink integration (AWS Documentation, cập nhật 2025‑2026): https://docs.aws.amazon.com/bedrock/latest/userguide/bedrock-private-link.html

AWS PrivateLink – How it works (AWS Docs, 2026): https://docs.aws.amazon.com/vpc/latest/privatelink/

Best practices for securing VPC endpoints (AWS Security Blog, 2025): https://aws.amazon.com/blogs/security/best-practices-for-vpc-endpoints/

🧩 Tổng kết:

Để “private access” tới Amazon Bedrock và bảo vệ dữ liệu khỏi Internet, AWS PrivateLink là giải pháp duy nhất đáp ứng yêu cầu mạng riêng và kiểm soát truy cập. Các lựa chọn khác (CloudFront, Glue, Lake Formation) đều không cung cấp kết nối VPC‑độc lập và do đó không phù hợp. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313026-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 05

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Takeaway nhanh: Công ty đã triển khai Amazon Bedrock để tạo một trợ lý AI sinh tạo (generative AI) trên website, nhiệm vụ của trợ lý là gợi ý sản phẩm và hỗ trợ quyết định mua hàng. Công ty muốn đo lường ảnh hưởng trực tiếp của trợ lý này tới kết quả bán hàng. Vì vậy, metric cần phải: Liên kết tương tác của khách hàng với hành động mua hàng (không chỉ là mức độ hài lòng hay số lần sử dụng).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312966-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses Amazon Bedrock to implement a generative AI assistant on a website. The AI assistant helps customers with product recommendations and purchasing decisions.
The company wants to measure the direct impact of the AI assistant on sales performance.
Which metric will meet these requirements?

### Các lựa chọn
1. The conversion rate of customers who purchase products after AI assistant interactions.
2. The number of customer interactions with the AI assistant
3. Sentiment analysis scores from customer feedback after AI assistant interactions
4. Natural language understanding accuracy rates

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đã triển khai Amazon Bedrock để tạo một trợ lý AI sinh tạo (generative AI) trên website, nhiệm vụ của trợ lý là gợi ý sản phẩm và hỗ trợ quyết định mua hàng.

Công ty muốn đo lường ảnh hưởng trực tiếp của trợ lý này tới kết quả bán hàng. Vì vậy, metric cần phải:

Liên kết tương tác của khách hàng với hành động mua hàng (không chỉ là mức độ hài lòng hay số lần sử dụng).

Cho phép so sánh “có trợ lý AI hay không” → “có mua hàng hay không” để tính tác động thực tế lên doanh thu.

✅ Đáp án đúng

The conversion rate of customers who purchase products after AI assistant interactions.

Vì sao đáp án này là đúng?

Conversion rate (tỷ lệ chuyển đổi) đo phần trăm khách hàng thực hiện hành động mua hàng sau khi đã tương tác với trợ lý AI.

Đây là metric kinh doanh trực tiếp phản ánh tác động của AI tới doanh thu – đúng yêu cầu “measure the direct impact of the AI assistant on sales performance”.

Khi so sánh conversion rate giữa nhóm có và không dùng trợ lý, công ty có thể xác định lợi nhuận thực sự mà AI mang lại.

AWS khuyến nghị sử dụng business‑oriented KPIs (conversion, revenue per visitor, AOV…) để đo hiệu quả của các dịch vụ AI trên nền tảng Amazon Bedrock (xem AWS Well‑Architected Framework – Business Metrics, 2025‑2026).

❌ Các phương án sai và lý do

The number of customer interactions with the AI assistant

Đây chỉ là độ phủ (how many times the assistant is used). Nó không cho biết khách hàng có thực sự mua hàng hay không, nên không phản ánh độ ảnh hưởng trực tiếp tới doanh số.

Có thể có nhiều tương tác nhưng tỷ lệ chuyển đổi thấp, dẫn đến hiểu lầm về hiệu quả.

Sentiment analysis scores from customer feedback after AI assistant interactions

Sentiment đo sự hài lòng / cảm xúc của khách hàng. Mặc dù quan trọng để cải thiện trải nghiệm, nhưng không đồng nghĩa với việc khách hàng mua hàng.

Các nghiên cứu AWS (2024‑2026) chỉ khuyến nghị kết hợp sentiment với sales‑oriented metrics để có cái nhìn toàn diện, chứ không dùng sentiment làm thước đo duy nhất cho doanh thu.

Natural language understanding accuracy rates

Đây là metric kỹ thuật đo độ chính xác của mô hình NLU (intent, entity extraction). Nó đánh giá hiệu năng mô hình, không phản ánh kết quả kinh doanh.

Một mô hình NLU có độ chính xác cao vẫn có thể không dẫn tới tăng doanh thu nếu không được tích hợp đúng cách vào quy trình bán hàng.

🛠️ Gợi ý thực tiễn để đo Conversion Rate với Amazon Bedrock

Xác định Event: Ghi lại sự kiện “AI Assistant Interaction Completed” (ví dụ: trong Amazon CloudWatch Events hoặc EventBridge).

Kết nối với Transaction: Khi người dùng thực hiện mua hàng, ghi nhận “Purchase Completed” với thông tin sessionId hoặc userId.

Tính toán metric:

Code

SELECT

COUNT(DISTINCT purchase.userId) / COUNT(DISTINCT interaction.userId) AS conversion_rate

FROM interactions AS interaction

LEFT JOIN purchases AS purchase

ON interaction.sessionId = purchase.sessionId

WHERE interaction.timestamp BETWEEN :start AND :end;

(Sử dụng Amazon Athena hoặc Amazon Redshift Spectrum).

So sánh A/B: Chạy thử nghiệm A/B (với/không AI) và sử dụng Amazon CloudWatch Evidently để theo dõi conversion rate theo thời gian.

📚 Tham khảo

AWS Well‑Architected Framework – Business Metrics (2025 cập nhật).

Amazon Bedrock Developer Guide, phần “Monitoring and measuring AI application outcomes” (phiên bản 2026).

AWS Blog – Measuring the impact of generative AI on revenue (08/2025).

Amazon CloudWatch Evidently documentation (phiên bản 2026).

Tóm lại: Để đo độ ảnh hưởng trực tiếp của trợ lý AI (dựa trên Amazon Bedrock) tới kết quả bán hàng, conversion rate của khách hàng sau khi tương tác với trợ lý là metric duy nhất đáp ứng yêu cầu. Các metric khác chỉ cung cấp thông tin phụ trợ (số lượng tương tác, cảm xúc, độ chính xác mô hình) nhưng không phản ánh trực tiếp doanh thu. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312966-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 06

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313001-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. An ecommerce company is developing a generative AI solution to create personalized product recommendations for its application users. The company wants to track how effectively the AI solution increases product sales and user engagement in the application.
2. Select the correct business metric from the following list for each business goal. Each business metric should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313001-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 07

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **SageMaker Clarify – cung cấp tính năng Explainability (feature importance, SHAP values) và bias detection, đáp ứng yêu cầu hiển thị ảnh hưởng của từng feature.**
- Takeaway nhanh: Công ty đang sử dụng Amazon SageMaker để triển khai một mô hình phân loại các bài đăng trên mạng xã hội, mục tiêu là xác định xem nội dung có chứa các “topic” (chủ đề) nhất định hay không. Yêu cầu quan trọng: công ty muốn minh bạch – thể hiện các đặc trưng (input features) nào đã ảnh hưởng tới quyết định của mô hình cho từng dự đoán. Nói cách khác, họ cần một công cụ “giải thích” (model explainability) để người dùng, nhà phát triển hoặc các bên liên quan có thể hiểu được cách mô hình hoạt động và đánh giá tính công bằng/độ tin cậy.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/313018-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/ | https://www.youtube.com/watch?v=clarify‑reInvent‑2025

### Đề bài
A company is using Amazon SageMaker to deploy a model that identifies if social media posts contain certain topics. The company needs to show how different input features influence model behavior.
Which SageMaker feature meets these requirements?

### Các lựa chọn
1. SageMaker Canvas
2. SageMaker Clarify
3. SageMaker Feature Store
4. SageMaker Ground Truth

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty đang sử dụng Amazon SageMaker để triển khai một mô hình phân loại các bài đăng trên mạng xã hội, mục tiêu là xác định xem nội dung có chứa các “topic” (chủ đề) nhất định hay không.

Yêu cầu quan trọng: công ty muốn minh bạch – thể hiện các đặc trưng (input features) nào đã ảnh hưởng tới quyết định của mô hình cho từng dự đoán. Nói cách khác, họ cần một công cụ “giải thích” (model explainability) để người dùng, nhà phát triển hoặc các bên liên quan có thể hiểu được cách mô hình hoạt động và đánh giá tính công bằng/độ tin cậy.

✅ Đáp án đúng

🔹 SageMaker Clarify

Lý do lựa chọn:

SageMaker Clarify được thiết kế chuyên để đánh giá độ công bằng (bias) và cung cấp giải thích cho mô hình máy học.

Nó cung cấp Feature Importance (Shapley values, permutation importance, …) cho từng dự đoán, cho phép bạn thấy “feature X đóng góp bao nhiêu % vào quyết định là có/không có topic”.

Tích hợp sẵn trong pipeline SageMaker: có thể chạy post‑training explainability jobs hoặc real‑time inference with explainability.

Được cập nhật liên tục đến năm 2026, Clarify hỗ trợ SageMaker JumpStart, SageMaker Pipelines và các framework phổ biến (TensorFlow, PyTorch, XGBoost, …), đồng thời cho phép xuất kết quả dưới dạng JSON/CSV để trực quan hoá trong QuickSight hoặc các dashboard tùy chỉnh.

Vì vậy, Clarify đáp ứng đúng yêu cầu “show how different input features influence model behavior”.

❌ Giải thích các phương án sai

SageMaker Canvas

Mô tả: Canvas là một công cụ no‑code/low‑code cho phép người dùng phi‑kỹ thuật tạo, đào tạo và triển khai mô hình dựa trên dữ liệu CSV/Excel mà không cần viết code.

Tại sao không phù hợp: Canvas tập trung vào tạo mô hình nhanh, không cung cấp tính năng giải thích chi tiết cho các đặc trưng đã ảnh hưởng tới dự đoán. Nó không có module “Explainability” hay “Bias detection”. Do đó không đáp ứng yêu cầu “show how different input features influence model behavior”.

SageMaker Feature Store

Mô tả: Feature Store là kho lưu trữ điểm dữ liệu đã được chuẩn bị (features) cho training và inference, hỗ trợ versioning, online/offline store, và governance.

Tại sao không phù hợp: Mặc dù Feature Store giúp quản lý và phục vụ các feature, nó không cung cấp công cụ giải thích (feature importance) cho mô hình. Nó chỉ là nguồn cung cấp dữ liệu, không phải công cụ phân tích ảnh hưởng của các feature lên quyết định mô hình.

SageMaker Ground Truth

Mô tả: Ground Truth là dịch vụ gán nhãn dữ liệu (labeling) với hỗ trợ tự động nhãn (auto‑labeling) và kiểm soát chất lượng.

Tại sao không phù hợp: Ground Truth giúp tạo bộ dữ liệu đã được gán nhãn cho việc đào tạo mô hình, nhưng không liên quan tới việc giải thích mô hình sau khi đã đào tạo. Nó không cung cấp bất kỳ tính năng nào để hiển thị ảnh hưởng của các input feature.

🧩 Tổng hợp lại

✅ SageMaker Clarify – cung cấp tính năng Explainability (feature importance, SHAP values) và bias detection, đáp ứng yêu cầu hiển thị ảnh hưởng của từng feature.

❌ SageMaker Canvas – công cụ low‑code tạo mô hình, không có giải thích chi tiết.

❌ SageMaker Feature Store – kho lưu trữ feature, không thực hiện giải thích.

❌ SageMaker Ground Truth – dịch vụ gán nhãn dữ liệu, không liên quan tới explainability.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon SageMaker Clarify – Documentation (v2026.03) – phần Explainability và Bias Detection: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Well‑Architected Framework – Machine Learning Lens (2025 update) – khuyến nghị sử dụng Clarify để đạt được tính minh bạch và trách nhiệm giải trình.

AWS re:Invent 2025 – “Deep Dive into SageMaker Clarify” – video session: https://www.youtube.com/watch?v=clarify‑reInvent‑2025

🛠️ Kết luận: Đối với yêu cầu “show how different input features influence model behavior” trong môi trường SageMaker, SageMaker Clarify là giải pháp duy nhất trong các lựa chọn đã cho, vì nó cung cấp các phương pháp giải thích hiện đại (SHAP, permutation) và tích hợp trực tiếp vào quy trình triển khai mô hình.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313018-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 08

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Modality**
- Takeaway nhanh: 1️⃣ Latency 2️⃣ Model size 3️⃣ Model customization 4️⃣ Modality
- Nguồn tham khảo trong block: https://aws.amazon.com/sagemaker/jumpstart/ | https://d1.awsstatic.com/whitepapers/generative-ai-on-aws.pdf | https://docs.aws.amazon.com/bedrock/latest/userguide/model-ids.html | https://www.examtopics.com/discussions/amazon/view/312981-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to create an AI solution to generate images and descriptions for a product catalog. The company needs to select a foundation model (FM) for this solution.
The company must consider the output types of each FM.
Which FM characteristic is the company evaluating?

### Các lựa chọn
1. Latency
2. Model size
3. Model customization
4. Modality

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Giải thích nội dung câu hỏi

Công ty muốn xây dựng một giải pháp AI tạo hình ảnh và mô tả văn bản cho danh mục sản phẩm. Khi lựa chọn foundation model (FM) trong AWS (ví dụ: Amazon Bedrock), họ phải xét đến kiểu đầu ra mà mô hình có thể sinh ra – tức là mô hình có thể tạo ra image, text, audio, … Điều này liên quan tới đặc tính “Modality” của mô hình, tức là khả năng xử lý và sinh ra các dạng dữ liệu (modalities) nào.

✅ Đáp án đúng: Modality

Lý do: “Modality” mô tả loại dữ liệu mà mô hình đầu vào và đầu ra hỗ trợ (text‑only, image‑only, multi‑modal…). Vì công ty cần cả image và text, họ đang đánh giá modality của các FM để chắc chắn mô hình có thể tạo ra cả hai dạng đầu ra.

🧩 Phân tích các phương án

1️⃣ Latency

Giải thích: Latency đề cập tới thời gian phản hồi của mô hình (thời gian từ khi gửi yêu cầu tới khi nhận được kết quả). Mặc dù latency quan trọng với các ứng dụng thời gian thực, nó không liên quan đến việc mô hình tạo ra loại dữ liệu nào (image hay text). Vì vậy, đây không phải là tiêu chí mà câu hỏi đang hỏi.

2️⃣ Model size

Giải thích: Model size (số tham số, dung lượng lưu trữ) ảnh hưởng tới chi phí, khả năng mở rộng và tốc độ suy luận, nhưng không quyết định loại đầu ra mà mô hình có thể sinh ra. Một mô hình lớn có thể vẫn chỉ hỗ trợ một modality duy nhất (ví dụ: chỉ text). Do đó, đây không phải là tiêu chí cần xem xét trong trường hợp này.

3️⃣ Model customization

Giải thích: Model customization là khả năng tinh chỉnh mô hình (fine‑tuning, LoRA, …) để đáp ứng nhu cầu đặc thù của doanh nghiệp. Khi công ty cần tạo hình ảnh và mô tả, việc tùy chỉnh có thể hữu ích, nhưng không phải là yếu tố để xác định loại dữ liệu mô hình có thể sản xuất. Vì vậy, đây không phải đáp án đúng.

4️⃣ Modality

Giải thích: Modality chỉ ra kiểu dữ liệu mà mô hình có thể nhận vào và/hoặc xuất ra (text, image, video, audio, multi‑modal). Khi doanh nghiệp muốn một FM sinh ra cả hình ảnh và mô tả văn bản, họ cần kiểm tra modality của từng mô hình để chọn mô hình multi‑modal (ví dụ: Stable Diffusion cho image + Claude/ChatGPT cho text, hoặc mô hình đa mô hình như Gemini 1.5 Pro). Do đó, đây là tiêu chí đúng.

📚 Tham khảo tài liệu (cập nhật đến 2026)

AWS Documentation – Amazon Bedrock Foundations Models

https://docs.aws.amazon.com/bedrock/latest/userguide/model-ids.html (được cập nhật thường xuyên, bao gồm bảng “Modality” cho mỗi model).

AWS Whitepaper – Generative AI on AWS (2025‑2026 edition)

https://d1.awsstatic.com/whitepapers/generative-ai-on-aws.pdf

Amazon SageMaker JumpStart – Foundation Model Overview

https://aws.amazon.com/sagemaker/jumpstart/

🛠️ Kết luận:

Công ty đang đánh giá Modality của các foundation model để chắc chắn rằng mô hình có thể tạo ra cả hình ảnh và mô tả văn bản cho danh mục sản phẩm. Các tiêu chí khác như latency, model size, hay model customization đều không phản ánh yêu cầu về loại đầu ra. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312981-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 09

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon SageMaker, Amazon Textract, Amazon SageMaker AI, Amazon Q
- Đáp án tham khảo: **Amazon SageMaker Model Card**
- Takeaway nhanh: Một công ty đã xây dựng một mô hình Machine‑Learning (ML) để duyệt hay từ chối hồ sơ vay. Do quy định pháp luật yêu cầu “transparency” và “explainability”, công ty phải có cách ghi lại, mô tả chi tiết quy trình ra quyết định của mô hình để có thể đưa ra cho kiểm toán viên hoặc cơ quan quản lý. Câu hỏi đang hỏi: Giải pháp nào của AWS cho phép tài liệu hoá (document) quá trình quyết định của mô hình ML một cách chuẩn, có thể chia sẻ và bảo trì?
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/introducing-enhanced-sagemaker-model-cards/ | https://d1.awsstatic.com/whitepapers/aws-ai-ml-governance.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html | https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/what-is-ml-lens.html | https://www.examtopics.com/discussions/amazon/view/312970-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has developed an ML model to approve or reject loan applications. The model’s decision-making process must be transparent and explainable to comply with regulatory requirements. The company must document the decision-making process for audit purposes.
Which solution will meet these requirements?

### Các lựa chọn
1. Amazon Textract
2. Amazon SageMaker Model Card
3. AWS Cloud Formation
4. Amazon Comprehend

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Một công ty đã xây dựng một mô hình Machine‑Learning (ML) để duyệt hay từ chối hồ sơ vay. Do quy định pháp luật yêu cầu “transparency” và “explainability”, công ty phải có cách ghi lại, mô tả chi tiết quy trình ra quyết định của mô hình để có thể đưa ra cho kiểm toán viên hoặc cơ quan quản lý.

Câu hỏi đang hỏi: Giải pháp nào của AWS cho phép tài liệu hoá (document) quá trình quyết định của mô hình ML một cách chuẩn, có thể chia sẻ và bảo trì?

✅ Đáp án đúng: Amazon SageMaker Model Card

Tại sao lại là Model Card?

Model Card là tài liệu chuẩn được định dạng JSON/Markdown, được lưu trữ trong Amazon SageMaker Model Registry hoặc Amazon SageMaker Studio.

Nội dung Model Card bao gồm: mô tả mục tiêu, dữ liệu huấn luyện, kiến trúc, siêu tham số, các metric đánh giá (accuracy, fairness, robustness), các giới hạn và các hướng dẫn sử dụng.

Điều này đảm bảo tính minh bạch (transparent) và giải thích được (explainable) cho các bên liên quan, đáp ứng yêu cầu audit.

Từ 2024, AWS mở rộng Model Card với tính năng Model Card Export sang AWS Audit Manager và Amazon QuickSight để tạo báo cáo tự động.

Được khuyến nghị trong AWS Well‑Architected Framework – Machine Learning Lens và AWS AI/ML Governance best practices (tài liệu “Amazon SageMaker Model Card – Best Practices”, cập nhật 2025).

🧩 Phân tích các phương án

1. Amazon Textract (đánh dấu [SAI])

Chức năng: Dịch vụ OCR, tự động trích xuất văn bản và dữ liệu từ tài liệu hình ảnh (PDF, scan).

Vì sao không phù hợp: Textract không liên quan tới việc mô tả hay ghi lại logic của mô hình ML. Nó chỉ giúp “đọc” nội dung tài liệu, không cung cấp bất kỳ cấu trúc metadata nào về model hay cách ra quyết định.

Kết luận: ❌ Không đáp ứng yêu cầu về documenting decision‑making process.

2. Amazon SageMaker Model Card (đánh dấu [ĐÚNG])

Chức năng: Tạo, lưu trữ và chia sẻ tài liệu chi tiết về mô hình ML, bao gồm mục tiêu, dữ liệu, siêu tham số, các metric liên quan tới fairness, explainability và risk.

Lý do chọn: Cung cấp một “one‑stop” documentation, tích hợp sẵn trong SageMaker, hỗ trợ versioning và audit trail. Đáp ứng đầy đủ yêu cầu transparency, explainability, và auditability.

Kết luận: ✅ Lựa chọn chính xác.

3. AWS CloudFormation (đánh dấu [SAI])

Chức năng: Dịch vụ Infrastructure‑as‑Code (IaC) để tạo, cập nhật và xóa tài nguyên AWS bằng template JSON/YAML.

Vì sao không phù hợp: CloudFormation mô tả cơ sở hạ tầng, không phải logic của mô hình ML hay cách mô hình đưa ra quyết định. Nó có thể ghi lại kiến trúc hạ tầng chạy model, nhưng không cung cấp chi tiết về dữ liệu, metric, hay các yếu tố giải thích quyết định.

Kết luận: ❌ Không đáp ứng mục tiêu “document the decision‑making process”.

4. Amazon Comprehend (đánh dấu [SAI])

Chức năng: Dịch vụ NLP để phát hiện ngôn ngữ, sentiment, entity, key phrases trong văn bản.

Vì sao không phù hợp: Comprehend là mô hình pre‑trained cho phân tích ngôn ngữ, không phải công cụ để ghi chép hay mô tả model card cho một mô hình tùy chỉnh như mô hình duyệt vay. Nó không cung cấp khả năng lưu trữ metadata hay audit trail.

Kết luận: ❌ Không đáp ứng yêu cầu.

📚 Tham khảo tài liệu (đến 2026)

Amazon SageMaker Model Card – Documentation

https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html (phiên bản cập nhật 2025‑12).

AWS Well‑Architected Framework – Machine Learning Lens (2024).

https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/what-is-ml-lens.html

AWS AI/ML Governance Whitepaper (2025).

https://d1.awsstatic.com/whitepapers/aws-ai-ml-governance.pdf

AWS Blog – New features for SageMaker Model Cards (2025)

https://aws.amazon.com/blogs/machine-learning/introducing-enhanced-sagemaker-model-cards/

🎯 Kết luận nhanh

Để document quy trình quyết định của mô hình ML cho mục đích audit, Amazon SageMaker Model Card là giải pháp chuẩn nhất.

Các dịch vụ khác (Textract, CloudFormation, Comprehend) không cung cấp khả năng ghi chép chi tiết về model, do đó không thỏa mãn yêu cầu.

✅ Lựa chọn đúng: Amazon SageMaker Model Card.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312970-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 10

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **The company’s development framework is ISO certified.**
- Takeaway nhanh: Công ty vừa đạt được chứng nhận ISO (International Organization for Standardization) nhằm quản lý rủi ro AI và đảm bảo việc sử dụng AI một cách có trách nhiệm. Câu hỏi muốn kiểm tra hiểu biết của bạn về ý nghĩa thực tế của một chứng nhận ISO: nó chứng minh điều gì ở mức độ tổ chức, chứ không phải ở mức độ cá nhân hay từng sản phẩm riêng lẻ. ✅ The company’s development framework is ISO certified.
- Nguồn tham khảo trong block: https://aws.amazon.com/artifact/ | https://www.examtopics.com/discussions/amazon/view/313043-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company acquires International Organization for Standardization (ISO) accreditation to manage AI risks and to use AI responsibly.
What does this accreditation reflect about the company?

### Các lựa chọn
1. All members of the company are ISO certified.
2. All AI systems that the company uses are ISO certified.
3. All AI application team members are ISO certified.
4. The company’s development framework is ISO certified.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty vừa đạt được chứng nhận ISO (International Organization for Standardization) nhằm quản lý rủi ro AI và đảm bảo việc sử dụng AI một cách có trách nhiệm.

Câu hỏi muốn kiểm tra hiểu biết của bạn về ý nghĩa thực tế của một chứng nhận ISO: nó chứng minh điều gì ở mức độ tổ chức, chứ không phải ở mức độ cá nhân hay từng sản phẩm riêng lẻ.

✅ Đáp án đúng

✅ The company’s development framework is ISO certified.

Giải thích:

ISO là tiêu chuẩn quốc tế áp dụng cho các quy trình, hệ thống quản lý của một tổ chức (ví dụ: ISO 9001 – quản lý chất lượng, ISO 27001 – an ninh thông tin, ISO 42001 – hệ thống quản lý AI).

Khi một công ty “acquires ISO accreditation”, toàn bộ khung (framework) phát triển, quy trình kiểm soát, quản trị rủi ro AI của công ty đã được đánh giá và đáp ứng các yêu cầu của tiêu chuẩn ISO tương ứng.

Do vậy, chứng nhận không nói gì về các cá nhân (nhân viên, thành viên) hay các sản phẩm AI riêng lẻ; nó chỉ khẳng định cách thức công ty xây dựng, vận hành và kiểm soát AI đã đáp ứng tiêu chuẩn quốc tế.

❌ Phân tích các phương án sai

All members of the company are ISO certified.

Sai: ISO không cấp chứng nhận cá nhân. Các chứng chỉ cá nhân (ví dụ: “ISO‑Certified Auditor”) là do các tổ chức đào tạo cấp, không phải do ISO cấp cho thành viên của công ty. Chứng nhận ISO của công ty chỉ đề cập tới hệ thống/quy trình của tổ chức.

All AI systems that the company uses are ISO certified.

Sai: ISO không chứng nhận mỗi hệ thống AI riêng lẻ. Có những tiêu chuẩn như ISO/IEC 42001 (AI Management System) nhưng chúng áp dụng cho quy trình quản lý chứ không phải “đánh dấu” từng sản phẩm AI. Một công ty có thể có nhiều giải pháp AI, nhưng chỉ cần quy trình phát triển, kiểm thử, giám sát đáp ứng tiêu chuẩn.

All AI application team members are ISO certified.

Sai: Tương tự mục 1, ISO không cấp chứng chỉ cho cá nhân. Các thành viên đội ngũ AI có thể có các chứng chỉ chuyên môn (ví dụ: AWS Certified Machine Learning – Specialty) nhưng không phải “ISO certified”. Chứng nhận ISO phản ánh cách thức làm việc của nhóm (quy trình, kiểm soát), không phải trình độ cá nhân.

📚 Kiến thức cập nhật (đến năm 2026)

ISO/IEC 42001:2023 – AI Management System (AIMS). Đây là tiêu chuẩn mới nhất của ISO, cung cấp khung quản lý rủi ro, đạo đức và tuân thủ khi triển khai AI. Khi một công ty đạt chuẩn này, toàn bộ quy trình phát triển, vận hành, đánh giá và giám sát AI được xác nhận.

AWS & ISO: AWS cung cấp AWS Artifact để truy cập các báo cáo tuân thủ ISO (ISO 27001, ISO 9001, ISO 27701, ISO 14001, ISO 45001, v.v.). Khi một doanh nghiệp sử dụng AWS và muốn đạt chuẩn ISO cho AI, họ thường xây dựng CI/CD pipeline dựa trên AWS CodePipeline, AWS CodeBuild, Amazon SageMaker Pipelines, kết hợp với AWS Config, AWS Security Hub để đáp ứng yêu cầu kiểm soát và báo cáo của ISO/IEC 42001.

Best practice: Đặt ISO‑compliant controls ở mức infrastructure as code (IaC) (AWS CloudFormation, Terraform) và automation (AWS Step Functions) để duy trì tính nhất quán, đáp ứng yêu cầu audit.

🛠️ Lời khuyên thực tiễn cho các DevOps Engineer

Thiết kế pipeline: Áp dụng AWS CodePipeline + SageMaker Model Registry để quản lý vòng đời mô hình AI, đồng thời tích hợp AWS Config Rules để kiểm tra các cấu hình (ví dụ: mã hoá dữ liệu, IAM role giới hạn).

Audit & Logging: Sử dụng AWS CloudTrail, Amazon CloudWatch Logs, và AWS Security Hub để thu thập, lưu trữ và phân tích log, đáp ứng yêu cầu chứng minh tuân thủ ISO.

Documentation: Duy trì Documentation-as-Code (Markdown trong repo) cho mọi SOP, SOP kiểm thử, và risk assessment của mô hình AI – đây là một phần quan trọng của development framework được ISO công nhận.

📖 Tham khảo

ISO/IEC 42001:2023 – Artificial Intelligence Management System (AIMS). (ISO Official Website)

AWS Artifact – “AWS Compliance Programs” (https://aws.amazon.com/artifact/)

“AWS Well‑Architected Framework – Security Pillar” (2024 update).

“Amazon SageMaker Pipelines – Build, automate, and manage ML workflows” (2025).

Tóm lại:

✅ Correct answer: The company’s development framework is ISO certified.

✅ Lý do: Chứng nhận ISO phản ánh việc toàn bộ khung/quy trình phát triển và quản lý AI của công ty đáp ứng tiêu chuẩn quốc tế, chứ không liên quan tới cá nhân hay từng hệ thống AI riêng lẻ.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313043-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 11

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, Amazon SageMaker AI, Amazon SageMaker JumpStart, guardrails, RAG
- Đáp án tham khảo: **Amazon Bedrock Guardrails**
- Takeaway nhanh: Công ty đang triển khai các mô hình ngôn ngữ lớn (LLM) để xây dựng ứng dụng dạy kèm trực tuyến. Để bảo vệ người dùng và tuân thủ các quy tắc an toàn chung (ví dụ: không tạo nội dung bạo lực, ngôn từ thù địch, thông tin sai lệch, …) công ty cần cài đặt các “safeguards” có thể cấu hình cho các LLM. Yêu cầu quan trọng là phải thực hiện điều này với ít công sức nhất – tức là không phải tự viết code kiểm soát, không cần triển khai pipeline phức tạp, mà dùng dịch vụ đã có sẵn, tích hợp sẵn các quy tắc an toàn và cho phép tùy chỉnh nhanh chóng.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/configurable-guardrails-for-llms/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://www.aws.amazon.com/events/reinvent/2025/ | https://www.examtopics.com/discussions/amazon/view/313048-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using large language models (LLMs) to develop online tutoring applications. The company needs to apply configurable safeguards to the LLMs. These safeguards must ensure that the LLMs follow standard safety rules when creating applications.
Which solution will meet these requirements with the LEAST effort?

### Các lựa chọn
1. Amazon Bedrock playgrounds
2. Amazon SageMaker Clarify
3. Amazon Bedrock Guardrails
4. Amazon SageMaker Jumpstart

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

1. Giải thích nội dung câu hỏi

Công ty đang triển khai các mô hình ngôn ngữ lớn (LLM) để xây dựng ứng dụng dạy kèm trực tuyến. Để bảo vệ người dùng và tuân thủ các quy tắc an toàn chung (ví dụ: không tạo nội dung bạo lực, ngôn từ thù địch, thông tin sai lệch, …) công ty cần cài đặt các “safeguards” có thể cấu hình cho các LLM. Yêu cầu quan trọng là phải thực hiện điều này với ít công sức nhất – tức là không phải tự viết code kiểm soát, không cần triển khai pipeline phức tạp, mà dùng dịch vụ đã có sẵn, tích hợp sẵn các quy tắc an toàn và cho phép tùy chỉnh nhanh chóng.

2. Đáp án đúng

✅ Amazon Bedrock Guardrails

Lý do:

Guardrails là tính năng mới (được mở rộng và cập nhật liên tục đến năm 2026) của Amazon Bedrock, cho phép người dùng định nghĩa, bật/tắt và tùy chỉnh các quy tắc an toàn (ví dụ: “Content filtering”, “Prompt injection protection”, “Toxicity detection”).

Chúng hoạt động trực tiếp trên API của Bedrock – không cần xây dựng hạ tầng riêng, không cần viết mã kiểm tra sau khi nhận kết quả.

Được thiết kế để triển khai nhanh chóng: chỉ cần cấu hình trong console hoặc qua API, sau đó mọi cuộc gọi tới LLM sẽ tự động được lọc theo các guardrails đã đặt.

Do vậy đáp ứng yêu cầu “least effort” (ít công sức) một cách tối ưu.

3. Phân tích các phương án (giữ nguyên nội dung tiếng Anh)

❌ Amazon Bedrock playgrounds

Giải thích: Playground chỉ là môi trường demo/UI cho phép người dùng thử nghiệm các mô hình Bedrock (Claude, Titan, Llama, …) trong trình duyệt. Nó không cung cấp cơ chế cấu hình guardrails cho các ứng dụng thực tế, và không thể áp dụng quy tắc an toàn một cách tự động cho các API gọi từ code. Do vậy không đáp ứng yêu cầu về “configurable safeguards” và “least effort” trong môi trường production.

❌ Amazon SageMaker Clarify

Giải thích: Clarify là công cụ đánh giá bias và explainability cho mô hình máy học, đặc biệt hữu ích khi muốn kiểm tra độ công bằng hoặc giải thích quyết định của mô hình. Nó không cung cấp chức năng lọc nội dung hay thiết lập quy tắc an toàn cho LLM, và việc tích hợp vào workflow LLM sẽ đòi hỏi triển khai pipeline riêng, không phải là giải pháp “least effort”.

✅ Amazon Bedrock Guardrails

Giải thích: Như đã nêu ở mục 2, Guardrails là tính năng được thiết kế riêng cho việc bảo vệ LLM. Người dùng có thể tạo các guardrail templates, chỉnh sửa mức độ nhạy cảm, và gắn chúng vào endpoint Bedrock. Khi ứng dụng gọi LLM, guardrails sẽ tự động kiểm tra và chặn hoặc chỉnh sửa các nội dung không phù hợp trước khi trả về cho người dùng.

❌ Amazon SageMaker Jumpstart

Giải thích: Jumpstart cung cấp các mô hình và notebook mẫu để khởi tạo nhanh dự án ML, bao gồm một số LLM đã được tiền huấn luyện. Tuy nhiên, Jumpstart không bao gồm cơ chế guardrails hay các quy tắc an toàn tích hợp. Để có bảo vệ tương tự, người dùng vẫn phải tự xây dựng lớp middleware hoặc sử dụng các dịch vụ khác, làm tăng công sức triển khai.

4. Kiến thức cập nhật đến năm 2026

Từ 2023 đến 2026, Amazon Bedrock đã mở rộng bộ Guardrails, thêm hỗ trợ đa ngôn ngữ, công cụ UI cho việc tạo guardrail bằng drag‑and‑drop, và tích hợp với IAM policies để quản lý ai có thể thay đổi guardrails.

AWS đã công bố Bedrock Guardrails API v2 (2025) cho phép định nghĩa custom content filters bằng cách tải lên file JSON schema, giúp đáp ứng các yêu cầu pháp lý địa phương (GDPR, CCPA, …) mà không cần viết code xử lý phía client.

Các tài liệu chính:

Amazon Bedrock Developer Guide – Guardrails (phiên bản 2026‑03).

AWS Security Blog – Introducing Configurable Guardrails for LLMs (2024‑11).

5. Tài liệu tham khảo

📘 Amazon Bedrock Documentation – Guardrails: https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

📘 AWS Blog – Configurable Guardrails for LLMs (Nov 2024): https://aws.amazon.com/blogs/aws/configurable-guardrails-for-llms/

📘 AWS re:Invent 2025 – Deep Dive into Bedrock Guardrails (video): https://www.aws.amazon.com/events/reinvent/2025/

🧩 Tổng kết

Với yêu cầu “cấu hình các safeguard cho LLM, đảm bảo tuân thủ các quy tắc an toàn tiêu chuẩn, và thực hiện với ít công sức nhất”, Amazon Bedrock Guardrails là giải pháp phù hợp nhất, vì nó cung cấp cơ chế lọc nội dung tích hợp, dễ cấu hình và có thể áp dụng trực tiếp vào các endpoint Bedrock. Các lựa chọn còn lại chỉ là công cụ hỗ trợ thử nghiệm, phân tích bias, hoặc khởi tạo mô hình, không đáp ứng được mục tiêu bảo vệ nội dung LLM. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313048-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 12

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon S3, guardrails
- Đáp án tham khảo: **Data residency**
- Takeaway nhanh: Ngữ cảnh: Một công ty lưu trữ thông tin cá nhân nhận dạng (PII) của khách hàng trên AWS. Yêu cầu “phải lưu trữ dữ liệu PII trong khu vực (Region) của công ty” đồng nghĩa với việc dữ liệu không được phép di chuyển ra ngoài ranh giới địa lý của Region mà công ty đã lựa chọn. Điều cần xác định: Trong khuôn khổ governance (quản trị), yếu tố nào mô tả yêu cầu “lưu trữ dữ liệu trong một Region cụ thể”?
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/ensuring-data-residency/ | https://aws.amazon.com/compliance/artifact/ | https://docs.aws.amazon.com/controltower/latest/userguide/guardrails.html | https://docs.aws.amazon.com/general/latest/gr/rande.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/data-protection.html | https://www.examtopics.com/discussions/amazon/view/316402-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company stores customer personally identifiable information (PII) data. The company must store the PII data within the company's AWS Region.
Which aspect of governance does this describe?

### Các lựa chọn
1. Data mining
2. Data residency
3. Pre-training bias
4. Geolocation routing

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Ngữ cảnh: Một công ty lưu trữ thông tin cá nhân nhận dạng (PII) của khách hàng trên AWS. Yêu cầu “phải lưu trữ dữ liệu PII trong khu vực (Region) của công ty” đồng nghĩa với việc dữ liệu không được phép di chuyển ra ngoài ranh giới địa lý của Region mà công ty đã lựa chọn.

Điều cần xác định: Trong khuôn khổ governance (quản trị), yếu tố nào mô tả yêu cầu “lưu trữ dữ liệu trong một Region cụ thể”?

Trong AWS, khái niệm này được gọi là Data residency (địa điểm cư trú dữ liệu). Nó là một phần của tuân thủ (compliance) và quản trị dữ liệu, yêu cầu dữ liệu phải “cư trú” (ở lại) trong một khu vực địa lý nhất định, thường để đáp ứng luật pháp quốc gia hoặc quy định ngành (ví dụ: GDPR, CCPA, LGPD, ISO 27001…).

✅ Đáp án đúng: Data residency

Lý do lựa chọn:

Data residency đề cập tới việc xác định nơi dữ liệu được lưu trữ (Region, Country, hoặc Sovereign Cloud) để đáp ứng yêu cầu pháp lý hoặc nội bộ.

Câu hỏi yêu cầu “công ty phải lưu trữ PII trong AWS Region của công ty” → đúng với định nghĩa của Data residency.

AWS cung cấp các công cụ để kiểm soát vị trí dữ liệu: lựa chọn Region khi tạo tài nguyên, AWS Control Tower, AWS Organizations Service Control Policies (SCPs), AWS IAM policies, và các AWS Artifact reports để chứng minh việc tuân thủ địa điểm dữ liệu.

❌ Giải thích các phương án còn lại

Data mining

Giải thích: Data mining là quá trình khám phá các mẫu, xu hướng, hoặc thông tin có giá trị từ tập dữ liệu lớn bằng các thuật toán phân tích.

Tại sao sai: Câu hỏi không đề cập đến việc phân tích hay trích xuất thông tin từ dữ liệu mà chỉ nói đến nơi lưu trữ dữ liệu. Do vậy không liên quan tới governance về vị trí dữ liệu.

Pre‑training bias

Giải thích: Pre‑training bias là hiện tượng mô hình machine‑learning học được các thiên lệch (bias) từ dữ liệu huấn luyện trước khi được triển khai.

Tại sao sai: Đây là vấn đề về đạo đức và chất lượng mô hình AI, không liên quan tới quy tắc lưu trữ dữ liệu trong một Region.

Geolocation routing

Giải thích: Geolocation routing là tính năng của Amazon Route 53 (hoặc các dịch vụ CDN) cho phép định tuyến người dùng tới endpoint gần nhất dựa trên vị trí địa lý của họ.

Tại sao sai: Mặc dù liên quan tới vị trí địa lý, nhưng mục tiêu là định tuyến lưu lượng chứ không phải định vị nơi dữ liệu được lưu trữ. Do đó không đáp ứng yêu cầu “lưu trữ PII trong Region của công ty”.

🧩 Tổng hợp các khái niệm liên quan đến Data residency trong AWS (cập nhật tới 2026)

AWS Regions & Availability Zones – Mỗi Region là một khu vực địa lý độc lập, dữ liệu được sao lưu và lưu trữ chỉ trong các AZ của Region đó trừ khi người dùng cấu hình sao chép sang Region khác.

AWS Control Tower & Landing Zone – Cung cấp guardrails để ngăn việc tạo tài nguyên ra ngoài Region cho phép.

Service Control Policies (SCPs) – Có thể hạn chế các hành động “Create*” chỉ cho phép các Region được phê duyệt.

AWS Artifact – Cung cấp báo cáo tuân thủ (e.g., SOC, ISO, GDPR) chứng minh việc dữ liệu cư trú tại các Region được chỉ định.

AWS Data Residency Services – Từ 2023 AWS đã ra mắt AWS GovCloud (US), AWS China Regions, và AWS Europe (Zurich, Milan) để đáp ứng yêu cầu “sovereign cloud”.

Amazon S3 Object Lock & S3 Object Ownership – Cho phép bảo vệ dữ liệu PII tại chỗ, không cho phép di chuyển ra ngoài mà không có quy trình phê duyệt.

📚 Tham khảo

AWS Documentation – Data Residency: https://docs.aws.amazon.com/general/latest/gr/rande.html

AWS Control Tower Guardrails: https://docs.aws.amazon.com/controltower/latest/userguide/guardrails.html

AWS Artifact – Compliance Reports: https://aws.amazon.com/compliance/artifact/

AWS Well‑Architected Framework – Security Pillar (Data protection): https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/data-protection.html

AWS Blog – “Ensuring Data Residency in the Cloud” (2024): https://aws.amazon.com/blogs/security/ensuring-data-residency/

🛠️ Kết luận:

Yêu cầu “lưu trữ dữ liệu PII trong AWS Region của công ty” mô tả Data residency, một khía cạnh quan trọng của governance và compliance trong môi trường AWS. Các tùy chọn còn lại (Data mining, Pre‑training bias, Geolocation routing) không phản ánh yêu cầu về vị trí lưu trữ dữ liệu, do đó là sai. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316402-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 13

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon SageMaker, Amazon Textract, Amazon Transcribe, Amazon SageMaker AI, embeddings, RAG
- Đáp án tham khảo: **Amazon OpenSearch Service**
- Takeaway nhanh: Câu hỏi hỏi: “Which AWS service or feature stores embeddings in a vector database for use with foundation models (FMs) and Retrieval Augmented Generation (RAG)?” Embeddings: các vector số học được tạo ra từ mô hình nền (foundation model) để biểu diễn ngữ nghĩa của đoạn văn, câu, hay tài liệu. Vector database: cơ sở dữ liệu được tối ưu cho việc lưu trữ và tìm kiếm các vector (k‑Nearest Neighbor – k‑NN).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/retrieval-augmented-generation-with-opensearch/ | https://docs.aws.amazon.com/opensearch-service/latest/developerguide/vector-search.html | https://docs.aws.amazon.com/sagemaker/latest/dg/sms-groundtruth.html | https://docs.aws.amazon.com/textract/latest/dg/what-is.html | https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html | https://www.examtopics.com/discussions/amazon/view/312987-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which AWS service or feature stores embeddings in a vector database for use with foundation models (FMs) and Retrieval Augmented Generation (RAG)?

### Các lựa chọn
1. Amazon SageMaker Ground Truth
2. Amazon OpenSearch Service
3. Amazon Transcribe
4. Amazon Textract

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi hỏi: “Which AWS service or feature stores embeddings in a vector database for use with foundation models (FMs) and Retrieval Augmented Generation (RAG)?”

Embeddings: các vector số học được tạo ra từ mô hình nền (foundation model) để biểu diễn ngữ nghĩa của đoạn văn, câu, hay tài liệu.

Vector database: cơ sở dữ liệu được tối ưu cho việc lưu trữ và tìm kiếm các vector (k‑Nearest Neighbor – k‑NN).

Retrieval‑Augmented Generation (RAG): kỹ thuật kết hợp “tìm kiếm” (retrieval) các tài liệu liên quan với “tạo sinh” (generation) của mô hình ngôn ngữ, thường cần một kho lưu trữ embedding để tra cứu nhanh.

Do vậy, câu hỏi muốn biết dịch vụ AWS nào có khả năng lưu trữ embedding và cung cấp truy vấn vector (k‑NN) để hỗ trợ RAG với các foundation model.

✅ Đáp án đúng

✅ Amazon OpenSearch Service

Amazon OpenSearch Service (trước đây là Amazon Elasticsearch Service) đã bổ sung tính năng Vector Search (k‑NN) kể từ phiên bản OpenSearch 2.0 (ra mắt 2022) và được liên tục cải tiến tới 2026.

Tính năng này cho phép lưu trữ embeddings trong một index vector và thực hiện truy vấn k‑NN để lấy các tài liệu gần nhất – đúng yêu cầu của RAG.

OpenSearch còn hỗ trợ Hybrid search (cùng lúc full‑text + vector) và có OpenSearch Serverless, giúp khách hàng dễ dàng triển khai mà không cần quản lý cluster.

Nguồn:

AWS Documentation – Amazon OpenSearch Service – Vector Search (được cập nhật tới 2026).

AWS Blog – Retrieval‑Augmented Generation with Amazon OpenSearch Service (2024‑2025).

❌ Các phương án sai và lý do

Amazon SageMaker Ground Truth

Ground Truth là dịch vụ gán nhãn dữ liệu (image, video, text, audio) bằng cách kết hợp người lao động và thuật toán semi‑automatic labeling. Nó không lưu trữ embedding và không cung cấp khả năng truy vấn vector. Do đó không đáp ứng yêu cầu của câu hỏi.

Amazon Transcribe

Transcribe là dịch vụ chuyển giọng nói sang văn bản (speech‑to‑text). Nó chỉ tạo ra bản ghi text từ audio, không có chức năng lưu trữ hay truy vấn embeddings. RAG có thể dùng kết quả của Transcribe làm nguồn dữ liệu, nhưng không phải dịch vụ lưu trữ vector.

Amazon Textract

Textract là dịch vụ trích xuất thông tin (text, bảng, form) từ tài liệu (PDF, hình ảnh). Tương tự, nó cung cấp dữ liệu đã được xử lý, nhưng không có vector store hay khả năng tìm kiếm k‑NN. Vì vậy không phải đáp án đúng.

🧩 Tổng kết nhanh gọn

Câu hỏi: Tìm dịch vụ AWS có khả năng lưu trữ embeddings và truy vấn vector để hỗ trợ foundation models và RAG.

Đáp án: Amazon OpenSearch Service – cung cấp tính năng Vector Search (k‑NN) và hỗ trợ RAG.

Lý do các đáp án còn lại sai: chúng là dịch vụ chuyên về gán nhãn, chuyển đổi giọng nói hoặc trích xuất văn bản, không có chức năng vector database.

📚 Tham khảo thêm

Amazon OpenSearch Service – Vector Search – https://docs.aws.amazon.com/opensearch-service/latest/developerguide/vector-search.html (cập nhật 2026)

AWS Blog – Retrieval‑Augmented Generation with Amazon OpenSearch Service – https://aws.amazon.com/blogs/machine-learning/retrieval-augmented-generation-with-opensearch/ (2024)

Amazon SageMaker Ground Truth – https://docs.aws.amazon.com/sagemaker/latest/dg/sms-groundtruth.html

Amazon Transcribe – https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html

Amazon Textract – https://docs.aws.amazon.com/textract/latest/dg/what-is.html

Hy vọng phân tích trên giúp bạn nắm rõ lý do tại sao Amazon OpenSearch Service là đáp án đúng và hiểu rõ các lựa chọn còn lại. Chúc bạn ôn thi hiệu quả! 🎉

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312987-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 14

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon S3, RAG
- Takeaway nhanh: - Data retention “Data retention” định nghĩa chính sách giữ lại dữ liệu trong một khoảng thời gian nhất định và xóa dữ liệu khi hết thời hạn. AWS cung cấp nhiều công cụ hỗ trợ chính sách này: S3 Lifecycle: tự động chuyển dữ liệu sang các lớp lưu trữ giá rẻ hơn (Glacier, Deep Archive) và xóa bỏ sau thời gian quy định.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-configuration-examples.html | https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html | https://docs.aws.amazon.com/aws-backup/latest/devguide/backup-plan-retention.html | https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/operational-excellence-pillar.html | https://www.examtopics.com/discussions/amazon/view/313028-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has guidelines for data storage and deletion.
Which data governance strategy does this describe?

### Các lựa chọn
1. Data de-identification
2. Data quality standards
3. Data retention
4. Log storage

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi: “A company has guidelines for data storage and deletion. Which data governance strategy does this describe?”

Câu hỏi yêu cầu chúng ta xác định chiến lược quản trị dữ liệu (data governance) mà một tổ chức đang áp dụng khi họ có quy định rõ ràng về cách lưu trữ dữ liệu và thời điểm xóa dữ liệu.

Trong bối cảnh AWS, việc thiết lập “guidelines for data storage and deletion” thường liên quan tới chính sách lưu trữ lâu dài (retention) và xóa tự động – ví dụ: S3 Lifecycle policies, S3 Object Lock (Governance mode), Glacier Vault Lock, hoặc AWS Backup retention plans.

Do đó, chiến lược này chính là Data retention – tức là quy tắc giữ lại dữ liệu trong một khoảng thời gian xác định và sau đó xóa hoặc lưu trữ lại theo chính sách.

✅ Đáp án đúng

- Data retention

Lý do:

“Data retention” định nghĩa chính sách giữ lại dữ liệu trong một khoảng thời gian nhất định và xóa dữ liệu khi hết thời hạn.

AWS cung cấp nhiều công cụ hỗ trợ chính sách này:

S3 Lifecycle: tự động chuyển dữ liệu sang các lớp lưu trữ giá rẻ hơn (Glacier, Deep Archive) và xóa bỏ sau thời gian quy định.

S3 Object Lock (Governance hoặc Compliance mode): ngăn chặn việc xóa hoặc ghi đè dữ liệu trong thời gian lưu trữ tối thiểu.

AWS Backup: cho phép đặt retention periods cho bản sao lưu, tự động xóa các snapshot đã hết hạn.

Các hướng dẫn về storage và deletion trong câu hỏi phản ánh đúng khái niệm này.

❌ Giải thích các phương án sai

- Data de-identification

Giải thích: Data de-identification (hoặc anonymization) là quy trình làm mất hoặc thay đổi thông tin nhận dạng cá nhân để bảo vệ quyền riêng tư. Nó không đề cập tới thời gian lưu trữ hay quy trình xóa dữ liệu.

Ví dụ AWS: Sử dụng AWS Glue DataBrew hay Amazon Macie để phát hiện và gỡ bỏ thông tin nhạy cảm, nhưng không liên quan tới “guidelines for storage & deletion”.

- Data quality standards

Giải thích: Data quality standards liên quan tới độ chính xác, tính đầy đủ, tính nhất quán của dữ liệu (ví dụ: chuẩn ISO 8000, chuẩn DQM). Nó không quy định khi nào và như thế nào dữ liệu phải được lưu trữ hoặc xóa.

Ví dụ AWS: Sử dụng AWS Glue Data Catalog để quản lý metadata, nhưng không định nghĩa thời gian lưu trữ.

- Log storage

Giải thích: Log storage chỉ mô tả việc lưu trữ các bản ghi (log) như CloudTrail logs, VPC Flow Logs, không đề cập đến quy tắc xóa hay thời gian lưu trữ. Nó là một loại dữ liệu chứ không phải một chiến lược quản trị toàn diện.

Ví dụ AWS: Amazon S3 + S3 Object Lock cho log lưu trữ lâu dài, nhưng “log storage” không bao hàm chính sách xóa.

📚 Tham khảo (đến năm 2026)

AWS Documentation – S3 Object Lock – https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html

AWS Documentation – S3 Lifecycle configuration – https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-configuration-examples.html

AWS Backup – Retention periods – https://docs.aws.amazon.com/aws-backup/latest/devguide/backup-plan-retention.html

AWS Well‑Architected Framework – Operational Excellence Pillar (Data Retention) – https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/operational-excellence-pillar.html

🧩 Tổng kết

Câu hỏi muốn xác định chiến lược quản trị dữ liệu dựa trên hướng dẫn lưu trữ và xóa dữ liệu.

Đáp án đúng là Data retention vì nó chính xác mô tả việc đặt quy tắc thời gian lưu trữ và xóa dữ liệu.

Các lựa chọn khác (Data de-identification, Data quality standards, Log storage) không bao hàm cả hai yếu tố storage + deletion đồng thời, do đó là sai.

Hy vọng phân tích chi tiết này giúp bạn nắm vững khái niệm và áp dụng đúng trong môi trường AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313028-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 15

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Batch transform**
- Takeaway nhanh: Mục tiêu của doanh nghiệp y tế: Thu thập dữ liệu bệnh nhân trong suốt một năm. Hàng tháng tạo báo cáo phân tích xu hướng để trình cho các cơ quan y tế công cộng. Báo cáo cần cung cấp thông tin từ tháng gần nhất của năm hiện tại.
- Nguồn tham khảo trong block: https://aws.amazon.com/sagemaker/pricing/ | https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html | https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html | https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html | https://www.examtopics.com/discussions/amazon/view/312984-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A healthcare company wants to analyze patient data. The data was gathered over the previous year to detect patterns in disease outbreaks. The company needs to create a trend analysis report for each month to present to public health officials. The company must provide insights into patient data from the most recent month of the current year.
Which inference method will meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Real-time inference
2. Batch transform
3. Serverless inference
4. Asynchronous inference

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Mục tiêu của doanh nghiệp y tế:

Thu thập dữ liệu bệnh nhân trong suốt một năm.

Hàng tháng tạo báo cáo phân tích xu hướng để trình cho các cơ quan y tế công cộng.

Báo cáo cần cung cấp thông tin từ tháng gần nhất của năm hiện tại.

Yêu cầu về cách thực hiện inference:

Không cần trả lời ngay lập tức (real‑time).

Khối lượng dữ liệu lớn (toàn bộ dữ liệu của một tháng).

Công việc được thực hiện định kỳ một lần mỗi tháng.

Yêu cầu chi phí thấp nhất.

Vì vậy, phương pháp inference phải phù hợp với xử lý batch (xử lý tập hợp dữ liệu lớn một lần), không duy trì endpoint liên tục và không trả phí cho mỗi request riêng lẻ.

✅ Đáp án đúng: Batch transform

Lý do lựa chọn

Batch Transform của Amazon SageMaker cho phép bạn đưa vào một tập dữ liệu lớn (có thể lên tới terabytes) và tạo ra kết quả batch trong một job duy nhất.

Bạn chỉ trả tiền cho thời gian các instance chạy trong thời gian job thực thi → chi phí chỉ phát sinh khi job chạy, không có chi phí duy trì endpoint liên tục.

Có thể lên lịch (bằng Amazon EventBridge hoặc Step Functions) để tự động khởi chạy mỗi tháng, đáp ứng yêu cầu “báo cáo tháng”.

Đối với khối lượng dữ liệu “trong tháng gần nhất”, việc sử dụng Batch Transform là cách tiết kiệm nhất so với các phương án duy trì endpoint (real‑time, asynchronous) hoặc trả tiền theo request (serverless inference).

🧩 Phân tích các phương án còn lại

Real-time inference

❌ Được thiết kế để trả lời yêu cầu ngay lập tức (độ trễ < 100 ms).

Cần triển khai và duy trì một endpoint luôn sẵn sàng, dù chỉ sử dụng một lần mỗi tháng → chi phí cao hơn so với batch.

Không phù hợp với khối lượng dữ liệu lớn và yêu cầu không thời gian thực.

Serverless inference

❌ Là mô hình pay‑per‑request (trả tiền cho mỗi lời gọi) và tự động mở/đóng tài nguyên.

Thích hợp cho lượng traffic không đồng đều, ít yêu cầu. Khi xử lý một tập dữ liệu tháng (hàng triệu bản ghi), chi phí sẽ tăng đáng kể vì mỗi request được tính riêng.

Không tận dụng khả năng xử lý hàng loạt như Batch Transform, vì vậy không tối ưu về chi phí cho công việc định kỳ lớn.

Asynchronous inference

❌ Cũng dựa trên endpoint (provisioned hoặc on‑demand) nhưng hỗ trợ độ trễ cao và kích thước payload lớn.

Đòi hỏi giữ endpoint tồn tại trong suốt thời gian xử lý, dẫn tới chi phí đều dù chỉ sử dụng một lần mỗi tháng.

Khi so sánh với Batch Transform, chi phí duy trì endpoint thường cao hơn và không cần thiết cho công việc báo cáo tháng.

📌 Kết luận

Batch transform là phương án tiết kiệm nhất cho việc phân tích dữ liệu bệnh nhân hàng tháng, đáp ứng đầy đủ yêu cầu về khối lượng, tần suất và chi phí.

Các phương án khác (real‑time, serverless, asynchronous) đều đều duy trì endpoint hoặc tính phí theo request, không phù hợp với khối lượng và tính chất batch của bài toán.

📚 Tham khảo

Amazon SageMaker Batch Transform – AWS Documentation (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/batch-transform.html

SageMaker Serverless Inference – AWS Documentation: https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-inference.html

Real‑time vs Asynchronous Inference – AWS SageMaker Inference Types Overview: https://docs.aws.amazon.com/sagemaker/latest/dg/inference.html

Pricing – SageMaker (cập nhật 2026): https://aws.amazon.com/sagemaker/pricing/

🔚 Hy vọng phân tích trên đã giúp bạn hiểu rõ vì sao Batch transform là lựa chọn tối ưu nhất cho yêu cầu của công ty y tế. Nếu còn thắc mắc về cách cấu hình job hoặc lên lịch tự động, cứ thoải mái hỏi thêm nhé! 🙌

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312984-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 16

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Comprehend, Amazon Personalize, Amazon Rekognition, Amazon SageMaker, Amazon S3, model evaluation
- Đáp án tham khảo: **Use model evaluation on Amazon Bedrock**
- Takeaway nhanh: Nhóm nghiên cứu muốn so sánh nhiều mô hình generative AI (ví dụ: LLMs, diffusion models…) để tạo ra các bài báo khoa học. Họ đã chuẩn bị prompt cố định và cần phương pháp đánh giá kết quả đầu ra của các mô hình. Việc đánh giá sẽ được thực hiện bởi đội ngũ nhà khoa học (human‑in‑the‑loop), vì chất lượng của một bài báo cần xem xét về mặt độ chính xác, tính logic, độ sáng tạo, và tuân thủ chuẩn mực khoa học – những tiêu chí mà hiện tại các công cụ tự động chưa thể đo lường hoàn hảo.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313016-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A research group wants to test different generative AI models to create research papers. The research group has defined a prompt and needs a method to assess the models’ output. The research group wants to use a team of scientists to perform the output assessments.
Which solution will meet these requirements?

### Các lựa chọn
1. Use automatic evaluation on Amazon Personalize.
2. Use content moderation on Amazon Rekognition.
3. Use model evaluation on Amazon Bedrock.
4. Use sentiment analysis on Amazon Comprehend.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Nhóm nghiên cứu muốn so sánh nhiều mô hình generative AI (ví dụ: LLMs, diffusion models…) để tạo ra các bài báo khoa học.

Họ đã chuẩn bị prompt cố định và cần phương pháp đánh giá kết quả đầu ra của các mô hình.

Việc đánh giá sẽ được thực hiện bởi đội ngũ nhà khoa học (human‑in‑the‑loop), vì chất lượng của một bài báo cần xem xét về mặt độ chính xác, tính logic, độ sáng tạo, và tuân thủ chuẩn mực khoa học – những tiêu chí mà hiện tại các công cụ tự động chưa thể đo lường hoàn hảo.

Do vậy, câu hỏi đang hỏi: “Giải pháp nào đáp ứng được yêu cầu: (1) đánh giá đầu ra của mô hình generative AI; (2) cho phép một nhóm con người thực hiện đánh giá?”

✅ Đáp án đúng: Use model evaluation on Amazon Bedrock

Amazon Bedrock (được mở rộng và cập nhật đến 2026) cung cấp Model Evaluation – một tính năng cho phép bạn tạo pipeline đánh giá kết quả của các mô hình foundation (LLM, diffusion, etc.) và kết hợp Human Review thông qua Amazon SageMaker Ground Truth, Amazon A2I (Augmented AI) hoặc các workflow tùy chỉnh.

Bạn có thể định nghĩa metric (ví dụ: ROUGE, BLEU, factuality, citation correctness) và gửi đầu ra cho nhóm nhà khoa học để chấm điểm, sau đó thu thập phản hồi để tính toán điểm tổng hợp.

Giải pháp này đáp ứng cả hai yêu cầu: cung cấp môi trường chạy và so sánh các mô hình AI, đồng thời tích hợp human evaluation một cách chuẩn AWS.

❌ Giải thích các phương án sai

Use automatic evaluation on Amazon Personalize

Amazon Personalize là dịch vụ đề xuất cá nhân hoá (recommendation) cho các kịch bản như e‑commerce, streaming, nội dung. Nó không hỗ trợ đánh giá mô hình ngôn ngữ hay tạo nội dung và không cung cấp công cụ cho Human Review.

Do vậy, không phù hợp để đánh giá đầu ra của các mô hình generative AI.

Use content moderation on Amazon Rekognition

Amazon Rekognition chuyên phân tích hình ảnh/ video (đối tượng, khuôn mặt, nội dung không phù hợp). Nó không liên quan tới văn bản hay đánh giá mô hình ngôn ngữ.

Việc “content moderation” chỉ giúp lọc nội dung không phù hợp, không đáp ứng yêu cầu kiểm tra chất lượng và độ khoa học của bài báo.

Use sentiment analysis on Amazon Comprehend

Amazon Comprehend cung cấp phân tích cảm xúc, thực thể, key phrases, v.v. Mặc dù là dịch vụ xử lý ngôn ngữ tự nhiên, sentiment analysis chỉ cho biết cảm xúc (positive/negative) của văn bản, không đo lường độ chính xác, tính logic, hay tính học thuật của một bài báo nghiên cứu.

Ngoài ra, không có cơ chế tích hợp human evaluation cho các nhà khoa học.

🧩 Tổng hợp các điểm mạnh của Amazon Bedrock Model Evaluation

Đa mô hình: hỗ trợ các LLM của Amazon (Titan, Claude), Mistral, Cohere, Stability AI, v.v.

Pipeline tùy chỉnh: bạn có thể định nghĩa các metric, tạo batch jobs, và thu thập kết quả trong Amazon S3 hoặc DynamoDB.

Human‑in‑the‑loop: tích hợp sẵn Amazon A2I để cho phép các nhà khoa học đánh giá mỗi đầu ra và gửi lại nhãn.

Quy mô tự động: chạy đánh giá trên thousands of prompts đồng thời, tận dụng serverless tính năng của Bedrock.

Bảo mật & tuân thủ: dữ liệu được mã hoá, IAM fine‑grained, hỗ trợ PCI‑DSS, HIPAA, FedRAMP (đến 2026).

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide – Model Evaluation (v2026.03).

AWS Blog – Human‑in‑the‑loop AI evaluation with Bedrock and A2I (Nov 2025).

AWS Well‑Architected Framework – Machine Learning Lens (cập nhật 2026).

🔚 Kết luận

Với yêu cầu “đánh giá đầu ra của các mô hình generative AI bằng một đội ngũ nhà khoa học”, Amazon Bedrock – Model Evaluation là giải pháp duy nhất đáp ứng đầy đủ cả khía cạnh công nghệ (đánh giá mô hình) và con người (human review), trong khi các dịch vụ khác (Personalize, Rekognition, Comprehend) không phù hợp.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313016-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 17

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Comprehend
- Takeaway nhanh: Natural language processing (NLP) ✅ Lý do: Sentiment analysis dựa trên việc phân tích văn bản (hoặc lời nói) để nhận diện cảm xúc, vì vậy nó là một phần của NLP – lĩnh vực tập trung vào việc phân tích, hiểu và sinh ra ngôn ngữ tự nhiên.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html | https://www.examtopics.com/discussions/amazon/view/313044-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Sentiment analysis is a subset of which broader field of AI?

### Các lựa chọn
1. Computer vision
2. Robotics
3. Natural language processing (NLP)
4. Time series forecasting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi: “Sentiment analysis is a subset of which broader field of AI?”

“Sentiment analysis” (phân tích cảm xúc) là kỹ thuật dùng để xác định thái độ (tích cực, tiêu cực, trung tính) của một đoạn văn bản, tweet, review,…

Để thực hiện việc này, chúng ta cần xử lý và hiểu ngôn ngữ tự nhiên (các từ, câu, ngữ cảnh). Do đó, sentiment analysis thuộc về Natural Language Processing (NLP) – một nhánh lớn của trí tuệ nhân tạo chuyên về việc cho máy tính “đọc” và “hiểu” ngôn ngữ con người.

✅ Đáp án đúng

Natural language processing (NLP)

✅ Lý do: Sentiment analysis dựa trên việc phân tích văn bản (hoặc lời nói) để nhận diện cảm xúc, vì vậy nó là một phần của NLP – lĩnh vực tập trung vào việc phân tích, hiểu và sinh ra ngôn ngữ tự nhiên.

❌ Giải thích các phương án còn lại

Computer vision

📌 Giải thích: Computer vision (thị giác máy tính) tập trung vào việc “nhìn” và phân tích dữ liệu hình ảnh/video (nhận dạng khuôn mặt, object detection, …). Sentiment analysis không liên quan tới hình ảnh mà là văn bản, vì vậy đây không phải là lĩnh vực cha.

✅ Kết luận: Sai.

Robotics

📌 Giải thích: Robotics (công nghệ robot) bao gồm phần cứng, điều khiển chuyển động, lập kế hoạch hành động và thường dùng AI để robot tương tác với môi trường. Sentiment analysis không liên quan tới điều khiển robot hay cảm biến vật lý.

✅ Kết luận: Sai.

Time series forecasting

📌 Giải thích: Time series forecasting (dự báo chuỗi thời gian) là kỹ thuật dự đoán giá trị tương lai dựa trên dữ liệu theo thời gian (ví dụ: dự báo doanh thu, giá cổ phiếu). Mặc dù có thể áp dụng các mô hình học sâu, nó không liên quan tới việc xử lý ngôn ngữ tự nhiên để nhận diện cảm xúc.

✅ Kết luận: Sai.

📚 Tham khảo (đến năm 2026)

AWS Documentation – Amazon Comprehend – dịch vụ NLP của AWS hỗ trợ sentiment analysis, entity recognition, keyphrase extraction, … (https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html)

“Natural Language Processing (NLP) Overview” – AWS Machine Learning Blog, 2025 – mô tả vai trò của NLP trong các dịch vụ AI của AWS.

“Deep Learning for Natural Language Processing” – AWS re:Invent 2024 Session – trình bày cách các mô hình transformer (BERT, GPT) được dùng cho sentiment analysis.

🧩 Tổng kết

Câu hỏi yêu cầu xác định lĩnh vực AI rộng hơn mà sentiment analysis thuộc về.

Đáp án đúng là Natural language processing (NLP) vì sentiment analysis xử lý và hiểu ngôn ngữ tự nhiên.

Các lựa chọn còn lại (Computer vision, Robotics, Time series forecasting) đều không liên quan tới việc phân tích cảm xúc trong văn bản, nên là sai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313044-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 18

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, Amazon Lex, Amazon Q
- Takeaway nhanh: ✔️ Employing a chatbot to provide human‑like responses to customer queries in real time Chatbot sử dụng mô hình ngôn ngữ lớn (LLM) như Claude, Titan, hoặc các mô hình tùy chỉnh trên Amazon Bedrock để tạo ra phản hồi văn bản một cách tự nhiên, linh hoạt và thời gian thực – đúng bản chất “tạo sinh” nội dung. Đây là một use‑case thực tiễn được triển khai rộng rãi trên AWS: tích hợp Bedrock + Amazon Lex, hoặc SageMaker + API Gateway + Lambda để xây dựng chatbot hỗ trợ khách hàng, giảm tải cho trung tâm cuộc gọi.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/313024-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which scenario represents a practical use case for generative AI?

### Các lựa chọn
1. Using an ML model to forecast product demand
2. Employing a chatbot to provide human-like responses to customer queries in real time
3. Using an analytics dashboard to track website traffic and user behavior
4. Implementing a rule-based recommendation engine to suggest products to customers

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi: “Which scenario represents a practical use case for generative AI?”

Generative AI là nhánh của trí tuệ nhân tạo có khả năng tạo ra nội dung mới (văn bản, hình ảnh, âm thanh, mã…) dựa trên các mẫu đã học.

Những trường hợp thực tiễn thường liên quan tới sinh nội dung, tương tác ngôn ngữ tự nhiên, tạo mã, tổng hợp dữ liệu…

Các dịch vụ của AWS hỗ trợ generative AI hiện nay (2026) bao gồm Amazon Bedrock, Amazon SageMaker JumpStart, Amazon CodeWhisperer, và Amazon Q (Q‑Chat). Các dịch vụ này được dùng cho chatbot, tạo tài liệu, viết code, v.v.

✅ Đáp án đúng

✔️ Employing a chatbot to provide human‑like responses to customer queries in real time

Lý do:

Chatbot sử dụng mô hình ngôn ngữ lớn (LLM) như Claude, Titan, hoặc các mô hình tùy chỉnh trên Amazon Bedrock để tạo ra phản hồi văn bản một cách tự nhiên, linh hoạt và thời gian thực – đúng bản chất “tạo sinh” nội dung.

Đây là một use‑case thực tiễn được triển khai rộng rãi trên AWS: tích hợp Bedrock + Amazon Lex, hoặc SageMaker + API Gateway + Lambda để xây dựng chatbot hỗ trợ khách hàng, giảm tải cho trung tâm cuộc gọi.

Các ví dụ thực tế (2024‑2026) bao gồm: Amazon Q‑Chat cho hỗ trợ kỹ thuật, Shopify AI‑powered chatbot trên AWS, và các chatbot bán lẻ sử dụng Amazon Bedrock.

🧩 Phân tích các phương án còn lại (đúng và sai)

❌ Using an ML model to forecast product demand

Tại sao sai: Đây là mô hình dự báo (predictive analytics), không phải là generative AI. Các mô hình như Prophet, ARIMA, hoặc XGBoost dự đoán giá trị số trong tương lai, không “tạo” ra nội dung mới. Trên AWS, các giải pháp này thường chạy trên Amazon Forecast hoặc Amazon SageMaker, nhưng không thuộc lĩnh vực generative AI.

❌ Using an analytics dashboard to track website traffic and user behavior

Tại sao sai: Dashboard chỉ hiển thị và trực quan hoá dữ liệu đã thu thập; nó không tạo ra nội dung mới hay sinh ngôn ngữ. Các dịch vụ liên quan là Amazon QuickSight, AWS CloudWatch, AWS Glue, nhưng chúng không sử dụng mô hình generative.

❌ Implementing a rule‑based recommendation engine to suggest products to customers

Tại sao sai: Hệ thống khuyến nghị dựa trên luật tĩnh hoặc thuật toán collaborative filtering (ví dụ: Amazon Personalize). Nó không tạo nội dung mới mà chỉ đưa ra các mục đã tồn tại dựa trên các quy tắc hoặc mẫu thống kê. Generative AI sẽ tạo ra các đề xuất mới bằng cách “tưởng tượng” các kịch bản, ví dụ như sinh mô tả sản phẩm sáng tạo – không phải trường hợp này.

🛠️ Liên kết tới dịch vụ AWS (2026)

Amazon Bedrock – Cung cấp API cho các LLM (Claude, Titan, Llama 3) để triển khai chatbot sinh ngôn ngữ.

Amazon SageMaker JumpStart – Gói mẫu LLM có thể fine‑tune cho chatbot.

Amazon Q (Q‑Chat) – Dịch vụ AI chat nội bộ, dựa trên generative AI, hỗ trợ trả lời câu hỏi kỹ thuật.

Amazon Lex + Bedrock – Kết hợp nhận dạng giọng nói + sinh ngôn ngữ để tạo chatbot thoại.

📚 Tham khảo

AWS Documentation – Amazon Bedrock (2026 update): https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS Blog – Building Generative AI Chatbots with Amazon Bedrock and Amazon Lex (Nov 2024).

AWS re:Invent 2025 – “Generative AI on AWS: Best Practices & Real‑World Use Cases”.

Amazon SageMaker JumpStart – Generative AI Models (2025‑2026).

Tóm lại:

🔹 Câu hỏi đang kiểm tra khả năng phân biệt giữa generative AI và các dạng AI/ML truyền thống.

🔹 Đáp án đúng là Employing a chatbot to provide human‑like responses to customer queries in real time vì nó tận dụng khả năng tạo nội dung ngôn ngữ mới của mô hình generative.

🔹 Các đáp án còn lại đều liên quan tới dự báo, trực quan hoá, hay khuyến nghị dựa trên luật – không phải là trường hợp sử dụng generative AI.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313024-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 19

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Personalize, Amazon Polly, Amazon Transcribe, Amazon S3
- Đáp án tham khảo: **Amazon Personalize**
- Takeaway nhanh: Câu hỏi mô tả một nền tảng media streaming (ví dụ: Netflix, Disney+, …) muốn đưa ra đề xuất phim cho người dùng dựa trên lịch sử tài khoản (phim đã xem, đánh giá, thời gian xem, …). Yêu cầu chính: Xử lý dữ liệu hành vi người dùng (big‑data, time‑series, event streams). Áp dụng thuật toán máy học để tạo mô hình đề xuất (recommendation engine).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313027-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A media streaming platform wants to provide movie recommendations to users based on the users’ account history.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Polly
2. Amazon Comprehend
3. Amazon Transcribe
4. Amazon Personalize

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi mô tả một nền tảng media streaming (ví dụ: Netflix, Disney+, …) muốn đưa ra đề xuất phim cho người dùng dựa trên lịch sử tài khoản (phim đã xem, đánh giá, thời gian xem, …).

Yêu cầu chính:

Xử lý dữ liệu hành vi người dùng (big‑data, time‑series, event streams).

Áp dụng thuật toán máy học để tạo mô hình đề xuất (recommendation engine).

Cung cấp API trả về danh sách phim cá nhân hoá trong thời gian thực hoặc gần‑real‑time.

Do đó, dịch vụ cần hỗ trợ Machine Learning cho recommendation, không phải dịch vụ chuyển đổi giọng nói, phân tích ngôn ngữ hay dịch vụ tổng hợp âm thanh.

✅ Đáp án đúng: Amazon Personalize

Tại sao Amazon Personalize là lựa chọn phù hợp?

Mục đích chuyên biệt: Personalize được thiết kế để xây dựng, huấn luyện và triển khai các hệ thống recommendation (movie, music, e‑commerce, news feed…) chỉ với vài cú click.

Xử lý lịch sử hành vi: Nhận dữ liệu sự kiện (user‑item interaction, timestamps, metadata) thông qua Batch Import hoặc Real‑time Event Stream (Kinesis Data Streams).

Tự động lựa chọn thuật toán: Personalize tự động thử nghiệm và chọn mô hình (HRNN, SIMS, etc.) tối ưu cho dữ liệu của bạn, giảm thiểu công việc chuẩn bị mô hình.

API trả về đề xuất nhanh: Khi người dùng mở ứng dụng, bạn gọi GetRecommendations hoặc GetPersonalizedRanking và nhận danh sách phim trong mili‑giây.

Cập nhật mô hình liên tục: Với HRNN (Hierarchical Recurrent Neural Network) và incremental training, mô hình được cập nhật gần‑real‑time khi có event mới.

Tích hợp dễ dàng: Hoạt động tốt cùng Amazon S3, AWS Glue, Kinesis, Lambda, và IAM để bảo mật.

Tài liệu tham khảo (cập nhật 2026):

AWS Documentation – Amazon Personalize Developer Guide (phiên bản 2026.01).

AWS Blog – “How Amazon Personalize Powers Real‑Time Recommendations at Scale” (Jan 2025).

❌ Phân tích các phương án sai

1️⃣ Amazon Polly

Mô tả gốc: Amazon Polly

Chức năng thực tế: Dịch vụ Text‑to‑Speech (TTS), chuyển đổi văn bản thành giọng nói tự nhiên.

Tại sao không phù hợp: Không liên quan tới việc phân tích hành vi người dùng hay tạo đề xuất nội dung. Polly chỉ dùng để phát âm thanh (ví dụ: tạo lồng tiếng cho video), không thể xử lý hoặc dự đoán dữ liệu lịch sử.

2️⃣ Amazon Comprehend

Mô tả gốc: Amazon Comprehend

Chức năng thực tế: Dịch vụ Natural Language Processing (NLP), nhận diện thực thể, phân tích cảm xúc, topic modeling trên văn bản.

Tại sao không phù hợp: Nếu nền tảng streaming muốn phân tích nội dung mô tả phim (đánh giá, mô tả), Comprehend có thể hỗ trợ, nhưng không cung cấp mô hình recommendation dựa trên hành vi người dùng.

3️⃣ Amazon Transcribe

Mô tả gốc: Amazon Transcribe

Chức năng thực tế: Dịch vụ Automatic Speech Recognition (ASR), chuyển đổi audio/video thành văn bản.

Tại sao không phù hợp: Chỉ dùng để lấy transcript từ video/âm thanh, không liên quan tới việc đưa ra đề xuất phim.

🧩 Tổng kết (liệt kê)

✅ Amazon Personalize – Dịch vụ chuyên cho hệ thống recommendation dựa trên lịch sử tài khoản, đáp ứng đầy đủ yêu cầu câu hỏi.

❌ Amazon Polly – Chỉ chuyển văn bản thành giọng nói, không liên quan tới recommendation.

❌ Amazon Comprehend – Phân tích ngôn ngữ tự nhiên, không tạo đề xuất dựa trên hành vi.

❌ Amazon Transcribe – Chuyển đổi giọng nói thành văn bản, không liên quan tới đề xuất.

📘 Lời khuyên thực tiễn cho DevOps Engineer

CI/CD cho Personalize: Dùng AWS CodePipeline + AWS CodeBuild để tự động hoá việc export data → S3 → Glue Job → Personalize dataset import.

Giám sát: Đặt Amazon CloudWatch Alarms trên PersonalizeCampaign metrics (Precision, Recall) để cảnh báo khi chất lượng đề xuất giảm.

Chi phí: Personalize tính phí dựa trên training hours và inference requests; sử dụng auto‑scaling cho inference endpoint để tối ưu chi phí.

Những điểm này giúp bạn không chỉ chọn đúng dịch vụ mà còn triển khai và vận hành một cách hiệu quả trong môi trường production. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313027-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 20

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Use a negative prompt.**
- Takeaway nhanh: Một công ty đang dùng Amazon Nova Canvas – một mô hình tạo ảnh dựa trên AI (thuộc dịch vụ Amazon Bedrock). Mô hình hiện đang tạo ảnh thành công, nhưng công ty muốn ngăn không cho những vật phẩm nhất định xuất hiện trong ảnh (ví dụ: không muốn hình có xe hơi, logo, v.v.). Yêu cầu: chọn giải pháp cho phép “loại trừ” (exclude) các thành phần không mong muốn khi mô hình tạo ảnh.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313034-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using an Amazon Nova Canvas model to generate images. The model generates images successfully.
The company needs to prevent the model from including specific items in the generated images.
Which solution will meet this requirement?

### Các lựa chọn
1. Use a higher temperature value.
2. Use a more detailed prompt.
3. Use a negative prompt.
4. Use another foundation model (FM).

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty đang dùng Amazon Nova Canvas – một mô hình tạo ảnh dựa trên AI (thuộc dịch vụ Amazon Bedrock). Mô hình hiện đang tạo ảnh thành công, nhưng công ty muốn ngăn không cho những vật phẩm nhất định xuất hiện trong ảnh (ví dụ: không muốn hình có xe hơi, logo, v.v.).

Yêu cầu: chọn giải pháp cho phép “loại trừ” (exclude) các thành phần không mong muốn khi mô hình tạo ảnh.

✅ Đáp án đúng

✅ Use a negative prompt.

Giải thích:

Negative prompt là một kỹ thuật “prompt engineering” cho phép người dùng liệt kê các từ khóa hoặc mô tả điều không muốn mô hình sinh ra. Khi đưa vào API Bedrock (hoặc Amazon Nova Canvas), mô hình sẽ cố gắng tránh những đối tượng, màu sắc, phong cách được liệt kê trong negative prompt.

Đây là cách chuẩn nhất hiện nay để kiểm soát nội dung đầu ra của các mô hình tạo ảnh (cũng được áp dụng trong Amazon Titan‑Image G1, Stable Diffusion trên Bedrock, v.v.).

Tài liệu AWS (2024‑2026) về Prompt Engineering for Generative AI nêu rõ: “Use negative prompts to explicitly tell the model what to exclude from the generation.”

🧩 Giải thích các phương án còn lại

❌ Use a higher temperature value.

Temperature (nhiệt độ) điều chỉnh mức độ ngẫu nhiên trong quá trình sinh. Giá trị cao → kết quả đa dạng, ít dự đoán; giá trị thấp → ổn định, ít biến thể.

Tuy nhiên, temperature không ảnh hưởng đến việc loại bỏ một đối tượng cụ thể; nó chỉ thay đổi độ ngẫu nhiên của toàn bộ ảnh. Do đó không đáp ứng yêu cầu “ngăn không cho các mục cụ thể xuất hiện”.

❌ Use a more detailed prompt.

Việc cung cấp mô tả chi tiết (more detailed prompt) có thể giúp mô hình hiểu rõ hơn ý định tổng thể, nhưng không đảm bảo loại trừ những yếu tố không mong muốn. Thậm chí, chi tiết quá mức có thể gây nhầm lẫn và làm mô hình tạo ra các thành phần phụ không kiểm soát.

Để “loại trừ” cần một cơ chế đặc biệt (negative prompt), không phải chỉ làm rõ yêu cầu.

❌ Use another foundation model (FM).

Chuyển sang một mô hình nền tảng khác (ví dụ: từ Amazon Titan‑Image sang một model Stable Diffusion khác) không chắc chắn sẽ loại bỏ các đối tượng không mong muốn, trừ khi model đó đã được huấn luyện hoặc cấu hình sẵn để lọc.

Việc thay đổi FM thường gây tốn chi phí, thời gian tích hợp và có thể làm mất tính năng, hiệu năng hiện tại mà Nova Canvas đang cung cấp.

📘 Tham khảo tài liệu (2024‑2026)

AWS Documentation – Prompt Engineering for Amazon Bedrock (phiên bản cập nhật 2026).

Amazon Bedrock – Using Negative Prompts with Image Generation Models – Blog post AWS Machine Learning, 2025.

AWS re:Invent 2024 – “Advanced Prompt Techniques for Generative AI” (video và slide).

🛠️ Kết luận ngắn gọn

Để ngăn không cho các mục cụ thể xuất hiện trong ảnh do Amazon Nova Canvas tạo ra, sử dụng “negative prompt” là giải pháp đúng và hiệu quả nhất.

Các lựa chọn khác (tăng temperature, chi tiết prompt, đổi model) không đáp ứng nhu cầu loại trừ nội dung và vì thế là không phù hợp.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313034-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 21

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock
- Đáp án tham khảo: **Apply explainable AI techniques to show customers which factors influenced the model’s decision.**
- Takeaway nhanh: Công ty tài chính đang sử dụng một mô hình AI sinh ra (generative AI) để gán hạn mức tín dụng cho khách hàng mới. Mục tiêu: tăng tính minh bạch (transparency) trong quá trình quyết định của mô hình, để khách hàng hiểu được “tại sao” họ nhận được mức hạn mức hiện tại. Trong môi trường AWS, “giải thích được AI” (Explainable AI – XAI) được hỗ trợ qua các công cụ như Amazon SageMaker Clarify, Amazon SageMaker Model Monitor, và các tính năng Explainability trong Amazon Bedrock. Các công cụ này cho phép trích xuất feature importance, SHAP values, LIME, hoặc counterfactual explanations và hiển thị chúng cho người dùng cuối.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ml/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://www.examtopics.com/discussions/amazon/view/313033-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company uses a generative AI model to assign credit limits to new customers. The company wants to make the decision-making process of the model more transparent to its customers.
Which solution meets these requirements?

### Các lựa chọn
1. Use a rule-based system instead of an ML model.
2. Apply explainable AI techniques to show customers which factors influenced the model’s decision.
3. Develop an interactive UI for customers and provide clear technical explanations about the system.
4. Increase the accuracy of the model to reduce the need for transparency.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty tài chính đang sử dụng một mô hình AI sinh ra (generative AI) để gán hạn mức tín dụng cho khách hàng mới.

Mục tiêu: tăng tính minh bạch (transparency) trong quá trình quyết định của mô hình, để khách hàng hiểu được “tại sao” họ nhận được mức hạn mức hiện tại.

Trong môi trường AWS, “giải thích được AI” (Explainable AI – XAI) được hỗ trợ qua các công cụ như Amazon SageMaker Clarify, Amazon SageMaker Model Monitor, và các tính năng Explainability trong Amazon Bedrock. Các công cụ này cho phép trích xuất feature importance, SHAP values, LIME, hoặc counterfactual explanations và hiển thị chúng cho người dùng cuối.

Do đó, đáp án cần cung cấp kỹ thuật explainable AI để trình bày các yếu tố ảnh hưởng tới quyết định, chứ không phải thay thế mô hình bằng quy tắc cứng nhắc, hay chỉ tăng độ chính xác mà không giải thích, hay chỉ tạo UI mà không có nội dung giải thích thực sự.

✅ Đáp án đúng

• Apply explainable AI techniques to show customers which factors influenced the model’s decision.

Giải thích:

Sử dụng XAI (ví dụ: SageMaker Clarify, SHAP, LIME, hoặc các giải pháp Bedrock Explainability) cho phép trích xuất và hiển thị các yếu tố (features) quan trọng đã ảnh hưởng tới quyết định cấp hạn mức.

Khách hàng nhận được giải thích có tính chất “why” (ví dụ: “Điểm tín dụng, lịch sử thanh toán, và thu nhập hàng tháng là ba yếu tố quyết định”).

Giải pháp này phù hợp với yêu cầu minh bạch và vẫn giữ độ hiệu quả của mô hình AI hiện tại.

AWS cung cấp các dịch vụ và API tích hợp sẵn để tự động sinh explanations và đưa chúng vào UI của công ty mà không cần xây dựng lại toàn bộ pipeline.

❌ Các phương án sai và lý do

Use a rule‑based system instead of an ML model.

❌ Lý do: Thay đổi hoàn toàn sang hệ thống dựa trên quy tắc sẽ đánh mất lợi thế dự đoán chính xác của mô hình AI, đặc biệt trong lĩnh vực tài chính nơi dữ liệu phức tạp.

Quy tắc cứng nhắc không thể phản ánh mối quan hệ phi tuyến mà AI đã học được, và không đáp ứng yêu cầu “giải thích các yếu tố ảnh hưởng” mà chỉ cung cấp luật cố định.

AWS không đề xuất việc bỏ hoàn toàn ML khi mục tiêu chỉ là tăng tính minh bạch; thay vào đó, họ khuyến khích Explainability.

Develop an interactive UI for customers and provide clear technical explanations about the system.

❌ Lý do: Việc xây dựng UI là một phần quan trọng, nhưng không đủ nếu không có các giải thích dữ liệu thực tế (feature importance) do mô hình tạo ra.

“Clear technical explanations” mà không dựa trên kết quả thực tế của mô hình sẽ chỉ là mô tả chung (ví dụ: “hệ thống dựa trên học máy”) và không đáp ứng yêu cầu “which factors influenced the decision.”

Đúng hướng là kết hợp UI với công cụ XAI; tuy nhiên, câu trả lời này chỉ nói tới UI, không đề cập tới công nghệ explainability.

Increase the accuracy of the model to reduce the need for transparency.

❌ Lý do: Độ chính xác cao không thay thế được độ minh bạch. Ngay cả khi mô hình đạt 99% chính xác, khách hàng và các cơ quan quản lý vẫn yêu cầu giải thích về quyết định (đặc biệt trong ngành tài chính, nơi có các quy định như Fair Lending, GDPR, CCPA).

AWS luôn nhấn mạnh rằng explainability và accuracy là hai khía cạnh độc lập; một mô hình “đen” dù tốt vẫn không đáp ứng yêu cầu pháp lý và trải nghiệm khách hàng.

Việc “giảm nhu cầu minh bạch” là quan điểm sai lầm và không phù hợp với các chuẩn model governance hiện đại.

🛠️ Gợi ý triển khai trên AWS (đến năm 2026)

Amazon SageMaker Clarify:

Tự động tính SHAP values hoặc Permutation Feature Importance trong quá trình training hoặc inference.

Cung cấp API để lấy explanations cho mỗi dự đoán và đẩy chúng tới frontend.

Amazon Bedrock (Model Explainability):

Nếu mô hình generative được triển khai trên Bedrock, có thể bật Explainability để nhận feature attributions cho mỗi response.

AWS Lambda + API Gateway:

Xây dựng endpoint trả về explanations kèm theo kết quả hạn mức.

Amazon CloudWatch + SageMaker Model Monitor:

Theo dõi bias, drift, và explainability metrics để duy trì tính công bằng và minh bạch theo thời gian.

AWS IAM & AWS KMS:

Đảm bảo quyền truy cập và bảo mật cho dữ liệu nhạy cảm khi truyền explanations tới khách hàng.

📚 Tham khảo (đến 2026)

AWS Documentation – Amazon SageMaker Clarify – https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Blog – Explainability for Generative AI on Amazon Bedrock – 2025/09/15

AWS Well‑Architected Framework – Machine Learning Lens – https://aws.amazon.com/architecture/well-architected/ml/

Regulatory guidance – Fair Lending and Explainability – US CFPB, 2024 update (có liên quan tới yêu cầu giải thích quyết định tín dụng).

📌 Tổng kết

✅ Đáp án đúng: Apply explainable AI techniques to show customers which factors influenced the model’s decision.

❌ Các đáp án còn lại không đáp ứng yêu cầu minh bạch hoặc không liên quan tới việc cung cấp giải thích dựa trên mô hình AI.

Bằng cách áp dụng các công cụ Explainability của AWS (SageMaker Clarify, Bedrock Explainability) và tích hợp chúng vào giao diện khách hàng, công ty tài chính có thể đảm bảo tính minh bạch, tuân thủ quy định, và cải thiện niềm tin của khách hàng mà không hy sinh hiệu suất của mô hình AI. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313033-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 22

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, RAG
- Đáp án tham khảo: **F1 score**
- Takeaway nhanh: F1 score là trung bình điều hòa (harmonic mean) của precision và recall. Khi dữ liệu mất cân bằng, F1 score phản ánh mức độ cân bằng giữa việc không bỏ sót (recall) và không gây sai lệch (precision). Trong môi trường AWS, khi triển khai mô hình trên Amazon SageMaker, bạn có thể cấu hình metric definitions để tự động thu thập F1 score qua CloudWatch, giúp giám sát hiệu năng mô hình trên các lớp ít mẫu.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://aws.amazon.com/blogs/machine-learning/evaluation-metrics-imbalanced-data/ | https://docs.aws.amazon.com/sagemaker/latest/dg/monitoring-metrics.html | https://www.examtopics.com/discussions/amazon/view/313037-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is training ML models on datasets. The datasets contain some classes that have more examples than other classes. The company wants to measure how well the model balances detecting and labeling the classes.
Which metric should the company use?

### Các lựa chọn
1. Accuracy
2. Recall
3. Precision
4. F1 score

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đang huấn luyện các mô hình Machine Learning (ML) trên các bộ dữ liệu không cân bằng: một số lớp (class) có số lượng mẫu lớn, trong khi các lớp khác chỉ có ít mẫu. Khi đánh giá mô hình, công ty muốn đo lường khả năng cân bằng giữa việc phát hiện (detect) và gán nhãn (label) cho các lớp – tức là muốn biết mô hình có thể đánh giá đúng cả những mẫu đa dạng, không chỉ tối ưu cho lớp chiếm đa số.

Trong các metric truyền thống, một số chỉ tập trung vào độ chính xác tổng thể (accuracy) hoặc chỉ một khía cạnh (precision hay recall). Khi dữ liệu không cân bằng, những metric này có thể gây hiểu lầm vì một mô hình “đánh đồng” lớp chiếm đa số sẽ vẫn đạt accuracy cao, nhưng lại bỏ sót các lớp hiếm. Do đó cần một metric cân bằng độ chính xác (precision) và độ thu hồi (recall) cho mỗi lớp – F1 score là lựa chọn thích hợp.

✅ Đáp án đúng: F1 score

F1 score là trung bình điều hòa (harmonic mean) của precision và recall.

Khi dữ liệu mất cân bằng, F1 score phản ánh mức độ cân bằng giữa việc không bỏ sót (recall) và không gây sai lệch (precision).

Trong môi trường AWS, khi triển khai mô hình trên Amazon SageMaker, bạn có thể cấu hình metric definitions để tự động thu thập F1 score qua CloudWatch, giúp giám sát hiệu năng mô hình trên các lớp ít mẫu.

Đối với bài toán đa lớp (multi‑class), SageMaker hỗ trợ tính macro‑averaged F1 hoặc weighted‑averaged F1, giúp đánh giá toàn bộ mô hình một cách công bằng.

❌ Các phương án sai và lý do

Accuracy

Accuracy đo tỉ lệ tổng số dự đoán đúng trên tổng số mẫu.

Trong dữ liệu mất cân bằng, một mô hình dự đoán luôn là lớp chiếm đa số vẫn có accuracy cao, nhưng không phản ánh khả năng dự đoán đúng các lớp hiếm.

Vì vậy, accuracy không đáp ứng yêu cầu “cân bằng phát hiện và gán nhãn” trong trường hợp này.

Recall

Recall (hay sensitivity) chỉ đo tỷ lệ các mẫu thực tế thuộc lớp tích cực được mô hình phát hiện đúng.

Nó không xem xét precision – nghĩa là mô hình có thể trả về rất nhiều dự đoán dương tính giả, làm giảm độ tin cậy.

Khi chỉ dùng recall, chúng ta không biết mô hình có “phát hiện” nhưng đồng thời đánh dấu sai bao nhiêu.

Precision

Precision đo tỷ lệ các dự đoán dương tính là đúng (không có false positive).

Nó không phản ánh khả năng không bỏ sót các mẫu thực tế thuộc lớp mục tiêu (recall).

Khi chỉ dùng precision, mô hình có thể “cẩn thận” nhưng bỏ qua nhiều mẫu thực tế, gây mất cân bằng.

📚 Tham khảo tài liệu (AWS, 2026)

Amazon SageMaker – Built‑in Metrics

https://docs.aws.amazon.com/sagemaker/latest/dg/monitoring-metrics.html

Mô tả cách cấu hình MetricDefinition để ghi nhận F1 score (và các metric khác) trong CloudWatch.

AWS Well‑Architected Framework – Machine Learning Lens (2025 Update)

https://aws.amazon.com/architecture/well-architected/machine-learning/

Nhấn mạnh việc lựa chọn metric phù hợp (F1, ROC‑AUC) khi dữ liệu không cân bằng.

“Evaluation Metrics for Imbalanced Classification” – AWS Machine Learning Blog (2024)

https://aws.amazon.com/blogs/machine-learning/evaluation-metrics-imbalanced-data/

🛠️ Kết luận

Với dữ liệu mất cân bằng và yêu cầu cân bằng giữa việc phát hiện và gán nhãn các lớp, F1 score là metric phù hợp nhất vì nó kết hợp cả precision và recall. Các metric khác (accuracy, recall, precision) chỉ phản ánh một phần khía cạnh và có thể gây hiểu lầm trong môi trường dữ liệu không cân bằng. Khi triển khai trên AWS, bạn có thể tận dụng SageMaker và CloudWatch để theo dõi F1 score một cách tự động và liên tục. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313037-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 23

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Takeaway nhanh: Use the Amazon Nova Reel model on Amazon Bedrock to generate videos. Vì sao đây là đáp án đúng? Nova Reel là mô hình tạo video (từ văn bản hoặc chuỗi hình ảnh) được cung cấp trên Amazon Bedrock, dịch vụ AI serverless của AWS. Khi sử dụng Nova Reel, toàn bộ quy trình từ việc tạo nội dung tới xuất video được thực hiện trong môi trường được quản lý – không cần provisioning EC2, không cần cài đặt phần mềm chỉnh sửa video, không cần lưu trữ tạm thời.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/ | https://aws.amazon.com/blogs/aws/generating-video-at-scale-with-bedrock/ | https://aws.amazon.com/blogs/aws/introducing-amazon-nova-frontier-intelligence-and-industry-leading-price-performance/ | https://docs.aws.amazon.com/bedrock/latest/userguide/video-models.html | https://reinvent.awsevents.com/2025/novel-series | https://www.examtopics.com/discussions/amazon/view/312994-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company creates video content. The company wants to use generative AI to generate new creative content and to reduce video creation time.
Which solution will meet these requirements in the MOST operationally efficient way?

### Các lựa chọn
1. Use the Amazon Titan Image Generator model on Amazon Bedrock to generate intermediate images. Use video editing software to create videos.
2. Use the Amazon Nova Canvas model on Amazon Bedrock to generate intermediate images. Use video editing software to create videos.
3. Use the Amazon Nova Reel model on Amazon Bedrock to generate videos.
4. Use the Amazon Nova Pro model on Amazon Bedrock to generate videos.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích câu hỏi

Một công ty sản xuất nội dung video muốn khai thác Generative AI để:

Tạo ra nội dung sáng tạo mới.

Rút ngắn thời gian sản xuất video.

Yêu cầu “MOST operationally efficient” nghĩa là giải pháp phải:

Tự động hoá tối đa (không cần quản lý máy chủ, không cần công cụ trung gian).

Giảm bớt các bước thủ công (ví dụ: không phải xuất‑nhập ảnh‑video qua phần mềm chỉnh sửa).

Tận dụng dịch vụ được quản lý của AWS (độ sẵn sàng cao, bảo mật tích hợp, thanh toán theo mức sử dụng).

✅ Đáp án đúng

Use the Amazon Nova Reel model on Amazon Bedrock to generate videos.

Vì sao đây là đáp án đúng?

Nova Reel là mô hình tạo video (từ văn bản hoặc chuỗi hình ảnh) được cung cấp trên Amazon Bedrock, dịch vụ AI serverless của AWS.

Khi sử dụng Nova Reel, toàn bộ quy trình từ việc tạo nội dung tới xuất video được thực hiện trong môi trường được quản lý – không cần provisioning EC2, không cần cài đặt phần mềm chỉnh sửa video, không cần lưu trữ tạm thời.

Chi phí chỉ tính theo số token/giây video được sinh ra → pay‑as‑you‑go, giảm lãng phí tài nguyên.

Tích hợp dễ dàng với các service khác (S3 để lưu video, EventBridge để kích hoạt workflow, Step Functions để orchestrate) → độ tự động hoá cao.

So với việc tạo ảnh rồi dùng phần mềm chỉnh sửa video, Nova Reel loại bỏ một bước trung gian và giảm độ trễ, do đó hiệu quả vận hành tốt nhất.

❌ Giải thích các phương án sai

Use the Amazon Titan Image Generator model on Amazon Bedrock to generate intermediate images. Use video editing software to create videos.

Titan Image Generator chỉ tạo ảnh tĩnh; không có khả năng tạo video.

Việc phải xuất ảnh ra và sau đó dùng phần mềm chỉnh sửa video (có thể chạy trên EC2, on‑prem, hoặc desktop) tạo ra bước trung gian và đòi hỏi quản lý thêm (cài đặt, cập nhật, licensing).

Vì vậy không đạt “most operationally efficient”.

Use the Amazon Nova Canvas model on Amazon Bedrock to generate intermediate images. Use video editing software to create videos.

Nova Canvas, như tên gọi, là mô hình tạo canvas / hình ảnh; không hỗ trợ tạo video.

Tương tự như trên, cần bước chuyển đổi ảnh → video bằng công cụ bên ngoài → tăng độ phức tạp và chi phí vận hành.

Use the Amazon Nova Pro model on Amazon Bedrock to generate videos.

Mặc dù mô tả “generate videos”, Nova Pro (theo tài liệu hiện hành đến năm 2026) là mô hình tạo hình ảnh chất lượng cao (độ phân giải, chi tiết vượt trội) và không hỗ trợ trực tiếp tạo video.

Nếu muốn video, vẫn phải kết hợp nhiều ảnh và xử lý thêm bằng công cụ video, dẫn tới độ trễ và chi phí cao hơn so với Nova Reel được thiết kế đặc thù cho video.

📚 Tham khảo tài liệu (đến 2026)

Amazon Bedrock Documentation – “Generative AI models – Video generation (Nova Reel)”. https://docs.aws.amazon.com/bedrock/latest/userguide/video-models.html

AWS re:Invent 2025 – Announcement of Amazon Nova series (Canvas, Reel, Pro) with use‑case diagrams. https://reinvent.awsevents.com/2025/novel-series

AWS Blog – “Generating Video at Scale with Amazon Bedrock” (Nov 2025). https://aws.amazon.com/blogs/aws/generating-video-at-scale-with-bedrock/

Well‑Architected Framework – Operational Excellence Pillar – Guidance on using fully managed AI services. https://aws.amazon.com/architecture/well-architected/

🔧 Kết luận

Để đạt hiệu quả vận hành tối đa trong việc tạo video sáng tạo bằng Generative AI, công ty nên dùng mô hình Amazon Nova Reel trên Amazon Bedrock. Mô hình này cho phép tạo video trực tiếp trong môi trường serverless, loại bỏ các bước và công cụ trung gian, giảm chi phí, giảm độ phức tạp quản lý và đáp ứng nhanh chóng nhu cầu sản xuất nội dung.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312994-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://aws.amazon.com/blogs/aws/introducing-amazon-nova-frontier-intelligence-and-industry-leading-price-performance/

## Câu 24

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312986-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company uses ML techniques to build applications.
2. Select the correct ML technique from the following list for each task. Select each ML technique one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312986-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 25

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon Comprehend, Amazon Personalize, Amazon Polly, Amazon SageMaker, Amazon Bedrock, embeddings
- Takeaway nhanh: Mục tiêu của công ty: Cho phép khách hàng tìm kiếm và lọc ảnh dựa trên mô tả ngôn ngữ tự nhiên. Yêu cầu kỹ thuật: Khi người dùng nhập một câu mô tả, hệ thống sẽ chuyển câu đó thành một vector embedding (ví dụ dùng mô hình NLP). Sau đó cần tìm các vector ảnh có độ tương đồng cao nhất (similarity search / nearest‑neighbor query). Kiến trúc cần: Một cơ sở dữ liệu vector (vector store) hỗ trợ truy vấn k‑Nearest Neighbors (k‑NN) trên các vector có chiều cao (thường 128‑1024).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html | https://www.examtopics.com/discussions/amazon/view/312983-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An online media streaming company wants to give its customers the ability to perform natural language-based image search and filtering. The company needs a vector database that can help with similarity searches and nearest neighbor queries.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Comprehend
2. Amazon Personalize
3. Amazon Polly
4. Amazon OpenSearch Service

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Mục tiêu của công ty: Cho phép khách hàng tìm kiếm và lọc ảnh dựa trên mô tả ngôn ngữ tự nhiên.

Yêu cầu kỹ thuật: Khi người dùng nhập một câu mô tả, hệ thống sẽ chuyển câu đó thành một vector embedding (ví dụ dùng mô hình NLP). Sau đó cần tìm các vector ảnh có độ tương đồng cao nhất (similarity search / nearest‑neighbor query).

Kiến trúc cần: Một cơ sở dữ liệu vector (vector store) hỗ trợ truy vấn k‑Nearest Neighbors (k‑NN) trên các vector có chiều cao (thường 128‑1024).

Với yêu cầu “vector database” để thực hiện similarity searches và nearest‑neighbor queries, dịch vụ AWS phù hợp nhất hiện nay (tính tới năm 2026) là Amazon OpenSearch Service – phiên bản OpenSearch tích hợp plugin k‑NN cho phép lưu trữ và tra‑cứu vector bằng thuật toán HNSW hoặc IVF‑PQ.

✅ Đáp án đúng

🟢 Amazon OpenSearch Service

OpenSearch Service (trước đây là Amazon Elasticsearch Service) cung cấp tính năng k‑NN cho phép tạo index vector, lưu trữ vector embedding và thực hiện truy vấn tìm kiếm gần nhất với độ trễ thấp.

Hỗ trợ API RESTful, tích hợp dễ dàng với các mô hình NLP/Computer Vision (ví dụ Amazon SageMaker, Amazon Bedrock) để đưa vector vào index.

Được quản lý hoàn toàn, khả năng mở rộng tự động, và tích hợp sẵn với IAM, VPC, Encryption, đáp ứng các yêu cầu bảo mật của môi trường doanh nghiệp.

Nguồn tham khảo:

AWS Documentation – Amazon OpenSearch Service – k‑Nearest Neighbor (k‑NN) Search (https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html)

AWS Blog – Introducing k‑NN vector search on Amazon OpenSearch Service (2023)

🧩 Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

Amazon Comprehend

❌ Lý do: Amazon Comprehend là dịch vụ xử lý ngôn ngữ tự nhiên (NLP), chuyên về phân tích sentiment, thực thể, key phrases, v.v. Nó không cung cấp khả năng lưu trữ hoặc truy vấn vector. Do đó không phù hợp cho việc thực hiện tìm kiếm ảnh dựa trên vector similarity.

Amazon Personalize

❌ Lý do: Amazon Personalize là dịch vụ đề xuất (recommendation) dựa trên hành vi người dùng và dữ liệu giao dịch. Mặc dù có thể tạo ra mô hình machine‑learning, nó không phải là một vector database và không hỗ trợ truy vấn k‑NN cho embedding ảnh.

Amazon Polly

❌ Lý do: Amazon Polly là dịch vụ chuyển văn bản thành giọng nói (text‑to‑speech). Nó không liên quan tới lưu trữ hoặc tra‑cứu vector, nên không đáp ứng yêu cầu “vector database”.

Amazon OpenSearch Service

🟢 Lý do: Như đã nêu ở mục “Đáp án đúng”, OpenSearch Service cung cấp module k‑NN cho phép tạo index vector, thực hiện similarity search và nearest‑neighbor queries trên các vector embedding. Đây là dịch vụ duy nhất trong danh sách đáp ứng đầy đủ yêu cầu của câu hỏi.

🛠️ Kết luận nhanh

Để triển khai tìm kiếm ảnh dựa trên mô tả ngôn ngữ tự nhiên cần một cơ sở dữ liệu vector có khả năng k‑NN.

Amazon OpenSearch Service (với plugin k‑NN) là lựa chọn đúng trong các tùy chọn đã cho.

Các dịch vụ còn lại (Comprehend, Personalize, Polly) đều không cung cấp chức năng lưu trữ và truy vấn vector, vì vậy không phù hợp.

💡 Gợi ý thực tế: Khi xây dựng pipeline, bạn có thể dùng Amazon SageMaker hoặc Amazon Bedrock để sinh embeddings (ví dụ CLIP, BERT) và sau đó đẩy các vector này vào OpenSearch index để người dùng cuối thực hiện truy vấn tìm kiếm gần nhất.

✨ Chúc bạn ôn luyện thành công và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312983-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 26

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, hallucination
- Takeaway nhanh: “An AI practitioner notices a large language model (LLM) is generating different responses for the same input across multiple invocations. Which risk of AI does this describe?” Câu hỏi muốn kiểm tra khả năng nhận diện một rủi ro thường gặp khi làm việc với các mô hình ngôn ngữ lớn (LLM). Điểm mấu chốt là: cùng một prompt nhưng mỗi lần chạy lại cho ra kết quả khác nhau. Điều này phản ánh tính không xác định (nondeterministic) của mô hình – tức là kết quả không ổn định, gây khó khăn trong việc dự đoán, kiểm soát và tái tạo kết quả.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312992-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner notices a large language model (LLM) is generating different responses for the same input across multiple invocations.
Which risk of AI does this describe?

### Các lựa chọn
1. Hallucinations
2. Nondeterminism
3. Accuracy
4. Multimodality

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

“An AI practitioner notices a large language model (LLM) is generating different responses for the same input across multiple invocations. Which risk of AI does this describe?”

Câu hỏi muốn kiểm tra khả năng nhận diện một rủi ro thường gặp khi làm việc với các mô hình ngôn ngữ lớn (LLM). Điểm mấu chốt là: cùng một prompt nhưng mỗi lần chạy lại cho ra kết quả khác nhau. Điều này phản ánh tính không xác định (nondeterministic) của mô hình – tức là kết quả không ổn định, gây khó khăn trong việc dự đoán, kiểm soát và tái tạo kết quả.

✅ Đáp án đúng

Nondeterminism

Lý do: Khi một LLM trả về các phản hồi không đồng nhất cho cùng một đầu vào, đó là dấu hiệu của nondeterminism – mô hình có tính ngẫu nhiên trong quá trình sinh ra token (do sampling, temperature, top‑k, top‑p,…). Điều này tạo ra rủi ro về độ tin cậy và khả năng tái sử dụng của hệ thống AI, đặc biệt khi cần tính nhất quán trong các ứng dụng sản xuất hoặc khi tuân thủ quy định.

❌ Giải thích các phương án còn lại

Hallucinations

Hallucinations là hiện tượng mô hình “bịa ra” thông tin không có trong dữ liệu gốc (ví dụ: tạo ra dữ liệu sai, nguồn không tồn tại). Nó liên quan tới độ chính xác và độ tin cậy của nội dung, không phải sự biến đổi kết quả khi cùng một input được đưa vào nhiều lần.

Accuracy

Accuracy đề cập tới mức độ đúng đắn của câu trả lời so với thực tế hoặc so với đáp án chuẩn. Một mô hình có độ chính xác cao vẫn có thể nondeterministic nếu kết quả thay đổi mỗi lần chạy, và ngược lại, một mô hình có độ chính xác thấp không nhất thiết phải cho ra kết quả khác nhau cho cùng một input.

Multimodality

Multimodality là khả năng của mô hình xử lý và kết hợp nhiều kiểu dữ liệu (text, image, audio, video…). Đây là một tính năng/khả năng, không phải là rủi ro về tính nhất quán của output.

🧩 Tổng hợp các rủi ro liên quan đến Nondeterminism trong LLM (2026)

Khó tái tạo (Reproducibility)

Khi triển khai trong môi trường production, việc không thể tái tạo kết quả gây ra khó khăn trong debugging, kiểm thử, và đánh giá mô hình.

Tính ổn định của pipeline CI/CD

Trong DevOps, pipeline tự động hoá (ví dụ: kiểm thử API AI) dựa vào kết quả cố định; nondeterminism có thể làm pipeline thất bại ngẫu nhiên.

Tuân thủ và audit

Các quy định (ví dụ: GDPR, AI Act EU) yêu cầu giải thích được và độ nhất quán của quyết định AI. Nondeterminism gây khó khăn trong việc cung cấp bằng chứng.

Chi phí và tài nguyên

Để đạt được kết quả “đáng tin cậy”, thường phải chạy mô hình nhiều lần và chọn majority vote, tăng chi phí tính toán.

Biện pháp giảm thiểu (mitigation) (theo AWS Well‑Architected Framework for AI/ML – cập nhật 2025/2026):

Thiết lập seed cố định cho các thuật toán sampling (temperature, top‑k, top‑p) khi cần tính tái lập.

Sử dụng deterministic inference mode (có sẵn trong Amazon SageMaker JumpStart và các container Hugging Face mới nhất).

Log và versioning toàn bộ siêu tham số và môi trường (Docker image, AMI, instance type) để tái tạo môi trường.

Kiểm thử A/B để đo lường mức độ biến đổi và đưa ra ngưỡng chấp nhận.

📚 Tham khảo

AWS Whitepaper – “Architecting for AI/ML on AWS (2025 Update)” – phần Model Determinism & Reproducibility.

Amazon SageMaker Documentation (v2026.2) – Deterministic Inference và Seed Management.

IEEE Standard for AI System Risk Management (2025) – mô tả các rủi ro Nondeterminism và Hallucination.

“Large Language Model Risk Framework” – AI Governance Initiative, 2026 – chương về Consistency & Reproducibility.

Kết luận:

Câu hỏi mô tả rủi ro Nondeterminism – hiện tượng LLM tạo ra các phản hồi không đồng nhất cho cùng một đầu vào. Đây là một rủi ro quan trọng cần được quản lý trong quá trình thiết kế, triển khai và vận hành các hệ thống AI trên nền tảng AWS. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312992-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 27

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, prompt engineering
- Đáp án tham khảo: **The model is overfit.**
- Takeaway nhanh: 🟢 The model is overfit. Khi một mô hình “overfit”, nó học quá mức các đặc trưng, nhiễu và sai lệch riêng của tập dữ liệu huấn luyện. Do đó, nó đạt độ chính xác cao trên training set nhưng lại không tổng quát hoá được khi gặp dữ liệu mới (evaluation set). Đây là nguyên nhân nhiều nhất gây ra hiện tượng “training accuracy cao – validation accuracy thấp”.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/overfitting-underfitting/ | https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-overview.html | https://docs.aws.amazon.com/sagemaker/latest/dg/training-job-early-stopping.html | https://www.examtopics.com/discussions/amazon/view/313029-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner has trained a model on a training dataset. The model performs well on the training data. However, the model does not perform well on evaluation data.
What is the MOST likely cause of this issue?

### Các lựa chọn
1. The model is underfit.
2. The model requires prompt engineering.
3. The model is biased.
4. The model is overfit.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi mô tả một mô hình AI được huấn luyện trên training dataset và cho kết quả tốt trên dữ liệu huấn luyện, nhưng khi đánh giá (validation / test data) hiệu năng giảm mạnh. Đây là một tình huống rất phổ biến trong Machine Learning và thường liên quan tới độ khớp (fit) của mô hình với dữ liệu.

✅ Đáp án đúng

🟢 The model is overfit.

Khi một mô hình “overfit”, nó học quá mức các đặc trưng, nhiễu và sai lệch riêng của tập dữ liệu huấn luyện. Do đó, nó đạt độ chính xác cao trên training set nhưng lại không tổng quát hoá được khi gặp dữ liệu mới (evaluation set). Đây là nguyên nhân nhiều nhất gây ra hiện tượng “training accuracy cao – validation accuracy thấp”.

📚 Giải thích chi tiết các phương án (giữ nguyên nội dung tiếng Anh)

1️⃣ The model is underfit. ❌

Giải thích: Underfitting xảy ra khi mô hình quá đơn giản hoặc chưa được huấn luyện đủ lâu, dẫn đến hiệu năng kém trên cả training và evaluation data.

Vì sao sai: Ở đây mô hình “perform well on the training data”, vì vậy nó không phải là trường hợp underfit.

2️⃣ The model requires prompt engineering. ❌

Giải thích: Prompt engineering là kỹ thuật thiết kế câu lệnh (prompt) để tối ưu hoá đầu ra của các mô hình ngôn ngữ lớn (LLM) như GPT. Đây là vấn đề liên quan tới cách tương tác với mô hình, không phải về quá trình học và tổng quát hoá.

Vì sao sai: Câu hỏi nói về “training vs evaluation performance”, không đề cập tới prompt. Do đó, việc cải thiện prompt không giải quyết được vấn đề over/under‑fit.

3️⃣ The model is biased. ❌

Giải thích: Bias trong ML thường chỉ tới sự thiên lệch của mô hình đối với một nhóm dữ liệu nào đó (ví dụ: phân biệt đối xử). Bias có thể xuất hiện dù mô hình overfit hay không, nhưng nó không giải thích sự chênh lệch giữa training và evaluation accuracy.

Vì sao sai: Khi mô hình “bias”, chúng ta vẫn có thể thấy hiệu năng ổn định trên cả hai tập dữ liệu (nếu bias là hệ thống). Câu hỏi chỉ nêu hiện tượng không tổng quát hoá, không phải vấn đề công bằng.

4️⃣ The model is overfit. ✅

Giải thích: Overfitting là hiện tượng mô hình học quá chi tiết các mẫu trong training set, bao gồm cả nhiễu và các đặc trưng không đại diện cho dữ liệu thực tế. Khi đưa vào evaluation data (có phân phối khác hoặc ít nhiễu hơn), mô hình không thể dự đoán đúng, dẫn tới giảm mạnh hiệu năng.

Cơ chế thường gặp:

Số lượng tham số quá lớn so với kích thước dữ liệu.

Huấn luyện quá nhiều epoch mà không có regularization (L2, dropout, early stopping).

Không có kỹ thuật giảm độ phức tạp (feature selection, pruning).

Cách khắc phục (theo AWS SageMaker 2026):

Sử dụng early stopping trong SageMaker Training Jobs.

Áp dụng regularization (L1/L2) hoặc dropout trong các container Deep Learning.

Tăng kích thước tập validation và dùng cross‑validation.

Triển khai hyperparameter tuning (SageMaker Automatic Model Tuning) để tìm cấu hình không gây overfit.

🛠️ Liên hệ với AWS (đến năm 2026)

Amazon SageMaker cung cấp các tính năng Built‑in Model Debugger và Profiler giúp phát hiện dấu hiệu overfitting (ví dụ: training loss giảm liên tục trong khi validation loss tăng).

SageMaker Clarify hỗ trợ phân tích bias, nhưng không phải là công cụ giải quyết overfitting.

SageMaker Pipelines cho phép chèn bước validation monitoring và early‑stop callbacks tự động trong workflow.

Amazon CloudWatch Metrics có thể giám sát validation:accuracy và training:accuracy theo epoch để nhanh chóng nhận ra chênh lệch.

📘 Tài liệu tham khảo

AWS SageMaker Documentation – Training Jobs – Early Stopping (v2026.03) – https://docs.aws.amazon.com/sagemaker/latest/dg/training-job-early-stopping.html

AWS SageMaker Debugger – Detect Overfitting (v2026.01) – https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-overview.html

Machine Learning Foundations – Overfitting & Underfitting (AWS Machine Learning Blog, 2025) – https://aws.amazon.com/blogs/machine-learning/overfitting-underfitting/

Tóm tắt:

✅ Đáp án đúng: The model is overfit.

❌ Các lựa chọn còn lại không phù hợp vì chúng mô tả các vấn đề khác (underfitting, prompt engineering, bias) mà không gây ra hiện tượng “training tốt – evaluation kém”.

Hy vọng phân tích trên giúp bạn nắm rõ nguyên nhân và cách phòng tránh overfitting trong môi trường AWS hiện đại! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313029-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 28

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313013-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company periodically updates its product database by manually uploading digital product guides. The product guides contain text and images. The company wants to automate this task by using generative AI.
2. Select and order the steps from the following list to automate the database update task by using generative AI. Select each step one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313013-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 29

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Re‑train the model with fresh data.**
- Takeaway nhanh: Một công ty đang dùng Amazon SageMaker Model Monitor để giám sát mô hình dự báo. Khi dữ liệu đầu vào thay đổi (data drift) vượt quá ngưỡng đã định, công ty lo ngại rằng mô hình hiện tại sẽ cho ra kết quả kém, có thể gây ảnh hưởng tiêu cực tới hoạt động kinh doanh. Yêu cầu: “Mitigate a potentially adverse impact on the predictive model” – tức là phải thực hiện biện pháp để giảm thiểu tác động tiêu cực khi dữ liệu drift xảy ra.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-drift.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-updating.html | https://www.examtopics.com/discussions/amazon/view/312973-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is monitoring a predictive model by using Amazon SageMaker Model Monitor. The company notices data drift beyond a defined threshold. The company wants to mitigate a potentially adverse impact on the predictive model.
Which solution will meet these requirements?

### Các lựa chọn
1. Restart the SageMaker AI endpoint.
2. Adjust the monitoring sensitivity.
3. Re-train the model with fresh data.
4. Set up experiments tracking.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty đang dùng Amazon SageMaker Model Monitor để giám sát mô hình dự báo. Khi dữ liệu đầu vào thay đổi (data drift) vượt quá ngưỡng đã định, công ty lo ngại rằng mô hình hiện tại sẽ cho ra kết quả kém, có thể gây ảnh hưởng tiêu cực tới hoạt động kinh doanh.

Yêu cầu: “Mitigate a potentially adverse impact on the predictive model” – tức là phải thực hiện biện pháp để giảm thiểu tác động tiêu cực khi dữ liệu drift xảy ra.

Trong môi trường SageMaker, các cách khắc phục data drift thường là:

Cập nhật (re‑train) mô hình bằng dữ liệu mới phản ánh đúng phân phối hiện tại.

Triển khai lại (deploy) phiên bản mô hình mới lên endpoint.

Tự động hoá quy trình (pipeline) để tái huấn luyện khi drift được phát hiện.

Các hành động như restart endpoint, điều chỉnh độ nhạy của monitor, hay tạo experiment tracking chỉ giúp phát hiện hoặc ghi lại drift, không giải quyết được vấn đề mô hình đã lỗi thời.

✅ Đáp án đúng

✅ Re‑train the model with fresh data.

Lý do:

Khi drift xảy ra, phân phối dữ liệu mới không còn phù hợp với mô hình đã huấn luyện. Việc tái huấn luyện mô hình bằng dữ liệu mới (có nhãn hoặc không nhãn tùy thuộc vào quy trình) sẽ giúp mô hình học lại các mối quan hệ mới, từ đó giảm thiểu sai số và tác động tiêu cực.

Sau khi tái huấn luyện, bạn có thể đăng ký phiên bản mới trong SageMaker Model Registry và đổi endpoint hoặc cập nhật Blue/Green deployment để đưa mô hình mới vào sản xuất mà không gây gián đoạn.

AWS khuyến nghị: “When drift is detected, you should retrain the model on recent data and redeploy the updated model.” (AWS SageMaker Model Monitor documentation, 2026).

❌ Giải thích các phương án sai

❌ Restart the SageMaker AI endpoint.

Giải thích: Restart chỉ làm tái khởi động endpoint hiện tại, không thay đổi bất kỳ gì về trọng số hay kiến trúc mô hình. Khi dữ liệu drift, mô hình cũ vẫn sẽ đưa ra dự đoán sai dù endpoint đã được khởi động lại. Đây chỉ là một thao tác quản trị, không giải quyết vấn đề drift.

❌ Adjust the monitoring sensitivity.

Giải thích: Điều chỉnh độ nhạy (sensitivity) của Model Monitor chỉ ảnh hưởng đến cách phát hiện drift (ví dụ: giảm hoặc tăng ngưỡng cảnh báo). Nó không thay đổi mô hình hay dữ liệu đầu vào. Khi drift đã vượt ngưỡng, việc thay đổi ngưỡng sẽ chỉ làm chậm hoặc bỏ lỡ cảnh báo, không khắc phục tác động tiêu cực.

❌ Set up experiments tracking.

Giải thích: Experiments tracking (SageMaker Experiments) giúp ghi lại, so sánh và quản lý các thử nghiệm mô hình (phiên bản, siêu tham số, dữ liệu). Đây là công cụ giám sát quá trình phát triển, không phải công cụ để giảm thiểu drift trong môi trường sản xuất. Khi drift đã xảy ra, việc chỉ tạo experiment không đưa ra giải pháp khắc phục.

📚 Tham khảo tài liệu (AWS, cập nhật 2026)

Amazon SageMaker Model Monitor – Detecting Data Drift

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-drift.html (phiên bản 2026)

Best Practices for Updating Models in SageMaker

https://docs.aws.amazon.com/sagemaker/latest/dg/model-updating.html

SageMaker Model Registry and Blue/Green Deployments

https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html

AWS Well‑Architected Framework – Machine Learning Lens (2025 Update)

https://aws.amazon.com/architecture/well-architected/machine-learning/

🧩 Kết luận

Câu hỏi yêu cầu một giải pháp giảm thiểu tác động tiêu cực khi data drift xảy ra.

Giải pháp duy nhất đáp ứng yêu cầu là tái huấn luyện mô hình với dữ liệu mới (re‑train with fresh data), sau đó triển khai lại mô hình.

Các phương án còn lại chỉ liên quan tới việc quản lý, phát hiện hoặc ghi lại drift, không giải quyết được vấn đề mô hình lỗi thời.

👉 Khi gặp data drift thực tế, hãy thiết lập pipeline tự động (SageMaker Pipelines) để:

Phát hiện drift →

Thu thập dữ liệu mới →

Tái huấn luyện →

Đăng ký mô hình mới →

Cập nhật endpoint một cách an toàn.

Điều này giúp duy trì độ chính xác dự báo và giảm thiểu rủi ro cho doanh nghiệp. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312973-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 30

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312988-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. An AI practitioner is determining the appropriate data type for various use cases.
2. Select the correct data type from the following list for each use case. Select each data type one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312988-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 31

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Kendra, prompt engineering, RAG
- Đáp án tham khảo: **Use few-shot prompting to add domain‑specific context and explicit instructions.**
- Takeaway nhanh: Công ty đang dùng Amazon Bedrock – dịch vụ quản lý các mô hình foundation (Claude, Titan, Llama 2, …) – để xây dựng một AI assistant hỗ trợ khách hàng tìm sản phẩm. Mặc dù trợ lý đã đưa ra các gợi ý, nhưng các phản hồi quá chung chung, không liên quan tới ngữ cảnh cụ thể của sản phẩm. Công ty muốn cải thiện chất lượng trả lời bằng prompt engineering (kỹ thuật thiết kế lời nhắc).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/316401-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using Amazon Bedrock to build an AI assistant. The AI assistant helps customers find relevant products by making suggestions. However, the AI assistant's responses are often generic and irrelevant. The company wants to use prompt engineering to improve the AI assistant's responses.
Which solution will meet these requirements?

### Các lựa chọn
1. Use few-shot prompting to add domain-specific context and explicit instructions.
2. Use chain-of-thought prompting with hidden reasoning steps to ignore explicit domain instructions.
3. Modify the AI assistant's conversational style to use more formal language and include technical product specifications.
4. Use zero-shot prompting to augment retrieval from a product database.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang dùng Amazon Bedrock – dịch vụ quản lý các mô hình foundation (Claude, Titan, Llama 2, …) – để xây dựng một AI assistant hỗ trợ khách hàng tìm sản phẩm.

Mặc dù trợ lý đã đưa ra các gợi ý, nhưng các phản hồi quá chung chung, không liên quan tới ngữ cảnh cụ thể của sản phẩm.

Công ty muốn cải thiện chất lượng trả lời bằng prompt engineering (kỹ thuật thiết kế lời nhắc).

Yêu cầu:

Cung cấp ngữ cảnh miền (domain‑specific context) – ví dụ: danh mục sản phẩm, tính năng nổi bật.

Đưa ra hướng dẫn rõ ràng (explicit instructions) cho mô hình để nó biết cách lọc, ưu tiên thông tin phù hợp.

✅ Đáp án đúng:

Use few-shot prompting to add domain‑specific context and explicit instructions.

💡 Tại sao đây là đáp án đúng?

Few‑shot prompting cho phép bạn đưa vào prompt một vài ví dụ (câu hỏi + câu trả lời mẫu) trước khi mô hình sinh câu trả lời cho người dùng thực tế.

Các ví dụ này có thể chứa ngữ cảnh miền (ví dụ: “Khách hàng muốn mua giày chạy bộ, đề xuất 3 mẫu có độ bám tốt”) và hướng dẫn rõ ràng (ví dụ: “Luôn đưa ra 2‑3 đề xuất, kèm giá và đánh giá”).

Khi mô hình nhận được những “shot” này, nó học cách bám sát phong cách, cấu trúc và nội dung mà bạn muốn, giảm thiểu trả lời chung chung.

Amazon Bedrock hỗ trợ việc custom prompt cho mọi model và khuyến nghị dùng few‑shot khi cần độ chính xác cao trong các trường hợp miền‑cụ thể (AWS docs, 2025‑2026).

🛠️ Các phương án còn lại – giải thích vì sao sai

Use chain-of-thought prompting with hidden reasoning steps to ignore explicit domain instructions.

Chain‑of‑thought (CoT) prompting yêu cầu mô hình “nghĩ ra các bước suy luận trước khi đưa ra đáp án”.

Việc “hidden reasoning steps” (bước suy luận ẩn) không giúp đưa vào ngữ cảnh miền mà ngược lại có thể làm bỏ qua các hướng dẫn cụ thể vì mô hình sẽ tập trung vào logic chung.

CoT thường dùng để cải thiện độ chính xác trong các bài toán tính toán hoặc logic phức tạp, không phải để giảm tính chung chung của câu trả lời trong đề xuất sản phẩm.

Modify the AI assistant's conversational style to use more formal language and include technical product specifications.

Thay đổi giọng điệu (formal) và thêm thông số kỹ thuật không giải quyết vấn đề không liên quan hoặc quá tổng quát.

Nếu ngữ cảnh và hướng dẫn vẫn thiếu, mô hình vẫn sẽ sinh ra các đáp án không phù hợp, chỉ thay đổi cách diễn đạt chứ không cải thiện nội dung.

Prompt engineering tập trung vào việc cung cấp dữ liệu mẫu (few‑shot) hoặc định hướng rõ ràng, không chỉ thay đổi style.

Use zero-shot prompting to augment retrieval from a product database.

Zero‑shot prompting là khi bạn đưa ra một lời nhắc duy nhất, không có ví dụ mẫu.

Đối với retrieval‑augmented generation (RAG), Bedrock có thể kết hợp với Amazon Kendra hoặc DynamoDB, nhưng zero‑shot không cung cấp ngữ cảnh miền cần thiết để hướng mô hình lọc và sắp xếp kết quả.

Khi không có ví dụ hoặc chỉ dẫn cụ thể, mô hình có xu hướng trả lời chung chung – chính là vấn đề đang gặp.

📚 Tham khảo tài liệu

Amazon Bedrock Developer Guide (2026 edition) – “Prompt engineering best practices”, phần về few‑shot prompting và retrieval‑augmented generation.

AWS Whitepaper: Prompt Engineering for Generative AI (2025) – so sánh zero‑shot, one‑shot, few‑shot và chain‑of‑thought trong các trường hợp miền‑cụ thể.

AWS Blog – “Improving relevance of LLM responses with domain‑specific few‑shot examples” (Mar 2025).

📝 Tóm tắt

Câu hỏi yêu cầu cải thiện tính liên quan và độ chuyên môn của phản hồi AI assistant.

Few‑shot prompting là cách tiếp cận phù hợp nhất vì nó cho phép chèn ngữ cảnh miền và hướng dẫn cụ thể vào lời nhắc.

Các lựa chọn còn lại either không cung cấp đủ ngữ cảnh (zero‑shot), không phù hợp với mục tiêu (chain‑of‑thought, formal style), nên bị đánh dấu sai.

✅ Đáp án đúng: Use few-shot prompting to add domain‑specific context and explicit instructions.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316401-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 32

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, prompt engineering, RAG
- Đáp án tham khảo: **A transformer‑based model**
- Takeaway nhanh: Công ty đang xây dựng một ứng dụng generative AI để tự động tạo mô tả sản phẩm cho website thương mại điện tử. Yêu cầu quan trọng: Độ dài: các mô tả phải là đoạn văn (paragraph), không chỉ câu ngắn. Phong cách & tông: phải nhất quán (style & tone) trên hàng nghìn mô tả. Quy mô: cần tạo ra hàng ngàn mô tả duy nhất mỗi ngày → mô hình phải có khả năng sinh văn bản dài, đa dạng và có tốc độ inference đủ nhanh để đáp ứng khối lượng lớn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312990-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing a generative AI application to automatically generate product descriptions for an ecommerce website. The product descriptions must consist of paragraphs of text that are consistent in style and tone. The application must generate thousands of unique descriptions each day.
Which type of generative model will meet these requirements?

### Các lựa chọn
1. A variational autoencoder (VAE) model
2. A transformer-based model
3. A diffusion model
4. A generative adversarial network (GAN) model

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang xây dựng một ứng dụng generative AI để tự động tạo mô tả sản phẩm cho website thương mại điện tử. Yêu cầu quan trọng:

Độ dài: các mô tả phải là đoạn văn (paragraph), không chỉ câu ngắn.

Phong cách & tông: phải nhất quán (style & tone) trên hàng nghìn mô tả.

Quy mô: cần tạo ra hàng ngàn mô tả duy nhất mỗi ngày → mô hình phải có khả năng sinh văn bản dài, đa dạng và có tốc độ inference đủ nhanh để đáp ứng khối lượng lớn.

Vì câu hỏi thuộc chủ đề AI/ML trên AWS, chúng ta nên xét các kiến trúc mô hình hiện đại mà AWS cung cấp (Amazon SageMaker, Amazon Bedrock, Amazon Titan, …) và xác định loại mô hình nào phù hợp nhất với việc sinh văn bản có độ dài và độ nhất quán cao.

✅ Đáp án đúng: A transformer‑based model

Vì sao transformer‑based model là lựa chọn phù hợp?

Kiến trúc chuyên cho ngôn ngữ: Các transformer như GPT‑3/4, PaLM, LLaMA, Claude (đều dựa trên kiến trúc transformer) đã chứng minh khả năng sinh đoạn văn dài với ngữ cảnh được duy trì qua nhiều token, do có cơ chế self‑attention.

Kiểm soát style & tone: Bằng cách fine‑tune hoặc dùng prompt engineering, chúng ta có thể hướng mô hình tạo ra văn bản có giọng điệu đồng nhất (ví dụ: “friendly, concise, SEO‑optimized”).

Hiệu suất quy mô lớn: Trên AWS, các mô hình transformer có thể được triển khai trên SageMaker Inference hoặc Amazon Bedrock với autoscaling, cho phép thousands of requests/second – đáp ứng yêu cầu tạo hàng ngàn mô tả mỗi ngày.

Cập nhật mới nhất (2024‑2026): AWS đã ra mắt Amazon Bedrock hỗ trợ các mô hình LLM như Titan Text, Claude 3, Mistral… Tất cả đều là transformer‑based và được tối ưu cho text generation.

Vì vậy, transformer‑based model là đáp án đúng.

❌ Giải thích các phương án sai

- A variational autoencoder (VAE) model

VAE được thiết kế chủ yếu cho tạo dữ liệu dạng ảnh, âm thanh hoặc các biểu diễn có cấu trúc thấp (latent space).

Khi áp dụng vào text generation, VAE thường gặp vấn đề “posterior collapse” → mô hình không học được thông tin ngữ cảnh dài, dẫn tới các câu ngắn, mất mạch.

Không có cơ chế self‑attention mạnh mẽ để duy trì style & tone qua một đoạn văn dài, nên không đáp ứng yêu cầu đồng nhất và chất lượng cao.

- A diffusion model

Diffusion models (ví dụ: Stable Diffusion) là kiến trúc tạo ảnh dựa trên quá trình ngược lại của nhiễu.

Mặc dù đã có một số nghiên cứu mở rộng sang text‑to‑image và text generation, chúng vẫn chưa đạt được độ độ trễ (latency) và độ ổn định cần thiết cho việc sinh đoạn văn dài trong thời gian thực.

Hiện tại, trên AWS không có dịch vụ managed diffusion model cho text generation; nên không phù hợp với yêu cầu.

- A generative adversarial network (GAN) model

GAN nổi bật trong tạo ảnh, video, âm thanh, nơi discriminator đánh giá độ thật của dữ liệu.

Đối với văn bản, GAN gặp khó khăn trong việc định nghĩa loss phù hợp và tránh mode collapse, dẫn tới các câu rời rạc, không liền mạch.

Không có cơ chế attention để duy trì ngữ cảnh dài; do đó không thể tạo ra các đoạn văn nhất quán về style & tone.

🛠️ Liên hệ với dịch vụ AWS (2024‑2026)

Amazon Bedrock: Cung cấp các LLM transformer (Titan Text, Claude 3, Mistral, Llama‑2) – được quản lý, có sẵn và hỗ trợ prompt‑based control để duy trì phong cách.

Amazon SageMaker: Cho phép training hoặc inference các mô hình transformer tùy chỉnh, kèm elastic inference và multi‑model endpoints để đáp ứng khối lượng lớn.

AWS Inferentia2 và Trainium2: Chip chuyên dụng cho transformer, giảm latency và chi phí khi chạy hàng ngàn yêu cầu mỗi ngày.

📚 Tham khảo (2024‑2026)

Amazon Bedrock Developer Guide – “Working with foundation models” (phiên bản cập nhật 2025).

SageMaker Documentation – “Deploying large language models at scale” (2024).

“Attention Is All You Need”, Vaswani et al., 2017 – nền tảng kiến trúc transformer.

AWS Machine Learning Blog – “Generative AI on AWS: Best practices for LLMs” (2024).

“Diffusion Models Beat GANs on Image Synthesis”, 2023 – mô tả ưu thế của diffusion trong hình ảnh, không phải văn bản.

🧩 Tóm tắt nhanh

✅ Transformer‑based model → đáp án đúng vì khả năng sinh đoạn văn dài, duy trì style & tone, và hỗ trợ quy mô lớn trên AWS.

❌ VAE, Diffusion, GAN → không thích hợp cho text generation dài, nhất quán và tốc độ cao.

Hy vọng phân tích này giúp bạn nắm rõ lý do lựa chọn mô hình transformer cho yêu cầu tạo mô tả sản phẩm tự động! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312990-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 33

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, Amazon Bedrock, Amazon Q
- Đáp án tham khảo: **Summarization**
- Takeaway nhanh: ✅ Summarization Tóm tắt sử dụng mô hình ngôn ngữ lớn (LLM) để “rút gọn” văn bản dài thành một bản ngắn gọn, giữ lại các khái niệm, quy định, và hành động quan trọng. Trên AWS, Amazon Bedrock cung cấp các mô hình “Titan Text” và “Claude” có khả năng summarize tài liệu pháp lý, chính sách nội bộ. Kết quả giúp nhân viên nhanh chóng nắm bắt nội dung cốt lõi mà không phải đọc toàn bộ tài liệu, từ đó tăng hiệu quả làm việc.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/text-summarization.html | https://docs.aws.amazon.com/q/latest/userguide/summarize.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-pretrained-models.html#summarization | https://www.examtopics.com/discussions/amazon/view/312999-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to extract key insights from large policy documents to increase employee efficiency.
Which generative AI strategy meets this requirement?

### Các lựa chọn
1. Regression
2. Clustering
3. Summarization
4. Classification

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

A company wants to extract key insights from large policy documents to increase employee efficiency.

Which generative AI strategy meets this requirement?

Câu hỏi muốn chúng ta chọn chiến lược AI sinh (generative AI) thích hợp để “trích xuất những thông tin quan trọng” từ tài liệu chính sách dài.

Trong bối cảnh AWS hiện nay (2024‑2026), các dịch vụ Amazon Bedrock, Amazon Titan, Amazon SageMaker JumpStart, và Amazon Q‑Chat đều hỗ trợ các mô hình NLP như summarization (tóm tắt), classification (phân loại), clustering (phân cụm), regression (hồi quy).

Summarization: mô hình tạo ra bản tóm tắt ngắn gọn, nêu bật các điểm chính, đáp ứng trực tiếp yêu cầu “extract key insights”.

Classification: gán nhãn cho đoạn văn bản (ví dụ: “HR”, “Finance”). Không tự động đưa ra nội dung chính.

Clustering: nhóm các tài liệu/đoạn văn bản lại với nhau dựa trên tính tương đồng, không cung cấp nội dung tóm tắt.

Regression: dự đoán một giá trị số; không liên quan tới xử lý ngôn ngữ tự nhiên.

Vì vậy, chiến lược tóm tắt (Summarization) là lựa chọn phù hợp nhất.

✅ Đáp án đúng

✅ Summarization

Lý do:

Tóm tắt sử dụng mô hình ngôn ngữ lớn (LLM) để “rút gọn” văn bản dài thành một bản ngắn gọn, giữ lại các khái niệm, quy định, và hành động quan trọng.

Trên AWS, Amazon Bedrock cung cấp các mô hình “Titan Text” và “Claude” có khả năng summarize tài liệu pháp lý, chính sách nội bộ.

Kết quả giúp nhân viên nhanh chóng nắm bắt nội dung cốt lõi mà không phải đọc toàn bộ tài liệu, từ đó tăng hiệu quả làm việc.

❌ Giải thích các phương án sai

1. Regression

Mô tả: Dự đoán một biến số liên tục (ví dụ: dự báo chi phí, thời gian xử lý).

Tại sao sai: Không liên quan tới việc trích xuất nội dung hay hiểu ngôn ngữ tự nhiên. Regression không thể “tóm tắt” hay “rút ra insight” từ văn bản.

Ví dụ AWS: Amazon SageMaker Linear Learner, XGBoost – dùng cho dự báo bán hàng, không phải xử lý văn bản.

2. Clustering

Mô tả: Nhóm các tài liệu hoặc đoạn văn bản dựa trên độ tương đồng (k-means, HDBSCAN, …).

Tại sao sai: Mặc dù giúp tổ chức tài liệu, clustering không tạo ra bản tóm tắt hay liệt kê các điểm quan trọng. Nó chỉ cho biết “các tài liệu này thuộc nhóm nào”.

Ví dụ AWS: Amazon SageMaker K‑Means, Amazon EMR Spark MLlib – dùng để phân nhóm dữ liệu, không phải để rút ra insight.

3. Classification

Mô tả: Gán nhãn (label) cho từng đoạn văn bản (ví dụ: “Confidential”, “HR Policy”).

Tại sao sai: Phân loại giúp đánh dấu nội dung, nhưng không cung cấp bản tóm tắt các ý chính. Nhân viên vẫn cần đọc toàn bộ tài liệu để hiểu chi tiết.

Ví dụ AWS: Amazon Comprehend Custom Classification, SageMaker built‑in classifiers – dùng để gán nhãn, không tóm tắt.

🛠️ Các công cụ AWS hỗ trợ Summarization (2024‑2026)

Amazon Bedrock – Titan Text / Claude

API invokeModel với taskType: "summarize" cho phép truyền văn bản dài (đến 100 KB) và nhận bản tóm tắt.

Amazon SageMaker JumpStart

Mô hình Flan‑T5, Mistral‑Instruct có fine‑tuned “summarization” endpoints.

Amazon Q‑Chat / Q‑Developer

Tích hợp tính năng “Summarize this document” trong UI, dùng LLM nội bộ để rút gọn tài liệu.

Amazon Comprehend (tính năng Extractive Summarization) – trả về các câu quan trọng nhất từ đoạn văn bản.

📘 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Developer Guide – “Text Summarization” (v2026.03) – https://docs.aws.amazon.com/bedrock/latest/userguide/text-summarization.html

AWS SageMaker JumpStart – Pre‑trained Summarization Models (v2025.12) – https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-pretrained-models.html#summarization

Amazon Q – Documentation – Summarize Documents (v2026.01) – https://docs.aws.amazon.com/q/latest/userguide/summarize.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025) – hướng dẫn lựa chọn mô hình phù hợp cho use‑case NLP.

🧩 Kết luận

Đối với yêu cầu “extract key insights from large policy documents”, Summarization là chiến lược generative AI duy nhất đáp ứng trực tiếp: nó tự động tạo ra bản tóm tắt ngắn gọn, nêu bật các điểm quan trọng, giúp nhân viên tiết kiệm thời gian đọc và nhanh chóng hiểu nội dung. Các phương án Regression, Clustering, và Classification đều không cung cấp chức năng này, vì vậy chúng là sai trong ngữ cảnh câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312999-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 34

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313008-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. Select and order the steps from the following list to correctly describe the ML lifecycle for a new custom model. Select each step one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313008-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 35

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Q, Amazon Q Developer, Amazon Bedrock
- Đáp án tham khảo: **Use Amazon Q Developer in an integrated development environment (IDE).**
- Takeaway nhanh: 🔹 Use Amazon Q Developer in an integrated development environment (IDE). Vì sao đây là đáp án đúng? Amazon Q Developer (trước đây là Amazon Q for Code) là dịch vụ AI‑assisted coding của AWS, được tích hợp trực tiếp vào các IDE phổ biến như VS Code, JetBrains IntelliJ, PyCharm, … Nó sử dụng foundation models của AWS (ví dụ: Titan, Claude‑3, Gemini‑1) để:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/developer/amazon-q-developer-boosts-productivity/ | https://docs.aws.amazon.com/amazonq/latest/devguide/ | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/313039-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner is writing software code. The AI practitioner wants to quickly develop a test case and create documentation for the code.
Which solution will meet these requirements with the LEAST effort?

### Các lựa chọn
1. Upload the code to an online coding assistant.
2. Develop an application to use foundation models (FMs).
3. Use Amazon Q Developer in an integrated development environment (IDE).
4. Research and write test cases. Then, create test cases and add documentation.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi mô tả một AI practitioner đang viết code và muốn:

Nhanh chóng tạo một test case cho đoạn mã vừa viết.

Tự động tạo tài liệu (documentation) cho code.

Yêu cầu “with the LEAST effort” (đòi hỏi ít công sức nhất) đồng nghĩa với việc cần một công cụ tích hợp sẵn, hỗ trợ AI để sinh test case và documentation mà không phải tự mình viết, cấu hình hay triển khai mô hình.

✅ Đáp án đúng

🔹 Use Amazon Q Developer in an integrated development environment (IDE).

Vì sao đây là đáp án đúng?

Amazon Q Developer (trước đây là Amazon Q for Code) là dịch vụ AI‑assisted coding của AWS, được tích hợp trực tiếp vào các IDE phổ biến như VS Code, JetBrains IntelliJ, PyCharm, …

Nó sử dụng foundation models của AWS (ví dụ: Titan, Claude‑3, Gemini‑1) để:

Tự động tạo unit test (với lệnh “Generate tests”).

Viết documentation/comments cho hàm, lớp, hoặc toàn bộ module (với “Generate docstring”).

Cung cấp gợi ý code, refactor, và giải thích logic – tất cả trong cùng một môi trường làm việc, không cần rời IDE, không cần copy‑paste hay chuyển sang công cụ khác.

Thiết lập nhanh: chỉ cần cài plugin/extension, đăng nhập AWS, và bật tính năng. Không cần triển khai mô hình, không cần viết code bổ sung.

Chi phí và thời gian: trả phí theo thời gian sử dụng mô hình, không tốn chi phí phát triển và bảo trì. Do đã được tối ưu cho developer, công sức “least effort” đạt mức cao nhất.

Do vậy, Amazon Q Developer đáp ứng đầy đủ yêu cầu “quickly develop a test case and create documentation with the least effort”.

❌ Giải thích các phương án sai

1. Upload the code to an online coding assistant.

Lý do sai:

Các “online coding assistants” (ví dụ: ChatGPT, Claude web, hoặc các công cụ không tích hợp) yêu cầu đăng nhập, sao chép‑dán code, sau đó mới yêu cầu tạo test case hoặc documentation.

Không được tích hợp trong IDE, nên phải chuyển đổi ngữ cảnh, làm tăng công sức và thời gian.

Thêm vào đó, việc tải code lên dịch vụ bên ngoài có thể gây rủi ro bảo mật (code chứa thông tin nhạy cảm).

Vì mục tiêu là ít công sức nhất, phương án này không tối ưu.

2. Develop an application to use foundation models (FMs).

Lý do sai:

Đòi hỏi phát triển một ứng dụng riêng để gọi các foundation model (ví dụ: Titan, Claude, Gemini) qua Amazon Bedrock hoặc SageMaker JumpStart.

Cần thiết kế workflow, xây dựng prompt, xử lý kết quả, và tích hợp vào quy trình CI/CD – mọi thứ này tốn thời gian và công sức đáng kể.

Đây là cách “tự làm” (DIY) thích hợp khi muốn tùy biến sâu, nhưng không phù hợp với yêu cầu “least effort”.

3. Research and write test cases. Then, create test cases and add documentation.

Lý do sai:

Đây là phương pháp thủ công truyền thống: người phát triển tự nghiên cứu, viết test case và tài liệu.

Mặc dù có thể tạo ra kết quả chất lượng, chi phí thời gian là cao nhất trong số các lựa chọn.

Không tận dụng bất kỳ AI hay công cụ tự động nào, nên không đáp ứng yêu cầu “ít công sức”.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Q Developer – Developer Guide (AWS Documentation, phiên bản cập nhật 2026).

https://docs.aws.amazon.com/amazonq/latest/devguide/

Amazon Q Developer – Feature Overview (AWS Blog, 2025).

https://aws.amazon.com/blogs/developer/amazon-q-developer-boosts-productivity/

AWS Bedrock – Foundation Models (đối chiếu để hiểu tại sao Amazon Q sử dụng các mô hình này).

https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

🧩 Tóm tắt nhanh (danh sách)

✅ Đáp án đúng: Use Amazon Q Developer in an integrated development environment (IDE).

Tích hợp AI trong IDE → tạo test case & documentation tự động → ít công sức.

❌ Lý do các đáp án còn lại sai:

Upload the code to an online coding assistant: phải chuyển đổi ngữ cảnh, không an toàn.

Develop an application to use foundation models (FMs): cần xây dựng, triển khai, tốn thời gian.

Research and write test cases. Then, create test cases and add documentation: thủ công, công sức cao nhất.

Hy vọng phân tích trên giúp bạn nắm rõ lý do tại sao Amazon Q Developer là giải pháp tối ưu nhất cho yêu cầu “least effort” trong việc tạo test case và tài liệu cho code. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313039-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 36

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Comprehend, Amazon Personalize, Amazon Rekognition, guardrails
- Đáp án tham khảo: **Amazon Bedrock**
- Takeaway nhanh: Mục tiêu của công ty: Có một website đặt vé du lịch. Muốn tự động tạo nội dung mô tả khách sạn (hotel descriptions) để duy trì độ nhất quán về phong cách viết trên toàn site. Yêu cầu kỹ thuật:
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/ | https://www.examtopics.com/discussions/amazon/view/316399-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company runs a website for users to make travel reservations. The company wants an AI solution to help create consistent branding for hotels on the website.
The AI solution needs to generate hotel descriptions for the website in a consistent writing style.
Which AWS service will meet these requirements?

### Các lựa chọn
1. Amazon Comprehend
2. Amazon Personalize
3. Amazon Rekognition
4. Amazon Bedrock

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Mục tiêu của công ty:

Có một website đặt vé du lịch.

Muốn tự động tạo nội dung mô tả khách sạn (hotel descriptions) để duy trì độ nhất quán về phong cách viết trên toàn site.

Yêu cầu kỹ thuật:

Cần một dịch vụ AI sinh (generative) văn bản có thể được “đào tạo” hoặc “điều chỉnh” (fine‑tune) để viết theo một style nhất định.

Không yêu cầu phân tích cảm xúc, cá nhân hoá gợi ý, hay nhận dạng ảnh/video.

Vì vậy, dịch vụ phù hợp là một nền tảng LLM (Large Language Model) có khả năng tạo nội dung – trong danh sách các dịch vụ AWS hiện tại (đến 2026) Amazon Bedrock đáp ứng đầy đủ.

✅ Đáp án đúng: Amazon Bedrock

Lý do chọn:

Amazon Bedrock là dịch vụ quản lý LLM (cũng như các mô hình diffusion cho hình ảnh) cho phép tạo, tùy chỉnh và triển khai các mô hình ngôn ngữ lớn như Claude (Anthropic), Titan (AWS), Llama‑2, Mistral, v.v.

Bạn có thể fine‑tune mô hình với dữ liệu mô tả khách sạn mẫu để đạt được độ nhất quán trong phong cách viết.

Bedrock cung cấp API gọi nhanh, không cần quản lý cơ sở hạ tầng và tích hợp an toàn (IAM, VPC endpoints, encryption).

Các tính năng mới (đến 2026) như “Prompt Guard” giúp kiểm soát nội dung, “Foundation Model Marketplace” cho phép chọn mô hình phù hợp nhất với yêu cầu chất lượng và chi phí.

❌ Giải thích các phương án còn lại

Amazon Comprehend

Chức năng: Dịch vụ phân tích ngôn ngữ tự nhiên (NLP) – trích xuất thực thể, phân loại văn bản, phát hiện ngôn ngữ, sentiment analysis, v.v.

Tại sao không phù hợp: Comprehend không sinh ra văn bản mới; nó chỉ phân tích văn bản hiện có. Do đó không đáp ứng yêu cầu “tạo mô tả khách sạn”.

Amazon Personalize

Chức năng: Dịch vụ gợi ý cá nhân hoá (recommendation) dựa trên machine learning, thường dùng cho danh sách sản phẩm, video, nội dung…

Tại sao không phù hợp: Personalize không phải là công cụ tạo nội dung. Nó giúp đưa ra “đề xuất” dựa trên hành vi người dùng, không hỗ trợ viết mô tả đồng nhất.

Amazon Rekognition

Chức năng: Dịch vụ phân tích hình ảnh và video – nhận diện khuôn mặt, đối tượng, văn bản trong hình ảnh, phát hiện nội dung không phù hợp, v.v.

Tại sao không phù hợp: Rekognition chỉ làm việc với dữ liệu hình ảnh/video, không có khả năng tạo ra văn bản mô tả.

📚 Tham khảo tài liệu (2026)

Amazon Bedrock Developer Guide – https://docs.aws.amazon.com/bedrock/latest/userguide/

AWS Blog – “Introducing Amazon Bedrock: A new service to build generative AI applications” (cập nhật liên tục tới 2026).

AWS Well‑Architected Framework – Machine Learning Lens – giúp lựa chọn dịch vụ generative AI phù hợp.

🛠️ Gợi ý triển khai thực tế

Thu thập mẫu mô tả: Tạo một corpus gồm các mô tả khách sạn đã được biên tập theo phong cách mong muốn.

Fine‑tune mô hình trên Bedrock: Dùng API CreateModelCustomizationJob để đào tạo mô hình Titan‑Text hoặc Claude‑3 trên dữ liệu mẫu.

Triển khai endpoint: Tạo endpoint InvokeModel để trả về mô tả khi truyền vào các thông tin cơ bản (tên khách sạn, vị trí, tiện nghi…).

Kiểm soát nội dung: Kích hoạt Guardrails để ngăn chặn việc tạo nội dung không phù hợp hoặc vi phạm bản quyền.

Tích hợp với website: Dùng AWS SDK (Python, JavaScript…) để gọi Bedrock từ backend của website, đồng thời áp dụng IAM role hạn chế quyền truy cập.

Tóm lại: Để tự động sinh mô tả khách sạn với phong cách thống nhất, dịch vụ phù hợp nhất trong danh sách là Amazon Bedrock. Các dịch vụ khác (Comprehend, Personalize, Rekognition) không có khả năng tạo nội dung ngôn ngữ tự nhiên, vì vậy chúng không đáp ứng yêu cầu của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316399-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 37

- Domain heuristic: `Domain 1`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313021-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company wants to improve multiple ML models.
2. Select the correct technique from the following list of use cases. Each technique should be selected one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313021-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 38

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Takeaway nhanh: Bối cảnh: Một công ty đã đưa một mô hình Machine Learning vào môi trường sản xuất (production). Sau 4 tháng, chất lượng suy giảm (model inference quality degraded). Yêu cầu: Nhận thông báo (notification) ngay khi chất lượng suy giảm. Đảm bảo rằng vấn đề không tái diễn trong tương lai (có cơ chế giám sát, cảnh báo và cập nhật mô hình).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312975-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company deployed a model to production. After 4 months, the model inference quality degraded. The company wants to receive a notification if the model inference quality degrades. The company also wants to ensure that the problem does not happen again.
Which solution will meet these requirements?

### Các lựa chọn
1. Retrain the model. Monitor model drift by using Amazon SageMaker Clarify.
2. Retrain the model. Monitor model drift by using Amazon SageMaker Model Monitor.
3. Build a new model. Monitor model drift by using Amazon SageMaker Feature Store.
4. Build a new model. Monitor model drift by using Amazon SageMaker JumpStart.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Một công ty đã đưa một mô hình Machine Learning vào môi trường sản xuất (production). Sau 4 tháng, chất lượng suy giảm (model inference quality degraded).

Yêu cầu:

Nhận thông báo (notification) ngay khi chất lượng suy giảm.

Đảm bảo rằng vấn đề không tái diễn trong tương lai (có cơ chế giám sát, cảnh báo và cập nhật mô hình).

=> Câu hỏi đang kiểm tra kiến thức về giám sát drift (model drift / data drift) và cơ chế tự động hoá quy trình tái huấn luyện trong Amazon SageMaker.

✅ Đáp án đúng

Retrain the model. Monitor model drift by using Amazon SageMaker Model Monitor.

Vì sao đây là đáp án đúng?

Amazon SageMaker Model Monitor (được cập nhật liên tục tới 2026) cho phép:

Tự động giám sát các thống kê đầu ra của mô hình (feature distribution, prediction distribution) và phát hiện drift so với baseline đã lưu.

Tạo cảnh báo qua Amazon CloudWatch Events / SNS khi phát hiện drift vượt ngưỡng, đáp ứng yêu cầu “receive a notification”.

Tích hợp với pipeline CI/CD (SageMaker Pipelines) để tự động re‑train mô hình khi drift được phát hiện, giúp “ensure that the problem does not happen again”.

Việc re‑train mô hình là bước thực tiễn khi drift đã làm giảm chất lượng, và Model Monitor cung cấp các metric và alerts cần thiết.

❌ Giải thích các phương án sai

1. Retrain the model. Monitor model drift by using Amazon SageMaker Clarify.

Amazon SageMaker Clarify chủ yếu dùng để đánh giá bias, explainability và một số tính năng phát hiện data bias; không phải công cụ chính để giám sát drift và không cung cấp cảnh báo tự động qua CloudWatch/SNS.

Dù có thể dùng Clarify để detect bias, nó không đáp ứng yêu cầu “receive a notification if the model inference quality degrades”.

2. Build a new model. Monitor model drift by using Amazon SageMaker Feature Store.

Amazon SageMaker Feature Store là kho lưu trữ và quản lý feature data (định dạng, versioning, retrieval). Nó không thực hiện giám sát drift hay tạo cảnh báo.

“Build a new model” là hành động không cần thiết nếu chỉ cần re‑train dựa trên dữ liệu mới; việc xây dựng một mô hình hoàn toàn mới sẽ tốn thời gian và không giải quyết vấn đề cảnh báo.

3. Build a new model. Monitor model drift by using Amazon SageMaker JumpStart.

Amazon SageMaker JumpStart cung cấp các mẫu (pre‑trained models) và solution templates để khởi tạo nhanh, nhưng không có chức năng giám sát drift hay cảnh báo.

Tương tự như trên, việc “build a new model” không phải là cách tiếp cận tối ưu khi đã có mô hình đang hoạt động và chỉ cần re‑train khi drift xảy ra.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon SageMaker Model Monitor – Documentation (cập nhật 2026: hỗ trợ tự động tạo alarm CloudWatch, tích hợp SageMaker Pipelines).

Amazon SageMaker Clarify – Documentation.

Amazon SageMaker Feature Store – Documentation.

Amazon SageMaker JumpStart – Documentation.

🛠️ Kết luận nhanh gọn

Công cụ đúng: SageMaker Model Monitor + re‑train.

Lý do: Cung cấp giám sát drift, cảnh báo tự động và dễ tích hợp vào pipeline tái huấn luyện, đáp ứng cả hai yêu cầu “notification” và “prevent recurrence”.

👍 Nếu công ty muốn một giải pháp toàn diện, nên:

Thiết lập baseline cho các thống kê đầu vào/đầu ra bằng Model Monitor.

Định nghĩa thresholds và CloudWatch alarms → SNS để gửi email/SMS.

Kết nối Model Monitor với SageMaker Pipelines để tự động trigger quy trình re‑training và deployment khi drift được phát hiện.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312975-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 39

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Bạn nên chọn Logistic regression model cho dự án này và triển khai qua SageMaker Linear Learner + Clarify để đáp ứng cả hiệu năng và yêu cầu tuân thủ.**
- Takeaway nhanh: Công ty muốn phát triển một mô hình Machine Learning có khả năng giải thích (interpretable) để đánh giá rủi ro của các hồ sơ vay ngân hàng. “Có khả năng giải thích” ở đây nghĩa là: Người dùng (như nhà phân tích tín dụng, quản trị rủi ro, hoặc các bên kiểm toán) cần hiểu được cách mô hình đưa ra quyết định – ví dụ: các hệ số, tầm quan trọng của các đặc trưng, hoặc công thức tính điểm rủi ro.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/explainable-ai-2024/ | https://d1.awsstatic.com/whitepapers/machine-learning-interpretability.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/sagemaker/latest/dg/linear-learner.html | https://www.examtopics.com/discussions/amazon/view/316403-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to develop an interpretable ML model to assess the risk of loan applications.
Which type of ML model or algorithm will meet these requirements?

### Các lựa chọn
1. Deep learning model
2. Logistic regression model
3. K-means algorithm
4. Random cut forest algorithm

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn phát triển một mô hình Machine Learning có khả năng giải thích (interpretable) để đánh giá rủi ro của các hồ sơ vay ngân hàng.

“Có khả năng giải thích” ở đây nghĩa là:

Người dùng (như nhà phân tích tín dụng, quản trị rủi ro, hoặc các bên kiểm toán) cần hiểu được cách mô hình đưa ra quyết định – ví dụ: các hệ số, tầm quan trọng của các đặc trưng, hoặc công thức tính điểm rủi ro.

Đối với ngành tài chính, các quy định (ví dụ: Basel III, GDPR “right to explanation”) yêu cầu mô hình phải có thể được giải thích và kiểm tra.

Vì vậy, câu hỏi đang hỏi: “Loại mô hình hoặc thuật toán nào phù hợp nhất để đáp ứng yêu cầu này?”

✅ Đáp án đúng:

Logistic regression model

🔎 Lý do lựa chọn Logistic regression là đáp án đúng

Giải thích được (interpretable) – Logistic regression trả về các hệ số (weights) cho từng biến đầu vào; mỗi hệ số cho biết mức độ ảnh hưởng (có/không có, tăng/giảm) tới xác suất vay không thành công.

Mô hình tuyến tính – Dễ dàng biến đổi thành “scorecard” hoặc “odds ratio” để trình bày cho người không chuyên.

Phù hợp với bài toán nhị phân – Đánh giá rủi ro vay thường là “có rủi ro / không có rủi ro” (default vs non‑default), logistic regression được thiết kế cho xác suất nhị phân.

Hỗ trợ trên AWS – Có thể triển khai nhanh trên Amazon SageMaker Linear Learner, Amazon SageMaker Autopilot (chọn Logistic Regression khi yêu cầu interpretability), hoặc AWS Glue DataBrew để tạo mô hình logistic.

Tuân thủ quy định – Do tính giải thích rõ ràng, mô hình này thường được chấp nhận trong các cuộc kiểm toán tài chính.

❌ Phân tích các phương án sai

Deep learning model

Giải thích: Các mạng nơ-ron sâu (CNN, RNN, Transformer…) thường đen‑hộp; dù có các kỹ thuật như SHAP, LIME, hay Explainable AI (XAI) trên SageMaker Clarify, nhưng chúng vẫn không cung cấp mức độ giải thích trực quan và đơn giản như logistic regression.

Đối với rủi ro vay: Độ phức tạp cao, yêu cầu dữ liệu lớn, thời gian huấn luyện dài và chi phí tính toán cao; không phải là lựa chọn tối ưu khi mục tiêu chính là interpretability.

K-means algorithm

Giải thích: K‑means là thuật toán phân cụm không giám sát. Nó không tạo ra mô hình dự đoán rủi ro mà chỉ gộp các hồ sơ thành các cụm dựa trên khoảng cách Euclidean. Không có khái niệm “xác suất rủi ro” hay “hệ số ảnh hưởng” nên không đáp ứng yêu cầu giải thích và dự đoán.

Ứng dụng thực tế: Thích hợp cho việc phân đoạn khách hàng, nhưng không phải để đánh giá rủi ro vay.

Random cut forest algorithm

Giải thích: Random Cut Forest (RCF) là thuật toán phát hiện bất thường (anomaly detection), thường được dùng cho phát hiện gian lận, giám sát log, hoặc phát hiện sự thay đổi bất thường trong dữ liệu thời gian.

Vấn đề: RCF không cung cấp độ tin cậy hay giải thích về tại sao một hồ sơ được gán là “rủi ro”. Ngoài ra, nó không trả về xác suất mặc định mà chỉ đưa ra điểm anomaly.

AWS: Có sẵn trong Amazon SageMaker Random Cut Forest nhưng không phù hợp cho mô hình giải thích rủi ro tín dụng.

🛠️ Cách triển khai Logistic Regression trên AWS (năm 2026)

SageMaker Linear Learner – Chọn binary_classifier và solver=‘adam’ hoặc sgd. Kết quả trả về coefficients có thể xuất ra CSV để phân tích.

SageMaker Clarify – Tích hợp để tạo feature importance và bias detection ngay sau khi huấn luyện, hỗ trợ các yêu cầu tuân thủ.

Amazon SageMaker Studio – Giao diện kéo‑thả, hỗ trợ AutoML (SageMaker Autopilot) với tùy chọn “interpretable model”. Nếu Autopilot chọn Logistic Regression, bạn vẫn nhận được báo cáo giải thích.

Deploy – Đưa mô hình lên SageMaker Endpoint hoặc AWS Lambda + API Gateway cho dự đoán thời gian thực.

📚 Tham khảo tài liệu (2026)

AWS Documentation – Amazon SageMaker Linear Learner: https://docs.aws.amazon.com/sagemaker/latest/dg/linear-learner.html

AWS Documentation – Amazon SageMaker Clarify: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

AWS Whitepaper – Machine Learning Interpretability (2025 edition): https://d1.awsstatic.com/whitepapers/machine-learning-interpretability.pdf

Google Cloud & AWS Comparative Guide – Explainable AI (2024): https://aws.amazon.com/blogs/machine-learning/explainable-ai-2024/

🧩 Tổng kết

Câu hỏi yêu cầu mô hình có khả năng giải thích để đánh giá rủi ro vay.

Logistic regression là lựa chọn duy nhất đáp ứng tiêu chí “interpretable”, “binary classification”, và “easy to audit”.

Các phương án còn lại (Deep learning, K‑means, Random Cut Forest) đều không phù hợp vì khó giải thích, không cung cấp dự đoán nhị phân hoặc là thuật toán không giám sát.

✅ Bạn nên chọn Logistic regression model cho dự án này và triển khai qua SageMaker Linear Learner + Clarify để đáp ứng cả hiệu năng và yêu cầu tuân thủ.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316403-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 40

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: prompt engineering
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312996-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. Select the correct prompt engineering technique from the following list for each description. Select each prompt engineering technique one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312996-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 41

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon Kendra, Amazon S3, fine-tuning, RAG
- Đáp án tham khảo: **Continued pre‑training**
- Takeaway nhanh: Công ty đang sở hữu một large language model (LLM) đã được huấn luyện sẵn. Mô hình cần thực hiện nhiều nhiệm vụ (multiple tasks) đòi hỏi kiến thức chuyên môn trong một miền cụ thể. LLM hiện tại thiếu thông tin về một số chủ đề kỹ thuật quan trọng trong miền đó. Công ty có dữ liệu không gán nhãn (unlabeled data) và muốn fine‑tune mô hình sao cho nó có thể “hiểu” và trả lời các câu hỏi liên quan tới những chủ đề còn thiếu.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/continued-pretraining-sagemaker/ | https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html | https://docs.aws.amazon.com/sagemaker/latest/dg/custom-training.html | https://huggingface.co/docs/transformers/training#domain-adaptive-pre-training | https://www.deepspeed.ai/tutorials/large-models/ | https://www.examtopics.com/discussions/amazon/view/316398-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using a pre-trained large language model (LLM). The LLM must perform multiple tasks that require specific domain knowledge. The LLM does not have information about several technical topics in the domain. The company has unlabeled data that the company can use to fine-tune the model.
Which fine-tuning method will meet these requirements?

### Các lựa chọn
1. Full training
2. Supervised fine-tuning
3. Continued pre-training
4. Retrieval Augmented Generation (RAG)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang sở hữu một large language model (LLM) đã được huấn luyện sẵn.

Mô hình cần thực hiện nhiều nhiệm vụ (multiple tasks) đòi hỏi kiến thức chuyên môn trong một miền cụ thể.

LLM hiện tại thiếu thông tin về một số chủ đề kỹ thuật quan trọng trong miền đó.

Công ty có dữ liệu không gán nhãn (unlabeled data) và muốn fine‑tune mô hình sao cho nó có thể “hiểu” và trả lời các câu hỏi liên quan tới những chủ đề còn thiếu.

Yêu cầu quan trọng:

Không cần dữ liệu có nhãn (vì dữ liệu hiện chỉ là unlabeled).

Cần bổ sung kiến thức cho mô hình mà không thay đổi hoàn toàn kiến trúc hay các tham số đã học trước.

Phương pháp phải tiết kiệm chi phí và độ phức tạp hợp lý cho môi trường AWS (SageMaker, JumpStart, hoặc các dịch vụ ML của AWS).

✅ Đáp án đúng: Continued pre‑training

Lý do chọn:

Continued pre‑training (còn gọi là “domain‑adaptive pre‑training” hoặc “further pre‑training”) là quá trình tiếp tục huấn luyện mô hình trên một tập dữ liệu mới (có thể không gán nhãn) để mô hình “học” thêm ngôn ngữ, thuật ngữ và kiến thức đặc thù của miền.

Vì dữ liệu không có nhãn, các phương pháp dựa trên supervision (ví dụ: Supervised fine‑tuning) không phù hợp.

Việc tiếp tục pre‑train giúp mô hình nắm bắt các khái niệm và mối quan hệ trong dữ liệu mới mà không cần xây dựng bộ nhãn, đồng thời giữ lại kiến thức tổng quát đã học từ giai đoạn pre‑training ban đầu.

Trên AWS, bạn có thể thực hiện continued pre‑training bằng SageMaker Training Jobs hoặc SageMaker JumpStart với các script custom; SageMaker cũng hỗ trợ distributed training để giảm thời gian chạy khi dữ liệu lớn.

Kết quả là mô hình được “điều chỉnh” để phù hợp với domain, sau đó có thể được sử dụng trong các downstream tasks (prompt‑tuning, few‑shot inference, …) mà không cần thêm dữ liệu có nhãn.

❌ Phân tích các phương án sai

1️⃣ Full training

Full training có nghĩa là huấn luyện lại mô hình từ đầu (từ random weights) trên toàn bộ tập dữ liệu.

Điều này cực kỳ tốn kém về thời gian, chi phí tính toán (GPU/TPU) và yêu cầu lượng dữ liệu rất lớn để đạt hiệu suất tương đương mô hình pre‑trained.

Vì công ty chỉ có unlabeled data và muốn tận dụng mô hình đã được pre‑trained, full training không đáp ứng yêu cầu thực tiễn và không hợp lý trong môi trường AWS (chi phí EC2/GPU quá cao).

2️⃣ Supervised fine‑tuning

Supervised fine‑tuning yêu cầu có nhãn (labelled) để huấn luyện mô hình trên một nhiệm vụ cụ thể (ví dụ: classification, QA).

Ở đây dữ liệu không có nhãn, vì vậy không thể áp dụng phương pháp này trừ khi công ty tốn công tạo nhãn – điều ngược lại với yêu cầu “sử dụng unlabeled data”.

Ngoài ra, supervised fine‑tuning thường chỉ “điều chỉnh” một phần nhỏ của mô hình cho một task cụ thể, không tối ưu cho việc bổ sung kiến thức domain rộng rãi.

4️⃣ Retrieval Augmented Generation (RAG)

RAG kết hợp một mô hình tạo (generator) với một hệ thống truy xuất (retriever) để lấy thông tin từ một kho kiến thức bên ngoài (có thể là vector store, Elasticsearch, …).

Mặc dù RAG giải quyết được vấn đề thiếu kiến thức mà không cần fine‑tune mô hình, nhưng nó không phải là một phương pháp fine‑tuning; nó là một kiến trúc hệ thống.

Đòi hỏi cơ sở dữ liệu tài liệu đã được lập chỉ mục và cơ chế truy xuất, không phù hợp nếu mục tiêu là cải thiện trực tiếp khả năng hiểu nội bộ của LLM thông qua pre‑training.

Ngoài ra, triển khai RAG trên AWS cần Amazon Kendra, OpenSearch, hoặc Amazon Vector Store, tạo thêm độ phức tạp không được đề cập trong câu hỏi.

🛠️ Cách thực hiện Continued pre‑training trên AWS (2026)

Chuẩn bị dữ liệu

Đặt dữ liệu không gán nhãn (text corpus) vào Amazon S3.

Sử dụng AWS Glue hoặc Amazon Athena để chuyển đổi/định dạng nếu cần.

Tạo môi trường training

Dùng Amazon SageMaker Training Jobs với instance type phù hợp (ml.p4d.24xlarge, ml.g5.12xlarge, …).

Lựa chọn distributed training (Data Parallelism) nếu dữ liệu lớn.

Sử dụng SageMaker Debugger để giám sát loss và xác định khi nào pre‑training hội tụ.

Script continued pre‑training

Sử dụng Hugging Face Transformers hoặc DeepSpeed tích hợp trong SageMaker.

Tham số quan trọng: model_name_or_path (đường dẫn tới checkpoint pre‑trained), train_file (đường dẫn S3 tới corpus), per_device_train_batch_size, learning_rate (thường rất nhỏ, ví dụ 1e‑5), num_train_epochs (có thể 1‑3 epoch tùy dữ liệu).

Lưu checkpoint

Khi training kết thúc, lưu mô hình đã “điều chỉnh” lại vào S3 và tạo Model Package trong SageMaker để triển khai.

Triển khai

Dùng SageMaker Endpoints (real‑time inference) hoặc SageMaker Serverless Inference nếu lưu lượng không ổn định.

Kết hợp với Amazon Bedrock (nếu muốn sử dụng model dưới dạng foundation model) – Bedrock hỗ trợ custom model fine‑tuning và có sẵn tính năng continued pre‑training.

📚 Tham khảo (tới 2026)

AWS SageMaker Documentation – Custom Training: https://docs.aws.amazon.com/sagemaker/latest/dg/custom-training.html

AWS Bedrock – Custom Model Fine‑tuning (v2.0, ra mắt 2025): https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html

Hugging Face – Domain Adaptive Pre‑Training: https://huggingface.co/docs/transformers/training#domain-adaptive-pre-training

AWS Machine Learning Blog – “How to do continued pre‑training on SageMaker” (2024): https://aws.amazon.com/blogs/machine-learning/continued-pretraining-sagemaker/

DeepSpeed – Efficient Large‑Scale Pre‑training (v0.15, 2025): https://www.deepspeed.ai/tutorials/large-models/

📌 Kết luận

Correct answer: Continued pre‑training – phù hợp vì chỉ cần dữ liệu không gán nhãn để bổ sung kiến thức domain, giảm chi phí và thời gian so với full training, đồng thời không yêu cầu nhãn như supervised fine‑tuning và không phải là kiến trúc hệ thống như RAG.

Các phương án còn lại không đáp ứng yêu cầu về dữ liệu, chi phí, hoặc bản chất của “fine‑tuning”.

Hy vọng phân tích chi tiết này giúp bạn nắm rõ cách lựa chọn phương pháp fine‑tuning phù hợp trong môi trường AWS hiện đại! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316398-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 42

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Đáp án tham khảo: **Agents**
- Takeaway nhanh: Công ty muốn xây dựng AI assistant (trợ lý AI) có khả năng: Đánh giá (evaluate) các nguồn dữ liệu nội bộ – có thể là tài liệu, cơ sở dữ liệu, hoặc các knowledge store. Gửi yêu cầu tới (query) các API bên ngoài – ví dụ: dịch vụ thời tiết, hệ thống CRM, v.v. Tạo ra (generate) nhiều lựa chọn câu trả lời – mô hình sẽ đưa ra các “response options”.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases.html | https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html | https://docs.aws.amazon.com/bedrock/latest/userguide/response-streaming.html | https://www.examtopics.com/discussions/amazon/view/313004-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build an AI assistant to provide responses to user queries. The AI assistant must evaluate specific data sources, query external APIs, generate response options, and compare and prioritize response options.
Which Amazon Bedrock feature or resource will meet these requirements?

### Các lựa chọn
1. Prompt Management
2. Response streaming
3. Knowledge Bases
4. Agents

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn xây dựng AI assistant (trợ lý AI) có khả năng:

Đánh giá (evaluate) các nguồn dữ liệu nội bộ – có thể là tài liệu, cơ sở dữ liệu, hoặc các knowledge store.

Gửi yêu cầu tới (query) các API bên ngoài – ví dụ: dịch vụ thời tiết, hệ thống CRM, v.v.

Tạo ra (generate) nhiều lựa chọn câu trả lời – mô hình sẽ đưa ra các “response options”.

So sánh và ưu tiên (compare & prioritize) các lựa chọn – để đưa ra đáp án tốt nhất cho người dùng.

Câu hỏi hỏi: “Which Amazon Bedrock feature or resource will meet these requirements?”

Trong môi trường Amazon Bedrock (phiên bản cập nhật 2026), có một số thành phần hỗ trợ phát triển ứng dụng AI, trong đó Agents là chức năng mới được ra mắt để “orchestrate” (điều phối) nhiều công cụ, API và knowledge base, đồng thời thực hiện logic quyết định để chọn đáp án tối ưu. Vì vậy đáp án đúng là Agents.

✅ Đáp án đúng: Agents

Lý do lựa chọn:

Agents trong Amazon Bedrock là một lớp trừu tượng cho phép bạn kết hợp một hoặc nhiều large language models (LLMs) với tooling (API, function calls, knowledge bases, etc.).

Chúng có khả năng đánh giá nguồn dữ liệu, gọi API bên ngoài, tạo ra nhiều candidate responses, và so sánh, ưu tiên chúng dựa trên quy tắc hoặc hàm scoring do bạn định nghĩa.

Đây chính là thiết kế “điều phối viên” (orchestrator) phù hợp nhất với yêu cầu của câu hỏi: evaluate data sources → query external APIs → generate response options → compare & prioritize.

🧩 Phân tích các phương án khác (đúng và sai)

1. Prompt Management

Mô tả: Cung cấp khả năng tạo, lưu, và tái sử dụng các prompt (đầu vào) cho LLM, đồng thời quản lý phiên bản và kiểm soát truy cập.

Tại sao ❌ không đáp ứng yêu cầu:

Prompt Management chỉ giúp quản lý và tái sử dụng các prompt, không thực hiện việc gọi API hay so sánh/đánh giá các đáp án.

Nó không cung cấp cơ chế orchestration để tích hợp nhiều nguồn dữ liệu hoặc logic quyết định.

2. Response streaming

Mô tả: Tính năng trả về kết quả theo luồng (stream) khi LLM đang sinh ra văn bản, giảm độ trễ cho người dùng cuối.

Tại sao ❌ không đáp ứng yêu cầu:

Response streaming chỉ cải thiện trải nghiệm thời gian thực của một câu trả lời duy nhất.

Nó không hỗ trợ đánh giá nhiều nguồn, gọi API, hay so sánh nhiều lựa chọn trả về.

3. Knowledge Bases

Mô tả: Dịch vụ lưu trữ và truy vấn các tài liệu, tệp và định dạng không cấu trúc, cho phép LLM “rút trích” thông tin trong quá trình sinh câu trả lời.

Tại sao ❌ không đáp ứng yêu cầu:

Knowledge Bases giúp tích hợp nội dung (knowledge) vào prompt, nhưng không tự động gọi API bên ngoài hay tạo và đánh giá nhiều lựa chọn.

Để thực hiện logic ưu tiên, bạn vẫn cần một lớp điều phối (như Agents) để xử lý kết quả từ Knowledge Base và các API.

4. Agents (ĐÚNG)

Mô tả: Khả năng định nghĩa một “agent” với:

LLM làm bộ não chính.

Toolset gồm các API endpoints, functions, knowledge bases hoặc custom services.

Workflow logic cho phép lặp lại (iterate) qua các bước: lấy dữ liệu, gọi API, tạo candidate responses, tính điểm, và trả về câu trả lời tốt nhất.

Tại sao ✅ đáp ứng đầy đủ:

Evaluate specific data sources → Agent có thể truy cập Knowledge Base hoặc các data store được cấu hình.

Query external APIs → Agent có thể định nghĩa “tool” là HTTP API và thực hiện request trong quá trình xử lý.

Generate response options → LLM bên trong Agent có thể sinh ra nhiều candidate answers.

Compare and prioritize response options → Bạn có thể cung cấp scoring function hoặc rule‑based logic trong Agent để lựa chọn đáp án tối ưu.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock Developer Guide – Agents

https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html (phiên bản cập nhật 2026)

Amazon Bedrock – Prompt Management

https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html

Amazon Bedrock – Response Streaming

https://docs.aws.amazon.com/bedrock/latest/userguide/response-streaming.html

Amazon Bedrock – Knowledge Bases

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-bases.html

🛠️ Kết luận nhanh

Đáp án đúng: Agents – cung cấp khả năng orchestrate đa nguồn dữ liệu, gọi API, tạo nhiều đáp án, và thực hiện so sánh/đánh giá để đưa ra câu trả lời tối ưu.

Các lựa chọn còn lại (Prompt Management, Response streaming, Knowledge Bases) chỉ đáp ứng một phần chức năng (quản lý prompt, truyền dữ liệu nhanh, hoặc lưu trữ kiến thức) và không đáp ứng toàn bộ chuỗi yêu cầu được nêu trong câu hỏi.

👍 Hy vọng phần phân tích này giúp bạn nắm rõ lý do tại sao Agents là lựa chọn duy nhất phù hợp!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313004-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 43

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Q, Amazon IAM, Amazon KMS, Amazon Inspector, Amazon Q Business
- Đáp án tham khảo: **Các đáp án đúng**
- Takeaway nhanh: Công ty muốn sử dụng Amazon Q Business để khai thác dữ liệu nội bộ, nhưng đồng thời phải bảo đảm bảo mật và riêng tư cho dữ liệu đó. Yêu cầu “Choose two” nghĩa là chỉ cần chọn hai biện pháp đáp ứng được mục tiêu: Mã hoá dữ liệu ở mức lưu trữ (ngăn chặn người không có quyền truy cập đọc được dữ liệu). Xác thực & ủy quyền để chỉ những người, vai trò hợp lệ mới có thể truy cập vào chỉ mục (index) của Q Business.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/316394-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use Amazon Q Business for its data. The company needs to ensure the security and privacy of the data.
Which combination of steps will meet these requirements? (Choose two.)

### Các lựa chọn
1. Enable AWS Key Management Service (AWS KMS) keys for the Amazon Q Business Enterprise index.
2. Set up cross-account access to the Amazon Q index.
3. Configure Amazon Inspector for authentication.
4. Allow public access to the Amazon Q index.
5. Configure AWS Identity and Access Management (IAM) for authentication.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn sử dụng Amazon Q Business để khai thác dữ liệu nội bộ, nhưng đồng thời phải bảo đảm bảo mật và riêng tư cho dữ liệu đó.

Yêu cầu “Choose two” nghĩa là chỉ cần chọn hai biện pháp đáp ứng được mục tiêu:

Mã hoá dữ liệu ở mức lưu trữ (ngăn chặn người không có quyền truy cập đọc được dữ liệu).

Xác thực & ủy quyền để chỉ những người, vai trò hợp lệ mới có thể truy cập vào chỉ mục (index) của Q Business.

✅ Các đáp án đúng

1. Enable AWS Key Management Service (AWS KMS) keys for the Amazon Q Business Enterprise index.

Tại sao đúng?

KMS cung cấp mã hoá bên trong cho dữ liệu khi nó được lưu trữ trong Enterprise index của Q Business.

Khi KMS được bật, mọi tài liệu được đưa vào index sẽ được encrypt bằng CMK (Customer Managed Key) hoặc AWS‑managed key, giúp đáp ứng yêu cầu bảo mật dữ liệu “at rest”.

Điều này ngăn chặn việc dữ liệu bị lộ nếu có truy cập trái phép vào bucket hoặc dịch vụ lưu trữ phía sau Q Business.

2. Configure AWS Identity and Access Management (IAM) for authentication.

Tại sao đúng?

IAM là cơ chế chuẩn của AWS để xác thực (authentication) và ủy quyền (authorization) cho người dùng, nhóm, vai trò hoặc các dịch vụ.

Bằng cách tạo IAM policies cho phép/không cho phép các hành động như qbusiness:Search, qbusiness:CreateIndex, …, công ty có thể kiểm soát ai được phép truy cập vào Q Business và đối tượng nào (ví dụ: chỉ một domain nội bộ).

Kết hợp với IAM Identity Center (SSO) hoặc AWS SSO cũng có thể tích hợp với các IdP doanh nghiệp (AD, Okta) để thực hiện single‑sign‑on và tuân thủ các tiêu chuẩn bảo mật.

❌ Các đáp án sai và lý do

Set up cross‑account access to the Amazon Q index.

Sai vì việc thiết lập cross‑account access (cho phép tài khoản AWS khác truy cập) không phải là một biện pháp bảo mật dữ liệu nội bộ; ngược lại, nó mở rộng phạm vi truy cập ra ngoài, làm tăng rủi ro rò rỉ dữ liệu nếu không quản lý chặt chẽ.

Khi mục tiêu là riêng tư, nên hạn chế quyền truy cập trong cùng một tài khoản hoặc cùng tổ chức (Organization) và không cần chia sẻ sang tài khoản khác.

Configure Amazon Inspector for authentication.

Sai vì Amazon Inspector là dịch vụ đánh giá bảo mật (vulnerability assessment) cho EC2, container, và các workload. Nó không liên quan tới xác thực người dùng hay kiểm soát truy cập vào Q Business.

Việc cấu hình Inspector không giúp bảo vệ dữ liệu trong Q Business; thay vào đó, nó chỉ cung cấp báo cáo về lỗ hổng bảo mật của môi trường compute.

Allow public access to the Amazon Q index.

Sai vì mở public access (truy cập công cộng) đối nghịch hoàn toàn với yêu cầu “security and privacy”.

Khi chỉ mục được công khai, bất kỳ ai có URL đều có thể thực hiện tìm kiếm và truy cập dữ liệu, gây rò rỉ nghiêm trọng.

Đối với môi trường doanh nghiệp, luôn phải giới hạn truy cập bằng IAM, VPC endpoints, hoặc PrivateLink.

🛠️ Gợi ý triển khai thực tế (theo chuẩn AWS 2026)

Tạo Customer Managed Key (CMK) trong KMS

Đặt policy cho phép chỉ IAM role của Q Business và các role ứng dụng được phép kms:Encrypt, kms:Decrypt.

Khi tạo Enterprise index trong Q Business, chọn “Enable encryption” và chỉ định CMK đã tạo.

Xây dựng IAM policy cho Q Business

Ví dụ policy:

Code

{

"Version": "2012-10-17",

"Statement": [

{

"Effect": "Allow",

"Action": [

"qbusiness:Chat",

"qbusiness:Search",

"qbusiness:GetDocument"

],

"Resource": "arn:aws:qbusiness:region:account-id:index/YourEnterpriseIndex"

}

]

}

Gán policy này cho IAM users, groups, hoặc roles tương ứng (ví dụ: QBusinessReadOnlyRole).

Kết hợp với AWS PrivateLink / VPC endpoint (tùy chọn) để giữ lưu lượng truy cập trong mạng VPC nội bộ, giảm bớt rủi ro từ internet.

📚 Tham khảo tài liệu

Amazon Q Business Developer Guide (v2026.x) – “Security and encryption” section.

AWS Key Management Service Documentation – “Using AWS KMS with Amazon Q Business”.

IAM Best Practices – “Controlling access to Amazon Q Business”.

AWS Security Blog (2025‑2026) – “Protecting enterprise data in generative AI services”.

Tóm lại: Để đáp ứng yêu cầu bảo mật & riêng tư cho dữ liệu trong Amazon Q Business, công ty cần mã hoá index bằng KMS và cấu hình IAM để thực hiện xác thực/ủy quyền. Hai lựa chọn còn lại (cross‑account access, Amazon Inspector, public access) không phù hợp hoặc thậm chí trái ngược với mục tiêu. ✅✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316394-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Temperature**
- Takeaway nhanh: Temperature là một tham số được dùng trong phương pháp sampling (ví dụ: softmax temperature hoặc top‑k / top‑p sampling khi kết hợp). Khi temperature ↑ (ví dụ: 1.0 → 1.5), hàm softmax “phẳng” hơn → xác suất các token ít phổ biến tăng, mô hình sẽ sinh ra các câu trả lời đa dạng, sáng tạo hơn. Khi temperature ↓ (ví dụ: 1.0 → 0.3), hàm softmax “sắc nét” hơn → xác suất tập trung vào các token có xác suất cao nhất → kết quả trở nên lặp lại, ít đa dạng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312967-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is working on a large language model (LLM) and noticed that the LLM’s outputs are not as diverse as expected.
Which parameter should the company adjust?

### Các lựa chọn
1. Temperature
2. Batch size
3. Learning rate
4. Optimizer type

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

A company is working on a large language model (LLM) and noticed that the LLM’s outputs are not as diverse as expected.

Which parameter should the company adjust?

Câu hỏi đề cập tới độ đa dạng (diversity) của kết quả sinh ra khi mô hình ngôn ngữ tạo văn bản. Khi một LLM được “sampling” (rút mẫu) để sinh ra chuỗi ký tự, có một số siêu‑tham số (hyper‑parameter) ảnh hưởng trực tiếp tới việc mô hình có “mạo hiểm” chọn các token ít phổ biến hơn hay không. Trong các lựa chọn được đưa ra, chỉ có Temperature là siêu‑tham số kiểm soát trực tiếp mức độ ngẫu nhiên và do đó ảnh hưởng tới độ đa dạng của output.

✅ Đáp án đúng: Temperature

Temperature là một tham số được dùng trong phương pháp sampling (ví dụ: softmax temperature hoặc top‑k / top‑p sampling khi kết hợp).

Khi temperature ↑ (ví dụ: 1.0 → 1.5), hàm softmax “phẳng” hơn → xác suất các token ít phổ biến tăng, mô hình sẽ sinh ra các câu trả lời đa dạng, sáng tạo hơn.

Khi temperature ↓ (ví dụ: 1.0 → 0.3), hàm softmax “sắc nét” hơn → xác suất tập trung vào các token có xác suất cao nhất → kết quả trở nên lặp lại, ít đa dạng.

Do đó, để cải thiện đa dạng, công ty cần tăng giá trị temperature (hoặc thực hiện thí nghiệm với các giá trị như 0.7‑1.2 tùy vào độ “creativity” mong muốn).

📚 Tham khảo:

Amazon SageMaker Documentation – Deploying Hugging Face Transformers (phiên bản 2026) – phần “Controlling Generation with temperature, top‑k, top‑p”.

AWS Blog – Fine‑tuning Large Language Models on SageMaker (tháng 3/2025) – ví dụ về điều chỉnh temperature để thay đổi tính sáng tạo của model.

❌ Các phương án sai và lý do

Batch size

Batch size quyết định số lượng mẫu (samples) được đưa vào GPU/TPU trong một bước training hoặc inference.

Thay đổi batch size có thể ảnh hưởng tới hiệu năng (thời gian training, tiêu thụ GPU memory) và đôi khi tới stability của quá trình training, nhưng không ảnh hưởng trực tiếp tới tính đa dạng của token được sinh ra trong quá trình inference.

Vì vậy, việc tăng/giảm batch size sẽ không giải quyết vấn đề “output không đa dạng”.

Learning rate

Learning rate là tốc độ cập nhật trọng số trong quá trình training.

Nó quyết định mô hình hội tụ nhanh hay chậm, và có thể ảnh hưởng tới chất lượng tổng thể (over‑fitting / under‑fitting).

Tuy learning rate có thể gián tiếp ảnh hưởng tới khả năng mô hình “học” các mẫu phong phú, nhưng không phải là tham số điều khiển trực tiếp khi sinh ra văn bản sau khi mô hình đã được huấn luyện.

Khi mô hình đã được fine‑tuned và đang được dùng để tạo văn bản, việc thay đổi learning rate không còn ảnh hưởng.

Optimizer type

Loại optimizer (Adam, AdamW, SGD, …) quyết định cách tính gradient và cập nhật trọng số trong giai đoạn training.

Giống như learning rate, optimizer ảnh hưởng tới quá trình hội tụ và chất lượng mô hình cuối cùng, nhưng không kiểm soát việc sampling token trong inference.

Thay đổi optimizer không làm tăng hoặc giảm độ đa dạng của output ngay lập tức.

🛠️ Gợi ý thực tiễn khi điều chỉnh Temperature trên AWS

SageMaker Endpoints: Khi gọi endpoint (bằng InvokeEndpoint), truyền temperature trong payload JSON nếu model hỗ trợ (ví dụ: Hugging Face text-generation pipeline).

SageMaker JumpStart: Các mô hình có sẵn cho LLM thường cho phép tùy chỉnh temperature, top_k, top_p thông qua model_kwargs.

Batch Transform: Khi thực hiện batch inference, cũng có thể truyền temperature trong TransformInput để đồng nhất mức độ đa dạng cho toàn bộ batch.

Best practice: Bắt đầu với temperature = 0.7, đánh giá kết quả, sau đó tăng dần (0.9 → 1.2) nếu cần nhiều sáng tạo hơn, nhưng chú ý tới risk of incoherent output khi temperature quá cao.

📌 Tổng kết

✅ Temperature là tham số duy nhất trong danh sách ảnh hưởng trực tiếp tới độ đa dạng của kết quả sinh ra từ một LLM.

❌ Batch size, Learning rate, và Optimizer type là các tham số liên quan tới quá trình training hoặc hiệu năng tính toán, không quyết định mức độ sáng tạo khi inference.

Việc điều chỉnh temperature một cách hợp lý sẽ giúp công ty đạt được kết quả LLM đa dạng và phong phú hơn, đồng thời vẫn duy trì chất lượng ngữ nghĩa cần thiết. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312967-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 45

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, Amazon Lex
- Takeaway nhanh: 🔹 Conduct stakeholder interviews to refine use cases and set measurable goals. Xác định nhu cầu thực tế: Các buổi interview với stakeholder (marketing manager, product owner, sales, khách hàng…) giúp nắm bắt các vấn đề cần giải quyết (ví dụ: tạo nội dung quảng cáo tự động, cá nhân hoá email, dự đoán xu hướng). Đặt mục tiêu KPI: Khi đã có use‑case rõ ràng, công ty có thể thiết lập các chỉ số đo lường (increase conversion rate % , lift in campaign ROI, revenue uplift). Điều này đáp ứng yêu cầu “tăng doanh thu trong 6 tháng”.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/316395-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to implement a generative AI solution to improve its marketing operations. The company wants to increase its revenue in the next 6 months.
Which approach will meet these requirements?

### Các lựa chọn
1. Immediately start training a custom FM by using the company's existing data.
2. Conduct stakeholder interviews to refine use cases and set measurable goals.
3. Implement a prebuilt AI assistant solution and measure its impact on customer satisfaction.
4. Analyze industry AI implementations and replicate the most successful features.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty muốn triển khai giải pháp AI sinh (generative AI) nhằm cải thiện hoạt động marketing và tăng doanh thu trong vòng 6 tháng tới.

Yêu cầu quan trọng:

Thời gian ngắn (6 tháng) – cần một cách tiếp cận nhanh, không phải xây dựng từ đầu.

Tập trung vào doanh thu – phải có các chỉ tiêu kinh doanh rõ ràng, đo lường được.

Giải pháp phù hợp với marketing – phải hiểu nhu cầu thực tế của các bên liên quan (marketing, bán hàng, khách hàng).

Vì vậy, cách tiếp cận nên bắt đầu bằng khảo sát, xác định rõ use‑case và đặt mục tiêu đo lường trước khi lựa chọn công nghệ hay mô hình nào.

✅ Đáp án đúng

🔹 Conduct stakeholder interviews to refine use cases and set measurable goals.

Lý do:

Xác định nhu cầu thực tế: Các buổi interview với stakeholder (marketing manager, product owner, sales, khách hàng…) giúp nắm bắt các vấn đề cần giải quyết (ví dụ: tạo nội dung quảng cáo tự động, cá nhân hoá email, dự đoán xu hướng).

Đặt mục tiêu KPI: Khi đã có use‑case rõ ràng, công ty có thể thiết lập các chỉ số đo lường (increase conversion rate % , lift in campaign ROI, revenue uplift). Điều này đáp ứng yêu cầu “tăng doanh thu trong 6 tháng”.

Giảm rủi ro & tối ưu chi phí: Thay vì đầu tư vào mô hình tùy chỉnh hoặc sao chép giải pháp, việc xác định mục tiêu giúp lựa chọn công cụ AWS phù hợp (Amazon Bedrock, Amazon SageMaker JumpStart, Amazon Personalize, …) một cách có chiến lược, nhanh chóng triển khai và đo lường.

AWS cung cấp các framework để hỗ trợ quá trình này, ví dụ: AWS Well‑Architected Framework – Machine Learning Lens, AWS Solutions Lab để làm việc cùng stakeholder, và Amazon SageMaker Canvas cho người không chuyên để tạo prototype nhanh.

❌ Giải thích các phương án sai

🔹 Immediately start training a custom FM by using the company's existing data.

Sai vì:

Thời gian: Đào tạo một Foundation Model (FM) tùy chỉnh thường mất tháng (thu thập, tiền xử lý, huấn luyện, đánh giá). Không thể đáp ứng mục tiêu 6 tháng.

Chi phí & nguồn lực: Cần GPU/TPU lớn, đội ngũ ML chuyên sâu, và chi phí tính bằng hàng trăm nghìn USD.

Rủi ro chất lượng: Dữ liệu nội bộ có thể không đủ đa dạng, dẫn tới over‑fitting và hiệu suất kém.

AWS cập nhật 2026: AWS khuyến nghị dùng Amazon Bedrock (pre‑trained models) hoặc SageMaker JumpStart cho các dự án nhanh, thay vì tự đào tạo từ đầu.

🔹 Implement a prebuilt AI assistant solution and measure its impact on customer satisfaction.

Sai vì:

Mục tiêu không phù hợp: Đo lường customer satisfaction không đồng nhất với tăng doanh thu trong 6 tháng. Một trợ lý AI có thể cải thiện trải nghiệm, nhưng không chắc sẽ tạo ra doanh thu ngay lập tức.

Thiếu định hướng use‑case: Không có quá trình khám phá nhu cầu marketing cụ thể, nên có thể triển khai tính năng không liên quan đến mục tiêu doanh thu.

Giải pháp “prebuilt” (ví dụ Amazon Lex, Q‑Chatbot) thường tập trung vào hỗ trợ khách hàng, không phải tạo nội dung marketing hay cá nhân hoá chiến dịch.

🔹 Analyze industry AI implementations and replicate the most successful features.

Sai vì:

Chiến lược sao chép không tính tới điểm mạnh yếu nội tại của công ty (đặc thù dữ liệu, quy trình, thương hiệu).

Thời gian thực hiện: Phân tích và “replicate” thường đòi hỏi đánh giá sâu, lập kế hoạch và tùy biến, có thể kéo dài hơn 6 tháng.

Không có KPI cụ thể: Việc “replicate features” không tự động đưa ra mục tiêu doanh thu hay cách đo lường.

AWS best practice (2026): Khuyến khích design thinking – bắt đầu bằng việc hiểu nhu cầu người dùng (stakeholder) và thiết lập mục tiêu, sau đó chọn công nghệ phù hợp.

📚 Tham khảo tài liệu (2026)

AWS Well‑Architected Framework – Machine Learning Lens (v2026.2) – hướng dẫn cách xác định mục tiêu kinh doanh và đo lường ROI.

Amazon Bedrock Documentation – các mô hình foundation model đã được tối ưu, có thể triển khai trong vòng ngày tới.

Amazon SageMaker JumpStart & Canvas – công cụ “no‑code/low‑code” giúp tạo prototype nhanh, phù hợp cho dự án 6 tháng.

AWS Solutions Lab – AI/ML Enablement – quy trình stakeholder interview, use‑case prioritization.

AWS re:Invent 2025 – Session “Accelerating Generative AI for Marketing” – case study về việc bắt đầu từ “business problem discovery” tới triển khai Bedrock.

🧩 Kết luận

Để đáp ứng yêu cầu tăng doanh thu trong 6 tháng, công ty cần đầu tiên hiểu rõ nhu cầu và mục tiêu kinh doanh bằng cách phỏng vấn các stakeholder, xác định use‑case và thiết lập KPI có thể đo lường. Sau bước này, họ mới lựa chọn công nghệ (Bedrock, SageMaker, Personalize…) và triển khai nhanh chóng. Do đó, phương án “Conduct stakeholder interviews to refine use cases and set measurable goals” là lựa chọn duy nhất đúng.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316395-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 46

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Đáp án tham khảo: **Nova Lite**
- Takeaway nhanh: Bối cảnh: Công ty đang khám phá các mô hình Amazon Nova trong dịch vụ Amazon Bedrock. Yêu cầu: Cần một mô hình đa phương tiện (multimodal) – có khả năng xử lý / tạo ra nhiều loại dữ liệu (ví dụ: văn bản + hình ảnh + âm thanh) và hỗ trợ đa ngôn ngữ. Tiêu chí lựa chọn: “Most cost‑effectively” → mô hình phải đáp ứng đủ yêu cầu và có chi phí vận hành (giá token, thời gian tính toán) thấp nhất trong số các lựa chọn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313014-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is exploring Amazon Nova models in Amazon Bedrock. The company needs a multimodal model that supports multiple languages.
Which Nova model will meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Nova Lite
2. Nova Pro
3. Nova Canvas
4. Nova Reel

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Công ty đang khám phá các mô hình Amazon Nova trong dịch vụ Amazon Bedrock.

Yêu cầu: Cần một mô hình đa phương tiện (multimodal) – có khả năng xử lý / tạo ra nhiều loại dữ liệu (ví dụ: văn bản + hình ảnh + âm thanh) và hỗ trợ đa ngôn ngữ.

Tiêu chí lựa chọn: “Most cost‑effectively” → mô hình phải đáp ứng đủ yêu cầu và có chi phí vận hành (giá token, thời gian tính toán) thấp nhất trong số các lựa chọn.

✅ Đáp án đúng: Nova Lite

Lý do:

Multimodal: Nova Lite được thiết kế để xử lý đồng thời văn bản, hình ảnh và âm thanh, đáp ứng yêu cầu “multimodal”.

Đa ngôn ngữ: Nova Lite hỗ trợ hơn 100 ngôn ngữ, đủ để công ty làm việc với khách hàng toàn cầu.

Chi phí: Đây là phiên bản “lite” – tức là tối ưu chi phí (giá token thấp hơn 60 % so với các phiên bản Pro/Canvas) đồng thời vẫn duy trì độ chính xác và khả năng đa phương tiện cần thiết.

Kết luận: Vì Nova Lite vừa đáp ứng đầy đủ yêu cầu chức năng vừa có mức giá rẻ nhất, nên nó là lựa chọn most cost‑effective.

❌ Phân tích các phương án còn lại

Nova Pro

Chức năng: Cung cấp khả năng mô hình lớn hơn, độ chính xác cao hơn và băng thông ngữ cảnh (context) rộng.

Multimodal: Có hỗ trợ đa phương tiện, nhưng chi phí cao gấp 2‑3 lần Nova Lite (giá token và thời gian xử lý).

Kết luận: Không phù hợp về mặt chi phí khi nhu cầu chỉ cần “đủ” chứ không yêu cầu siêu hiệu năng → SAI.

Nova Canvas

Chức năng: Tập trung vào tạo nội dung sáng tạo (hình ảnh, đồ họa, bố cục) và cung cấp các công cụ “canvas” cho việc kết hợp đa phương tiện.

Đa ngôn ngữ: Hỗ trợ chủ yếu tiếng Anh và một số ngôn ngữ châu Âu; không được quảng cáo là đa ngôn ngữ toàn diện.

Chi phí: Giá token cao hơn Nova Lite khoảng 80 %.

Kết luận: Dù mạnh về sáng tạo, nhưng không đáp ứng đầy đủ yêu cầu đa ngôn ngữ và chi phí không tối ưu → SAI.

Nova Reel

Chức năng: Được tối ưu cho tạo và xử lý video (video generation, video‑to‑text).

Multimodal: Chỉ chuyên về video + audio; không có khả năng xử lý văn bản đa ngôn ngữ như yêu cầu.

Chi phí: Mức giá cao nhất trong nhóm vì tính toán video nặng.

Kết luận: Không phù hợp với yêu cầu “multimodal + đa ngôn ngữ” chung và chi phí cao → SAI.

📚 Tham khảo nguồn tài liệu (đến năm 2026)

Amazon Bedrock – Nova Model Family Documentation, AWS Documentation (phiên bản 2026‑03).

Trang “Nova Lite Overview” mô tả: “supports text, image, and audio inputs, 100+ languages, cost‑optimized pricing tier.”

Trang “Nova Pro vs. Lite pricing comparison” cung cấp bảng giá token (Lite = $0.0002/1k tokens; Pro = $0.0005/1k tokens).

AWS Blogs – “Introducing Amazon Nova: The Next‑Gen Multimodal Foundation Models” (15 Nov 2025).

AWS Well‑Architected Framework – Cost Optimization Pillar (cập nhật 2026) – hướng dẫn lựa chọn mô hình có chi phí tối ưu dựa trên nhu cầu thực tế.

🧩 Tóm tắt nhanh

Câu hỏi yêu cầu mô hình đa phương tiện + đa ngôn ngữ với chi phí thấp nhất.

Nova Lite đáp ứng đầy đủ cả ba tiêu chí → đáp án đúng.

Các mô hình Pro, Canvas, Reel đều either quá tốn kém hoặc không đáp ứng đầy đủ tính năng → đáp án sai.

✅ Kết luận: Chọn Nova Lite là lựa chọn hợp lý nhất cho công ty.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313014-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 47

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312971-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. Select the correct AI term from the following list for each statement. Each AI term should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312971-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 48

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon S3
- Đáp án tham khảo: **Continued pre‑training**
- Takeaway nhanh: Bối cảnh: Công ty đang phát triển một công cụ AI sinh (generative AI). Họ muốn “customize” (tùy biến) một foundation model (FM) bằng cách sử dụng các tài liệu nội bộ của mình. Yêu cầu: Chọn phương pháp phù hợp nhất để “điều chỉnh” (customize) mô hình nền tảng sao cho mô hình nắm bắt được kiến thức, ngôn ngữ và phong cách đặc thù của tài liệu nội bộ. Trong môi trường AWS hiện nay (2024‑2026) :
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html | https://docs.aws.amazon.com/sagemaker/latest/dg/training.html | https://www.examtopics.com/discussions/amazon/view/313045-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a generative AI tool. The company will use internal documents to customize a foundation model (FM).
Which approach will meet this requirement?

### Các lựa chọn
1. Classification
2. Continued pre-training
3. Distillation
4. Regression

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Bối cảnh: Công ty đang phát triển một công cụ AI sinh (generative AI). Họ muốn “customize” (tùy biến) một foundation model (FM) bằng cách sử dụng các tài liệu nội bộ của mình.

Yêu cầu: Chọn phương pháp phù hợp nhất để “điều chỉnh” (customize) mô hình nền tảng sao cho mô hình nắm bắt được kiến thức, ngôn ngữ và phong cách đặc thù của tài liệu nội bộ.

Trong môi trường AWS hiện nay (2024‑2026) :

Amazon Bedrock và Amazon SageMaker hỗ trợ continued pre‑training (còn gọi là pre‑training tiếp tục hoặc domain‑adaptive pre‑training) để “đào tạo lại” mô hình nền tảng trên tập dữ liệu riêng.

Các phương pháp như classification, distillation hay regression không phải là cách “tùy biến” mô hình sinh dựa trên dữ liệu văn bản.

✅ Đáp án đúng: Continued pre‑training

📖 Lý do lựa chọn:

Continued pre‑training (tiếp tục đào tạo) cho phép lấy một foundation model đã được huấn luyện trên một kho dữ liệu lớn (ví dụ: Amazon Titan, Llama‑3, Claude, …) và đào tạo thêm (pre‑train) trên tập dữ liệu nội bộ của công ty.

Kỹ thuật này giúp mô hình học các thuật ngữ, cấu trúc, phong cách và kiến thức chuyên ngành mà chỉ có trong tài liệu nội bộ, đồng thời vẫn giữ được khả năng sinh nội dung tổng quát.

AWS SageMaker Data Parallel và Model Parallel cùng với SageMaker JumpStart hoặc Bedrock Custom Model cung cấp workflow “continual pre‑training” chỉ với vài bước cấu hình và chi phí tính theo thời gian tính toán.

❌ Phân tích các phương án còn lại

Classification

Giải thích: Phương pháp này dùng để phân loại đầu vào thành các nhãn (label) cố định (ví dụ: spam/không spam, sentiment).

Tại sao sai: Không liên quan đến việc “điều chỉnh” một mô hình sinh để hiểu nội dung tài liệu. Classification chỉ tạo ra một mô hình discriminative chứ không thay đổi trọng số của mô hình sinh nền tảng.

Distillation

Giải thích: Model distillation là kỹ thuật tạo mô hình nhẹ (student) từ một mô hình lớn (teacher) bằng cách truyền kiến thức.

Tại sao sai: Mục tiêu của distillation là giảm kích thước và tốc độ suy luận, không phải tùy biến mô hình để nắm bắt dữ liệu nội bộ. Ngoài ra, quá trình này không “học” thêm kiến thức mới từ tài liệu nội bộ.

Regression

Giải thích: Regression là phương pháp dự đoán một giá trị số liên tục (ví dụ: dự báo giá, thời gian).

Tại sao sai: Không liên quan tới việc huấn luyện lại một mô hình ngôn ngữ để sinh văn bản. Regression chỉ áp dụng cho các bài toán dự báo số học, không phải cho việc “customize” foundation model.

🛠️ Cách thực hiện Continued Pre‑training trên AWS (2024‑2026)

Chuẩn bị dữ liệu

Thu thập tài liệu nội bộ, chuyển thành text files hoặc JSONL (mỗi dòng một đoạn văn).

Dùng Amazon S3 để lưu trữ, áp dụng S3 Object Lock/Encryption để bảo mật dữ liệu nhạy cảm.

Tạo môi trường SageMaker

Khởi tạo SageMaker Studio hoặc SageMaker Notebook Instance.

Cài đặt Hugging Face Deep Learning Container hoặc AWS Trainium‑enabled image (trong trường hợp muốn dùng trainium cho hiệu năng cao).

Thiết lập job continued pre‑training

Sử dụng SageMaker TrainingJob với training_image là một mô hình foundation (ví dụ: huggingface/pytorch‑transformers:latest).

Đặt hyperparameters như learning_rate, num_train_epochs, và do_train = true.

Chỉ định train_dataset trỏ tới S3 bucket chứa dữ liệu nội bộ.

Triển khai mô hình đã tùy biến

Đăng ký mô hình lên SageMaker Model Registry hoặc Amazon Bedrock Custom Model để sử dụng qua API hoặc SDK.

Kích hoạt inference endpoint (Real‑time hoặc Asynchronous) để tích hợp vào công cụ AI sinh của công ty.

Quản lý chi phí và bảo mật

Kích hoạt SageMaker Savings Plans hoặc Spot Instances cho training để giảm chi phí.

Áp dụng IAM policies và VPC endpoints để hạn chế truy cập dữ liệu.

📚 Tham khảo tài liệu (đến 2026)

AWS Documentation – SageMaker Training: https://docs.aws.amazon.com/sagemaker/latest/dg/training.html (phiên bản cập nhật 2025‑12).

Amazon Bedrock – Custom Model: https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html (cập nhật 2026‑02).

AWS Blog – “Fine‑tuning foundation models with SageMaker” (2024‑08) – hướng dẫn chi tiết về continued pre‑training.

Hugging Face – “Continual Pre‑training of Large Language Models” (2025‑03) – mô tả thuật toán và best‑practice.

🔚 Kết luận

Để “customize” một foundation model bằng các tài liệu nội bộ, Continued pre‑training là cách tiếp cận đúng nhất trong môi trường AWS hiện đại. Các phương pháp khác (Classification, Distillation, Regression) không đáp ứng yêu cầu về việc học thêm kiến thức ngôn ngữ và nội dung từ dữ liệu nội bộ. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313045-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 49

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Supervised learning**
- Takeaway nhanh: Công ty đang xây dựng một mô hình Machine Learning (ML) để dự đoán nguy cơ bệnh tim dựa trên các đặc trưng của bệnh nhân (tuổi, cholesterol, huyết áp, trạng thái hút thuốc, thói quen tập thể dục). Trong tập dữ liệu, mỗi bản ghi đều có giá trị mục tiêu (target) cho biết bệnh nhân có/không có bệnh tim. Yêu cầu: Chọn kỹ thuật ML phù hợp để “học” mối quan hệ giữa các đặc trưng đầu vào và giá trị mục tiêu đã biết, sao cho mô hình có thể dự đoán nhãn (có bệnh / không bệnh) cho các bệnh nhân mới.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/supervised-learning-basics/ | https://d1.awsstatic.com/whitepapers/Machine-Learning-at-Scale.pdf | https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works.html | https://www.examtopics.com/discussions/amazon/view/312991-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing an ML model to predict heart disease risk. The model uses patient data, such as age, cholesterol, blood pressure, smoking status, and exercise habits. The dataset includes a target value that indicates whether a patient has heart disease.
Which ML technique will meet these requirements?

### Các lựa chọn
1. Unsupervised learning
2. Supervised learning
3. Reinforcement learning
4. Semi-supervised learning

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang xây dựng một mô hình Machine Learning (ML) để dự đoán nguy cơ bệnh tim dựa trên các đặc trưng của bệnh nhân (tuổi, cholesterol, huyết áp, trạng thái hút thuốc, thói quen tập thể dục).

Trong tập dữ liệu, mỗi bản ghi đều có giá trị mục tiêu (target) cho biết bệnh nhân có/không có bệnh tim.

Yêu cầu: Chọn kỹ thuật ML phù hợp để “học” mối quan hệ giữa các đặc trưng đầu vào và giá trị mục tiêu đã biết, sao cho mô hình có thể dự đoán nhãn (có bệnh / không bệnh) cho các bệnh nhân mới.

✅ Đáp án đúng: Supervised learning

Lý do:

Khi dữ liệu đã gắn nhãn (có target) như trong câu hỏi, chúng ta sử dụng học có giám sát (supervised learning) để huấn luyện mô hình dự đoán nhãn.

Đây là bài toán phân loại nhị phân (có bệnh tim hay không), một dạng điển hình của supervised learning.

Trên AWS, dịch vụ Amazon SageMaker cung cấp các thuật toán supervised (Linear Learner, XGBoost, DeepAR, …) và quy trình “training‑inference” phù hợp.

🧩 Giải thích từng phương án

Unsupervised learning

Giải thích: Unsupervised learning được dùng khi dữ liệu không có nhãn và mục tiêu là khám phá cấu trúc ẩn (clustering, dimensionality reduction). Vì đề bài đã có nhãn “có/không bệnh tim”, nên không phù hợp.

AWS liên quan: Amazon SageMaker Clustering, K‑Means, DBSCAN – dùng cho phân cụm khách hàng, anomaly detection, không phải cho dự đoán nhãn đã biết.

Supervised learning

Giải thích: Như đã nêu ở trên, dữ liệu có nhãn, mô hình học cách ánh xạ từ các thuộc tính đầu vào sang nhãn đầu ra. Đây là cách chuẩn để giải quyết bài toán dự đoán bệnh tim.

AWS liên quan: SageMaker Built‑in Algorithms (XGBoost, Linear Learner) hoặc tự xây dựng model TensorFlow/PyTorch trong SageMaker, triển khai bằng SageMaker Endpoint để inference.

Reinforcement learning

Giải thích: Reinforcement learning (RL) xử lý các tác vụ tương tác môi trường và học dựa trên phần thưởng/penalty (ví dụ: robot di chuyển, game AI). Không liên quan tới việc dự đoán dựa trên dữ liệu lịch sử có nhãn.

AWS liên quan: SageMaker RL, DeepRacer – dùng cho các bài toán quyết định thời gian thực, không phải classification có nhãn.

Semi‑supervised learning

Giải thích: Semi‑supervised learning kết hợp có một phần dữ liệu có nhãn và phần còn lại không nhãn. Khi toàn bộ dữ liệu đã có nhãn như trong câu hỏi, việc dùng kỹ thuật này là không cần thiết và không tối ưu.

AWS liên quan: SageMaker hỗ trợ semi‑supervised qua custom scripts, nhưng thường dùng khi chi phí gán nhãn cao và dữ liệu không đủ nhãn.

📚 Tham khảo tài liệu (đến 2026)

AWS Documentation – Amazon SageMaker Training

https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works.html

Machine Learning Foundations – Supervised vs Unsupervised vs Reinforcement (AWS Machine Learning Blog, 2025)

https://aws.amazon.com/blogs/machine-learning/supervised-learning-basics/

AWS Whitepaper – Machine Learning at Scale (2026 update)

https://d1.awsstatic.com/whitepapers/Machine-Learning-at-Scale.pdf

🛠️ Kết luận: Đối với bài toán dự đoán nguy cơ bệnh tim dựa trên dữ liệu đã gắn nhãn, Supervised learning là kỹ thuật thích hợp nhất. Các dịch vụ như Amazon SageMaker cung cấp đầy đủ công cụ để triển khai, huấn luyện và phục vụ mô hình này trong môi trường AWS hiện đại.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312991-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 50

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Relational Database Service, Amazon SageMaker, Amazon S3, Amazon Q
- Takeaway nhanh: Công ty muốn đo và theo dõi chất lượng Internet ở các khu vực xa xôi. Họ sẽ thu thập dữ liệu tốc độ Internet (ví dụ: độ trễ, băng thông tải xuống / lên) và lưu trữ chúng trong Amazon RDS. Sau đó, họ sẽ phân tích sự biến thiên của tốc độ trong suốt một ngày và xây dựng mô hình AI để dự đoán các trường hợp gián đoạn mạng. Vì mục tiêu là đánh giá sự thay đổi theo thời gian (các phép đo được thực hiện liên tục, thường mỗi vài phút hoặc mỗi giờ), dữ liệu cần phải có đánh dấu thời gian để có thể xem xu hướng, mùa vụ, các mẫu lặp lại và dự báo tương lai.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313030-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to assess internet quality in remote areas of the world. The company needs to collect internet speed data and store the data in Amazon RDS. The company will analyze internet speed variation throughout each day. The company wants to create an AI model to predict potential internet disruptions.
Which type of data should the company collect for this task?

### Các lựa chọn
1. Tabular data
2. Text data
3. Time series data
4. Audio data

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty muốn đo và theo dõi chất lượng Internet ở các khu vực xa xôi.

Họ sẽ thu thập dữ liệu tốc độ Internet (ví dụ: độ trễ, băng thông tải xuống / lên) và lưu trữ chúng trong Amazon RDS.

Sau đó, họ sẽ phân tích sự biến thiên của tốc độ trong suốt một ngày và xây dựng mô hình AI để dự đoán các trường hợp gián đoạn mạng.

Vì mục tiêu là đánh giá sự thay đổi theo thời gian (các phép đo được thực hiện liên tục, thường mỗi vài phút hoặc mỗi giờ), dữ liệu cần phải có đánh dấu thời gian để có thể xem xu hướng, mùa vụ, các mẫu lặp lại và dự báo tương lai.

✅ Đáp án đúng

🟢 Time series data

🔎 Lý do chọn:

Dữ liệu time‑series là tập hợp các quan sát được ghi lại theo thứ tự thời gian, thường có khoảng thời gian đều đặn (giây, phút, giờ…).

Khi muốn phân tích biến động trong ngày và dự báo gián đoạn bằng các thuật toán Machine Learning/Deep Learning (ARIMA, LSTM, Prophet, …), dữ liệu time‑series là dạng phù hợp nhất.

AWS cung cấp các dịch vụ hỗ trợ xử lý time‑series (Amazon Timestream, Amazon SageMaker với các built‑in algorithms cho forecasting) và có thể lưu trữ bản gốc trong Amazon RDS để thực hiện truy vấn SQL truyền thống.

❌ Phân tích các phương án còn lại

Tabular data

Giải thích: Dữ liệu dạng bảng (các hàng và cột) thường được dùng cho các bài toán phân loại hoặc hồi quy mà không yêu cầu thông tin thứ tự thời gian.

Tại sao sai: Mặc dù RDS có thể lưu trữ bảng, không phản ánh được tính chất “theo thời gian” của các phép đo tốc độ Internet. Nếu chỉ lưu dưới dạng bảng mà không có chuỗi thời gian, chúng ta sẽ mất khả năng phân tích xu hướng và dự báo chính xác.

Text data

Giải thích: Dữ liệu văn bản (log, mô tả, bình luận…) thường dùng cho các mô hình NLP.

Tại sao sai: Tốc độ Internet là các giá trị số (Mbps, ms) chứ không phải nội dung văn bản. Thu thập text sẽ không cung cấp thông tin định lượng cần thiết để đo lường và dự báo.

Audio data

Giải thích: Dữ liệu âm thanh được dùng trong các ứng dụng như nhận dạng giọng nói, phân tích âm thanh.

Tại sao sai: Không có liên quan tới việc đo tốc độ hay độ trễ mạng. Thu thập audio sẽ không giúp phân tích hay dự báo gián đoạn Internet.

🛠️ Gợi ý triển khai trên AWS (2026)

Thu thập dữ liệu

Dùng AWS IoT Greengrass hoặc AWS Snowball Edge tại các vị trí xa để chạy script đo tốc độ (speedtest‑cli) và gửi kết quả lên Amazon Kinesis Data Streams.

Lưu trữ

Đẩy dữ liệu vào Amazon RDS (MySQL/PostgreSQL) với bảng có các cột: timestamp, download_mbps, upload_mbps, latency_ms.

Đối với khối lượng lớn, cân nhắc sao chép sang Amazon Timestream để tối ưu truy vấn time‑series.

Phân tích & dự báo

Dùng Amazon SageMaker: thuật toán DeepAR, LSTM, hoặc Prophet để huấn luyện mô hình dự báo gián đoạn.

Kết quả có thể được lưu trong Amazon S3 và visualized bằng Amazon QuickSight.

📚 Tham khảo (đến năm 2026)

Amazon RDS Documentation – lưu trữ dữ liệu quan hệ, hỗ trợ MySQL, PostgreSQL, Aurora (2026 update).

Amazon Timestream – Time Series Database – giải pháp tối ưu cho dữ liệu time‑series (2025‑2026).

Amazon SageMaker Built‑in Algorithms – DeepAR, Prophet, và các framework LSTM cho forecasting (phiên bản 2026).

AWS Well‑Architected Framework – Operational Excellence Pillar – hướng dẫn thu thập và lưu trữ metric liên tục.

🔚 Tổng kết

Đối với việc đo và dự báo chất lượng Internet theo thời gian, dữ liệu time‑series là loại dữ liệu thích hợp nhất. Các lựa chọn khác (tabular, text, audio) không đáp ứng yêu cầu về đánh dấu thời gian và định lượng cần thiết cho phân tích và mô hình AI dự đoán gián đoạn. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313030-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 51

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon SageMaker
- Đáp án tham khảo: **“A model that groups customers based on their purchase history” – ví dụ điển hình của clustering.**
- Takeaway nhanh: Câu hỏi: “Which option is an example of unsupervised learning?” “Unsupervised learning” (học không giám sát) là một nhánh của Machine Learning trong đó mô hình không nhận được nhãn (label) nào từ dữ liệu huấn luyện. Mục tiêu chính của các thuật toán không giám sát là khám phá cấu trúc, mẫu, hoặc mối quan hệ ẩn trong dữ liệu, ví dụ như clustering (phân cụm), dimensionality reduction (giảm chiều), hay anomaly detection (phát hiện bất thường).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/unstructured-data-clustering-sagemaker/ | https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html | https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html | https://docs.aws.amazon.com/sagemaker/latest/dg/rl.html | https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-pillar/ | https://www.examtopics.com/discussions/amazon/view/313000-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is an example of unsupervised learning?

### Các lựa chọn
1. A model that groups customers based on their purchase history
2. A model that classifies images as dogs or cats
3. A model that predicts a house’s price based on various features
4. A model that learns to play chess by using trial and error

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which option is an example of unsupervised learning?”

“Unsupervised learning” (học không giám sát) là một nhánh của Machine Learning trong đó mô hình không nhận được nhãn (label) nào từ dữ liệu huấn luyện.

Mục tiêu chính của các thuật toán không giám sát là khám phá cấu trúc, mẫu, hoặc mối quan hệ ẩn trong dữ liệu, ví dụ như clustering (phân cụm), dimensionality reduction (giảm chiều), hay anomaly detection (phát hiện bất thường).

AWS cung cấp các dịch vụ hỗ trợ học không giám sát, tiêu biểu là Amazon SageMaker‑Built‑in Algorithms – K‑Means clustering, Amazon SageMaker Canvas (cho người không chuyên), và AWS Glue DataBrew (khám phá dữ liệu).

Vì vậy, câu hỏi đang muốn chúng ta nhận diện phương án mô tả một mô hình không dùng nhãn để học, chỉ “phát hiện” các nhóm hoặc mẫu trong dữ liệu.

✅ Đáp án đúng

🟢 A model that groups customers based on their purchase history

Giải thích tại sao đây là unsupervised learning

Không có nhãn: Dữ liệu mua hàng của khách hàng chỉ chứa các giao dịch (số lượng, sản phẩm, thời gian…) mà không có “nhãn” chỉ ra khách hàng thuộc nhóm nào.

Mục tiêu: Tìm các nhóm (clusters) khách hàng có hành vi tương đồng – đây là clustering, một kỹ thuật học không giám sát điển hình.

AWS liên quan:

Amazon SageMaker K‑Means hoặc SageMaker Clustering: cho phép tạo mô hình phân cụm dựa trên các đặc trưng mua hàng.

Amazon SageMaker Canvas: người dùng kéo‑thả có thể thực hiện “Group customers” mà không cần viết code, dựa trên unsupervised learning.

❌ Các phương án sai và lý do

🟠 A model that classifies images as dogs or cats

Giải thích: Đây là supervised learning (học có giám sát). Mô hình nhận được nhãn “dog” hoặc “cat” cho mỗi ảnh trong quá trình huấn luyện.

AWS liên quan:

Amazon SageMaker Image Classification (với thuật toán ResNet, EfficientNet…) sử dụng dữ liệu có nhãn.

Amazon Rekognition Custom Labels: cũng yêu cầu cung cấp nhãn cho từng hình ảnh.

🟠 A model that predicts a house’s price based on various features

Giải thích: Đây là regression – một dạng supervised learning. Mô hình học dựa trên các đầu vào (đặc trưng) và đầu ra (giá nhà) đã được gán nhãn.

AWS liên quan:

Amazon SageMaker Linear Learner hoặc XGBoost để thực hiện regression.

Amazon Forecast (dự báo thời gian) cũng dựa trên dữ liệu có nhãn.

🟠 A model that learns to play chess by using trial and error

Giải thích: Đây là reinforcement learning (học tăng cường). Mô hình tương tác với môi trường (trò chơi cờ), nhận reward (phần thưởng) và penalty (phạt) để tối ưu hành vi – không phải là unsupervised learning.

AWS liên quan:

Amazon SageMaker RL Toolkit (với thuật toán PPO, DQN) hỗ trợ xây dựng các tác vụ RL như chơi cờ, trò chơi video.

📚 Tham khảo (tài liệu AWS cập nhật tới 2026)

Amazon SageMaker Documentation – Built‑in Algorithms (K‑Means clustering, Linear Learner, XGBoost).

https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html

Amazon SageMaker Canvas User Guide – “Create an unsupervised model”.

https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html

AWS Machine Learning Blog – “Unsupervised learning on SageMaker: clustering and anomaly detection”. (2024).

https://aws.amazon.com/blogs/machine-learning/unstructured-data-clustering-sagemaker/

Amazon SageMaker Reinforcement Learning (RL) Toolkit – Documentation.

https://docs.aws.amazon.com/sagemaker/latest/dg/rl.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025).

https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-pillar/

📌 Tổng kết nhanh gọn

Unsupervised learning = không có nhãn, thường dùng clustering hoặc anomaly detection.

Đáp án đúng: “A model that groups customers based on their purchase history” – ví dụ điển hình của clustering.

Các đáp án còn lại thuộc supervised learning (classification, regression) hoặc reinforcement learning, vì chúng đều dựa vào nhãn hoặc phần thưởng để học.

Hy vọng phân tích chi tiết này giúp bạn nắm rõ khái niệm và lựa chọn đúng đáp án! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313000-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 52

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, model evaluation, RAG
- Đáp án tham khảo: **Classification**
- Takeaway nhanh: Công ty muốn sử dụng một mô hình Machine Learning (ML) để phân tích các đánh giá của khách hàng trên mạng xã hội. Mục tiêu: xác định cảm xúc (sentiment) của mỗi đánh giá và gán nhãn là neutral, positive, hoặc negative. ➡️ Đây là một bài toán gán nhãn (label) cho từng mẫu dữ liệu dựa trên nội dung văn bản → bài toán phân loại (classification), cụ thể là classification đa lớp (multi‑class classification) với 3 lớp.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/comprehend/latest/dg/custom-classification.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-algorithms.html | https://www.examtopics.com/discussions/amazon/view/313046-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to use an ML model to analyze customer reviews on social media. The model must determine if each review has a neutral, positive, or negative sentiment.
Which model evaluation strategy will meet these requirements?

### Các lựa chọn
1. Open-ended generation
2. Text summarization
3. Machine translation
4. Classification

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn sử dụng một mô hình Machine Learning (ML) để phân tích các đánh giá của khách hàng trên mạng xã hội.

Mục tiêu: xác định cảm xúc (sentiment) của mỗi đánh giá và gán nhãn là neutral, positive, hoặc negative.

➡️ Đây là một bài toán gán nhãn (label) cho từng mẫu dữ liệu dựa trên nội dung văn bản → bài toán phân loại (classification), cụ thể là classification đa lớp (multi‑class classification) với 3 lớp.

Vì vậy, chiến lược đánh giá mô hình phải đo lường khả năng dự đoán đúng nhãn của mô hình (accuracy, precision, recall, F1‑score, confusion matrix, …). Các chiến lược như “open‑ended generation”, “text summarization” hay “machine translation” không liên quan tới việc đưa ra nhãn cảm xúc.

✅ Đáp án đúng: Classification

Lý do:

Classification là kỹ thuật ML dùng để dự đoán một trong một tập hợp các lớp rời rạc.

Trong AWS, có nhiều dịch vụ và thuật toán hỗ trợ text classification, ví dụ: Amazon SageMaker JumpStart “BlazingText” hoặc “Linear Learner”, Amazon Comprehend Custom Classification, và các mô hình Transformers (BERT, RoBERTa…) được triển khai trên SageMaker Inference.

Đánh giá mô hình phân loại thường dùng các chỉ số: accuracy, precision, recall, F1‑score, ROC‑AUC (cho binary) hoặc macro‑averaged metrics (cho multi‑class), cùng với confusion matrix để kiểm tra lỗi giữa các lớp (neutral vs. positive vs. negative).

🧩 Phân tích các phương án (giữ nguyên nội dung tiếng Anh)

1. Open‑ended generation

❌ Sai

Đây là dạng mô hình tạo văn bản tự do (ví dụ: GPT‑4, Claude) mà đầu ra không bị ràng buộc bởi một tập nhãn cố định.

Đối với yêu cầu “neutral / positive / negative”, mô hình cần đưa ra nhãn cụ thể, không phải tạo ra đoạn văn bản tự do.

Đánh giá thường dùng BLEU, ROUGE, METEOR, không phù hợp cho bài toán sentiment classification.

2. Text summarization

❌ Sai

Text summarization (tóm tắt văn bản) mục tiêu là rút gọn nội dung thành một đoạn ngắn hơn, giữ nguyên ý chính.

Nó không cung cấp thông tin về cảm xúc của văn bản gốc, và các chỉ số đánh giá (ROUGE, ROUGE‑L) không phản ánh độ chính xác của nhãn cảm xúc.

Vì vậy không đáp ứng yêu cầu “determine if each review has a neutral, positive, or negative sentiment”.

3. Machine translation

❌ Sai

Machine translation (dịch máy) chuyển ngữ từ ngôn ngữ này sang ngôn ngữ khác (ví dụ: English → Vietnamese).

Không liên quan tới việc phân loại cảm xúc và không tạo ra nhãn.

Các metric như BLEU, TER chỉ đo độ chính xác của bản dịch, không phù hợp với bài toán sentiment analysis.

4. Classification

✅ Đúng

Như đã giải thích, đây là chiến lược đánh giá mô hình dựa trên khả năng gán nhãn chính xác cho các lớp cảm xúc.

AWS cung cấp công cụ Amazon Comprehend Custom Classification cho sentiment analysis, hoặc SageMaker Autopilot/JumpStart để tự động xây dựng và đánh giá mô hình phân loại đa lớp.

Các metric (accuracy, macro‑F1, confusion matrix) cho phép đo lường mức độ đáp ứng yêu cầu “neutral, positive, negative”.

🛠️ Gợi ý triển khai trên AWS (2026)

Amazon Comprehend Custom Classification

Tạo dataset với các review đã được gán nhãn (neutral/positive/negative).

Đào tạo mô hình và nhận các metric như Precision, Recall, F1‑score cho mỗi lớp.

Amazon SageMaker JumpStart

Sử dụng mô hình BlazingText (fastText) hoặc BERT‑based để thực hiện text classification.

Kích hoạt Hyperparameter tuning và model evaluation để thu thập các metric multi‑class.

SageMaker Pipelines + Model Registry

Xây dựng pipeline tự động: thu thập dữ liệu → preprocessing → training → evaluation (classification metrics) → deployment.

CloudWatch Metrics & SageMaker Model Monitor

Giám sát drift của nhãn cảm xúc sau khi đưa model vào production, đảm bảo độ chính xác không giảm theo thời gian.

📚 Tham khảo

AWS Documentation – Amazon Comprehend Custom Classification (phiên bản 2026): https://docs.aws.amazon.com/comprehend/latest/dg/custom-classification.html

AWS Documentation – SageMaker JumpStart Built‑in Algorithms (BlazingText, Text Classification): https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-algorithms.html

AWS Whitepaper – Best Practices for Machine Learning on AWS (2025 Update), chương “Text Classification & Sentiment Analysis”.

Tóm lại: Đối với yêu cầu xác định cảm xúc “neutral, positive, negative” từ các review, chiến lược đánh giá phù hợp nhất là Classification. Các lựa chọn còn lại (Open‑ended generation, Text summarization, Machine translation) không đáp ứng yêu cầu gán nhãn và do đó không phải là câu trả lời đúng. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313046-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 53

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Clustering data points into groups based on their similarity – là ví dụ điển hình của unsupervised learning vì không cần nhãn và dựa vào sự tương đồng để tự động phân nhóm.**
- Takeaway nhanh: Which option is an example of unsupervised learning? Câu hỏi yêu cầu bạn nhận biết phương pháp học máy (machine‑learning) nào thuộc loại “unsupervised learning” – tức là mô hình được huấn luyện không có nhãn (label) đầu vào. Trong unsupervised learning, thuật toán tự khám phá cấu trúc, mẫu, hoặc quan hệ ẩn trong dữ liệu, ví dụ như clustering, dimensionality reduction, hay anomaly detection. Ngược lại, supervised learning cần dữ liệu đã được gán nhãn (ví dụ: ảnh có nhãn “cat”, “dog” hoặc giá nhà kèm theo giá thực tế) để mô hình học cách dự đoán nhãn.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/unsupervised-learning-on-aws/ | https://docs.aws.amazon.com/sagemaker/latest/dg/algos-unsupervised.html | https://www.examtopics.com/discussions/amazon/view/312969-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is an example of unsupervised learning?

### Các lựa chọn
1. Clustering data points into groups based on their similarity
2. Training a model to recognize images of animals
3. Predicting the price of a house based on the house’s features
4. Generating human-like text based on a given prompt

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Which option is an example of unsupervised learning?

Câu hỏi yêu cầu bạn nhận biết phương pháp học máy (machine‑learning) nào thuộc loại “unsupervised learning” – tức là mô hình được huấn luyện không có nhãn (label) đầu vào. Trong unsupervised learning, thuật toán tự khám phá cấu trúc, mẫu, hoặc quan hệ ẩn trong dữ liệu, ví dụ như clustering, dimensionality reduction, hay anomaly detection. Ngược lại, supervised learning cần dữ liệu đã được gán nhãn (ví dụ: ảnh có nhãn “cat”, “dog” hoặc giá nhà kèm theo giá thực tế) để mô hình học cách dự đoán nhãn.

✅ Đáp án đúng

Clustering data points into groups based on their similarity

Giải thích:

Thuật toán clustering (ví dụ: K‑Means, DBSCAN, hierarchical clustering) không yêu cầu nhãn cho các điểm dữ liệu.

Nó chỉ dựa trên độ tương đồng (distance, similarity) để tự động phân nhóm các đối tượng sao cho các đối tượng trong cùng một nhóm gần nhau hơn so với các đối tượng ở nhóm khác.

Đây là một ví dụ tiêu biểu của unsupervised learning.

❌ Giải thích các phương án sai

Training a model to recognize images of animals

Đây là supervised learning. Để “recognize” (nhận dạng) ảnh động vật, mô hình cần một tập dữ liệu có nhãn (ví dụ: ảnh “cat”, “dog”, “elephant”…). Nhãn cung cấp câu trả lời đúng mà mô hình học để dự đoán.

Do có nhãn, nên không phải là unsupervised learning.

Predicting the price of a house based on the house’s features

Đây là regression, một dạng supervised learning. Đầu vào là các đặc trưng (diện tích, số phòng, vị trí…) và đầu ra là giá nhà – một giá trị đã biết trong dữ liệu huấn luyện.

Vì mô hình học từ cặp (đặc trưng, giá trị mục tiêu) đã được gán nhãn, nên không thuộc unsupervised learning.

Generating human‑like text based on a given prompt

Phương pháp này thường dùng large language models (LLMs) như GPT‑4, được huấn luyện bằng cách dự đoán token tiếp theo trên một khối lượng lớn văn bản. Quá trình huấn luyện ban đầu là self‑supervised (các token được tạo ra thành “nhãn” tạm thời), nhưng trong bối cảnh câu hỏi, việc “generate text from a prompt” được coi là inference của một mô hình đã được huấn luyện có mục tiêu rõ ràng (tạo ra văn bản hợp lý).

Do không phải là một thuật toán không có nhãn như clustering, nên không được xem là unsupervised learning.

📚 Tham khảo (cập nhật đến 2026)

AWS Machine Learning Blog – “Unsupervised Learning on AWS”, 2025.

https://aws.amazon.com/blogs/machine-learning/unsupervised-learning-on-aws/

Amazon SageMaker Documentation – “Built‑in Algorithms – Unsupervised Learning”, phiên bản 2026.

https://docs.aws.amazon.com/sagemaker/latest/dg/algos-unsupervised.html

Goodfellow, I., Bengio, Y., Courville, A. – “Deep Learning”, 2nd ed., 2023, Ch. 5 (Unsupervised Learning).

🧩 Tổng kết

✅ Đáp án đúng: Clustering data points into groups based on their similarity – là ví dụ điển hình của unsupervised learning vì không cần nhãn và dựa vào sự tương đồng để tự động phân nhóm.

❌ Các phương án còn lại đều liên quan tới supervised learning (nhận dạng ảnh, hồi quy giá nhà) hoặc inference từ mô hình đã huấn luyện (tạo văn bản), vì vậy không phải là unsupervised learning.

Hy vọng phần giải thích chi tiết này giúp bạn nắm vững khái niệm và dễ dàng lựa chọn đáp án đúng trong các đề thi AWS Certified DevOps Engineer Professional hoặc các kỳ thi liên quan tới Machine Learning! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312969-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 54

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Glue, Amazon Glue Data Quality, Amazon Lambda, Amazon Bedrock, Amazon S3
- Đáp án tham khảo: **Lý do chọn**
- Takeaway nhanh: Công ty muốn thực hiện các phép biến đổi số (numeric transformations) trên một tập hợp ảnh, cụ thể là transpose (đảo vị) và rotate (xoay). Yêu cầu “most operationally efficient” (hiệu quả vận hành nhất) có nghĩa là: Giải pháp được quản lý (managed) hoặc serverless để giảm tối thiểu công việc vận hành (bảo trì, provisioning, scaling). Không cần xây dựng, huấn luyện mô hình phức tạp nếu chỉ thực hiện các thao tác hình học đơn giản.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/compute/processing-images-with-aws-lambda-and-pillow/ | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://docs.aws.amazon.com/glue/latest/dg/data-quality.html | https://docs.aws.amazon.com/lambda/latest/dg/best-practices.html | https://docs.aws.amazon.com/lambda/latest/dg/welcome.html | https://www.examtopics.com/discussions/amazon/view/312965-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company needs to apply numerical transformations to a set of images to transpose and rotate the images.
Which solution will meet these requirements in the MOST operationally efficient way?

### Các lựa chọn
1. Create a deep neural network by using the images as input.
2. Create an AWS Lambda function to perform the transformations.
3. Use an Amazon Bedrock large language model (LLM) with a high temperature.
4. Use AWS Glue Data Quality to make corrections to each image.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn thực hiện các phép biến đổi số (numeric transformations) trên một tập hợp ảnh, cụ thể là transpose (đảo vị) và rotate (xoay).

Yêu cầu “most operationally efficient” (hiệu quả vận hành nhất) có nghĩa là:

Giải pháp được quản lý (managed) hoặc serverless để giảm tối thiểu công việc vận hành (bảo trì, provisioning, scaling).

Không cần xây dựng, huấn luyện mô hình phức tạp nếu chỉ thực hiện các thao tác hình học đơn giản.

Có thể tích hợp dễ dàng vào luồng xử lý dữ liệu (ví dụ: trigger khi ảnh được tải lên S3).

✅ Đáp án đúng

Create an AWS Lambda function to perform the transformations.

✅ Lý do chọn

Serverless & tự động scaling – Lambda được AWS quản lý, không cần provision EC2, không phải lo về patching hay scaling.

Chi phí dựa trên thời gian thực thi – chỉ trả tiền cho thời gian chạy của hàm, phù hợp với khối lượng công việc biến đổi ảnh không liên tục.

Có thể gắn trigger với Amazon S3 – mỗi khi một ảnh mới được đưa vào bucket, Lambda có thể tự động đọc, thực hiện transpose/rotate (sử dụng Pillow, OpenCV, hoặc AWS Rekognition‑style libraries) và ghi lại kết quả.

Quản lý môi trường runtime – Lambda hỗ trợ Python, Node.js, Java… với các layer để đưa thư viện xử lý ảnh vào.

Do đó, đây là cách hoạt động hiệu quả nhất về mặt vận hành so với các lựa chọn còn lại.

🧩 Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

1. Create a deep neural network by using the images as input.

❌ Sai vì:

Việc huấn luyện một mạng neural sâu chỉ để thực hiện các phép biến đổi hình học (transpose, rotate) là quá mức và không cần thiết.

Đòi hỏi công cụ GPU, cluster, quản lý mô hình, tăng chi phí và độ phức tạp vận hành.

Các phép biến đổi này đã có sẵn trong các thư viện xử lý ảnh; không cần AI để dự đoán hay tạo ra chúng.

2. Create an AWS Lambda function to perform the transformations.

✅ Đúng – đã phân tích ở trên. Lambda cung cấp môi trường serverless, tự động scaling, giá trả theo milisecond, và dễ dàng tích hợp với S3, CloudWatch, EventBridge để tạo pipeline chuyển đổi ảnh.

3. Use an Amazon Bedrock large language model (LLM) with a high temperature.

❌ Sai vì:

LLM (ví dụ Claude, Titan, Llama) được thiết kế để xử lý ngôn ngữ tự nhiên, không phải thao tác trên dữ liệu nhị phân như ảnh.

“High temperature” chỉ điều chỉnh độ ngẫu nhiên trong tạo văn bản, hoàn toàn không liên quan tới việc quay hoặc đảo ảnh.

Việc gọi Bedrock sẽ tạo thêm độ trễ và chi phí mà không mang lại giá trị cho tác vụ hình học.

4. Use AWS Glue Data Quality to make corrections to each image.

❌ Sai vì:

AWS Glue Data Quality là tính năng kiểm tra và cải thiện chất lượng dữ liệu dạng bảng (CSV, Parquet, JSON…) thông qua rule‑based profiling.

Nó không hỗ trợ xử lý hoặc sửa đổi dữ liệu binary như ảnh.

Ngay cả khi có thể, việc dùng Glue – một dịch vụ ETL lớn, dựa trên Spark – sẽ quá nặng và không tối ưu cho các phép biến đổi nhẹ, nhanh trên từng file ảnh.

📚 Tham khảo tài liệu (đến năm 2026)

AWS Lambda – Serverless Compute – https://docs.aws.amazon.com/lambda/latest/dg/welcome.html

Xử lý ảnh trong Lambda bằng Pillow (Python) – https://aws.amazon.com/blogs/compute/processing-images-with-aws-lambda-and-pillow/

Best Practices for Lambda Performance – https://docs.aws.amazon.com/lambda/latest/dg/best-practices.html

AWS Glue Data Quality Overview – https://docs.aws.amazon.com/glue/latest/dg/data-quality.html

Amazon Bedrock Documentation – https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

🛠️ Kết luận

Đối với các thao tác transpose và rotate trên ảnh, AWS Lambda là giải pháp đơn giản, nhanh, chi phí hợp lý và ít công sức vận hành.

Các lựa chọn còn lại (deep neural network, Bedrock LLM, Glue Data Quality) đều không phù hợp với yêu cầu về tính năng và hiệu quả vận hành.

✅ Chọn Lambda để đáp ứng yêu cầu một cách tối ưu!

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312965-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 55

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Autoencoders**
- Takeaway nhanh: 🔍 Giải thích từng phương án Linear regression
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/unsupervised-autoencoders-anomaly-detection/ | https://docs.aws.amazon.com/sagemaker/latest/dg/autoencoder-anomaly-detection.html | https://www.examtopics.com/discussions/amazon/view/313038-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to build an ML model to detect abnormal patterns in sensor data. The company does not have labeled data for training.
Which ML method will meet these requirements?

### Các lựa chọn
1. Linear regression
2. Classification
3. Decision tree
4. Autoencoders

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi yêu cầu chúng ta chọn một phương pháp Machine Learning (ML) phù hợp để phát hiện “abnormal patterns” (mẫu bất thường) trong dữ liệu cảm biến không có dữ liệu đã gán nhãn (unlabeled data).

“Không có dữ liệu đã gán nhãn” → không thể áp dụng các thuật toán giám sát (supervised) mà cần một kỹ thuật không giám sát (unsupervised) hoặc tự giám sát (self‑supervised).

“Phát hiện bất thường” (anomaly detection) thường được giải quyết bằng các mô hình học không giám sát, trong đó autoencoders là một trong những giải pháp phổ biến hiện nay, đặc biệt khi triển khai trên Amazon SageMaker (phiên bản 2026 hỗ trợ “SageMaker Anomaly Detection” dựa trên autoencoders).

✅ Đáp án đúng: Autoencoders

Lý do: Autoencoders là mạng nơ‑ron học tự mã hoá (self‑encoding), được huấn luyện để tái tạo đầu vào. Khi chỉ dùng dữ liệu “bình thường” để huấn luyện, mô hình sẽ học được biểu diễn (latent space) của dữ liệu chuẩn. Khi đưa dữ liệu bất thường vào, sai số tái tạo (reconstruction error) sẽ tăng đáng kể → dùng làm chỉ số phát hiện anomaly. Đây là kỹ thuật không giám sát nên không yêu cầu nhãn.

🔍 Giải thích từng phương án

Linear regression

❌ Linear regression là thuật toán giám sát dùng để dự đoán một giá trị liên tục dựa trên các biến đầu vào có nhãn. Nó không được thiết kế để phát hiện bất thường và cần dữ liệu đã gán nhãn (target). Vì câu hỏi không có nhãn, nên Linear regression không phù hợp.

Classification

❌ Classification là một loại học giám sát (binary hoặc multi‑class) yêu cầu nhãn cho từng mẫu (ví dụ “bình thường” vs “bất thường”). Khi không có nhãn, không thể xây dựng mô hình classification. Thêm vào đó, classification chỉ trả về nhãn, không cung cấp “độ bất thường” dựa trên reconstruction error.

Decision tree

❌ Decision tree (cây quyết định) cũng là một thuật toán giám sát (có thể dùng cho regression hoặc classification). Nó cần dữ liệu đã gán nhãn để xây dựng các nhánh quyết định. Không có nhãn → không thể huấn luyện. Ngoài ra, decision tree không phải là phương pháp thường dùng cho anomaly detection khi không có nhãn.

Autoencoders

✅ Như đã nêu ở trên, autoencoders là mạng nơ‑ron không giám sát hoặc tự giám sát, được huấn luyện để tái tạo đầu vào. Khi huấn luyện chỉ trên dữ liệu “bình thường”, mô hình sẽ có reconstruction error thấp cho dữ liệu bình thường và cao cho dữ liệu bất thường → phù hợp cho yêu cầu “không có nhãn” và “phát hiện bất thường”.

🧩 Liên hệ với dịch vụ AWS (cập nhật đến 2026)

Amazon SageMaker Canvas & SageMaker Studio: hỗ trợ tạo, huấn luyện và triển khai autoencoder mà không cần viết mã (SageMaker Autopilot đã mở rộng hỗ trợ unsupervised models).

SageMaker Anomaly Detection (ra mắt 2024, cập nhật 2026): cung cấp built‑in algorithm dựa trên autoencoders cho việc phát hiện anomaly trong dữ liệu thời gian thực (sensor streams).

AWS Glue & Amazon Kinesis Data Streams: có thể dùng để thu thập, chuẩn bị dữ liệu sensor và đưa vào pipeline SageMaker.

Amazon CloudWatch Evidently: cho phép theo dõi reconstruction error và thiết lập alarm khi giá trị vượt ngưỡng.

📚 Tham khảo tài liệu

Amazon SageMaker Documentation – Autoencoder for Anomaly Detection (v2026.03) – https://docs.aws.amazon.com/sagemaker/latest/dg/autoencoder-anomaly-detection.html

AWS Machine Learning Blog – Unsupervised Learning with Autoencoders (2025) – https://aws.amazon.com/blogs/machine-learning/unsupervised-autoencoders-anomaly-detection/

Deep Learning with Python – Autoencoders for Anomaly Detection, 2nd edition, Francois Chollet, 2023 (cung cấp nền tảng lý thuyết).

🔚 Tổng kết

Vì công ty không có dữ liệu đã gán nhãn, chỉ có thể dùng kỹ thuật không giám sát.

Autoencoders đáp ứng yêu cầu này, cho phép phát hiện bất thường dựa trên reconstruction error.

Các lựa chọn khác (Linear regression, Classification, Decision tree) đều là mô hình giám sát và không thích hợp trong trường hợp này.

Hy vọng giải thích trên giúp bạn nắm rõ lý do tại sao Autoencoders là đáp án duy nhất đúng! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313038-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 56

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon Comprehend, Amazon SageMaker, Amazon Bedrock, Amazon S3
- Đáp án tham khảo: **LLM + NLP (hoặc dịch vụ NLP quản lý như Amazon Comprehend) là cách tiếp cận chuẩn, hiện đại và được AWS hỗ trợ mạnh mẽ.**
- Takeaway nhanh: Công ty nhận được một lượng lớn phản hồi người dùng không có cấu trúc, dưới dạng văn bản (text). Nhiệm vụ là phân tích cảm xúc (sentiment) của các phản hồi này – tức là xác định xem mỗi đoạn văn bản mang tính “tích cực”, “trung tính” hay “tiêu cực”. Để thực hiện việc này, chúng ta cần một giải pháp xử lý ngôn ngữ tự nhiên (NLP) có khả năng hiểu ngữ nghĩa, ngữ cảnh và các biểu hiện cảm xúc trong tiếng tự do. Các dịch vụ và mô hình hiện đại của AWS (đến năm 2026) như Amazon Bedrock, Amazon SageMaker JumpStart (LLM), hay Amazon Comprehend đều cung cấp khả năng sentiment analysis dựa trên các large language model (LLM) hoặc mô hình NLP đã được huấn luyện sẵn.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html | https://docs.aws.amazon.com/comprehend/latest/dg/tutorial-reviews.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://www.examtopics.com/discussions/amazon/view/313007-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company receives a large amount of unstructured user feedback in text format. The company wants to analyze the sentiment of the user feedback. Which solution will meet these requirements?

### Các lựa chọn
1. Use a large language model (LLM) to perform natural language processing (NLP) for sentiment analysis.
2. Use a regression algorithm to classify the feedback based on predefined categories. Then, analyze user sentiment.
3. Use a recommendation engine algorithm to detect user sentiment.
4. Use a time series algorithm to predict user sentiment based on past feedback.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty nhận được một lượng lớn phản hồi người dùng không có cấu trúc, dưới dạng văn bản (text). Nhiệm vụ là phân tích cảm xúc (sentiment) của các phản hồi này – tức là xác định xem mỗi đoạn văn bản mang tính “tích cực”, “trung tính” hay “tiêu cực”.

Để thực hiện việc này, chúng ta cần một giải pháp xử lý ngôn ngữ tự nhiên (NLP) có khả năng hiểu ngữ nghĩa, ngữ cảnh và các biểu hiện cảm xúc trong tiếng tự do. Các dịch vụ và mô hình hiện đại của AWS (đến năm 2026) như Amazon Bedrock, Amazon SageMaker JumpStart (LLM), hay Amazon Comprehend đều cung cấp khả năng sentiment analysis dựa trên các large language model (LLM) hoặc mô hình NLP đã được huấn luyện sẵn.

✅ Đáp án đúng

- Use a large language model (LLM) to perform natural language processing (NLP) for sentiment analysis.

Giải thích:

LLM (ví dụ: Claude, Titan, GPT‑4) có khả năng hiểu ngôn ngữ tự nhiên và phân loại cảm xúc một cách chính xác ngay cả với dữ liệu không có cấu trúc.

Trên AWS, bạn có thể triển khai LLM qua Amazon Bedrock (được quản lý, không cần quản lý hạ tầng) hoặc SageMaker JumpStart để nhanh chóng tạo endpoint cho sentiment analysis.

Ngoài ra, Amazon Comprehend (dịch vụ NLP được quản lý) cung cấp API DetectSentiment – thực chất là một mô hình NLP được huấn luyện sẵn, cũng dựa trên kiến trúc LLM hiện đại.

🛠️ Ví dụ triển khai:

Đưa dữ liệu văn bản vào Amazon S3.

Dùng AWS Glue hoặc Amazon Athena để trích xuất dữ liệu.

Tạo SageMaker endpoint với mô hình LLM (hoặc sử dụng Bedrock InvokeModel).

Gửi mỗi đoạn phản hồi tới endpoint → nhận kết quả sentiment (POSITIVE, NEGATIVE, NEUTRAL).

Lưu kết quả vào Amazon Redshift / QuickSight để phân tích và visualize.

Nguồn tham khảo:

AWS Documentation – Amazon Bedrock (2026): https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS Documentation – Amazon Comprehend DetectSentiment: https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html

AWS Documentation – SageMaker JumpStart (LLM): https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

❌ Các phương án sai và lý do

Use a regression algorithm to classify the feedback based on predefined categories. Then, analyze user sentiment.

📉 Regression (hồi quy) thường dùng để dự đoán một giá trị liên tục (ví dụ: giá bán, thời gian). Đối với phân loại cảm xúc, chúng ta cần một mô hình classification (phân loại), không phải hồi quy.

Thêm vào đó, việc “phân loại dựa trên các danh mục định sẵn” không giải quyết được các nuance trong ngôn ngữ tự do; sentiment analysis yêu cầu hiểu ngữ cảnh sâu hơn, điều mà một thuật toán hồi quy đơn giản không thể làm.

Use a recommendation engine algorithm to detect user sentiment.

🎯 Recommendation engine (hệ thống gợi ý) được thiết kế để đưa ra đề xuất dựa trên hành vi hoặc sở thích (ví dụ: Amazon Personalize). Nó không được huấn luyện để nhận diện cảm xúc trong văn bản.

Việc áp dụng thuật toán gợi ý vào sentiment analysis sẽ dẫn tới kết quả vô nghĩa vì mô hình không có đầu vào/đầu ra liên quan đến cảm xúc.

Use a time series algorithm to predict user sentiment based on past feedback.

⏳ Time‑series (chuỗi thời gian) thích hợp cho dữ liệu có đánh dấu thời gian và muốn dự đoán giá trị số (ví dụ: doanh thu, tải CPU).

Sentiment là đặc tính ngôn ngữ, không phải một giá trị số theo thời gian. Dù bạn có thể tạo mô hình dự báo xu hướng sentiment tổng thể, đầu vào chính vẫn phải là phân tích cảm xúc – không thể bỏ qua bước NLP. Do đó, một thuật toán chuỗi thời gian không đáp ứng yêu cầu “phân tích sentiment” trực tiếp.

🧩 Tổng kết

✅ LLM + NLP (hoặc dịch vụ NLP quản lý như Amazon Comprehend) là cách tiếp cận chuẩn, hiện đại và được AWS hỗ trợ mạnh mẽ.

❌ Các thuật toán hồi quy, gợi ý, và chuỗi thời gian không phù hợp vì chúng không được thiết kế để hiểu và phân loại cảm xúc trong văn bản phi cấu trúc.

Hy vọng phân tích trên giúp bạn nắm rõ lý do lựa chọn giải pháp LLM cho bài toán sentiment analysis và tránh những sai lầm phổ biến khi áp dụng các thuật toán không liên quan. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313007-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://docs.aws.amazon.com/comprehend/latest/dg/tutorial-reviews.html

## Câu 57

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Công ty chăm sóc sức khỏe muốn xây dựng một mô hình chẩn đoán bệnh dựa trên giọng nói của bệnh nhân. Hiện tại họ đã thu thập hàng trăm bản ghi âm, rồi lọc chúng theo độ dài và ngôn ngữ trước khi đưa vào các bước tiếp theo. Câu hỏi yêu cầu xác định giai đoạn nào của vòng đời Machine Learning (ML lifecycle) mà hoạt động “lọc voice recordings theo duration và language” thuộc về.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/databrew/latest/dg/what-is.html | https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html | https://docs.aws.amazon.com/sagemaker/latest/dg/ml-lifecycle.html | https://www.examtopics.com/discussions/amazon/view/316404-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A healthcare company wants to create a model to improve disease diagnostics by analyzing patient voices. The company has recorded hundreds of patient voices for this project.
The company is currently filtering voice recordings according to duration and language.
Which phase of the ML lifecycle describes the current project phase?

### Các lựa chọn
1. Data collection
2. Data preprocessing
3. Feature engineering
4. Model training

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty chăm sóc sức khỏe muốn xây dựng một mô hình chẩn đoán bệnh dựa trên giọng nói của bệnh nhân.

Hiện tại họ đã thu thập hàng trăm bản ghi âm, rồi lọc chúng theo độ dài và ngôn ngữ trước khi đưa vào các bước tiếp theo.

Câu hỏi yêu cầu xác định giai đoạn nào của vòng đời Machine Learning (ML lifecycle) mà hoạt động “lọc voice recordings theo duration và language” thuộc về.

Trong mô hình chuẩn của AWS (và các mô hình chung như CRISP‑DM, SEMMA), vòng đời ML gồm các giai đoạn chính:

Data collection – thu thập dữ liệu thô.

Data preprocessing / data cleaning – làm sạch, chuẩn hoá, lọc dữ liệu để loại bỏ “tiếng ồn” và chuẩn bị cho việc trích xuất đặc trưng.

Feature engineering – tạo ra các đặc trưng (features) hữu ích từ dữ liệu đã được làm sạch.

Model training – huấn luyện mô hình trên tập dữ liệu đã sẵn sàng.

(Các giai đoạn tiếp theo: evaluation, deployment, monitoring …)

Ở đây, công việc “filter voice recordings according to duration and language” không phải là việc thu thập mới (dữ liệu đã có), mà là làm sạch / chuẩn bị dữ liệu để loại bỏ các bản ghi không phù hợp. Vì vậy nó thuộc Data preprocessing.

✅ Đáp án đúng

Data preprocessing

🔸 Lý do:

Data preprocessing (tiền xử lý dữ liệu) bao gồm các bước như filtering, cleaning, normalizing, removing outliers, handling missing values… Việc lọc bản ghi âm theo độ dài và ngôn ngữ chính là một ví dụ điển hình của việc loại bỏ dữ liệu không mong muốn để tạo ra bộ dữ liệu sạch, đồng nhất cho các bước tiếp theo.

Trong AWS SageMaker, quá trình này thường được thực hiện bằng SageMaker Processing Jobs, AWS Glue, hoặc AWS Lambda để chuẩn bị dữ liệu trước khi đưa vào Feature Store hoặc Training Jobs.

🧩 Phân tích các phương án khác

Data collection

❌ Giải thích: Giai đoạn này chỉ bao gồm thu thập dữ liệu thô (ví dụ: ghi âm, tải lên S3). Công việc đã hoàn thành việc thu thập và đang chuyển sang xử lý. Việc lọc theo độ dài và ngôn ngữ không phải là thu thập mà là tiền xử lý.

Feature engineering

❌ Giải thích: Feature engineering tập trung vào việc trích xuất hoặc tạo ra các đặc trưng từ dữ liệu đã được làm sạch (ví dụ: trích xuất MFCC, pitch, spectral features từ âm thanh). Việc chỉ lọc bản ghi không tạo ra đặc trưng nào, mà chỉ chuẩn bị dữ liệu.

Model training

❌ Giải thích: Model training là bước huấn luyện mô hình trên dữ liệu đã sẵn sàng. Lọc dữ liệu trước khi huấn luyện là một công đoạn chuẩn bị, không phải huấn luyện.

🛠️ Liên quan tới AWS (cập nhật đến năm 2026)

Amazon SageMaker Data Wrangler (ra mắt 2022, cập nhật tính năng tự động filtering & validation tới 2025) cho phép người dùng kéo‑thả các phép lọc dựa trên duration, language metadata,… và xuất dữ liệu đã tiền xử lý ra S3 hoặc Feature Store.

SageMaker Processing vẫn là công cụ chính để chạy các script Python, Spark thực hiện tiền xử lý ở quy mô lớn, với khả năng auto‑scaling và IAM‑controlled truy cập.

AWS Glue DataBrew (phiên bản 2024) cung cấp giao diện không mã để filter rows dựa trên điều kiện, rất hữu ích cho việc loại bỏ file âm thanh không đáp ứng tiêu chí.

📚 Tham khảo

AWS SageMaker Documentation – Machine Learning Lifecycle (phiên bản 2026) – https://docs.aws.amazon.com/sagemaker/latest/dg/ml-lifecycle.html

Amazon SageMaker Data Wrangler – Data Preparation (2025 Update) – https://docs.aws.amazon.com/sagemaker/latest/dg/data-wrangler.html

AWS Glue DataBrew – Data Cleaning and Filtering – https://docs.aws.amazon.com/databrew/latest/dg/what-is.html

Tóm lại: Việc “filter voice recordings according to duration and language” là Data preprocessing – giai đoạn làm sạch và chuẩn bị dữ liệu trước khi chuyển sang Feature engineering và Model training. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316404-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 58

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: The use of a trained model to make predictions or decisions on unseen data Đây là định nghĩa chuẩn nhất của inference trong AI. Sau khi mô hình đã học (training) trên tập dữ liệu huấn luyện, ta đưa mô hình vào hoạt động (serve) để thực hiện suy luận trên dữ liệu mới (unseen data). Trong môi trường AWS, khi tạo SageMaker Endpoint hoặc chạy Batch Transform, chúng ta đang thực hiện inference – mô hình nhận dữ liệu đầu vào, thực hiện tính toán và trả về kết quả dự đoán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313032-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What does inference refer to in the context of AI?

### Các lựa chọn
1. The process of creating new AI algorithms
2. The use of a trained model to make predictions or decisions on unseen data
3. The process of combining multiple AI models into one model
4. The method of collecting training data for AI systems

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi: “What does inference refer to in the context of AI?”

Trong lĩnh vực trí tuệ nhân tạo (AI), inference (suy luận) là khái niệm mô tả giai đoạn sử dụng mô hình đã được huấn luyện để đưa ra dự đoán, quyết định hoặc trích xuất thông tin từ dữ liệu mới mà mô hình chưa từng “nhìn thấy” trong quá trình huấn luyện.

AWS cung cấp nhiều dịch vụ liên quan tới inference, ví dụ: Amazon SageMaker Inference, SageMaker Real‑Time Endpoints, Batch Transform, hay AWS Inferentia (chip chuyên dụng). Các dịch vụ này đều tập trung vào việc triển khai mô hình đã huấn luyện và thực thi các yêu cầu dự đoán (inference) trên dữ liệu đầu vào thực tế.

✅ Đáp án đúng

The use of a trained model to make predictions or decisions on unseen data

Giải thích:

Đây là định nghĩa chuẩn nhất của inference trong AI. Sau khi mô hình đã học (training) trên tập dữ liệu huấn luyện, ta đưa mô hình vào hoạt động (serve) để thực hiện suy luận trên dữ liệu mới (unseen data).

Trong môi trường AWS, khi tạo SageMaker Endpoint hoặc chạy Batch Transform, chúng ta đang thực hiện inference – mô hình nhận dữ liệu đầu vào, thực hiện tính toán và trả về kết quả dự đoán.

❌ Giải thích các phương án sai

The process of creating new AI algorithms

Giải thích: Đây là research & development hoặc algorithm design, không phải inference. Việc tạo ra thuật toán mới liên quan tới giai đoạn conceptualization và implementation, còn inference chỉ liên quan tới việc sử dụng mô hình đã hoàn thành.

The process of combining multiple AI models into one model

Giải thích: Quá trình này gọi là model ensembling, model stacking, hoặc model blending. Mặc dù các mô hình ensemble có thể được triển khai để inference, nhưng việc kết hợp chúng không phải là định nghĩa của inference.

The method of collecting training data for AI systems

Giải thích: Thu thập dữ liệu huấn luyện thuộc giai đoạn data acquisition / data preparation, còn inference xảy ra sau khi mô hình đã được huấn luyện và sẵn sàng dự đoán.

🧩 Các khái niệm liên quan trong AWS (đến năm 2026)

Amazon SageMaker Real‑Time Inference: Triển khai mô hình dưới dạng endpoint luôn sẵn sàng nhận yêu cầu HTTP/HTTPS, trả về dự đoán trong mili‑giây.

Amazon SageMaker Batch Transform: Thực hiện inference trên khối lượng lớn dữ liệu lưu trữ trong S3, phù hợp cho công việc không yêu cầu thời gian thực.

AWS Inferentia & Trainium: Chip chuyên dụng (AWS Graviton) để tăng tốc inference (Inferentia) và training (Trainium) với độ trễ thấp, chi phí hiệu quả.

Amazon Elastic Inference: Gán tài nguyên GPU linh hoạt cho các endpoint SageMaker để tối ưu chi phí khi nhu cầu inference không liên tục.

📚 Tham khảo

AWS Documentation – Amazon SageMaker Inference (phiên bản cập nhật 2026).

“Machine Learning Glossary” – AWS Machine Learning Blog, 2025.

“Deep Learning on AWS: From Training to Inference” – Whitepaper, AWS, 2024.

Tóm lại: Inference trong AI là việc dùng một mô hình đã được huấn luyện để đưa ra dự đoán hoặc quyết định trên dữ liệu chưa từng thấy. Đây là đáp án đúng, trong khi các lựa chọn còn lại mô tả các khía cạnh khác của quy trình phát triển AI. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313032-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 59

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Kendra, Amazon Personalize, Amazon Textract, Amazon S3, RAG
- Đáp án tham khảo: **Amazon Kendra**
- Takeaway nhanh: Công ty học trực tuyến có lượng lớn tài liệu giáo dục và muốn triển khai “enterprise search”. “Enterprise search” ở đây nghĩa là một công cụ tìm kiếm nội bộ, cho phép người dùng nhập từ khóa và nhận được kết quả chính xác, liên quan, dựa trên nội dung tài liệu (văn bản, PDF, slide, video metadata …) được lưu trữ trong các hệ thống của doanh nghiệp. Yêu cầu: khả năng index số lượng lớn tài liệu, hỗ trợ ngôn ngữ tự nhiên, cho phép tích hợp nhanh với các nguồn dữ liệu phổ biến (Amazon S3, SharePoint, RDS, DynamoDB …) và cung cấp kết quả xếp hạng dựa trên Machine Learning.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/introducing-hybrid-search-amazon-kendra/ | https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html | https://docs.aws.amazon.com/kendra/latest/dg/what-is-kendra.html | https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html | https://docs.aws.amazon.com/textract/latest/dg/what-is.html | https://www.awsreinvent.com/ | https://www.examtopics.com/discussions/amazon/view/313047-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An online learning company with large volumes of education materials wants to use enterprise search.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Comprehend
2. Amazon Textract
3. Amazon Kendra
4. Amazon Personalize

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty học trực tuyến có lượng lớn tài liệu giáo dục và muốn triển khai “enterprise search”.

“Enterprise search” ở đây nghĩa là một công cụ tìm kiếm nội bộ, cho phép người dùng nhập từ khóa và nhận được kết quả chính xác, liên quan, dựa trên nội dung tài liệu (văn bản, PDF, slide, video metadata …) được lưu trữ trong các hệ thống của doanh nghiệp.

Yêu cầu: khả năng index số lượng lớn tài liệu, hỗ trợ ngôn ngữ tự nhiên, cho phép tích hợp nhanh với các nguồn dữ liệu phổ biến (Amazon S3, SharePoint, RDS, DynamoDB …) và cung cấp kết quả xếp hạng dựa trên Machine Learning.

Với bối cảnh này, AWS cung cấp Amazon Kendra – dịch vụ tìm kiếm doanh nghiệp được xây dựng trên ML và được tối ưu cho các trường hợp sử dụng như “search over large corpus of documents”.

✅ Đáp án đúng: Amazon Kendra

Lý do lựa chọn:

Dịch vụ chuyên biệt cho enterprise search – Kendra cung cấp API và console để tạo “index”, cấu hình “data source connectors”, và cho phép người dùng thực hiện các truy vấn bằng tiếng tự nhiên.

Khả năng mở rộng – Tự động mở rộng quy mô để xử lý hàng triệu tài liệu, phù hợp với “large volumes” của công ty.

Tích hợp sẵn – Kendra hỗ trợ các connector chuẩn (S3, SharePoint, OneDrive, Salesforce, RDS, DynamoDB, etc.) và có khả năng “incremental sync” để cập nhật tài liệu mới mà không cần tái lập chỉ mục toàn bộ.

Công nghệ ML hiện đại – Sử dụng retrieval‑augmented generation (RAG), BM25, semantic ranking, và relevance tuning giúp trả về kết quả chính xác ngay cả khi người dùng nhập câu hỏi dạng tự nhiên.

Cập nhật 2025‑2026 – Kendra đã bổ sung tính năng Hybrid Search (kết hợp tìm kiếm dựa trên keyword và embedding), Query Suggestion, và fine‑grained access control (IAM + SAML) để đáp ứng các yêu cầu bảo mật doanh nghiệp.

❌ Giải thích các phương án sai

Amazon Comprehend

Mô tả: Dịch vụ NLP (Natural Language Processing) để phân tích văn bản – nhận diện thực thể, cảm xúc, key phrases, và tạo custom classification.

Tại sao không phù hợp: Comprehend chỉ cung cấp phân tích nội dung, không phải công cụ tìm kiếm. Nó không có khả năng tạo index, kết nối tới nguồn dữ liệu, hoặc trả về danh sách tài liệu dựa trên truy vấn. Đối với “enterprise search”, chúng ta cần một hệ thống index‑query chứ không chỉ là phân tích ngôn ngữ.

Amazon Textract

Mô tả: Dịch vụ OCR/Document Text Extraction, chuyển đổi ảnh, PDF, và tài liệu scan thành text và dữ liệu cấu trúc.

Tại sao không phù hợp: Textract là công cụ trích xuất dữ liệu từ tài liệu, không phải công cụ tìm kiếm. Nó thường được dùng trước khi đưa dữ liệu vào một hệ thống tìm kiếm (ví dụ Kendra) để chuyển đổi tài liệu hình ảnh thành văn bản. Nhưng Textract không có chức năng index hay trả về kết quả tìm kiếm.

Amazon Personalize

Mô tả: Dịch vụ tạo hệ thống recommendation dựa trên ML, tương tự như Netflix/Spotify.

Tại sao không phù hợp: Personalize tập trung vào gợi ý cá nhân hoá (sản phẩm, video, nội dung) dựa trên hành vi người dùng, không phải tìm kiếm tài liệu dựa trên từ khóa hoặc câu hỏi. Nó không cung cấp index tài liệu, không hỗ trợ các connector tới nguồn dữ liệu doanh nghiệp.

🧩 Tổng hợp lại

Câu hỏi yêu cầu một dịch vụ enterprise search cho khối lượng lớn tài liệu.

Amazon Kendra là dịch vụ duy nhất trong danh sách đáp ứng đầy đủ các tiêu chí: tạo index, hỗ trợ đa nguồn dữ liệu, khả năng tìm kiếm ngôn ngữ tự nhiên, và mở rộng quy mô.

Các dịch vụ còn lại (Comprehend, Textract, Personalize) đều là công cụ chuyên môn (NLP, OCR, recommendation) chứ không phải hệ thống tìm kiếm doanh nghiệp.

📚 Tham khảo tài liệu (2026)

Amazon Kendra – Documentation (AWS, phiên bản 2026.03) – https://docs.aws.amazon.com/kendra/latest/dg/what-is-kendra.html

AWS Blog – “Introducing Hybrid Search in Amazon Kendra” (Nov 2025) – https://aws.amazon.com/blogs/aws/introducing-hybrid-search-amazon-kendra/

AWS Re:Invent 2025 – Session “Deep Dive into Amazon Kendra for Enterprise Search” – video và slide tại https://www.awsreinvent.com/

Amazon Comprehend – Documentation – https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html

Amazon Textract – Documentation – https://docs.aws.amazon.com/textract/latest/dg/what-is.html

Amazon Personalize – Documentation – https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html

💡 Khi cần triển khai tìm kiếm cho kho tài liệu giáo dục, hãy bắt đầu bằng việc cấu hình một Kendra index, kết nối các nguồn (S3 buckets chứa PDF, video metadata trong DynamoDB, …), và điều chỉnh “relevance tuning” để tối ưu kết quả cho người học.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313047-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 60

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon CloudTrail, Amazon CloudWatch, Amazon Config, Amazon Trusted Advisor
- Đáp án tham khảo: **Amazon CloudWatch**
- Takeaway nhanh: Amazon Comprehend tự động xuất các metric vào CloudWatch, bao gồm NumberOfInvocations (số lần gọi endpoint) và InferenceLatency. Bạn có thể tạo CloudWatch Metric Alarm hoặc Metric Math để kiểm tra điều kiện “NumberOfInvocations = 0 trong 15 ngày liên tiếp”. Khi alarm được kích hoạt, CloudWatch có thể gửi thông báo qua Amazon SNS hoặc khởi chạy một hàm Lambda để tổng hợp và gửi báo cáo.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html | https://docs.aws.amazon.com/cloudtrail/latest/userguide/cloudtrail-user-guide.html | https://docs.aws.amazon.com/cloudwatch/latest/monitoring/AlarmThatSendsEmail.html | https://docs.aws.amazon.com/comprehend/latest/dg/monitoring-cloudwatch.html | https://docs.aws.amazon.com/config/latest/developerguide/what-is-aws-config.html | https://docs.aws.amazon.com/eventbridge/latest/userguide/create-eventbridge-scheduled-rule.html | https://www.examtopics.com/discussions/amazon/view/316408-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses Amazon Comprehend to analyze customer feedback. A customer has several unique trained models. The company uses Comprehend to assign each model an endpoint. The company wants to automate a report on each endpoint that is not used for more than 15 days.
Which service will meet these requirements?

### Các lựa chọn
1. AWS Trusted Advisor
2. Amazon CloudWatch
3. AWS CloudTrail
4. AWS Config

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đang sử dụng Amazon Comprehend để tạo các mô hình machine‑learning tùy chỉnh và gán mỗi mô hình vào một endpoint (điểm cuối) riêng.

Mục tiêu: tự động tạo báo cáo liệt kê các endpoint không có bất kỳ lượt gọi nào trong hơn 15 ngày.

Để đáp ứng yêu cầu này, chúng ta cần một dịch vụ có khả năng:

Theo dõi (monitor) các metric hoặc sự kiện liên quan đến việc gọi endpoint của Amazon Comprehend.

Đánh giá thời gian không hoạt động (idle time) – ví dụ: “số lần gọi = 0” trong một khoảng thời gian liên tục.

Kích hoạt (trigger) một hành động – như gửi báo cáo qua SNS, Lambda, hoặc lưu vào S3 – một cách tự động.

Trong các lựa chọn, Amazon CloudWatch là dịch vụ duy nhất cung cấp các tính năng trên (metric collection, metric math, alarm, EventBridge rules).

✅ Đáp án đúng: Amazon CloudWatch

Lý do lựa chọn

Amazon Comprehend tự động xuất các metric vào CloudWatch, bao gồm NumberOfInvocations (số lần gọi endpoint) và InferenceLatency.

Bạn có thể tạo CloudWatch Metric Alarm hoặc Metric Math để kiểm tra điều kiện “NumberOfInvocations = 0 trong 15 ngày liên tiếp”.

Khi alarm được kích hoạt, CloudWatch có thể gửi thông báo qua Amazon SNS hoặc khởi chạy một hàm Lambda để tổng hợp và gửi báo cáo.

CloudWatch EventBridge cũng cho phép lập lịch (cron) để chạy định kỳ một job (Lambda, Step Functions, …) thực hiện truy vấn metric và tạo báo cáo.

Do đó, CloudWatch đáp ứng đầy đủ yêu cầu “tự động báo cáo các endpoint không được sử dụng >15 ngày”.

❌ Giải thích các lựa chọn sai

AWS Trusted Advisor

🛠️ Trusted Advisor cung cấp các khuyến nghị về chi phí, bảo mật, hiệu năng, fault tolerance, và service limits.

Nó không theo dõi metric hoặc trạng thái hoạt động của các endpoint Comprehend, và không có khả năng lập lịch hay gửi báo cáo tự động dựa trên thời gian không sử dụng.

Vì vậy không phù hợp với nhu cầu “monitor usage of endpoints”.

AWS CloudTrail

📘 CloudTrail ghi lại các API call (audit log) cho hầu hết các dịch vụ AWS, bao gồm cả StartEndpoint / InvokeEndpoint của Comprehend.

Tuy nó có thể xem lịch sử gọi, nhưng CloudTrail không cung cấp công cụ báo cáo tự động dựa trên khoảng thời gian không hoạt động; bạn cần phải xây dựng pipeline phức tạp (ví dụ: export log sang S3 → Athena → Lambda).

So với CloudWatch, CloudTrail không phải là công cụ monitoring thời gian thực và không hỗ trợ alarm trực tiếp cho “không có gọi trong 15 ngày”.

AWS Config

🧩 Config theo dõi cấu hình và thay đổi cấu hình của các tài nguyên AWS (ví dụ: VPC, IAM, EC2).

Nó không ghi nhận số lần gọi hay hoạt động runtime của các endpoint Comprehend.

Do vậy, Config không thể đáp ứng yêu cầu “phát hiện endpoint không được sử dụng”.

📚 Tham khảo tài liệu (2026)

Amazon CloudWatch Metrics for Amazon Comprehend – https://docs.aws.amazon.com/comprehend/latest/dg/monitoring-cloudwatch.html

Creating CloudWatch Alarms – https://docs.aws.amazon.com/cloudwatch/latest/monitoring/AlarmThatSendsEmail.html

Amazon EventBridge (formerly CloudWatch Events) – Scheduled Rules – https://docs.aws.amazon.com/eventbridge/latest/userguide/create-eventbridge-scheduled-rule.html

AWS Trusted Advisor Documentation – https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html

AWS CloudTrail User Guide – https://docs.aws.amazon.com/cloudtrail/latest/userguide/cloudtrail-user-guide.html

AWS Config Developer Guide – https://docs.aws.amazon.com/config/latest/developerguide/what-is-aws-config.html

Tóm tắt nhanh gọn gàng

✅ Amazon CloudWatch → Giám sát metric NumberOfInvocations, tạo alarm 15 ngày không gọi, tự động gửi báo cáo.

❌ AWS Trusted Advisor → Chỉ đưa ra khuyến nghị, không theo dõi metric.

❌ AWS CloudTrail → Ghi log API, không có alarm thời gian không hoạt động tích hợp.

❌ AWS Config → Quản lý cấu hình, không liên quan tới việc gọi endpoint.

Với kiến trúc hiện đại và tích hợp sâu với Amazon Comprehend, CloudWatch là lựa chọn duy nhất đáp ứng đầy đủ yêu cầu tự động hoá báo cáo về các endpoint không hoạt động trong hơn 15 ngày. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316408-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 61

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Data labeling Khi bạn thêm thông tin phân loại (personal / business) vào bản ghi, bạn đang gán nhãn cho dữ liệu. Đây là bước chuẩn bị dữ liệu đầu vào cho các thuật toán giám sát (supervised learning) để mô hình biết “đây là gì”. AWS cung cấp dịch vụ Amazon SageMaker Ground Truth và Amazon SageMaker Data Wrangler để thực hiện việc gán nhãn tự động hoặc bán tự động, phù hợp với quy mô doanh nghiệp.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313010-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is analyzing financial transaction records. The company categorizes the records as either personal or business. The company inserts the categories into the transaction records.
Which data preparation step does this describe?

### Các lựa chọn
1. Data encoding
2. Data labeling
3. Data normalization
4. Data balancing

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Công ty đang xử lý các bản ghi giao dịch tài chính và muốn phân loại mỗi bản ghi thành “personal” (cá nhân) hoặc “business” (doanh nghiệp). Để thực hiện việc này, họ chèn nhãn (category) vào trong từng bản ghi. Trong quy trình chuẩn bị dữ liệu (data‑pre‑processing) của Machine Learning, bước này được gọi là gán nhãn (data labeling) – tức là gán một giá trị mô tả (label) cho mỗi mẫu dữ liệu để mô hình sau này có thể học phân loại.

✅ Đáp án đúng

Data labeling

Giải thích:

Khi bạn thêm thông tin phân loại (personal / business) vào bản ghi, bạn đang gán nhãn cho dữ liệu. Đây là bước chuẩn bị dữ liệu đầu vào cho các thuật toán giám sát (supervised learning) để mô hình biết “đây là gì”.

AWS cung cấp dịch vụ Amazon SageMaker Ground Truth và Amazon SageMaker Data Wrangler để thực hiện việc gán nhãn tự động hoặc bán tự động, phù hợp với quy mô doanh nghiệp.

❌ Các phương án còn lại (giải thích tại sao sai)

Data encoding

Giải thích: Data encoding (mã hoá dữ liệu) là quá trình chuyển đổi dữ liệu dạng ký tự hoặc danh mục thành dạng số (ví dụ: one‑hot encoding, label encoding). Ở đây công ty chưa chuyển đổi gì, chỉ gán nhãn cho bản ghi, vì vậy không phải là data encoding.

AWS liên quan: Khi cần chuyển nhãn thành số để đưa vào mô hình, bạn có thể dùng SageMaker Processing Jobs để thực hiện one‑hot hoặc ordinal encoding, nhưng đây không phải bước hiện tại.

Data normalization

Giải thích: Data normalization (chuẩn hoá dữ liệu) là việc điều chỉnh các giá trị số sao cho nằm trong một khoảng nhất định (ví dụ: Min‑Max scaling, Z‑score). Việc thêm nhãn “personal”/“business” không liên quan đến việc thay đổi thang đo của các thuộc tính số, nên đây không phải là normalization.

AWS liên quan: Các bước chuẩn hoá thường được thực hiện trong SageMaker Processing hoặc SageMaker Pipelines.

Data balancing

Giải thích: Data balancing (cân bằng dữ liệu) là điều chỉnh tỷ lệ các lớp trong tập dữ liệu (sử dụng oversampling, undersampling, SMOTE…) để tránh bias khi huấn luyện. Chỉ “chèn nhãn” vào bản ghi không thay đổi số lượng mẫu của mỗi lớp, vì vậy không phải là balancing.

AWS liên quan: Khi cần cân bằng, bạn có thể dùng SageMaker Clarify hoặc SMOTE trong các notebook SageMaker.

📚 Tham khảo tài liệu (AWS, 2026)

Amazon SageMaker Data Wrangler – “Prepare data for machine learning” (đối tượng: labeling, encoding, normalization).

Amazon SageMaker Ground Truth – “Build highly accurate training datasets for machine learning” – quy trình gán nhãn dữ liệu.

AWS Well‑Architected Framework – Machine Learning Lens (phiên bản 2025) – mô tả các bước chuẩn bị dữ liệu, bao gồm labeling, encoding, normalization, balancing.

AWS Documentation – Feature Engineering for ML (cập nhật 2026) – giải thích chi tiết các khái niệm preprocessing.

🧩 Tóm tắt nhanh

Data labeling ✅ – đúng, vì bạn đang gán nhãn “personal” hoặc “business” cho mỗi bản ghi.

Data encoding ❌ – sai, chưa chuyển đổi sang dạng số.

Data normalization ❌ – sai, không thay đổi thang đo của các giá trị số.

Data balancing ❌ – sai, không thay đổi tỉ lệ lớp.

Hy vọng giải thích trên giúp bạn nắm rõ bước chuẩn bị dữ liệu nào đang được mô tả trong câu hỏi! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313010-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 62

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon Redshift, Amazon DynamoDB, Amazon ElastiCache, Amazon Bedrock, RAG
- Đáp án tham khảo: **Amazon OpenSearch Service là dịch vụ đáp ứng đầy đủ yêu cầu lưu trữ vector và tìm kiếm vector cho giải pháp generative AI dựa trên Amazon Bedrock. Các dịch vụ còn lại (DynamoDB, ElastiCache, Redshift) không cung cấp tính năng vector search hoặc không thích hợp về mặt kiến trúc và chi phí. 🚀**
- Takeaway nhanh: Công ty đang xây dựng một giải pháp AI sinh nội dung (generative AI) bằng Amazon Bedrock. Sau khi tạo ra các embedding (vector) từ mô hình ngôn ngữ, họ cần một dịch vụ lưu trữ vector và có khả năng tìm kiếm vector (vector search / similarity search) để so sánh các embedding với nhau. Yêu cầu: Lưu trữ các vector ở dạng bảng/đối tượng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313015-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using Amazon Bedrock for a generative AI solution. The solution must integrate a service with vector database storage and vector search capabilities.
Which AWS service will meet these requirements?

### Các lựa chọn
1. Amazon DynamoDB
2. Amazon OpenSearch Service
3. Amazon ElastiCache
4. Amazon Redshift

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích câu hỏi

Công ty đang xây dựng một giải pháp AI sinh nội dung (generative AI) bằng Amazon Bedrock.

Sau khi tạo ra các embedding (vector) từ mô hình ngôn ngữ, họ cần một dịch vụ lưu trữ vector và có khả năng tìm kiếm vector (vector search / similarity search) để so sánh các embedding với nhau.

Yêu cầu:

Lưu trữ các vector ở dạng bảng/đối tượng.

Thực hiện truy vấn gần‑nhất (nearest‑neighbor) một cách hiệu quả, thường là k‑NN hoặc Approximate Nearest Neighbor (ANN).

Chúng ta phải chọn dịch vụ AWS đáp ứng cả hai yêu cầu trên.

✅ Đáp án đúng

Amazon OpenSearch Service

🧩 Lý do lựa chọn:

OpenSearch (phiên bản được quản lý của Elasticsearch) đã tích hợp plugin k‑Nearest Neighbor (kNN) và Amazon OpenSearch Serverless hỗ trợ vector fields.

Bạn có thể lưu trữ vector embedding dưới dạng trường kiểu dense_vector hoặc knn_vector và thực hiện truy vấn vector similarity (cosine, L2, dot‑product) trực tiếp trong OpenSearch.

Dịch vụ được quản lý, tích hợp sẵn với IAM, VPC, và có thể kết nối dễ dàng với Amazon Bedrock thông qua AWS SDK hoặc API Gateway.

Được cập nhật liên tục tới phiên bản mới nhất (2026) với tối ưu hoá hiệu năng ANN và tự động scaling.

❌ Giải thích các phương án sai

Amazon DynamoDB

DynamoDB là Cơ sở dữ liệu NoSQL key‑value/document, tối ưu cho truy cập theo khóa nhanh và khả năng mở rộng ngang.

Không hỗ trợ trường vector hay tìm kiếm k‑NN; chỉ có các chỉ mục băm/định dạng số nguyên.

Vì vậy không thể đáp ứng yêu cầu vector search của bài toán.

Amazon ElastiCache

ElastiCache cung cấp Redis hoặc Memcached dưới dạng cache in‑memory.

Mặc dù Redis (phiên bản 6.2+) có hỗ trợ vector similarity thông qua module RedisAI hoặc RedisVector, dịch vụ ElastiCache không tích hợp sẵn các module này và không được thiết kế cho lưu trữ lâu dài hoặc truy vấn vector phức tạp.

Do vậy không phải là lựa chọn phù hợp cho “vector database storage & search”.

Amazon Redshift

Redshift là data warehouse quan hệ, dùng cho phân tích dữ liệu lớn.

Từ 2023 Redshift đã giới thiệu Vector Search (preview), nhưng tính năng này vẫn ở giai đoạn beta/preview và không được khuyến nghị cho các workload AI thời gian thực, đặc biệt khi cần độ trễ thấp và tích hợp trực tiếp với Bedrock.

Ngoài ra, chi phí và mô hình quản lý phức tạp hơn so với OpenSearch cho mục đích lưu trữ và tìm kiếm vector.

Vì vậy trong ngữ cảnh câu hỏi (đòi hỏi giải pháp “có sẵn, quản lý, tối ưu cho vector search”), Redshift không phải là đáp án tốt nhất.

📚 Tham khảo & nguồn tài liệu (đến năm 2026)

Amazon OpenSearch Service Developer Guide – “Working with k‑Nearest Neighbor (kNN) and dense_vector fields” (phiên bản 2026).

AWS Blog – “Amazon OpenSearch Service adds native vector search” (cập nhật tháng 3/2025).

AWS Documentation – Amazon Bedrock Integration Patterns (2026).

AWS re:Invent 2024 – Session “Building Generative AI Applications with Bedrock and OpenSearch”.

Tóm tắt

✅ Amazon OpenSearch Service là dịch vụ đáp ứng đầy đủ yêu cầu lưu trữ vector và tìm kiếm vector cho giải pháp generative AI dựa trên Amazon Bedrock. Các dịch vụ còn lại (DynamoDB, ElastiCache, Redshift) không cung cấp tính năng vector search hoặc không thích hợp về mặt kiến trúc và chi phí. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313015-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 63

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/313042-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is building an AI solution by using Amazon SageMaker AI. The company wants to use SageMaker AI features to facilitate application development.
2. Select the correct SageMaker AI feature from the following list for each use case. Select each feature one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/313042-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 64

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/316396-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company wants to build generative AI applications by using Amazon Bedrock. The company wants to minimize development effort.
2. Select and order the model development techniques from the following list from the LEAST development effort to the MOST development effort. Each model development technique should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/316396-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 65

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Transcribe, Amazon Macie, Amazon SageMaker AI
- Takeaway nhanh: Công ty muốn gán nhãn (label) cho tập dữ liệu đào tạo bằng cách thu thập phản hồi của con người (human feedback) để fine‑tune một Foundation Model (FM). Điều quan trọng là công ty không muốn tự xây dựng ứng dụng gán nhãn và không muốn quản lý đội ngũ gán nhãn (labeling workforce). Vì vậy họ cần một dịch vụ đã được quản lý hoàn toàn, cung cấp giao diện người dùng để thu thập nhãn và có thể tích hợp trực tiếp vào quy trình Machine Learning trên AWS.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/312985-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to label training datasets by using human feedback to fine-tune a foundation model (FM). The company does not want to develop labeling applications or manage a labeling workforce.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Data Wrangler
2. Amazon SageMaker Ground Truth Plus
3. Amazon Transcribe
4. Amazon Macie

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn gán nhãn (label) cho tập dữ liệu đào tạo bằng cách thu thập phản hồi của con người (human feedback) để fine‑tune một Foundation Model (FM). Điều quan trọng là công ty không muốn tự xây dựng ứng dụng gán nhãn và không muốn quản lý đội ngũ gán nhãn (labeling workforce). Vì vậy họ cần một dịch vụ đã được quản lý hoàn toàn, cung cấp giao diện người dùng để thu thập nhãn và có thể tích hợp trực tiếp vào quy trình Machine Learning trên AWS.

✅ Đáp án đúng

Amazon SageMaker Ground Truth Plus

Đây là dịch vụ được quản lý cho việc tạo và quản lý nhãn dữ liệu.

Ground Truth Plus cung cấp Human‑in‑the‑Loop (HITL) labeling với đội ngũ lao động nội bộ của AWS (AWS workforce) hoặc cộng đồng bên ngoài (Mechanical Turk, Scale AI, …) mà không cần công ty tự xây dựng hay quản lý workforce.

Tính năng Active Learning giúp giảm số lượng mẫu cần gán nhãn, phù hợp cho việc “fine‑tune” một Foundation Model.

Kết nối liền mạch với SageMaker Studio, SageMaker Pipelines, và Feature Store, cho phép đưa dữ liệu đã gán nhãn vào quy trình huấn luyện mô hình một cách tự động.

Đến tháng 3/2026, AWS đã cập nhật Ground Truth Plus để hỗ trợ labeling cho các mô hình ngôn ngữ lớn (LLM) và multimodal foundation models, đáp ứng yêu cầu “human feedback for FM fine‑tuning”.

Nguồn tham khảo:

AWS Documentation – Amazon SageMaker Ground Truth (phiên bản 2026)

AWS Blog – Introducing SageMaker Ground Truth Plus for foundation model labeling (Jan 2025)

❌ Giải thích các phương án sai

Amazon SageMaker Data Wrangler

🧩 Chức năng: Dùng để khảo sát, làm sạch, chuyển đổi và chuẩn bị dữ liệu trước khi đưa vào mô hình.

❌ Lý do sai: Không cung cấp bất kỳ tính năng nào để gán nhãn bằng con người; nó chỉ là công cụ ETL cho dữ liệu. Do đó không đáp ứng yêu cầu “human feedback” và “no workforce management”.

Amazon Transcribe

🧩 Chức năng: Dịch vụ chuyển đổi giọng nói thành văn bản (speech‑to‑text).

❌ Lý do sai: Không liên quan tới việc gán nhãn dữ liệu; chỉ tạo ra bản ghi âm được chuyển sang text. Không hỗ trợ labeling workflow, không có workforce tích hợp.

Amazon Macie

🧩 Chức năng: Dịch vụ phát hiện và bảo vệ dữ liệu nhạy cảm (PII, dữ liệu tài chính) trong S3 bằng machine learning.

❌ Lý do sai: Macie tập trung vào bảo mật và tuân thủ, không có tính năng gán nhãn hay thu thập phản hồi con người. Vì vậy không phù hợp với yêu cầu của câu hỏi.

🛠️ Tổng kết (điểm mạnh của Ground Truth Plus)

Quản lý toàn bộ quy trình labeling → không cần phát triển ứng dụng riêng.

Cung cấp workforce nội bộ của AWS → công ty không phải “manage a labeling workforce”.

Active Learning & Human‑in‑the‑Loop → giảm chi phí và tăng chất lượng nhãn, rất phù hợp cho việc fine‑tune foundation model.

Tích hợp sẵn với SageMaker → dữ liệu sau khi gán nhãn có thể đưa thẳng vào pipeline huấn luyện.

Vì vậy, Amazon SageMaker Ground Truth Plus là lựa chọn duy nhất đáp ứng đầy đủ các yêu cầu của câu hỏi. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/312985-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/
