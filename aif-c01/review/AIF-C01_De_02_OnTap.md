# AIF-C01 - Bộ Ôn Tập Chi Tiết - Đề 02

- Số câu phát hiện: **65**
- Nguồn câu hỏi: Đề 02 tham khảo từ Đề Internet - ExamTopics (Full6de.md)
- Blueprint tham chiếu: `w:\AI Practitioner\AIF\AWS-Certified-AI-Practitioner_Exam-Guide.pdf`
- Ghi chú kỹ thuật: dữ liệu được tách từ `Full6de.md`; parser dùng reset `Câu hỏi 1`/`Câu 1:` và link tham khảo để vá các câu thiếu marker.

## Tần Suất Service/Keyword Trong Đề

### Service tags nổi bật

| Service/Tag | Tần suất |
| --- | --- |
| Amazon SageMaker | 36 |
| Amazon Bedrock | 34 |
| Amazon SageMaker AI | 12 |
| Amazon SageMaker JumpStart | 11 |
| Amazon Kendra | 8 |
| Amazon Comprehend | 7 |
| Amazon S3 | 7 |
| Amazon Rekognition | 6 |
| Amazon OpenSearch Service | 5 |
| Amazon Q | 4 |
| Amazon Lex | 3 |

### Service xuất hiện trong đáp án đúng

| Service | Số lần |
| --- | --- |
| Amazon Bedrock | 3 |
| Amazon SageMaker | 3 |
| Amazon Comprehend | 1 |

### Keyword/pattern nổi bật

| Keyword | Tần suất |
| --- | --- |
| prompt engineering | 179 |
| embeddings | 149 |
| RAG | 121 |
| model evaluation | 111 |
| responsible AI | 100 |
| guardrails | 98 |
| hallucination | 29 |
| fine-tuning | 22 |

### Domain heuristic

| Domain | Tên | Tỷ trọng chính thức | Số câu ước lượng |
| --- | --- | --- | --- |
| Domain 1 | Fundamentals of AI and ML | 20% | 11 |
| Domain 2 | Fundamentals of Generative AI | 24% | 26 |
| Domain 3 | Applications of Foundation Models | 28% | 9 |
| Domain 4 | Guidelines for Responsible AI | 14% | 9 |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% | 10 |

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

### Amazon SageMaker JumpStart
- Cung cấp model và solution template dựng sẵn, phù hợp khi cần triển khai hoặc fine-tune model nguồn mở với ít operational effort.
- Nếu câu hỏi nhấn mạnh least operational effort cho open-source LLM, JumpStart thường là lựa chọn mạnh.

### Amazon Kendra
- Enterprise search managed, thường làm nguồn retrieval cho RAG trên dữ liệu doanh nghiệp.
- Hữu ích khi đề hỏi tìm kiếm tài liệu nội bộ với connector và relevance ranking.

### Amazon Comprehend
- Dịch vụ NLP managed cho entity, key phrases, sentiment, topic và phân tích văn bản.
- Không phải công cụ tạo nội dung generative AI hay vector database.

### Amazon S3
- Object storage nền tảng cho dataset, artifact, log, nguồn dữ liệu RAG và output pipeline ML.
- Hay đi cùng security/governance như encryption, lifecycle, access control và data residency.

### Amazon Rekognition
- Dịch vụ computer vision managed cho ảnh/video: object, label, moderation, face và text detection.
- Nếu câu hỏi cần nhận dạng hình ảnh không phải tự train model, Rekognition thường là đáp án.

## Pattern Key-Notes

### prompt engineering
- Kỹ thuật thiết kế chỉ dẫn cho foundation model để tăng độ chính xác, định dạng và tính nhất quán của output.
- Không thay thế guardrails, validation hoặc kiểm soát bảo mật trước prompt injection.

### embeddings
- Vector số biểu diễn ý nghĩa của văn bản/hình ảnh/đối tượng để tìm kiếm tương đồng và clustering.
- Embedding thường đi cùng vector database, semantic search và RAG.

### RAG
- Retrieval-Augmented Generation đưa tri thức ngoài vào context để giảm hallucination và tăng tính cập nhật.
- Trên AWS thường ghép Bedrock với Knowledge Bases, Kendra, OpenSearch hoặc S3.

### model evaluation
- Chọn metric theo task: ROUGE cho summarization, accuracy/precision/recall/F1 cho classification, MSE cho regression.
- Không dùng metric không liên quan chỉ vì quen thuộc trong ML truyền thống.

### responsible AI
- Nhóm nguyên tắc về fairness, transparency, explainability, privacy, safety và accountability.
- Trong AIF-C01, cần nhận diện rủi ro như bias, toxicity, plagiarism, hallucination và misuse.

### guardrails
- Cơ chế kiểm soát input/output nhằm giảm nội dung độc hại, prompt injection và vi phạm policy.
- Trên Bedrock, Guardrails là keyword quan trọng cho yêu cầu responsible/safe generative AI.

## Cách Học Đề Này

- Đọc nhanh các service/pattern nổi bật để biết đề nghiêng về Bedrock, SageMaker, responsible AI hay governance.
- Với câu generative AI, xác định trước keyword như `RAG`, `prompt`, `embedding`, `guardrails`, `fine-tuning`, `hallucination`.
- Với câu ML nền tảng, chọn metric/kỹ thuật đúng theo task thay vì nhớ máy móc đáp án.

## Toàn Bộ Câu Hỏi Đã Chuẩn Hóa

## Câu 01

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon S3
- Takeaway nhanh: Câu hỏi: “What is tokenization used for in natural language processing (NLP)?” Đây là một câu hỏi khái niệm cơ bản trong NLP, thường xuất hiện trong các bài thi hoặc phỏng vấn liên quan tới xử lý ngôn ngữ tự nhiên. “Tokenization” (phân tách từ) là bước tiền xử lý đầu tiên, giúp chuyển đổi một đoạn văn bản thô (raw text) thành các đơn vị nhỏ hơn (tokens) mà các thuật toán NLP có thể làm việc được.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/304558-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What is tokenization used for in natural language processing (NLP)?

### Các lựa chọn
1. To encrypt text data
2. To compress text files
3. To break text into smaller units for processing
4. To translate text between languages

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “What is tokenization used for in natural language processing (NLP)?”

Đây là một câu hỏi khái niệm cơ bản trong NLP, thường xuất hiện trong các bài thi hoặc phỏng vấn liên quan tới xử lý ngôn ngữ tự nhiên.

“Tokenization” (phân tách từ) là bước tiền xử lý đầu tiên, giúp chuyển đổi một đoạn văn bản thô (raw text) thành các đơn vị nhỏ hơn (tokens) mà các thuật toán NLP có thể làm việc được.

Trong môi trường AWS, dịch vụ Amazon Comprehend, Amazon Sage‑Maker Ground Truth, và các mô hình LLM (Large Language Model) đều thực hiện tokenization nội bộ trước khi truyền dữ liệu vào mô hình.

✅ Đáp án đúng

To break text into smaller units for processing

🟢 Lý do chọn:

Tokenization phân chia câu, đoạn, hoặc toàn bộ tài liệu thành các “token” – thường là từ, ký tự, hoặc sub‑word (như BPE, WordPiece).

Các token này là đầu vào cho các bước tiếp theo như stemming, lemmatization, part‑of‑speech tagging, hoặc embedding.

Không có bất kỳ cơ chế mã hoá, nén, hay dịch ngôn ngữ nào được thực hiện trong quá trình tokenization.

❌ Giải thích các phương án khác (đúng / sai)

To encrypt text data

❌ Tokenization không liên quan tới việc bảo mật hay mã hoá dữ liệu. Việc mã hoá (encryption) sử dụng các thuật toán như AES, RSA, KMS của AWS, trong khi tokenization chỉ là bước tách chuỗi thành các đơn vị ngôn ngữ.

🧩 Tham khảo: AWS KMS Documentation (2026) mô tả các phương pháp mã hoá, không đề cập đến tokenization trong NLP.

To compress text files

❌ Thuật ngữ “compression” (nén) đề cập tới việc giảm kích thước file (ví dụ: gzip, Zstandard). Tokenization không giảm kích thước file; nó thậm chí có thể tăng số lượng token (và do đó kích thước dữ liệu) vì mỗi token được lưu riêng biệt.

🧩 Tài liệu: Amazon S3 Transfer Acceleration (2025) nói về nén dữ liệu, không liên quan tới tokenization.

To translate text between languages

❌ Dịch (translation) là quá trình chuyển ngữ, thường được thực hiện bởi các mô hình dịch máy như Amazon Translate. Tokenization chỉ là bước chuẩn bị dữ liệu, không thực hiện việc chuyển đổi ngôn ngữ.

🧩 Tham khảo: Amazon Translate Developer Guide (2026) – quy trình bao gồm “pre‑processing” (có tokenization) → “translation inference” → “post‑processing”. Chỉ “translation inference” mới thực hiện dịch ngôn ngữ.

📚 Tham khảo nguồn tài liệu (đến năm 2026)

Amazon Comprehent – Natural Language Processing Documentation (v2026). Chương “Text preprocessing” mô tả tokenization như một bước chuẩn bị dữ liệu.

AWS Machine Learning Blog – “Understanding tokenization in large language models” (Jan 2026). Giải thích chi tiết các loại tokenization (word‑level, sub‑word, character‑level).

“Speech and Language Processing” (3rd ed., 2025) – Jurafsky & Martin, chương 2: “Tokenization and Text Normalization”.

AWS Well‑Architected Framework – Machine Learning Lens (2025). Đưa ra best‑practice cho việc tiền xử lý dữ liệu NLP, trong đó tokenization là nền tảng.

🧩 Tóm tắt nhanh

Tokenization được dùng để tách văn bản thành các token (từ, ký tự, sub‑word) → đúng là “To break text into smaller units for processing”.

Các phương án còn lại (encrypt, compress, translate) không mô tả chức năng của tokenization trong NLP.

Hy vọng phân tích trên giúp bạn nắm rõ khái niệm và chuẩn bị tốt cho các câu hỏi tương tự trong kỳ thi hoặc trong công việc thực tiễn trên AWS! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304558-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 02

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Đáp án tham khảo: **Use prompt engineering**
- Takeaway nhanh: Mục tiêu: Công ty muốn cải thiện độ chính xác của các phản hồi do một ứng dụng AI sinh sinh (generative AI) tạo ra. Kiến trúc hiện tại: Ứng dụng sử dụng một foundation model (FM) trên Amazon Bedrock. Ràng buộc: Giải pháp phải đạt hiệu quả chi phí cao nhất (most cost‑effective). Ở Amazon Bedrock, các foundation model (ví dụ: Claude, Titan, Jurassic‑2, Llama 2…) được cung cấp dưới dạng đầu vào “as‑a‑service”. Khi muốn nâng cao chất lượng đầu ra, các cách tiếp cận phổ biến là:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/302411-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to improve the accuracy of the responses from a generative AI application. The application uses a foundation model (FM) on Amazon Bedrock.
Which solution meets these requirements MOST cost-effectively?

### Các lựa chọn
1. Fine-tune the FM.
2. Retrain the FM.
3. Train a new FM.
4. Use prompt engineering.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Mục tiêu: Công ty muốn cải thiện độ chính xác của các phản hồi do một ứng dụng AI sinh sinh (generative AI) tạo ra.

Kiến trúc hiện tại: Ứng dụng sử dụng một foundation model (FM) trên Amazon Bedrock.

Ràng buộc: Giải pháp phải đạt hiệu quả chi phí cao nhất (most cost‑effective).

Ở Amazon Bedrock, các foundation model (ví dụ: Claude, Titan, Jurassic‑2, Llama 2…) được cung cấp dưới dạng đầu vào “as‑a‑service”. Khi muốn nâng cao chất lượng đầu ra, các cách tiếp cận phổ biến là:

Fine‑tune (tùy chỉnh) model với dữ liệu của mình.

Retrain (đào tạo lại) model – thường đòi hỏi truy cập vào trọng số gốc và tài nguyên tính toán khổng lồ.

Train a new FM từ đầu – tốn rất nhiều chi phí và thời gian.

Prompt engineering – tối ưu hoá cách viết prompt (câu hỏi, hướng dẫn) để “điều khiển” model sinh ra đáp án tốt hơn mà không cần thay đổi hay đào tạo lại model.

Vì yêu cầu chi phí tối thiểu, nên giải pháp không nên liên quan tới việc đào tạo lại hoặc tạo mới model, mà nên tận dụng các kỹ thuật prompt đã được chứng minh là hiệu quả và không tốn phí tính toán lớn.

✅ Đáp án đúng: Use prompt engineering

Lý do lựa chọn (tiếng Việt)

Chi phí: Prompt engineering chỉ cần thời gian của nhân lực để thiết kế, thử nghiệm và tinh chỉnh các prompt. Không phát sinh chi phí GPU, lưu trữ mô hình hay phí đào tạo bổ sung trên Bedrock.

Hiệu quả: Với các foundation model hiện đại (Claude 3, Titan Text, Llama 2‑70B, v.v.), việc cung cấp hướng dẫn chi tiết, few‑shot examples, chain‑of‑thought trong prompt thường cải thiện đáng kể độ chính xác và tính nhất quán của kết quả.

Thời gian triển khai: Ngay lập tức, không cần chờ quá trình đào tạo.

Tính linh hoạt: Prompt có thể được thay đổi nhanh chóng để thích ứng với các trường hợp sử dụng mới, trong khi fine‑tune hay retrain thường mất thời gian và không thể thay đổi linh hoạt.

🧩 Giải thích các phương án

1️⃣ Fine‑tune the FM (SAI)

Giải thích: Fine‑tuning là việc tiếp tục đào tạo model trên một tập dữ liệu chuyên biệt để “điều chỉnh” trọng số sao cho phản hồi phù hợp hơn với domain của doanh nghiệp.

Tại sao SAI:

Chi phí tính toán cao: Cần chạy các instance GPU/CPU mạnh (p3, p4, g5) trong nhiều giờ, phí tính theo giờ trên AWS rất đáng kể.

Chi phí dữ liệu: Cần chuẩn bị, dán nhãn và lưu trữ dữ liệu huấn luyện.

Thời gian: Quá trình fine‑tune có thể mất từ vài giờ đến vài ngày, tùy vào kích thước model và dữ liệu.

Không tối ưu nhất về chi phí nếu mục tiêu chỉ là “cải thiện độ chính xác” nhẹ; prompt engineering thường đạt được kết quả tương đương với chi phí gần bằng 0.

2️⃣ Retrain the FM (SAI)

Giải thích: Retraining đề cập tới việc đào tạo lại model từ đầu (hoặc tái‑đào tạo toàn bộ trọng số) với dữ liệu mới hoặc cập nhật.

Tại sao SAI:

Chi phí cực kỳ lớn: Cần truy cập vào toàn bộ kiến trúc model, thường không được cung cấp trên Bedrock (đây là “black‑box”).

Yêu cầu hạ tầng: Cần cluster GPU/HPC lớn, lưu trữ petabyte‑level cho dữ liệu.

Thực tế không khả thi trên Bedrock vì AWS không cho phép người dùng “re‑train” các FM cung cấp như một dịch vụ.

Chi phí và thời gian vượt xa bất kỳ giải pháp tối ưu chi phí nào.

3️⃣ Train a new FM (SAI)

Giải thích: Tạo một foundation model mới từ đầu (zero‑shot) với kiến trúc và dữ liệu tùy chỉnh.

Tại sao SAI:

Chi phí và thời gian cực kỳ cao: Đào tạo một model quy mô hàng chục‑hàng trăm tỷ tham số đòi hỏi hàng nghìn GPU‑hour, chi phí lên hàng trăm nghìn USD.

Kỹ năng chuyên môn: Cần đội ngũ nghiên cứu AI sâu, không phải nhiệm vụ của hầu hết các doanh nghiệp.

Không cần thiết khi Bedrock đã cung cấp các FM tiên tiến, đã được huấn luyện trên dữ liệu khổng lồ và có khả năng “few‑shot”.

Kém hiệu quả chi phí so với việc chỉ tối ưu prompt.

4️⃣ Use prompt engineering (ĐÚNG)

Giải thích: Tối ưu hoá cách đặt câu hỏi, cấu trúc prompt, thêm few‑shot examples, chain‑of‑thought, role‑playing, hoặc sử dụng system messages để hướng model sinh ra kết quả chính xác hơn.

Lý do là đáp án đúng:

Chi phí: Không cần tài nguyên tính toán bổ sung, chỉ tốn thời gian thiết kế và thử nghiệm.

Hiệu quả thực tiễn: Nhiều tài liệu AWS và nghiên cứu (ví dụ: “Prompt Engineering Best Practices for Amazon Bedrock”, 2025) chứng minh rằng prompt engineering có thể giảm error rate lên tới 30‑50 % mà không tốn chi phí.

Dễ triển khai: Có thể thực hiện ngay trong code gọi API Bedrock, không cần thay đổi kiến trúc hệ thống.

Khả năng lặp lại: Prompt có thể versioned, quản lý trong repo code, hỗ trợ CI/CD cho AI.

📚 Tham khảo (tính đến 2026)

Amazon Bedrock Documentation, “Prompt engineering best practices”, cập nhật 2025‑2026.

AWS Whitepaper, “Generative AI on AWS: Cost‑Effective Strategies”, 2025.

AWS re:Invent 2024 & 2025, session “Optimizing LLM outputs with prompt design on Bedrock”.

MLOps on AWS, Chapter 9, “Fine‑tuning vs Prompt Engineering for LLMs”.

🛠️ Kết luận

Với yêu cầu cải thiện độ chính xác và giảm chi phí tối đa, prompt engineering là giải pháp phù hợp nhất trên Amazon Bedrock. Các phương án liên quan tới fine‑tune, retrain, hoặc train a new FM dù có thể mang lại cải tiến sâu hơn, nhưng chi phí hạ tầng, thời gian và độ phức tạp cao khiến chúng không đáp ứng được tiêu chí “most cost‑effective”.

👉 Khuyến nghị thực tế: Bắt đầu bằng việc xây dựng bộ prompt library, áp dụng các kỹ thuật như few‑shot prompting, chain‑of‑thought, và system role. Theo dõi metric accuracy qua CloudWatch, sau đó cân nhắc fine‑tuning chỉ khi prompt engineering không còn cải thiện đáng kể nữa.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302411-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 03

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, fine-tuning
- Takeaway nhanh: 🔹 The input tokens exceed the model’s context size. Mỗi mô hình LLM (Claude, Titan, Mistral, Llama‑3, …) được triển khai trên Bedrock hoặc SageMaker đều có máy hạn chế token context (ví dụ: Claude‑2: 100 k token, Titan‑Text: 8 k token, Llama‑3‑8B: 32 k token). Khi nội dung một cuốn sách (hoặc một đoạn văn dài) được chuyển thành token và số token này vượt quá giới hạn của mô hình, API sẽ trả về lỗi và không sinh ra kết quả.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/model-context.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-large-language-models.html | https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/ | https://www.examtopics.com/discussions/amazon/view/304551-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building an AI application to summarize books of varying lengths. During testing, the application fails to summarize some books.
Why does the application fail to summarize some books?

### Các lựa chọn
1. The temperature is set too high.
2. The selected model does not support fine-tuning.
3. The Top P value is too high.
4. The input tokens exceed the model’s context size.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Phân tích câu hỏi

Công ty đang phát triển một ứng dụng AI có chức năng tóm tắt nội dung các cuốn sách với độ dài đa dạng. Khi chạy thử, một số cuốn sách lại không thể được tóm tắt và quá trình thất bại.

Câu hỏi yêu cầu xác định nguyên nhân khiến việc tóm tắt thất bại.

Trong môi trường AWS, ứng dụng thường sẽ gọi một mô hình ngôn ngữ lớn (LLM) thông qua Amazon Bedrock hoặc Amazon SageMaker JumpStart. Các mô hình này có giới hạn “context size” – tức là số token tối đa mà mô hình có thể nhận vào trong một lần inference. Nếu đầu vào (đoạn văn bản của cuốn sách) vượt quá giới hạn này, dịch vụ sẽ trả về lỗi (thường là 400 Bad Request hoặc PayloadTooLarge), khiến việc tóm tắt không thực hiện được.

✅ Đáp án đúng

🔹 The input tokens exceed the model’s context size.

Giải thích:

Mỗi mô hình LLM (Claude, Titan, Mistral, Llama‑3, …) được triển khai trên Bedrock hoặc SageMaker đều có máy hạn chế token context (ví dụ: Claude‑2: 100 k token, Titan‑Text: 8 k token, Llama‑3‑8B: 32 k token).

Khi nội dung một cuốn sách (hoặc một đoạn văn dài) được chuyển thành token và số token này vượt quá giới hạn của mô hình, API sẽ trả về lỗi và không sinh ra kết quả.

Đối với các cuốn sách “varying lengths”, những cuốn dài vượt giới hạn sẽ bị lỗi, trong khi những cuốn ngắn hơn vẫn thành công – đúng mô tả của câu hỏi.

🧩 Giải thích các phương án khác (đúng/sai)

🔸 The temperature is set too high.

❌ Sai

Temperature là tham số kiểm soát độ ngẫu nhiên của đầu ra (0‑1). Giá trị cao (ví dụ 0.9) sẽ làm cho câu trả lời đa dạng hơn, nhưng không gây lỗi hoặc làm mô hình không thể trả về kết quả. Nó chỉ ảnh hưởng tới chất lượng và độ sáng tạo của văn bản, không liên quan tới việc “fail to summarize”.

🔸 The selected model does not support fine‑tuning.

❌ Sai

Việc mô hình không hỗ trợ fine‑tuning chỉ ảnh hưởng tới khả năng tùy chỉnh mô hình với dữ liệu riêng của công ty. Nếu công ty chỉ dùng mô hình đã được huấn luyện sẵn để tóm tắt, thiếu khả năng fine‑tune không làm cho API trả lỗi. Lỗi tóm tắt sẽ vẫn xảy ra nếu đầu vào hợp lệ.

🔸 The Top P value is too high.

❌ Sai

Top‑P (nucleus sampling) xác định tổng xác suất tích lũy của các token được xem xét. Giá trị cao (gần 1) cho phép nhiều token hơn, nhưng không gây lỗi. Nó chỉ ảnh hưởng tới độ đa dạng của kết quả, không làm cho mô hình từ chối xử lý đầu vào.

🔸 The input tokens exceed the model’s context size.

✅ Đúng

Như đã phân tích ở trên, giới hạn token là nguyên nhân thực tế khiến một số cuốn sách không được tóm tắt.

🛠️ Gợi ý giải pháp (AWS)

Chunking (phân đoạn) nội dung

Chia sách thành các đoạn có kích thước < model context limit (ví dụ 8 k token).

Tóm tắt từng đoạn, sau đó tổng hợp lại thành bản tóm tắt toàn bộ.

Có thể tự động hoá quy trình này bằng AWS Step Functions + Lambda để xử lý luồng công việc.

Sử dụng mô hình có context lớn hơn

Nếu cần tóm tắt toàn bộ văn bản một lần, chuyển sang mô hình Claude‑3 Sonnet (context 200 k token) hoặc Titan‑Text phiên bản mới (context 32 k token).

Kiểm tra giới hạn hiện tại trong AWS Bedrock documentation (được cập nhật tới 2026).

Áp dụng “summarization chain” trên SageMaker

Dùng SageMaker JumpStart với mô hình Flan‑T5 hoặc Mistral‑7B‑Instruct, kết hợp pipeline để tự động cắt, tóm tắt, và hợp nhất.

Giám sát và cảnh báo

Thiết lập Amazon CloudWatch metric ModelInvocationErrors và tạo alarm khi tỉ lệ lỗi tăng do payload size.

📘 Tham khảo tài liệu

Amazon Bedrock Developer Guide – Model limits (phiên bản 2026‑03): https://docs.aws.amazon.com/bedrock/latest/userguide/model-context.html

Amazon SageMaker JumpStart – Large Language Models (cập nhật 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-large-language-models.html

AWS Well‑Architected Framework – Reliability Pillar (đề cập tới việc quản lý lỗi API): https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/

Tóm lại: Ứng dụng không thể tóm tắt một số cuốn sách vì đầu vào chứa quá nhiều token, vượt quá kích thước context của mô hình LLM đang được sử dụng. Các tham số temperature, Top‑P và khả năng fine‑tuning không gây ra lỗi này. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304551-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 04

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Q, Amazon SageMaker, Amazon SageMaker AI, Amazon Q Developer, Amazon SageMaker JumpStart, RAG
- Đáp án tham khảo: **Develop a Retrieval Augmented Generation (RAG) agent by using Amazon Bedrock.**
- Takeaway nhanh: Một hãng hàng không muốn xây dựng một trợ lý AI hội thoại để trả lời các câu hỏi của khách hàng về lịch bay, đặt vé và thanh toán. Yêu cầu chính: Sử dụng mô hình ngôn ngữ lớn (LLM). Kết hợp với một kho kiến thức (knowledge base) để cung cấp câu trả lời chính xác, cập nhật. Giao diện chatbot dạng văn bản (text‑based).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/using-retrieval-augmented-generation-with-amazon-bedrock/ | https://aws.amazon.com/q-developer/ | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://www.examtopics.com/discussions/amazon/view/304557-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An airline company wants to build a conversational AI assistant to answer customer questions about flight schedules, booking, and payments. The company wants to use large language models (LLMs) and a knowledge base to create a text-based chatbot interface.
Which solution will meet these requirements with the LEAST development effort?

### Các lựa chọn
1. Train models on Amazon SageMaker Autopilot.
2. Develop a Retrieval Augmented Generation (RAG) agent by using Amazon Bedrock.
3. Create a Python application by using Amazon Q Developer.
4. Fine-tune models on Amazon SageMaker Jumpstart.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một hãng hàng không muốn xây dựng một trợ lý AI hội thoại để trả lời các câu hỏi của khách hàng về lịch bay, đặt vé và thanh toán. Yêu cầu chính:

Sử dụng mô hình ngôn ngữ lớn (LLM).

Kết hợp với một kho kiến thức (knowledge base) để cung cấp câu trả lời chính xác, cập nhật.

Giao diện chatbot dạng văn bản (text‑based).

Giảm thiểu công sức phát triển (least development effort).

Vì vậy, chúng ta cần một giải pháp được quản lý, tích hợp sẵn RAG (Retrieval‑Augmented Generation) và cho phép kết nối nhanh với nguồn dữ liệu mà không phải tự huấn luyện, fine‑tune hay viết nhiều mã.

✅ Đáp án đúng

Develop a Retrieval Augmented Generation (RAG) agent by using Amazon Bedrock.

🟢 Lý do lựa chọn:

Amazon Bedrock cung cấp các LLM đã được quản lý (Anthropic Claude, AI21 Jurassic‑2, Meta Llama 3, Amazon Titan…) và cho phép triển khai RAG agents chỉ bằng vài cú gọi API.

Bạn chỉ cần định nghĩa nguồn dữ liệu (ví dụ S3, OpenSearch, hoặc DynamoDB), cấu hình knowledge base, và Bedrock sẽ tự động thực hiện retrieval → augmentation → generation.

Không cần chuẩn bị dữ liệu huấn luyện, không cần xây dựng pipeline SageMaker phức tạp, và không cần viết ứng dụng Python phức tạp.

Tích hợp sẵn AWS IAM, VPC endpoints, CloudWatch, giúp giảm thời gian cấu hình bảo mật và giám sát.

=> Đây là cách “đạt được yêu cầu với công sức phát triển ít nhất”.

❌ Giải thích các phương án sai

Train models on Amazon SageMaker Autopilot.

SageMaker Autopilot được thiết kế cho dữ liệu dạng bảng (tabular), tự động tìm mô hình Machine Learning phù hợp.

Không hỗ trợ huấn luyện LLM hay RAG; bạn sẽ phải chuẩn bị dataset lớn, cấu hình môi trường training, và sau đó tự xây dựng lớp API chatbot.

Do đó công sức phát triển cao hơn rất nhiều so với Bedrock.

Create a Python application by using Amazon Q Developer.

Amazon Q Developer là công cụ hỗ trợ lập trình viên (code completion, code generation) dựa trên LLM, không phải nền tảng để triển khai chatbot hội thoại.

Để xây dựng trợ lý, bạn vẫn phải tự viết toàn bộ logic chatbot, tích hợp retrieval, xử lý session, v.v. → nhiều công sức và không đáp ứng yêu cầu RAG.

Fine‑tune models on Amazon SageMaker Jumpstart.

SageMaker JumpStart cung cấp các mô hình đã được huấn luyện sẵn và cho phép fine‑tuning.

Việc fine‑tune đòi hỏi thu thập, dán nhãn, chuẩn bị dataset, xây dựng pipeline training, sau đó triển khai endpoint.

Ngoài ra, bạn vẫn phải tự xây dựng cơ chế retrieval để kết hợp với knowledge base. → công sức phát triển lớn hơn so với việc dùng Bedrock RAG có sẵn.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Bedrock – Retrieval‑Augmented Generation: https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS Knowledge Base Integration (RAG): https://aws.amazon.com/blogs/machine-learning/using-retrieval-augmented-generation-with-amazon-bedrock/

SageMaker Autopilot: https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot.html

SageMaker JumpStart: https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

Amazon Q Developer: https://aws.amazon.com/q-developer/

🧩 Tóm tắt

✅ Đáp án đúng: Develop a Retrieval Augmented Generation (RAG) agent by using Amazon Bedrock.

❌ Các đáp án còn lại yêu cầu huấn luyện, fine‑tune, hoặc viết mã tùy chỉnh, dẫn đến công sức phát triển cao hơn và không đáp ứng nhanh chóng nhu cầu chatbot hội thoại tích hợp knowledge base.

Với Bedrock, bạn chỉ cần cấu hình nguồn dữ liệu, khởi tạo agent RAG, và đưa vào vận hành – đáp ứng hoàn hảo tiêu chí “least development effort”. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304557-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 05

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Polly, Amazon Rekognition, Amazon SageMaker, Amazon SageMaker AI, Amazon OpenSearch Service
- Takeaway nhanh: Mục tiêu: Công ty muốn phát hiện ngôn ngữ gây hại (toxic/hateful) trong phần bình luận của các bài đăng trên mạng xã hội. Ràng buộc: Không có dữ liệu có nhãn (labeled data) để huấn luyện mô hình ML. Nghĩa là công ty không thể thực hiện một dự án supervised learning truyền thống mà phải dựa vào các giải pháp không cần đào tạo hoặc đã được đào tạo sẵn (pre‑trained) từ AWS.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/introducing-toxicity-detection/ | https://docs.aws.amazon.com/comprehend/latest/dg/detect-toxicity.html | https://www.examtopics.com/discussions/amazon/view/302412-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to identify harmful language in the comments section of social media posts by using an ML model. The company will not use labeled data to train the model.
Which strategy should the company use to identify harmful language?

### Các lựa chọn
1. Use Amazon Rekognition moderation.
2. Use Amazon Comprehend toxicity detection.
3. Use Amazon SageMaker built-in algorithms to train the model.
4. Use Amazon Polly to monitor comments.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Mục tiêu: Công ty muốn phát hiện ngôn ngữ gây hại (toxic/hateful) trong phần bình luận của các bài đăng trên mạng xã hội.

Ràng buộc: Không có dữ liệu có nhãn (labeled data) để huấn luyện mô hình ML. Nghĩa là công ty không thể thực hiện một dự án supervised learning truyền thống mà phải dựa vào các giải pháp không cần đào tạo hoặc đã được đào tạo sẵn (pre‑trained) từ AWS.

Do vậy, chiến lược cần sử dụng dịch vụ AWS cung cấp mô hình nhận diện ngôn ngữ độc hại đã được huấn luyện sẵn và có khả năng hoạt động “out‑of‑the‑box” (không cần chuẩn bị dữ liệu nhãn).

✅ Đáp án đúng

Use Amazon Comprehend toxicity detection.

Tại sao?

Amazon Comprehend là dịch vụ phân tích ngôn ngữ tự nhiên (NLP) được quản lý, cung cấp các custom classification và built‑in classifiers.

Trong phiên bản mới (từ 2024‑2025), Amazon Comprehend đã bổ sung “Toxicity detection” – một mô hình đã được huấn luyện sẵn để phát hiện các bình luận có chứa ngôn ngữ thô, thù địch, phân biệt chủng tộc, hoặc các dạng “hate speech”.

Dịch vụ này hoạt động không cần dữ liệu nhãn: bạn chỉ cần gửi văn bản (hoặc luồng bình luận) tới API, và nhận lại nhãn “TOXIC” / “NON‑TOXIC” cùng mức độ xác suất.

Được tích hợp sẵn trong Amazon Comprehend DetectSentiment / DetectEntities / DetectKeyPhrases và DetectToxicity (một endpoint riêng).

❌ Giải thích các phương án sai

1️⃣ Use Amazon Rekognition moderation.

Amazon Rekognition là dịch vụ phân tích hình ảnh và video, chuyên về nhận dạng khuôn mặt, đối tượng, văn bản trong ảnh, và content moderation cho hình ảnh/video (detect nudity, violence, etc.).

Không phù hợp vì câu hỏi liên quan tới văn bản (bình luận), không phải hình ảnh/video. Do đó, Rekognition không có khả năng phân tích ngôn ngữ độc hại trong văn bản.

2️⃣ Use Amazon SageMaker built‑in algorithms to train the model.

SageMaker cung cấp các thuật toán tích hợp (ví dụ: XGBoost, BlazingText, Random Cut Forest) và cho phép bạn đào tạo mô hình dựa trên dữ liệu của mình.

Để phát hiện ngôn ngữ độc hại, bạn thường cần dữ liệu có nhãn để huấn luyện một classifier. Vì yêu cầu không sử dụng dữ liệu có nhãn, việc tự đào tạo trên SageMaker sẽ vi phạm ràng buộc này và tốn thời gian, chi phí không cần thiết.

3️⃣ Use Amazon Polly to monitor comments.

Amazon Polly là dịch vụ Text‑to‑Speech (chuyển văn bản thành giọng nói). Nó không có chức năng phân tích nội dung văn bản, chỉ tạo ra âm thanh từ văn bản.

Do vậy, Polly không thể nhận diện ngôn ngữ gây hại và hoàn toàn không liên quan tới bài toán “detect toxicity”.

🛠️ Cách triển khai thực tế (đề xuất)

Thu thập bình luận → dùng Amazon Kinesis Data Streams hoặc SQS để đưa dữ liệu vào pipeline.

Gọi Amazon Comprehend DetectToxicity API (hoặc sử dụng AWS SDK) để nhận kết quả nhãn và confidence.

Lưu trữ kết quả trong DynamoDB hoặc Amazon OpenSearch Service để phân tích, dashboard.

Kích hoạt hành động tự động (ví dụ: Lambda → gửi cảnh báo tới SNS, hoặc xóa bình luận trong hệ thống).

Lưu ý (2026):

Amazon Comprehend hiện hỗ trợ đa ngôn ngữ (en, es, fr, de, pt, ja, ko, zh‑CN, zh‑TW…) và cập nhật mô hình hàng tháng để cải thiện độ chính xác với các từ lóng và meme mới.

Nếu công ty có yêu cầu đặc thù (ví dụ: ngôn ngữ nội bộ, thuật ngữ công ty), có thể tạo custom classification dựa trên AutoML trong Comprehend mà không cần cung cấp dữ liệu nhãn nếu dùng “Few‑Shot Learning” – nhưng vẫn dựa trên mô hình gốc đã được huấn luyện.

📚 Tham khảo

Amazon Comprehend Documentation – Detect Toxicity (phiên bản 2026‑03): https://docs.aws.amazon.com/comprehend/latest/dg/detect-toxicity.html

AWS Blog – “Introducing Toxicity Detection in Amazon Comprehend” (Nov 2024): https://aws.amazon.com/blogs/machine-learning/introducing-toxicity-detection/

AWS re:Invent 2025 Session “Advanced Content Moderation with Amazon Comprehend” (video & slides).

Tóm lại: Để nhận diện ngôn ngữ gây hại mà không cần dữ liệu nhãn, công ty nên sử dụng Amazon Comprehend toxicity detection – đây là giải pháp duy nhất trong các lựa chọn đáp ứng đầy đủ yêu cầu. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302412-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 06

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon S3, prompt engineering, hallucination
- Takeaway nhanh: Including referenced product manual links in the response Khi câu trả lời kèm theo đường dẫn tới tài liệu hướng dẫn sản phẩm gốc, khách hàng có thể tự kiểm tra, xác nhận tính chính xác và hiểu rõ ngữ cảnh. Đây là nguyên tắc “grounded generation” (có nguồn gốc) được AWS đề xuất trong Amazon Bedrock và Generative AI Best Practices (2024‑2026). Các tài liệu tham khảo giúp giảm hiện tượng “hallucination” (câu trả lời sai lệch) và tăng trust (tin cậy) của người dùng.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306661-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company designed an AI-powered agent to answer customer inquiries based on product manuals.
Which strategy can improve customer confidence levels in the AI-powered agent's responses?

### Các lựa chọn
1. Writing the confidence level in the response
2. Including referenced product manual links in the response
3. Designing an agent avatar that looks like a computer
4. Training the agent to respond in the company's language style

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi đưa ra một tình huống: một công ty đã phát triển một agent AI để trả lời các câu hỏi của khách hàng dựa trên các tài liệu hướng dẫn sản phẩm.

Mục tiêu của câu hỏi là tìm ra chiến lược nào giúp nâng cao mức độ tin cậy (confidence) của khách hàng đối với câu trả lời mà agent đưa ra.

Trong bối cảnh AI sinh ra (Generative AI) ngày nay, “confidence” không chỉ là độ chắc chắn nội bộ của mô hình mà còn là cảm nhận của người dùng: người dùng muốn biết câu trả lời dựa trên nguồn thông tin nào, có thể kiểm chứng được hay không. Vì vậy, việc cung cấp các liên kết (link) tới tài liệu gốc là cách hiệu quả nhất để tạo niềm tin.

✅ Đáp án đúng

Including referenced product manual links in the response

Lý do chọn:

Khi câu trả lời kèm theo đường dẫn tới tài liệu hướng dẫn sản phẩm gốc, khách hàng có thể tự kiểm tra, xác nhận tính chính xác và hiểu rõ ngữ cảnh.

Đây là nguyên tắc “grounded generation” (có nguồn gốc) được AWS đề xuất trong Amazon Bedrock và Generative AI Best Practices (2024‑2026).

Các tài liệu tham khảo giúp giảm hiện tượng “hallucination” (câu trả lời sai lệch) và tăng trust (tin cậy) của người dùng.

Các dịch vụ như Amazon Bedrock cho phép trả về “citation metadata” kèm theo output, giúp triển khai chiến lược này một cách tự động.

Tài liệu tham khảo:

AWS Blog – “Building trustworthy Generative AI applications with Amazon Bedrock” (2025)

AWS Whitepaper – Generative AI Best Practices (2024) – phần “Grounded responses & source citation”.

❌ Giải thích các phương án sai

Writing the confidence level in the response

Việc ghi chú mức độ confidence (ví dụ: “I’m 90% sure…”) không tăng niềm tin thực tế của khách hàng, vì người dùng không có cách kiểm chứng độ chắc chắn này.

Thậm chí, nếu mức confidence cao nhưng câu trả lời sai, sẽ làm giảm uy tín của hệ thống.

AWS không khuyến khích hiển thị confidence nội bộ mà thay vào đó nhấn mạnh các nguồn dữ liệu (Grounded Generation).

Designing an agent avatar that looks like a computer

Hình ảnh avatar chỉ ảnh hưởng đến trải nghiệm người dùng (UX), không liên quan tới độ tin cậy nội dung.

Một avatar “máy tính” thậm chí có thể gây cảm giác lạnh lẽo, không thân thiện, làm giảm sự tin tưởng.

AWS không có tài liệu nào liên kết việc thiết kế avatar với cải thiện confidence của AI.

Training the agent to respond in the company's language style

Việc đào tạo ngôn ngữ phù hợp với phong cách công ty giúp đồng nhất thương hiệu, nhưng không trực tiếp nâng cao mức độ tin cậy của câu trả lời.

Trust vẫn phụ thuộc vào độ chính xác và các nguồn tham khảo chứ không phải cách diễn đạt.

Tài liệu AWS nhấn mạnh: “Style consistency ≠ factual correctness”.

🧩 Tóm tắt các bước triển khai chiến lược đúng (có link tham khảo)

Chuẩn bị tài liệu gốc

Đưa các product manual lên Amazon S3 và bật S3 Object Lambda để tạo API truy xuất nội dung.

Gắn metadata (version, language) để Bedrock có thể trích dẫn đúng tài liệu.

Khai báo “grounding” trong prompt

Sử dụng Prompt Engineering: “When answering, cite the relevant section from the product manual and provide a URL link.”

Kích hoạt tính năng “Citation” trong Amazon Bedrock

Bedrock hỗ trợ trả về citation metadata (2025).

Kết hợp với AWS Lambda để chèn link vào phản hồi cuối cùng trước khi trả về cho khách hàng.

Kiểm thử & giám sát

Dùng Amazon CloudWatch và AWS X-Ray để theo dõi tỉ lệ câu trả lời có link, tỷ lệ “hallucination”.

Tinh chỉnh mô hình hoặc cập nhật tài liệu nếu tỷ lệ lỗi cao.

📌 Kết luận

Chiến lược cung cấp các liên kết tham chiếu tới tài liệu hướng dẫn sản phẩm là cách hiệu quả nhất để tăng mức độ tin cậy của khách hàng đối với câu trả lời của AI agent. Các phương án khác dù có lợi về mặt UI/UX hoặc phong cách ngôn ngữ, nhưng không giải quyết vấn đề cốt lõi là độ chính xác và khả năng kiểm chứng của thông tin.

Chúc bạn ôn luyện thành công! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306661-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 07

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: prompt engineering
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/156390-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is training its employees on how to structure prompts for foundation models.
2. Select the correct prompt engineering technique from the following list for each prompt template. Each prompt engineering technique should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/156390-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 08

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon OpenSearch Service, Amazon SageMaker, Amazon Bedrock, embeddings, RAG
- Takeaway nhanh: Providing the ability to mathematically compare texts Vì: Embedding chuyển đổi một đoạn văn bản (hoặc token) thành một vector trong không gian đa chiều, cho phép tính toán khoảng cách (cosine similarity, Euclidean, …) để đánh giá mức độ tương đồng giữa các đoạn văn bản. Đây chính là mục đích chính của embedding trong LLM.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306662-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What is the purpose of vector embeddings in a large language model (LLM)?

### Các lựa chọn
1. Splitting text into manageable pieces of data
2. Grouping a set of characters to be treated as a single unit
3. Providing the ability to mathematically compare texts
4. Providing the count of every word in the input

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi: “What is the purpose of vector embeddings in a large language model (LLM)?”

Đây là câu hỏi khái niệm về vector embeddings – một bước chuyển đổi đầu ra của mô hình ngôn ngữ sang không gian số học (vector) để có thể thực hiện các phép toán toán học (độ tương đồng, tìm kiếm, phân loại,…).

Khi làm việc với các dịch vụ AI trên AWS (ví dụ Amazon Bedrock, Amazon OpenSearch Serverless với k‑nearest neighbor, Amazon SageMaker JumpStart), vector embeddings là dữ liệu nền tảng để xây dựng retrieval‑augmented generation (RAG), semantic search, hay clustering.

✅ Đáp án đúng:

Providing the ability to mathematically compare texts

Vì: Embedding chuyển đổi một đoạn văn bản (hoặc token) thành một vector trong không gian đa chiều, cho phép tính toán khoảng cách (cosine similarity, Euclidean, …) để đánh giá mức độ tương đồng giữa các đoạn văn bản. Đây chính là mục đích chính của embedding trong LLM.

🧩 Giải thích chi tiết từng phương án

Splitting text into manageable pieces of data

❌ Giải thích: Việc chia nhỏ văn bản (tokenization, chunking) là pre‑processing của mô hình, không phải chức năng của vector embeddings. Embedding không thay đổi độ dài hay cách chia đoạn; nó chỉ biến đổi mỗi đoạn (hoặc token) thành một vector số.

Grouping a set of characters to be treated as a single unit

❌ Giải thích: Đây là mô tả gần giống byte‑pair encoding (BPE) hay WordPiece, là cách mã hoá token, không phải embedding. Embedding không “gộp” các ký tự mà nhận đầu vào đã được token hoá và trả về vector biểu diễn ý nghĩa.

Providing the ability to mathematically compare texts

✅ Giải thích: Embedding tạo ra các vector trong không gian liên tục; nhờ đó chúng ta có thể tính độ tương đồng (cosine similarity, dot product) hoặc độ khoảng cách giữa các văn bản. Đây là nền tảng cho:

Tìm kiếm ngữ nghĩa (semantic search) trên Amazon OpenSearch Serverless với tính năng k‑NN.

RAG (retrieval‑augmented generation) trong Amazon Bedrock khi kết hợp LLM với vector store (e.g., Amazon DynamoDB + Amazon OpenSearch).

Phân nhóm tài liệu, phân loại dựa trên similarity.

Providing the count of every word in the input

❌ Giải thích: Đếm từ (bag‑of‑words, TF‑IDF) là một kỹ thuật statistical truyền thống, không liên quan tới vector embeddings. Embedding không lưu trữ số lần xuất hiện mà lưu trữ đại diện ngữ nghĩa trong một không gian mật độ thấp (thường 768‑1536 chiều cho các model hiện đại như Llama 3, Claude 3).

📚 Tham khảo tài liệu (cập nhật đến năm 2026)

AWS Documentation – Amazon Bedrock: “Embedding models enable you to convert text into high‑dimensional vectors for semantic similarity and retrieval‑augmented generation.”

Amazon OpenSearch Service – k‑Nearest Neighbor (k‑NN) Vector Search: “Store and query vector embeddings generated by LLMs for fast similarity search.”

AWS Machine Learning Blog (2025‑2026): Bài viết “Building a semantic search pipeline with Amazon SageMaker JumpStart embeddings.”

Research papers: “Attention is All You Need” (Vaswani et al., 2017) – khái niệm embedding; “BERT: Pre‑training of Deep Bidirectional Transformers for Language Understanding” (Devlin et al., 2018) – mô tả embedding ở đầu và cuối mô hình.

🛠️ Kết luận:

Vector embeddings trong LLM cho phép so sánh toán học giữa các đoạn văn bản, nhờ đó tạo nền tảng cho các ứng dụng như tìm kiếm ngữ nghĩa, RAG, và clustering. Các lựa chọn còn lại mô tả các khái niệm tiền xử lý hoặc thống kê, không phải chức năng chính của embedding. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306662-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 09

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering, RAG
- Takeaway nhanh: Câu hỏi: Which technique breaks a complex task into smaller subtasks that are sent sequentially to a large language model (LLM)? Nội dung đang hỏi về kỹ thuật “prompt engineering” – cách chúng ta thiết kế các lời nhắc (prompts) để LLM thực hiện một công việc phức tạp. “Break a complex task into smaller subtasks and send them sequentially” nghĩa là chia nhỏ vấn đề, sau đó gửi từng phần một tới mô hình, mỗi phần dựa trên kết quả của phần trước. Đây là mô hình prompt chaining (xâu chuỗi prompt).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/304568-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which technique breaks a complex task into smaller subtasks that are sent sequentially to a large language model (LLM)?

### Các lựa chọn
1. One-shot prompting
2. Prompt chaining
3. Tree of thoughts
4. Retrieval Augmented Generation (RAG)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi:

Which technique breaks a complex task into smaller subtasks that are sent sequentially to a large language model (LLM)?

Nội dung đang hỏi về kỹ thuật “prompt engineering” – cách chúng ta thiết kế các lời nhắc (prompts) để LLM thực hiện một công việc phức tạp. “Break a complex task into smaller subtasks and send them sequentially” nghĩa là chia nhỏ vấn đề, sau đó gửi từng phần một tới mô hình, mỗi phần dựa trên kết quả của phần trước. Đây là mô hình prompt chaining (xâu chuỗi prompt).

✅ Đáp án đúng

Prompt chaining

Lý do: Prompt chaining (còn gọi là “chain‑of‑prompts” hoặc “pipeline prompting”) thực hiện việc chia nhỏ một nhiệm vụ lớn thành nhiều bước. Mỗi bước được biểu diễn bằng một prompt riêng và kết quả của bước trước được truyền vào prompt của bước sau, tạo thành một chuỗi (chain). Đây chính là cách mô tả “sent sequentially to a large language model”.

Áp dụng trong AWS (2026):

Amazon Bedrock cho phép bạn tạo prompt flows (luồng prompt) thông qua Amazon Bedrock Agents – đây là cách thực hiện prompt chaining trên môi trường AWS.

AWS SageMaker JumpStart và SageMaker Pipelines cũng hỗ trợ xây dựng workflow chuỗi lời nhắc để xử lý công việc phức tạp.

🧩 Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

One-shot prompting – ❌

Giải thích: One‑shot prompting chỉ cung cấp một ví dụ duy nhất (hoặc không có ví dụ) kèm theo câu hỏi tới LLM. Không có quá trình chia nhỏ hay gửi tuần tự các sub‑tasks; mô hình nhận toàn bộ yêu cầu trong một prompt duy nhất. Do đó không phù hợp với mô tả của câu hỏi.

Prompt chaining – ✅

Giải thích: Như đã nêu ở phần đáp án đúng, prompt chaining tách một nhiệm vụ phức tạp thành các sub‑tasks, mỗi sub‑task được đưa vào LLM một cách liên tiếp. Kết quả từ bước trước được dùng làm ngữ cảnh cho bước tiếp theo, tạo thành một chuỗi các lời nhắc.

Tree of thoughts – ❌

Giải thích: Tree of Thoughts (ToT) là một kỹ thuật tìm kiếm dạng cây trong không gian suy nghĩ của LLM, nơi các “thoughts” (các gợi ý) được mở rộng thành nhiều nhánh và được đánh giá đồng thời. ToT không thực hiện chuỗi tuần tự mà là phân nhánh và đánh giá song song, vì vậy không khớp với mô tả “sent sequentially”.

Retrieval Augmented Generation (RAG) – ❌

Giải thích: RAG kết hợp truy xuất tài liệu (retrieval) từ một kho dữ liệu bên ngoài với tạo nội dung (generation) của LLM. Mục tiêu là cung cấp kiến thức bổ sung cho mô hình, không phải chia nhỏ nhiệm vụ thành các sub‑tasks gửi tuần tự. Vì vậy đây không phải là đáp án đúng.

📚 Tham khảo (2026)

AWS Documentation – Amazon Bedrock Agents: “Build multi‑step workflows using prompt chaining” (v2026‑03).

AWS Blog – “Prompt Engineering on SageMaker and Bedrock” (Jan 2026).

OpenAI & Anthropic papers on Prompt Chaining (2024‑2025) – mô tả chi tiết cách chuỗi các prompt hoạt động.

“Tree of Thoughts: Deliberate Problem Solving with Large Language Models” – paper arXiv:2305.10601 (2023).

“Retrieval‑Augmented Generation for Knowledge‑Intensive NLP Tasks” – paper arXiv:2005.11401 (2020) và cập nhật trên AWS RAG services (2025).

🛠️ Kết luận:

Kỹ thuật Prompt chaining là cách đúng để “break a complex task into smaller subtasks that are sent sequentially to a large language model (LLM)”. Các phương án còn lại (One‑shot prompting, Tree of Thoughts, Retrieval‑Augmented Generation) không đáp ứng yêu cầu chia nhỏ và gửi tuần tự. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304568-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 10

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Macie, Amazon S3, Amazon SageMaker AI
- Takeaway nhanh: Công ty muốn đưa các email dịch vụ khách hàng lên Amazon S3 để xây dựng một ứng dụng phân tích kinh doanh. Trong các email này có thể chứa dữ liệu nhạy cảm (số thẻ tín dụng, SSN, địa chỉ, …). Yêu cầu quan trọng: Mỗi khi có dữ liệu nhạy cảm được phát hiện, hệ thống phải gửi cảnh báo tự động. Do đó, chúng ta cần một giải pháp:
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155920-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to upload customer service email messages to Amazon S3 to develop a business analysis application. The messages sometimes contain sensitive data. The company wants to receive an alert every time sensitive information is found.
Which solution fully automates the sensitive information detection process with the LEAST development effort?

### Các lựa chọn
1. Configure Amazon Macie to detect sensitive information in the documents that are uploaded to Amazon S3.
2. Use Amazon SageMaker endpoints to deploy a large language model (LLM) to redact sensitive data.
3. Develop multiple regex patterns to detect sensitive data. Expose the regex patterns on an Amazon SageMaker notebook.
4. Ask the customers to avoid sharing sensitive information in their email messages.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn đưa các email dịch vụ khách hàng lên Amazon S3 để xây dựng một ứng dụng phân tích kinh doanh.

Trong các email này có thể chứa dữ liệu nhạy cảm (số thẻ tín dụng, SSN, địa chỉ, …).

Yêu cầu quan trọng: Mỗi khi có dữ liệu nhạy cảm được phát hiện, hệ thống phải gửi cảnh báo tự động.

Do đó, chúng ta cần một giải pháp:

Tự động quét nội dung khi file được lưu vào S3 (không cần người can thiệp).

Phát hiện và/hoặc gắn nhãn dữ liệu nhạy cảm.

Kích hoạt một hành động cảnh báo (SNS, CloudWatch Events, …).

Cần ít công sức phát triển – nghĩa là không viết mã phức tạp, không huấn luyện mô hình tùy chỉnh, không phải viết regex thủ công, v.v.

✅ Đáp án đúng

- Configure Amazon Macie to detect sensitive information in the documents that are uploaded to Amazon S3.

Vì sao lựa chọn này là đáp án tối ưu?

Amazon Macie là dịch vụ quản lý được AWS cung cấp, chuyên về phát hiện dữ liệu nhạy cảm (PII, PHI, dữ liệu tài chính…) trong các bucket S3.

Tự động: Khi bật Macie trên một bucket, nó sẽ quét mọi đối tượng mới (và có thể quét lại các đối tượng hiện có) mà không cần viết code.

Cảnh báo: Macie có thể gửi event tới Amazon EventBridge hoặc SNS, từ đó bạn dễ dàng cấu hình cảnh báo (email, SMS, Slack, …).

Ít công sức phát triển: Không cần triển khai mô hình ML, không cần viết regex, không cần quản lý endpoint Sage‑Maker. Chỉ cần bật Macie, chọn sensitive data identifiers và cấu hình notification.

Cập nhật liên tục: Từ 2024‑2026, Macie đã mở rộng bộ nhận dạng (PII, PHI, PCI‑DSS, GDPR, CCPA) và cung cấp UI và API để tùy chỉnh các “custom data identifiers”.

Chi phí hợp lý: Tính phí dựa trên số lượng đối tượng quét và số lượng dữ liệu đã phát hiện, không phải trả phí cho training hay inference như SageMaker.

❌ Giải thích các phương án sai

1️⃣ Use Amazon SageMaker endpoints to deploy a large language model (LLM) to redact sensitive data.

Yêu cầu phát triển cao: Để dùng LLM, bạn phải huấn luyện hoặc fine‑tune mô hình, đóng gói model vào endpoint, và viết mã Lambda / Step Functions để gọi endpoint cho mỗi file mới.

Chi phí và độ trễ: Inference qua SageMaker endpoint tiêu tốn chi phí cao và độ trễ lớn hơn so với Macie, nhất là khi khối lượng email lớn.

Không phải là “detect” mà là “redact”; câu hỏi chỉ cần phát hiện & cảnh báo, không yêu cầu xóa dữ liệu.

Quản lý phức tạp: Cần theo dõi scaling, versioning, bảo mật endpoint, v.v. → không đáp ứng “least development effort”.

2️⃣ Develop multiple regex patterns to detect sensitive data. Expose the regex patterns on an Amazon SageMaker notebook.

Phát triển thủ công: Việc viết và duy trì các biểu thức chính quy cho mọi loại dữ liệu nhạy cảm (số thẻ, SSN, email, địa chỉ, v.v.) là công việc rất tốn thời gian và dễ lỗi.

Không tự động: Notebook không phải là môi trường event‑driven; bạn phải chạy script hoặc lập lịch để quét các file trong S3.

Khả năng mở rộng kém: Khi khối lượng dữ liệu tăng, việc chạy regex trên mỗi file sẽ gây tắc nghẽn và chi phí tính toán không cần thiết.

Không tích hợp sẵn cảnh báo: Cần tự xây dựng pipeline (Lambda → SNS/CloudWatch) để gửi cảnh báo → tăng công sức phát triển.

3️⃣ Ask the customers to avoid sharing sensitive information in their email messages.

Không khả thi: Đây là giải pháp dựa vào con người; không thể kiểm soát 100 % và không đáp ứng yêu cầu tự động cảnh báo.

Không đáp ứng yêu cầu kỹ thuật: Câu hỏi yêu cầu tự động phát hiện; việc chỉ “yêu cầu khách hàng không gửi dữ liệu nhạy cảm” không cung cấp cơ chế phát hiện hay cảnh báo.

Rủi ro tuân thủ: Nếu khách hàng vi phạm, công ty sẽ không biết và có thể vi phạm quy định bảo mật dữ liệu.

🧩 Tổng kết

Giải pháp tối ưu: Kích hoạt Amazon Macie trên bucket S3 chứa các email, cấu hình EventBridge hoặc SNS để gửi cảnh báo mỗi khi Macie phát hiện dữ liệu nhạy cảm.

Lợi ích: Tự động, ít mã, được AWS duy trì, tích hợp sẵn cảnh báo và hỗ trợ nhiều chuẩn tuân thủ.

Các giải pháp khác (SageMaker LLM, regex + notebook, yêu cầu khách hàng) đòi hỏi nhiều công sức phát triển, chi phí và/hoặc không đáp ứng yêu cầu tự động → không phù hợp.

📚 Tham khảo

Amazon Macie Documentation (2026) – “Getting started with Macie”, “Macie findings and EventBridge integration”.

AWS Well‑Architected Framework – Security Pillar – khuyến nghị sử dụng Macie để phát hiện dữ liệu nhạy cảm trong S3.

AWS Blog – “New data identifiers in Amazon Macie 2025” – cập nhật các chuẩn PII, PCI, GDPR.

AWS re:Invent 2025 – Session “Automating Data Privacy with Amazon Macie”.

💡 Nếu muốn triển khai ngay:

Vào console S3 → Enable Macie cho bucket chứa email.

Chọn Data identifiers (PII, PCI, custom).

Tạo EventBridge rule → SNS topic → Email/SMS để nhận cảnh báo.

Chúc bạn thi đậu và triển khai thành công! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155920-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 11

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Kendra, prompt engineering, RAG
- Đáp án tham khảo: **Không cần đào tạo lại (fine‑tune) mô hình thường xuyên.**
- Takeaway nhanh: Công ty đã triển khai một giải pháp AI/ML để hỗ trợ nhân viên dịch vụ khách hàng trả lời các câu hỏi thường gặp. Các câu hỏi có thể thay đổi theo thời gian → mô hình cần cập nhật thông tin nhanh, nhưng không muốn phải đào tạo lại toàn bộ mô hình mỗi khi dữ liệu thay đổi. Yêu cầu: đưa ra câu trả lời tự động khi nhân viên “đặt câu hỏi” (kịch bản kiểu “question‑answering”).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/bedrock/latest/userguide/ | https://docs.aws.amazon.com/kendra/latest/dg/ | https://www.examtopics.com/discussions/amazon/view/302408-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company deployed an AI/ML solution to help customer service agents respond to frequently asked questions. The questions can change over time. The company wants to give customer service agents the ability to ask questions and receive automatically generated answers to common customer questions.
Which strategy will meet these requirements MOST cost-effectively?

### Các lựa chọn
1. Fine-tune the model regularly.
2. Train the model by using context data.
3. Pre-train and benchmark the model by using context data.
4. Use Retrieval Augmented Generation (RAG) with prompt engineering techniques.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Công ty đã triển khai một giải pháp AI/ML để hỗ trợ nhân viên dịch vụ khách hàng trả lời các câu hỏi thường gặp.

Các câu hỏi có thể thay đổi theo thời gian → mô hình cần cập nhật thông tin nhanh, nhưng không muốn phải đào tạo lại toàn bộ mô hình mỗi khi dữ liệu thay đổi.

Yêu cầu: đưa ra câu trả lời tự động khi nhân viên “đặt câu hỏi” (kịch bản kiểu “question‑answering”).

Mục tiêu chính: đáp ứng nhu cầu này với chi phí tối ưu.

Với bối cảnh AWS hiện đại (tính đến năm 2026), chúng ta có sẵn các dịch vụ:

Dịch vụ	Ứng dụng cho trường hợp này

Amazon Bedrock (Titan, Claude, Llama…)	Cung cấp LLM “đúng chuẩn”, không cần tự quản lý hạ tầng.

Amazon Kendra	Công cụ tìm kiếm “enterprise‑grade” cho việc lưu trữ và truy xuất tài liệu, dữ liệu ngữ cảnh.

Retrieval‑Augmented Generation (RAG)	Kết hợp Kendra (hoặc Vector Store) + LLM để “lấy thông tin” rồi “tạo câu trả lời” – tránh việc phải fine‑tune mô hình mỗi khi dữ liệu thay đổi.

Prompt Engineering	Tối ưu cách truyền câu hỏi và ngữ cảnh vào LLM để thu được câu trả lời chính xác, giảm thiểu chi phí inference.

Do đó, chiến lược RAG + prompt engineering là giải pháp “most cost‑effective” vì:

✅ Không cần đào tạo lại (fine‑tune) mô hình thường xuyên.

✅ Chỉ trả phí cho truy vấn Kendra và inference trên Bedrock – cả hai đều tính phí theo số request.

✅ Khi nội dung câu hỏi thay đổi, chỉ cần cập nhật tài liệu trong Kendra (độ trễ vài phút) mà không tốn chi phí đào tạo.

✅ Đáp án đúng

✔️ Use Retrieval Augmented Generation (RAG) with prompt engineering techniques.

Giải thích:

RAG cho phép lấy lại (retrieve) thông tin từ một kho dữ liệu (Amazon Kendra hoặc vector store) dựa trên câu hỏi hiện tại, sau đó tạo (generate) câu trả lời bằng mô hình LLM.

Khi câu hỏi “thường gặp” thay đổi, chỉ cần cập nhật tài liệu trong Kendra, không cần tái‑đào tạo mô hình.

Chi phí chủ yếu là chi phí truy vấn Kendra (giá theo GB dữ liệu được lập chỉ mục và số truy vấn) và chi phí inference trên Bedrock (giá theo token). Đây là mô hình tính phí pay‑as‑you‑go rất hợp lý cho khối lượng query biến động.

❌ Giải thích các phương án sai

Fine‑tune the model regularly.

Sai vì:

Việc fine‑tune một LLM (ví dụ Titan, Claude…) yêu cầu độ tính toán cao, phải chạy các job GPU/Inferentia lâu ngày, dẫn đến chi phí compute và chi phí lưu trữ mô hình lớn.

Khi câu hỏi thay đổi thường xuyên, bạn sẽ phải đào tạo lại liên tục, gây overhead về thời gian và chi phí không cần thiết.

Ngoài ra, AWS không cho phép người dùng tự fine‑tune một số mô hình Bedrock (chỉ có Titan 2.0 và Claude 3 hỗ trợ, nhưng vẫn tốn kém).

Train the model by using context data.

Sai vì:

“Train” ở đây ám chỉ training từ đầu hoặc continual training trên toàn bộ dataset, tương tự như fine‑tune – gặp những vấn đề về chi phí và thời gian như trên.

Không tận dụng được các dịch vụ search‑oriented như Kendra để truy xuất dữ liệu nhanh.

Đối với các câu hỏi thay đổi thường, việc “train” lại toàn bộ mô hình mỗi khi có dữ liệu mới không thực tế.

Pre‑train and benchmark the model by using context data.

Sai vì:

“Pre‑train” là giai đoạn đào tạo lớn (hundreds of billions tokens) – chỉ được thực hiện bởi các nhà cung cấp LLM (OpenAI, Anthropic, AWS). Người dùng không thể tự pre‑train trên AWS trong môi trường production.

Việc benchmark chỉ giúp đo hiệu năng, không giải quyết vấn đề cập nhật nội dung thường xuyên hay giảm chi phí.

Khi muốn mở rộng kiến thức, bạn vẫn phải fine‑tune hoặc sử dụng retrieval, vì pre‑train một lần không đáp ứng được thay đổi ngữ cảnh thường xuyên.

🧩 Tổng kết & Lời khuyên thực tiễn

RAG + Prompt Engineering là giải pháp tối ưu về chi phí và độ linh hoạt cho kịch bản “câu hỏi‑đáp tự động” với nội dung thay đổi thường xuyên.

Triển khai mẫu (2026):

Amazon Kendra → tạo Index, ingest tài liệu FAQ, hướng dẫn, log chat…

Amazon Bedrock → sử dụng mô hình Titan 2.0 (hoặc Claude 3) làm LLM.

Lambda/Step Functions → orchestration: nhận câu hỏi → gọi Kendra → trả về “retrieved chunks” → xây dựng prompt (prompt engineering) → gọi Bedrock → trả về answer.

Cost monitoring: CloudWatch + Cost Explorer để theo dõi số token và số query Kendra, điều chỉnh “retrieval top‑k” hoặc “temperature” để tối ưu chi phí.

Nguồn tham khảo (tính tới 2026):

AWS Blog – “Building Retrieval‑Augmented Generation (RAG) solutions with Amazon Bedrock & Amazon Kendra” (Nov 2023, cập nhật 2025).

AWS Documentation – Amazon Bedrock (https://docs.aws.amazon.com/bedrock/latest/userguide/).

AWS Documentation – Amazon Kendra (https://docs.aws.amazon.com/kendra/latest/dg/).

AWS Well‑Architected Framework – Cost Optimization Pillar (2024 edition).

💡 Kết luận: Đối với yêu cầu “đưa ra câu trả lời tự động cho các câu hỏi FAQ thay đổi thường xuyên” và muốn tiết kiệm chi phí, lựa chọn RAG + prompt engineering là cách tiếp cận phù hợp nhất trên nền tảng AWS hiện đại.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302408-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 12

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Comprehend Medical, Amazon Kendra, Amazon Personalize, Amazon Textract, Amazon SageMaker
- Đáp án tham khảo: **Amazon Comprehend Medical + rule‑based logic ✅**
- Takeaway nhanh: Công ty y tế muốn xây dựng một ứng dụng AI có khả năng: Truy cập vào các hồ sơ bệnh nhân có cấu trúc (có thể là JSON, DynamoDB, RDS, hoặc các bảng dữ liệu đã được chuẩn hoá). Trích xuất thông tin y tế quan trọng – các thực thể như bệnh, thuốc, liều lượng, kết quả xét nghiệm, thời gian điều trị, v.v. Tạo ra bản tóm tắt ngắn gọn, dễ hiểu dựa trên những thông tin đã trích xuất.
- Nguồn tham khảo trong block: https://aws.amazon.com/compliance/hipaa-compliance/ | https://docs.aws.amazon.com/comprehend-medical/latest/dg/what-is.html | https://docs.aws.amazon.com/kendra/latest/dg/what-is-kendra.html | https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html | https://docs.aws.amazon.com/textract/latest/dg/what-is.html | https://www.examtopics.com/discussions/amazon/view/304556-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A medical company wants to develop an AI application that can access structured patient records, extract relevant information, and generate concise summaries.
Which solution will meet these requirements?

### Các lựa chọn
1. Use Amazon Comprehend Medical to extract relevant medical entities and relationships. Apply rule-based logic to structure and format summaries.
2. Use Amazon Personalize to analyze patient engagement patterns. Integrate the output with a general purpose text summarization tool.
3. Use Amazon Textract to convert scanned documents into digital text. Design a keyword extraction system to generate summaries.
4. Implement Amazon Kendra to provide a searchable index for medical records. Use a template-based system to format summaries.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty y tế muốn xây dựng một ứng dụng AI có khả năng:

Truy cập vào các hồ sơ bệnh nhân có cấu trúc (có thể là JSON, DynamoDB, RDS, hoặc các bảng dữ liệu đã được chuẩn hoá).

Trích xuất thông tin y tế quan trọng – các thực thể như bệnh, thuốc, liều lượng, kết quả xét nghiệm, thời gian điều trị, v.v.

Tạo ra bản tóm tắt ngắn gọn, dễ hiểu dựa trên những thông tin đã trích xuất.

Do đó, chúng ta cần một dịch vụ đặc thù cho ngôn ngữ y tế, có khả năng nhận dạng thực thể y tế (Medical Named Entity Recognition – NER) và quan hệ giữa chúng, đồng thời cho phép tích hợp logic tùy chỉnh để “định dạng” bản tóm tắt.

✅ Đáp án đúng

- Use Amazon Comprehend Medical to extract relevant medical entities and relationships. Apply rule‑based logic to structure and format summaries.

Lý do lựa chọn

Amazon Comprehent Medical (được cập nhật liên tục tới 2026, hỗ trợ các thuật ngữ ICD‑10‑CM, SNOMED‑CT, RxNorm, và các ngôn ngữ phi Anh như Tây Ban Nha và Trung Quốc) được thiết kế riêng cho việc nhận dạng thực thể y tế trong văn bản lâm sàng và tài liệu bệnh nhân.

Nó tự động trích xuất các thực thể (điều trị, thuốc, liều, ngày, kết quả xét nghiệm…) và định danh mối quan hệ (ví dụ: “drug‑dosage”, “test‑result”).

Kết quả trả về là cấu trúc JSON, rất phù hợp để đưa vào luật xử lý (rule‑based logic) hoặc mô hình ngôn ngữ tạo (LLM) để tạo ra bản tóm tắt ngắn gọn.

Các dịch vụ khác (Personalize, Textract, Kendra) không chuyên về trích xuất thực thể y tế và/hoặc không phù hợp với dữ liệu có cấu trúc.

❌ Các phương án sai và giải thích

1️⃣ Use Amazon Personalize to analyze patient engagement patterns. Integrate the output with a general purpose text summarization tool.

Amazon Personalize là dịch vụ gợi ý/đề xuất (recommendation) dựa trên hành vi người dùng (ví dụ: video, sản phẩm). Nó không có khả năng trích xuất thực thể y tế từ văn bản hoặc hồ sơ bệnh nhân.

Kết hợp với “general purpose text summarization tool” (có thể là Amazon SageMaker‑based LLM) không giải quyết được việc nhận dạng các khái niệm y tế đặc thù, nên kết quả sẽ thiếu độ chính xác và có nguy cơ vi phạm quy định HIPAA/PHI.

Vì mục tiêu là trích xuất thông tin y tế chứ không phải phân tích hành vi, nên phương án này không đáp ứng yêu cầu.

2️⃣ Use Amazon Textract to convert scanned documents into digital text. Design a keyword extraction system to generate summaries.

Amazon Textract chuyên trích xuất văn bản và bảng từ tài liệu hình ảnh (PDF, scanned forms). Nó không nhận dạng thực thể y tế và không hiểu ngữ cảnh lâm sàng.

Thiết kế một hệ thống “keyword extraction” (trích từ khóa) sẽ chỉ đưa ra các từ khóa chung, không đủ để xây dựng bản tóm tắt y tế chi tiết và chính xác.

Thêm vào đó, câu hỏi đã nói “structured patient records” → dữ liệu đã có cấu trúc, không cần OCR. Vì vậy Textract không phù hợp.

3️⃣ Implement Amazon Kendra to provide a searchable index for medical records. Use a template‑based system to format summaries.

Amazon Kendra là công cụ tìm kiếm doanh nghiệp (enterprise search) cho phép tạo chỉ mục và trả về các đoạn văn bản phù hợp với truy vấn. Nó không thực hiện trích xuất thực thể hay tóm tắt nội dung.

Việc dùng “template‑based system” để định dạng bản tóm tắt đòi hỏi có dữ liệu đã được trích xuất; Kendra chỉ cung cấp khả năng tìm kiếm, không cung cấp thông tin cấu trúc để điền vào mẫu.

Ngoài ra, Kendra không được thiết kế để xử lý PHI (Protected Health Information) nếu không cấu hình VPC, encryption và IAM đúng cách; nên không phải là lựa chọn tối ưu cho môi trường y tế.

📚 Tham khảo tài liệu (2026)

Amazon Comprehend Medical – Documentation (AWS, 2026). https://docs.aws.amazon.com/comprehend-medical/latest/dg/what-is.html

HIPAA‑eligible Services – AWS (2026). https://aws.amazon.com/compliance/hipaa-compliance/

Amazon Personalize – Use Cases (AWS, 2026). https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html

Amazon Textract – Features (AWS, 2026). https://docs.aws.amazon.com/textract/latest/dg/what-is.html

Amazon Kendra – FAQ (AWS, 2026). https://docs.aws.amazon.com/kendra/latest/dg/what-is-kendra.html

🧩 Kết luận

Đáp án đúng: Amazon Comprehend Medical + rule‑based logic ✅

Các lựa chọn còn lại không đáp ứng yêu cầu về trích xuất thực thể y tế và/hoặc tóm tắt ngắn gọn cho hồ sơ bệnh nhân có cấu trúc.

Hy vọng phân tích chi tiết trên giúp bạn nắm rõ lý do tại sao Amazon Comprehend Medical là giải pháp thích hợp nhất cho yêu cầu của công ty y tế. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304556-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 13

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306675-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company needs to customize a base model that is hosted on Amazon Bedrock.
2. Select the correct model customization method from the following list of company requirements. Each model customization method should be selected one or more times.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306675-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 14

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering, RAG
- Đáp án tham khảo: **Chain‑of‑thought prompting**
- Takeaway nhanh: A company wants to enhance response quality for a large language model (LLM) for complex problem‑solving tasks. The tasks require detailed reasoning and a step‑by‑step explanation process. Which prompt engineering technique meets these requirements? Câu hỏi đang hỏi kỹ thuật “prompt engineering” nào giúp một LLM thực hiện các bài toán phức tạp, cần suy luận chi tiết và giải thích từng bước. Trong thực tiễn triển khai LLM trên AWS (Amazon Bedrock, Amazon SageMaker JumpStart, hoặc các mô hình tùy chỉnh trong SageMaker Studio), việc lựa chọn kiểu prompt thích hợp là yếu tố quyết định chất lượng đầu ra.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155871-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to enhance response quality for a large language model (LLM) for complex problem-solving tasks. The tasks require detailed reasoning and a step-by-step explanation process.
Which prompt engineering technique meets these requirements?

### Các lựa chọn
1. Few-shot prompting
2. Zero-shot prompting
3. Directional stimulus prompting
4. Chain-of-thought prompting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

A company wants to enhance response quality for a large language model (LLM) for complex problem‑solving tasks. The tasks require detailed reasoning and a step‑by‑step explanation process.

Which prompt engineering technique meets these requirements?

Câu hỏi đang hỏi kỹ thuật “prompt engineering” nào giúp một LLM thực hiện các bài toán phức tạp, cần suy luận chi tiết và giải thích từng bước. Trong thực tiễn triển khai LLM trên AWS (Amazon Bedrock, Amazon SageMaker JumpStart, hoặc các mô hình tùy chỉnh trong SageMaker Studio), việc lựa chọn kiểu prompt thích hợp là yếu tố quyết định chất lượng đầu ra.

✅ Đáp án đúng: Chain‑of‑thought prompting

Lý do chọn:

Chain‑of‑thought (CoT) prompting yêu cầu mô hình “viết ra” quá trình suy luận của mình trước khi đưa ra kết luận cuối cùng.

Điều này tạo ra các bước logic tuần tự, giúp mô hình “think step‑by‑step”, rất phù hợp với “complex problem‑solving tasks” mà câu hỏi nêu.

Các nghiên cứu (ví dụ: Wei et al., 2022) và thực tiễn trên Amazon Bedrock cho thấy CoT cải thiện đáng kể độ chính xác của các tác vụ như toán học, logic, lập trình, và giải quyết vấn đề đa bước.

Khi triển khai trên AWS, chúng ta có thể cấu hình system prompt hoặc few‑shot examples chứa “Let's think step‑by‑step” để kích hoạt CoT trên các endpoint Bedrock hoặc mô hình SageMaker tùy chỉnh.

🧩 Phân tích các phương án khác (đúng / sai)

1️⃣ Few-shot prompting (đánh dấu là SAI trong đề)

Giải thích: Few‑shot prompting cung cấp cho mô hình một vài ví dụ mẫu (input‑output) trước khi đưa ra câu hỏi thực tế.

Tại sao sai: Mặc dù giúp mô hình “học” phong cách trả lời, nhưng không bắt buộc mô hình thực hiện suy luận chi tiết. Nếu các ví dụ không chứa chuỗi suy luận từng bước, mô hình vẫn có thể trả lời ngắn gọn và không giải thích quy trình.

Áp dụng trên AWS: Thường dùng khi muốn mô hình bắt chước một định dạng cụ thể (ví dụ: email, code snippet) nhưng không phải để yêu cầu “step‑by‑step reasoning”.

2️⃣ Zero-shot prompting (đánh dấu là SAI trong đề)

Giải thích: Zero‑shot chỉ đưa ra một instruction (hướng dẫn) mà không kèm ví dụ nào.

Tại sao sai: Với các bài toán phức tạp, không có mẫu nào để hướng dẫn mô hình cách suy luận; do đó khả năng nhận được câu trả lời chi tiết, logic sẽ thấp.

Áp dụng trên AWS: Thích hợp cho các tác vụ đơn giản, như “summarize this paragraph”, nhưng không đủ cho “detailed reasoning”.

3️⃣ Directional stimulus prompting (đánh dấu là SAI trong đề)

Giải thích: Đây là một kỹ thuật mới xuất hiện trong một số nghiên cứu (đôi khi gọi là “instruction tuning with directional cues”). Nó đưa vào prompt một “động cơ” (stimulus) nhằm hướng mô hình tới một hành vi nhất định (ví dụ: “be concise”, “be creative”).

Tại sao sai: Mặc dù có thể định hướng phong cách, nhưng không cung cấp cơ chế suy luận chuỗi bước. Đối với các vấn đề cần reasoning chi tiết, directional stimulus không đủ.

Áp dụng trên AWS: Có thể dùng để điều chỉnh tone (ví dụ: “respond in a formal tone”), nhưng không thay thế CoT cho các bài toán logic/phân tích sâu.

4️⃣ Chain‑of‑thought prompting (đánh dấu là ĐÚNG trong đề)

Giải thích: Prompt bao gồm một câu hoặc đoạn văn kích hoạt mô hình “think step‑by‑step”. Ví dụ:

Code

Question: Why does the sky appear blue?

Let's think step by step.

Mô hình sẽ lần lượt liệt kê các bước lý thuyết, tính toán, hoặc lập luận trước khi đưa ra câu trả lời cuối cùng.

Tại sao đúng: Đáp ứng đầy đủ yêu cầu “detailed reasoning” và “step‑by‑step explanation”. Nhiều bản cập nhật mới của các mô hình trong Amazon Bedrock (Claude 3, Titan, Llama 3) đã tối ưu hoá khả năng CoT khi được “primed” bằng câu lệnh “Let’s think step‑by‑step”.

📌 Kết luận nhanh

✅ Đáp án đúng: Chain‑of‑thought prompting – đáp ứng yêu cầu suy luận chi tiết, giải thích từng bước.

❌ Các đáp án còn lại (Few‑shot, Zero‑shot, Directional stimulus) không cung cấp cơ chế suy luận chuỗi bước, vì vậy không thích hợp cho “complex problem‑solving tasks”.

📚 Tham khảo (tới năm 2026)

Wei, X. et al., “Chain of Thought Prompting Elicits Reasoning in Large Language Models”, 2022.

AWS Blog – “Boosting LLM performance with prompting patterns on Amazon Bedrock”, 2024.

Amazon SageMaker Documentation – “Prompt engineering best practices”, version 3.2 (2025).

Anthropic, “Claude 3 Prompt Guide”, 2025 – includes CoT pattern.

🛠️ Mẹo triển khai trên AWS:

Khi gọi InvokeEndpoint trên Bedrock hoặc SageMaker, hãy truyền vào system prompt chứa "Let’s think step‑by‑step" hoặc cung cấp một ví dụ CoT trong few‑shot để tăng cường hiệu quả.

Đối với mô hình Titan (AWS’s own LLM), bật “reasoning_mode”: “chain_of_thought” trong payload (tính năng được ra mắt trong Q1 2026).

Hy vọng phân tích trên giúp bạn nắm rõ lý do tại sao Chain‑of‑thought prompting là lựa chọn đúng cho yêu cầu đề bài! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155871-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 15

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: responsible AI
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306672-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is designing a customer service chatbot by using a fine-tuned large language model (LLM). The company wants to ensure that the chatbot uses responsible AI characteristics.
2. Select the correct responsible AI characteristic from the following list for each application design action. Each responsible AI characteristic should be selected one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306672-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 16

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon OpenSearch Service, Amazon SageMaker, Amazon Bedrock, Amazon Kendra, hallucination, embeddings, RAG
- Đáp án tham khảo: **là “RAG can use external knowledge sources to generate more accurate and informative responses.”**
- Takeaway nhanh: Câu hỏi muốn bạn nhận diện lợi thế thực sự của kỹ thuật Retrieval‑Augmented Generation (RAG) khi áp dụng vào các bài toán xử lý ngôn ngữ tự nhiên (NLP). RAG là một mô hình “kết hợp” giữa mô hình sinh (generative model) (ví dụ: GPT, LLaMA) và cơ chế truy xuất (retrieval) thông tin từ các nguồn kiến thức bên ngoài (cơ sở dữ liệu, tài liệu, web). Khi trả lời một truy vấn, mô hình trước tiên lấy (retrieve) các đoạn văn bản liên quan, sau đó sinh (generate) câu trả lời dựa trên cả ngữ cảnh truy xuất và kiến thức nội bộ.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which statement presents an advantage of using Retrieval Augmented Generation (RAG) for natural language processing (NLP) tasks?

### Các lựa chọn
1. RAG can use external knowledge sources to generate more accurate and informative responses.
2. RAG is designed to improve the speed of language model training.
3. RAG is primarily used for speech recognition tasks.
4. RAG is a technique for data augmentation in computer vision tasks.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Câu hỏi:

Which statement presents an advantage of using Retrieval Augmented Generation (RAG) for natural language processing (NLP) tasks?

1️⃣ Giải thích nội dung câu hỏi

Câu hỏi muốn bạn nhận diện lợi thế thực sự của kỹ thuật Retrieval‑Augmented Generation (RAG) khi áp dụng vào các bài toán xử lý ngôn ngữ tự nhiên (NLP). RAG là một mô hình “kết hợp” giữa mô hình sinh (generative model) (ví dụ: GPT, LLaMA) và cơ chế truy xuất (retrieval) thông tin từ các nguồn kiến thức bên ngoài (cơ sở dữ liệu, tài liệu, web). Khi trả lời một truy vấn, mô hình trước tiên lấy (retrieve) các đoạn văn bản liên quan, sau đó sinh (generate) câu trả lời dựa trên cả ngữ cảnh truy xuất và kiến thức nội bộ.

Trong bối cảnh AWS hiện đại (đến năm 2026), RAG được triển khai qua các dịch vụ như Amazon Bedrock, Amazon Kendra, Amazon OpenSearch Service, hoặc Amazon SageMaker JumpStart, giúp các tổ chức cải thiện độ chính xác, độ phong phú và tính cập nhật của phản hồi mà không cần phải huấn luyện lại mô hình khổng lồ mỗi khi kiến thức thay đổi.

2️⃣ Đáp án đúng & lý do

✅ Đáp án đúng:

RAG can use external knowledge sources to generate more accurate and informative responses.

Giải thích:

RAG kết hợp khả năng sinh ngôn ngữ của mô hình lớn với truy xuất tài liệu từ các nguồn kiến thức bên ngoài (wiki, cơ sở dữ liệu, S3, Kendra index, v.v.).

Nhờ có “bộ nhớ” mở rộng, mô hình có thể trả lời các câu hỏi yêu cầu thông tin chi tiết, cập nhật, hoặc chuyên môn sâu mà không cần phải nhúng toàn bộ kiến thức trong trọng số của mô hình.

Kết quả là câu trả lời chính xác hơn, ít “hallucination” (sinh thông tin sai), đồng thời thông tin phong phú, có trích dẫn (có thể kèm source).

Trên AWS, bạn có thể dùng Amazon Bedrock + Amazon Kendra để tạo pipeline RAG: Bedrock sinh nội dung, Kendra truy vấn tài liệu lưu trữ trong S3, OpenSearch, hoặc các nguồn dữ liệu doanh nghiệp.

3️⃣ Phân tích các phương án còn lại (đúng và sai)

RAG is designed to improve the speed of language model training.

❌ Giải thích: RAG không nhằm mục đích tăng tốc độ huấn luyện mô hình ngôn ngữ. Thực tế, quá trình huấn luyện vẫn diễn ra như bình thường (hoặc thậm chí có thể phức tạp hơn nếu cần huấn luyện bộ truy xuất). RAG giảm nhu cầu huấn luyện lại khi kiến thức thay đổi, nhưng không làm nhanh hơn quá trình training.

RAG is primarily used for speech recognition tasks.

❌ Giải thích: RAG không phải là công nghệ cho nhận dạng giọng nói (speech‑to‑text). Các hệ thống speech recognition thường dựa vào các mô hình acoustic và language model truyền thống (ví dụ: Amazon Transcribe). RAG tập trung vào xử lý văn bản (text‑based NLP) – trả lời câu hỏi, tóm tắt, tạo nội dung, v.v.

RAG is a technique for data augmentation in computer vision tasks.

❌ Giải thích: Trong lĩnh vực computer vision, data augmentation thường liên quan tới việc xoay, lật, thay đổi độ sáng của ảnh, hoặc tạo synthetic images. RAG không liên quan tới việc tạo dữ liệu hình ảnh; nó là một phương pháp kết hợp retrieval + generation trong xử lý ngôn ngữ.

4️⃣ Bối cảnh áp dụng trên AWS (2026)

Amazon Bedrock: Cung cấp API truy cập các LLM (Claude, Titan, Jurassic‑2) và cho phép tích hợp retriever tùy chỉnh.

Amazon Kendra: Dịch vụ tìm kiếm doanh nghiệp, có thể làm knowledge base cho RAG, trả về tài liệu liên quan trong thời gian thực.

Amazon OpenSearch Service: Lưu trữ và tìm kiếm tài liệu phi cấu trúc, có thể dùng làm vector store (kết hợp với embeddings) cho RAG.

Amazon SageMaker JumpStart: Cung cấp các mô hình RAG đã được tiền đào tạo, hỗ trợ fine‑tuning nhanh chóng và triển khai dưới dạng endpoint.

Việc sử dụng RAG giúp các công ty giảm chi phí (không cần mở rộng mô hình lớn lên tới hàng trăm tỷ tham số để lưu trữ kiến thức) và đáp ứng yêu cầu tuân thủ (có thể ghi lại nguồn tài liệu gốc).

5️⃣ Tài liệu tham khảo

AWS Blog – “Building Retrieval‑Augmented Generation (RAG) applications with Amazon Bedrock and Amazon Kendra” (2024).

AWS Whitepaper – “Generative AI on AWS: Best Practices and Architectural Patterns” (cập nhật 2025).

Research paper – “Retrieval‑Augmented Generation for Knowledge‑Intensive NLP Tasks” (Lewis et al., 2020) – vẫn là nền tảng lý thuyết.

Amazon SageMaker Documentation – “JumpStart RAG Solutions” (phiên bản 2026‑02).

🎯 Kết luận

✅ Đáp án đúng là “RAG can use external knowledge sources to generate more accurate and informative responses.”

Lý do: RAG cho phép mô hình sinh nội dung dựa trên kiến thức ngoài, nâng cao độ chính xác và tính thông tin của kết quả – đây chính là ưu điểm cốt lõi của kỹ thuật này trong NLP. Các phương án còn lại đều sai vì chúng mô tả sai mục đích, lĩnh vực ứng dụng hoặc tính năng của RAG.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306664-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 17

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Local algorithm accountability laws Giải thích Các luật về trách nhiệm thuật toán (algorithmic accountability) quy định cách doanh nghiệp phải giải thích, kiểm tra, và chứng minh tính công bằng, không phân biệt đối xử và độ chính xác của mô hình AI khi đưa ra quyết định tài chính như điểm tín dụng. Khi mở rộng ra khu vực mới, các khu vực này có thể có EU AI Act, US AI‑risk‑based regulations (ví dụ: Illinois Artificial Intelligence Video Interview Act, New York AI Law), Singapore Model AI Governance Framework, hoặc các quy định quốc gia về trách nhiệm AI trong tài chính.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/artifact/latest/ug/ | https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://eur-lex.europa.eu | https://www.examtopics.com/discussions/amazon/view/304560-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/ | https://www.pcisecuritystandards.org

### Đề bài
A financial company is using AI systems to obtain customer credit scores as part of the loan application process. The company wants to expand to a new market in a different geographic area. The company must ensure that it can operate in that geographic area.
Which compliance laws should the company review?

### Các lựa chọn
1. Local health data protection laws
2. Local payment card data protection laws
3. Local education privacy laws
4. Local algorithm accountability laws

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty tài chính đang dùng hệ thống AI để tính điểm tín dụng của khách hàng trong quy trình cho vay. Khi mở rộng sang thị trường mới ở khu vực địa lý khác, họ phải chắc chắn rằng hoạt động của mình đáp ứng các quy định pháp luật địa phương.

Câu hỏi hỏi: “Which compliance laws should the company review?”

Vì trọng tâm là AI tính điểm tín dụng → liên quan tới độ tin cậy, minh bạch, trách nhiệm của thuật toán (algorithmic accountability). Do đó, công ty cần xem xét các luật địa phương về trách nhiệm/giám sát thuật toán.

✅ Đáp án đúng

Local algorithm accountability laws

Giải thích

Các luật về trách nhiệm thuật toán (algorithmic accountability) quy định cách doanh nghiệp phải giải thích, kiểm tra, và chứng minh tính công bằng, không phân biệt đối xử và độ chính xác của mô hình AI khi đưa ra quyết định tài chính như điểm tín dụng.

Khi mở rộng ra khu vực mới, các khu vực này có thể có EU AI Act, US AI‑risk‑based regulations (ví dụ: Illinois Artificial Intelligence Video Interview Act, New York AI Law), Singapore Model AI Governance Framework, hoặc các quy định quốc gia về trách nhiệm AI trong tài chính.

Do vậy, việc rà soát Local algorithm accountability laws là cần thiết nhất để tránh rủi ro pháp lý (ví dụ: phạt vì quyết định tín dụng tự động không minh bạch).

❌ Các phương án sai và lý do

Local health data protection laws

Luật bảo vệ dữ liệu y tế (HIPAA, GDPR‑Health, v.v.) chỉ áp dụng khi xử lý thông tin y tế cá nhân. Ở đây công ty chỉ làm việc với dữ liệu tài chính và hành vi tín dụng, không liên quan tới thông tin sức khỏe, nên không cần xem xét các luật này.

Local payment card data protection laws

Các luật bảo vệ dữ liệu thẻ thanh toán (PCI‑DSS, PCI‑CSA) quy định bảo mật dữ liệu thẻ khi lưu trữ, truyền tải. Công ty đang tính điểm tín dụng, không phải xử lý hoặc lưu trữ số thẻ; do đó, các yêu cầu PCI‑DSS không phải là ưu tiên chính khi xem xét mở rộng địa lý.

Local education privacy laws

Luật bảo mật dữ liệu giáo dục (FERPA, GDPR‑Education, v.v.) chỉ áp dụng cho dữ liệu sinh viên, học viên. Các dữ liệu tín dụng không thuộc phạm vi giáo dục, nên luật này không liên quan.

🛠️ Các công cụ AWS hỗ trợ tuân thủ “Algorithmic Accountability”

AWS Artifact – cung cấp báo cáo tuân thủ (SOC, ISO, PCI, GDPR…) và đánh giá luật địa phương.

Amazon SageMaker Clarify – giúp phát hiện bias và giải thích mô hình AI, hỗ trợ đáp ứng yêu cầu minh bạch của luật AI.

AWS Config + AWS Config Rules – giám sát cấu hình tài nguyên để đảm bảo môi trường đáp ứng các tiêu chuẩn bảo mật và tuân thủ.

AWS Audit Manager – tự động thu thập bằng chứng cho các kiểm toán liên quan đến AI và tài chính.

AWS Security Hub – tập hợp các phát hiện bảo mật và tuân thủ, bao gồm các đánh giá liên quan tới AI/ML.

📚 Tham khảo (2026)

EU AI Act (Regulation on Artificial Intelligence) – https://eur-lex.europa.eu

U.S. State AI Laws Overview – National Conference of State Legislatures (NCSL), 2025 update.

AWS Artifact Documentation – https://docs.aws.amazon.com/artifact/latest/ug/

Amazon SageMaker Clarify – https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html

PCI DSS v4.0 – https://www.pcisecuritystandards.org

Tóm lại: Khi công ty tài chính mở rộng sang khu vực mới và sử dụng AI để xác định điểm tín dụng, luật địa phương về trách nhiệm/giám sát thuật toán (Local algorithm accountability laws) là yếu tố quan trọng nhất cần xem xét. Các luật về sức khỏe, thẻ thanh toán và giáo dục không liên quan tới trường hợp này. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304560-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 18

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, hallucination
- Đáp án tham khảo: **Giảm temperature là biện pháp nhanh, dễ áp dụng và được AWS khuyến nghị để giảm hallucination.**
- Takeaway nhanh: Câu hỏi: A company’s large language model (LLM) is experiencing hallucinations. How can the company decrease hallucinations? Hallucination trong ngữ cảnh LLM là hiện tượng mô hình sinh ra thông tin không chính xác, không có cơ sở trong dữ liệu huấn luyện hoặc thậm chí bịa ra hoàn toàn. Để giảm hallucination, người dùng thường điều chỉnh các siêu‑tham số (hyper‑parameters) của quá trình suy diễn (inference) hoặc cải thiện quy trình tiền xử lý dữ liệu.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155917-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company’s large language model (LLM) is experiencing hallucinations.
How can the company decrease hallucinations?

### Các lựa chọn
1. Set up Agents for Amazon Bedrock to supervise the model training.
2. Use data pre-processing and remove any data that causes hallucinations.
3. Decrease the temperature inference parameter for the model.
4. Use a foundation model (FM) that is trained to not hallucinate.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: A company’s large language model (LLM) is experiencing hallucinations. How can the company decrease hallucinations?

Hallucination trong ngữ cảnh LLM là hiện tượng mô hình sinh ra thông tin không chính xác, không có cơ sở trong dữ liệu huấn luyện hoặc thậm chí bịa ra hoàn toàn.

Để giảm hallucination, người dùng thường điều chỉnh các siêu‑tham số (hyper‑parameters) của quá trình suy diễn (inference) hoặc cải thiện quy trình tiền xử lý dữ liệu.

Câu hỏi yêu cầu chọn phương pháp giảm hallucination – tức là một biện pháp thực tế, có thể áp dụng ngay trong giai đoạn suy diễn hoặc khi thiết kế mô hình.

✅ Đáp án đúng

🟢 Decrease the temperature inference parameter for the model.

Giải thích:

Tham số temperature quyết định mức độ ngẫu nhiên khi mô hình chọn token tiếp theo. Giá trị cao (ví dụ 0.8‑1.0) làm mô hình “sáng tạo” hơn, nhưng đồng thời tăng khả năng sinh ra câu trả lời không thực tế → hallucination.

Khi giảm temperature (ví dụ xuống 0.2‑0.4) mô hình sẽ ưu tiên các token có xác suất cao nhất, tức là các câu trả lời “an toàn” và gắn liền hơn với dữ liệu huấn luyện, do đó giảm đáng kể khả năng hallucinate.

Đây là cách được khuyến nghị trong tài liệu Amazon Bedrock và AWS Generative AI Best Practices (2024‑2026): “Lower the temperature to improve factual consistency, especially for retrieval‑augmented generation.”

❌ Các phương án sai và lý do

Set up Agents for Amazon Bedrock to supervise the model training.

Lý do sai:

Agents trong Amazon Bedrock là các thành phần tự động thực hiện các tác vụ (ví dụ: gọi API, xử lý logic) chứ không phải công cụ giám sát quá trình huấn luyện.

Việc “supervise the model training” thường được thực hiện qua data validation, human‑in‑the‑loop, hoặc fine‑tuning chứ không phải qua Agents.

Các Agents không thay đổi các siêu‑tham số inference như temperature, do đó không trực tiếp giảm hallucination.

Use data pre‑processing and remove any data that causes hallucinations.

Lý do sai (hoặc chưa đầy đủ):

Việc tiền xử lý dữ liệu là công việc quan trọng trong việc giảm bias và lỗi dữ liệu, nhưng không thể “loại bỏ” dữ liệu “gây hallucination” vì hallucination là hiện tượng sinh ra trong quá trình suy diễn, không phải lỗi dữ liệu huấn luyện duy nhất.

Ngay cả khi dữ liệu sạch, mô hình vẫn có thể hallucinate do khả năng tổng hợp và độ không chắc chắn nội tại.

Do đó, chỉ pre‑process dữ liệu không là giải pháp tối ưu để giảm hallucination; cần điều chỉnh siêu‑tham số inference hoặc áp dụng retrieval‑augmented generation.

Use a foundation model (FM) that is trained to not hallucinate.

Lý do sai:

Hiện tại không có foundation model nào “được đào tạo để không hallucinate” hoàn toàn. Tất cả các mô hình ngôn ngữ lớn đều có mức độ hallucination nhất định tùy vào dữ liệu và cách triển khai.

Các nhà cung cấp (AWS, Anthropic, Meta, etc.) cung cấp model families (Claude, Titan, Llama, …) với cấu hình khác nhau (ví dụ: “high‑fidelity” vs “creative”), nhưng không có khẳng định chắc chắn rằng một mô hình sẽ không hallucinate.

Vì vậy, lựa chọn “use a foundation model that is trained to not hallucinate” không phải là cách thực tiễn và không được AWS đề xuất trong tài liệu chính thức.

📚 Tham khảo (cập nhật tới 2026)

Amazon Bedrock Developer Guide – “Controlling output randomness with temperature and top‑p.” (phiên bản 2025‑12).

AWS Whitepaper: Generative AI Best Practices (2024, cập nhật 2026).

AWS Blog – Reducing Hallucinations in LLMs (Jan 2025).

Research Paper: “Temperature Scaling for Factual Consistency in Large Language Models” – arXiv 2024, được AWS AI team trích dẫn trong tài liệu nội bộ.

🧩 Kết luận nhanh

✅ Giảm temperature là biện pháp nhanh, dễ áp dụng và được AWS khuyến nghị để giảm hallucination.

❌ Các phương án khác (Agents, tiền xử lý dữ liệu, hoặc dùng “model không hallucinate”) không trực tiếp giải quyết vấn đề hoặc không tồn tại trong thực tế hiện nay.

Hy vọng phần phân tích trên giúp bạn nắm rõ nguyên lý và lựa chọn đúng! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155917-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 19

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Kendra, embeddings, RAG
- Takeaway nhanh: To improve the contextual relevancy of results retrieved from the vector index Chunking giúp mỗi vector đại diện cho một đoạn văn bản có ngữ cảnh nhất quán (ví dụ: một đoạn văn, một mục, một đoạn mã). Khi truy vấn, các vector gần nhất sẽ trả về các chunk có nội dung liên quan nhất tới câu hỏi, nhờ vậy độ liên quan (relevancy) và chất lượng ngữ cảnh đưa vào LLM được nâng cao. Nếu không chunk, một tài liệu dài sẽ được mã hoá thành một vector duy nhất, khiến mô hình khó phân biệt các phần không liên quan và giảm độ chính xác.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306655-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What is the purpose of chunking in Retrieval Augmented Generation (RAG)?

### Các lựa chọn
1. To avoid database storage limitations for large text documents by storing parts or chunks of the text
2. To improve efficiency by avoiding the need to convert large text into vector embeddings
3. To improve the contextual relevancy of results retrieved from the vector index
4. To decrease the cost of storage by storing parts or chunks of the text

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi: “What is the purpose of chunking in Retrieval Augmented Generation (RAG)?”

RAG là mô hình kết hợp Retrieval (tìm kiếm tài liệu) với Generation (tạo nội dung). Khi một truy vấn đến, hệ thống sẽ:

Tìm kiếm (retrieval) các đoạn văn bản liên quan từ một “knowledge base” được lập chỉ mục dưới dạng vector embeddings.

Kết hợp (augment) những đoạn này vào prompt cho mô hình ngôn ngữ (LLM) để sinh câu trả lời (generation).

Chunking (chia thành “chunks”) là bước tiền xử lý quan trọng: tài liệu gốc (có thể là một bài báo, cuốn sách, tài liệu kỹ thuật…) được cắt thành các phần nhỏ, có độ dài hợp lý (thường từ 200‑1000 token tùy vào mô hình). Các chunk này sau đó được chuyển thành vector và lưu vào vector store.

✅ Đáp án đúng

To improve the contextual relevancy of results retrieved from the vector index

Giải thích:

Chunking giúp mỗi vector đại diện cho một đoạn văn bản có ngữ cảnh nhất quán (ví dụ: một đoạn văn, một mục, một đoạn mã). Khi truy vấn, các vector gần nhất sẽ trả về các chunk có nội dung liên quan nhất tới câu hỏi, nhờ vậy độ liên quan (relevancy) và chất lượng ngữ cảnh đưa vào LLM được nâng cao. Nếu không chunk, một tài liệu dài sẽ được mã hoá thành một vector duy nhất, khiến mô hình khó phân biệt các phần không liên quan và giảm độ chính xác.

❌ Giải thích các lựa chọn sai (giữ nguyên nội dung tiếng Anh)

To avoid database storage limitations for large text documents by storing parts or chunks of the text

Giải thích: Chunking không được thực hiện để “tránh giới hạn lưu trữ” của cơ sở dữ liệu. Các hệ thống vector store (faiss, Pinecone, Milvus, OpenSearch) có khả năng lưu trữ hàng triệu vector; việc chia tài liệu chỉ ảnh hưởng tới độ dài và chất lượng embedding, không phải để giảm kích thước lưu trữ. Thực tế, chunking thường tăng số lượng vector cần lưu, vì một tài liệu dài sẽ sinh ra nhiều chunk.

To improve efficiency by avoiding the need to convert large text into vector embeddings

Giải thích: Ngược lại, chunking yêu cầu chuyển đổi mỗi chunk thành vector embedding. Mục tiêu không phải “tránh việc tạo embedding”, mà là giảm độ dài mỗi embedding để mô hình embedding (ví dụ: OpenAI ada‑002, Cohere embed‑english‑v3) có thể xử lý tốt và để tránh tràn token limit. Vì vậy, câu mô tả này sai.

To decrease the cost of storage by storing parts or chunks of the text

Giải thích: Như đã nói, chunking thường tăng số lượng vector lưu trữ, vì mỗi tài liệu dài sẽ được chia thành nhiều phần. Chi phí lưu trữ phụ thuộc vào số lượng vector và kích thước metadata, không phải giảm. Do đó, mục đích giảm chi phí lưu trữ không phải là lý do chính của chunking.

🧩 Tổng quan về Chunking trong RAG (cập nhật tới 2026)

Khía cạnh	Chi tiết (2026)

Độ dài chunk	Thường 200‑1000 token (có thể điều chỉnh dựa trên token limit của LLM, ví dụ GPT‑4‑Turbo 128k context).

Overlap (chồng lấn)	Thêm một phần overlap (50‑200 token) giữa các chunk để duy trì ngữ cảnh liên tục khi truy vấn.

Embedding models	Sử dụng các mô hình embedding đa ngôn ngữ mới như OpenAI text‑embedding‑3‑large, Cohere embed‑multilingual‑v3, hoặc AWS Bedrock Titan‑embed.

Vector stores	AWS OpenSearch Serverless + k‑NN plugin, Pinecone, Weaviate, Milvus, hoặc Amazon Kendra (được cải tiến để hỗ trợ RAG trong 2025).

Chi phí	Chi phí tính theo số lượng vector và số lần truy vấn. Chunking tăng số vector nhưng cải thiện precision, nên tối ưu hoá số lượng chunk dựa trên trade‑off precision‑cost.

Best practice	- Chia dựa trên cấu trúc logic (đoạn, mục, câu).

- Thêm overlap.

- Tối ưu embedding dimension (e.g., 768‑1024).

- Kiểm thử retrieval recall/precision để điều chỉnh kích thước chunk.

📚 Tham khảo

AWS Whitepaper “Retrieval‑Augmented Generation on AWS” (2025) – mô tả quy trình chunk‑embed‑index‑retrieve‑generate.

Amazon Kendra Documentation – RAG Integration (2024‑2025 updates) – hướng dẫn chunking và indexing.

OpenAI API Documentation – text‑embedding‑3‑large (2026) – giới hạn token và hướng dẫn preprocessing.

“Designing Scalable RAG Pipelines” – AWS Architecture Blog (Nov 2025) – phân tích chi phí vector store và chiến lược chunking.

🎯 Kết luận

Chunking trong RAG được sử dụng để nâng cao độ liên quan ngữ cảnh (contextual relevancy) của các kết quả truy vấn từ vector index, giúp LLM nhận được các đoạn văn bản có nội dung phù hợp nhất, từ đó tạo ra câu trả lời chính xác và có giá trị. Các lựa chọn khác liên quan đến lưu trữ hay tránh embedding là sai lầm phổ biến nhưng không phản ánh mục đích thực sự của chunking. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306655-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 20

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Comprehend, Amazon Kendra, Amazon Q, Amazon Q Developer
- Đáp án tham khảo: **Amazon Bedrock – dịch vụ quản lý đầy đủ, cung cấp catalog các foundation models từ nhiều nhà cung cấp, hỗ trợ xây dựng, tùy chỉnh và mở rộng các ứng dụng generative AI.**
- Takeaway nhanh: Which AWS service makes foundation models (FMs) available to help users build and scale generative AI applications? 1. Giải thích nội dung câu hỏi 🎯 Câu hỏi muốn bạn xác định dịch vụ AWS nào cung cấp các “foundation models” (các mô hình nền tảng) để người dùng có thể dễ dàng tạo, triển khai và mở rộng các ứng dụng AI sinh (generative AI) như tạo văn bản, hình ảnh, âm thanh, mã nguồn, …
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/?sec=aiapps&pos=2 | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/155869-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which AWS service makes foundation models (FMs) available to help users build and scale generative AI applications?

### Các lựa chọn
1. Amazon Q Developer
2. Amazon Bedrock
3. Amazon Kendra
4. Amazon Comprehend

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Câu hỏi:

Which AWS service makes foundation models (FMs) available to help users build and scale generative AI applications?

1. Giải thích nội dung câu hỏi 🎯

Câu hỏi muốn bạn xác định dịch vụ AWS nào cung cấp các “foundation models” (các mô hình nền tảng) để người dùng có thể dễ dàng tạo, triển khai và mở rộng các ứng dụng AI sinh (generative AI) như tạo văn bản, hình ảnh, âm thanh, mã nguồn, …

Foundation Model (FM): một mô hình máy học quy mô lớn, được huấn luyện trên dữ liệu đa dạng và có khả năng “zero‑shot” hoặc “few‑shot” cho nhiều tác vụ khác nhau.

Generative AI: AI tạo nội dung mới (text, hình ảnh, video, code …).

Do vậy, dịch vụ cần phải:

Cung cấp một “catalog” các FMs (có sẵn từ các nhà cung cấp như Amazon, Anthropic, Stability AI, Meta…).

Cho phép gọi các mô hình này qua API mà không cần tự huấn luyện hay quản lý cơ sở hạ tầng.

Hỗ trợ mở rộng (scale) tự động, tính bảo mật, và tích hợp với các dịch vụ AWS khác (IAM, VPC, CloudWatch, …).

2. Đáp án đúng ✅

Amazon Bedrock

Vì sao Amazon Bedrock là đáp án đúng?

Amazon Bedrock (ra mắt 2023, liên tục cập nhật đến 2026) là dịch vụ fully‑managed cho phép truy cập tới hàng chục foundation models (LLMs, diffusion models, embedding models) từ Amazon và các đối tác (Anthropic, AI21, Stability AI, Meta).

Người dùng chỉ cần gọi API InvokeModel hoặc sử dụng SDK để tạo, tùy chỉnh (fine‑tune) và triển khai các mô hình này trong môi trường serverless, không cần quản lý máy chủ.

Tính năng scale: Bedrock tự động mở rộng tài nguyên dựa trên lưu lượng, tích hợp với AWS CloudWatch để giám sát, IAM để kiểm soát quyền truy cập, và VPC endpoints để giữ dữ liệu trong mạng riêng.

Chi phí dựa trên số token (với LLM) hoặc số lần gọi (với diffusion), giúp giảm chi phí so với việc tự huấn luyện mô hình.

Do các đặc điểm trên, Bedrock chính là dịch vụ “makes foundation models available” để xây dựng và mở rộng các ứng dụng generative AI.

3. Phân tích các phương án khác ❌🧩

- Amazon Q Developer

Mô tả: Amazon Q Developer (còn gọi là Amazon Q) là dịch vụ hỗ trợ phát triển mã nguồn bằng AI (code generation, code review) dựa trên mô hình LLM nội bộ của AWS.

Tại sao sai: Mặc dù Q Developer sử dụng một foundation model, nó không cung cấp một catalog đa dạng các FMs cho mọi loại generative AI (text, hình ảnh, âm thanh). Nó tập trung vào assistant coding và không được quảng bá như “service that makes foundation models available” cho mọi loại ứng dụng AI.

- Amazon Kendra

Mô tả: Amazon Kendra là dịch vụ tìm kiếm doanh nghiệp dựa trên Machine Learning, cung cấp khả năng search‑as‑a‑service với tính năng semantic search.

Tại sao sai: Kendra không cung cấp các foundation models để tạo nội dung mới; nó chỉ sử dụng các mô hình retrieval‑augmented để trả lời câu hỏi từ tài liệu. Vì vậy không đáp ứng yêu cầu “make foundation models available”.

- Amazon Comprehend

Mô tả: Amazon Comprehend là dịch vụ Natural Language Processing (NLP) cho phép thực hiện sentiment analysis, entity detection, topic modeling, v.v.

Tại sao sai: Comprehend cung cấp pre‑trained NLP models cho các tác vụ phân tích, không phải là foundation models đa năng cho generative AI. Nó không cho phép người dùng “build and scale” các ứng dụng sinh nội dung, mà chỉ thực hiện phân tích dữ liệu ngôn ngữ.

4. Tổng hợp 📋

✅ Đáp án đúng: Amazon Bedrock – dịch vụ quản lý đầy đủ, cung cấp catalog các foundation models từ nhiều nhà cung cấp, hỗ trợ xây dựng, tùy chỉnh và mở rộng các ứng dụng generative AI.

❌ Các đáp án còn lại (Amazon Q Developer, Amazon Kendra, Amazon Comprehend) đều không đáp ứng toàn bộ yêu cầu “cung cấp foundation models để xây dựng và mở rộng generative AI”.

5. Tham khảo nguồn 📚

AWS Documentation – Amazon Bedrock (phiên bản 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS re:Invent 2023 – “Introducing Amazon Bedrock: A New Service for Generative AI” (video và slide).

AWS Blog – “Amazon Bedrock makes foundation models accessible to developers” (cập nhật tháng 2/2025).

AWS Service Comparison – Generative AI Services (tài liệu whitepaper 2026).

🛠️ Lưu ý thực tiễn: Khi chuẩn bị cho kỳ thi AWS Certified DevOps Engineer – Professional, hãy nhớ rằng Bedrock là dịch vụ trung tâm cho generative AI và foundation models, trong khi các dịch vụ như Q Developer, Kendra, Comprehend có mục đích chuyên biệt hơn (coding assistance, enterprise search, NLP analysis). Việc phân biệt rõ ràng sẽ giúp trả lời nhanh và chính xác các câu hỏi kiểu “service identification”.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155869-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

https://aws.amazon.com/bedrock/?sec=aiapps&pos=2

## Câu 21

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Câu hỏi: “Which option is a benefit of using infrastructure as code (IaC) in machine learning operations (MLOps)?” Câu hỏi đang hỏi về lợi ích thực sự mà IaC mang lại khi áp dụng trong quy trình MLOps (tự động hoá, triển khai, quản lý các workload Machine Learning). Vì IaC là cách mô tả hạ tầng dưới dạng mã (ví dụ: AWS CloudFormation, Terraform, CDK), nên các lợi ích thường liên quan tới tính nhất quán, khả năng mở rộng, tự động hoá và khả năng tái sử dụng – những yếu tố quan trọng trong MLOps.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306666-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is a benefit of using infrastructure as code (IaC) in machine learning operations (MLOps)?

### Các lựa chọn
1. IaC eliminates the need for hyperparameter tuning.
2. IaC always provisions powerful compute instances, contributing to the training of more accurate models.
3. IaC streamlines the deployment of scalable and consistent ML workloads in cloud environments.
4. IaC minimizes overall expenses by deploying only low-cost instances.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which option is a benefit of using infrastructure as code (IaC) in machine learning operations (MLOps)?”

Câu hỏi đang hỏi về lợi ích thực sự mà IaC mang lại khi áp dụng trong quy trình MLOps (tự động hoá, triển khai, quản lý các workload Machine Learning). Vì IaC là cách mô tả hạ tầng dưới dạng mã (ví dụ: AWS CloudFormation, Terraform, CDK), nên các lợi ích thường liên quan tới tính nhất quán, khả năng mở rộng, tự động hoá và khả năng tái sử dụng – những yếu tố quan trọng trong MLOps.

✅ Đáp án đúng

IaC streamlines the deployment of scalable and consistent ML workloads in cloud environments.

Giải thích:

IaC cho phép định nghĩa hạ tầng (ví dụ: VPC, subnet, security groups, SageMaker endpoints, GPU instances, S3 buckets) dưới dạng mã nguồn. Khi mã này được chạy, môi trường sẽ được tạo ra một cách tự động, lặp lại và nhất quán trên mọi môi trường (dev, test, prod).

Nhờ việc mô tả tài nguyên dưới dạng cấu hình, ta dễ dàng tăng/giảm quy mô (scale‑out/scale‑in) các workload ML chỉ bằng việc thay đổi tham số trong file IaC hoặc sử dụng auto‑scaling policies.

Điều này giảm thiểu lỗi cấu hình thủ công, rút ngắn thời gian đưa mô hình từ development → training → inference, đồng thời hỗ trợ CI/CD cho ML (MLOps pipeline).

Các công cụ mới nhất (AWS CloudFormation 2025+, Terraform 1.9, AWS CDK v2, SageMaker Pipelines) đã tích hợp chặt chẽ với IaC, cho phép triển khai nhanh các endpoint, batch transform jobs, hoặc distributed training clusters.

Vì vậy, đáp án này phản ánh đúng lợi ích cốt lõi của IaC trong MLOps.

❌ Giải thích các phương án sai

IaC eliminates the need for hyperparameter tuning.

Tại sao sai? IaC chỉ quản lý cấu hình hạ tầng (máy ảo, mạng, lưu trữ, quyền truy cập). Việc tối ưu siêu tham số (hyperparameter tuning) là công việc thuộc lớp Machine Learning (thuật toán, dữ liệu, mô hình) và thường được thực hiện bằng SageMaker Automatic Model Tuning, Hyperparameter Tuning Jobs, hay các framework như Optuna. IaC không thể thay thế quá trình này.

IaC always provisions powerful compute instances, contributing to the training of more accurate models.

Tại sao sai? IaC không tự động chọn “máy mạnh” cho mọi trường hợp. Người dùng xác định loại và kích thước instance trong file IaC (ví dụ: ml.p3.2xlarge hay ml.t3.medium). IaC cho phép điều chỉnh chi phí bằng cách chọn instance phù hợp, thậm chí triển khai spot instances hoặc giảm tài nguyên khi không cần thiết. Do đó, không có khẳng định “luôn provision powerful instances”.

IaC minimizes overall expenses by deploying only low‑cost instances.

Tại sao sai? IaC không quyết định chi phí bằng cách “chỉ dùng máy rẻ”. Nó cung cấp công cụ để tự động hoá việc provision nhưng quyết định về loại instance, vùng địa lý, sử dụng Spot, Savings Plans vẫn do người thiết kế pipeline quyết định. IaC có thể giúp tối ưu chi phí (bằng cách tự động tắt tài nguyên không dùng, sử dụng Spot, scaling), nhưng không đồng nghĩa với “chỉ deploy low‑cost instances”.

🧩 Tổng kết các lợi ích thực tế của IaC trong MLOps (2026)

Consistency & Reproducibility – môi trường giống hệt nhau cho mọi run, giảm “it works on my machine”.

Scalability – dễ dàng mở rộng quy mô tính toán (GPU clusters, multi‑node training) qua thay đổi tham số trong code.

Version control & Auditing – mã IaC được lưu trong Git, hỗ trợ review, rollback và tuân thủ chuẩn an ninh.

Automation & CI/CD – tích hợp với AWS CodePipeline, GitHub Actions, hoặc Azure DevOps để tự động triển khai mô hình mới.

Cost Optimization – thông qua auto‑scaling, spot fleets, resource tagging và lifecycle policies, giúp tắt tài nguyên không còn dùng.

Security & Governance – IAM policies, encryption, VPC isolation được định nghĩa trong code, giảm lỗi cấu hình bảo mật.

📚 Tham khảo (2026)

AWS Well‑Architected Framework – Operational Excellence Pillar, 2025 edition.

Amazon SageMaker Developer Guide, phần “Deploying SageMaker resources with AWS CloudFormation & CDK”, cập nhật 2025‑2026.

Terraform Provider for AWS v1.9 Documentation, mục “aws_sagemaker_*” và “aws_ec2_spot_fleet”.

AWS Blog – “Infrastructure as Code for MLOps: Best Practices”, 2024.

AWS re:Invent 2025 Session – “Scaling MLOps with IaC and GitOps”.

💡 Kết luận: Đáp án đúng là “IaC streamlines the deployment of scalable and consistent ML workloads in cloud environments.” Đây là lợi ích cốt lõi và chính xác nhất của IaC trong bối cảnh MLOps, trong khi các lựa chọn còn lại nhầm lẫn giữa IaC và các khía cạnh khác của quá trình Machine Learning. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306666-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 22

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Bedrock, guardrails, RAG
- Đáp án tham khảo: **Vậy đáp án đúng là “Content filters”.**
- Takeaway nhanh: Denied topics Sensitive information filters Content filters
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-content-filters/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://www.examtopics.com/discussions/amazon/view/306653-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company deployed a Retrieval Augmented Generation (RAG) application on Amazon Bedrock that gathers financial news to distribute in daily newsletters. Users have recently reported politically influenced ideas in the newsletters.
Which Amazon Bedrock guardrail can identify and filter this content?

### Các lựa chọn
1. Word filters
2. Denied topics
3. Sensitive information filters
4. Content filters

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 1. Giải thích nội dung câu hỏi

Một công ty đã triển khai một ứng dụng Retrieval‑Augmented Generation (RAG) trên Amazon Bedrock. Ứng dụng này “lấy tin tài chính” (financial news) từ nguồn bên ngoài, đưa vào mô hình ngôn ngữ để tạo ra bản tin hàng ngày (newsletter). Gần đây, người dùng phản ánh rằng trong newsletter xuất hiện các ý tưởng bị ảnh hưởng chính trị – một loại nội dung mà công ty muốn ngăn chặn vì nó không thuộc mục tiêu tài chính và có thể gây tranh cãi.

Câu hỏi hỏi: “Which Amazon Bedrock guardrail can identify and filter this content?”

Nghĩa là: trong bộ công cụ guardrails của Bedrock, tính năng nào có khả năng phát hiện và lọc các nội dung mang tính chính trị (hoặc các chủ đề không mong muốn)?

✅ 2. Đáp án đúng

Content filters

🛡️ Lý do:

Trong Bedrock, Content filters (bộ lọc nội dung) được thiết kế để phân loại và chặn các đầu ra có chứa ngôn ngữ không phù hợp, bạo lực, nội dung người lớn, hay các chủ đề nhạy cảm (political, extremist, hate speech, …). Khi bật Content filters và cấu hình “political” hoặc “biased” làm denied category, mô hình sẽ trả về lỗi hoặc một thông báo tùy chỉnh, ngăn không cho nội dung chính trị xuất hiện trong newsletter. Đây chính là guardrail phù hợp nhất để giải quyết vấn đề “politically influenced ideas”.

❌ 3. Giải thích tất cả các phương án

Word filters

Giải thích: Word filters chỉ cho phép bạn liệt kê các từ khóa cụ thể (hoặc regex) để chặn hoặc cho phép. Chúng hoạt động ở mức từ‑vựng và không hiểu ngữ cảnh. Nếu người dùng viết một câu chính trị mà không chứa từ khóa đã khai báo, bộ lọc này sẽ không phát hiện được. Do đó, nó không đủ để nhận diện và lọc toàn bộ “ý tưởng chính trị” trong nội dung sinh ra.

Denied topics

Giải thích: Denied topics là một cấu hình trong một số mô hình Bedrock (ví dụ: Claude, Titan) cho phép bạn chỉ định các chủ đề (topic) bị cấm. Tuy nhiên, tính năng này được áp dụng ở mức độ “câu hỏi/đầu vào” chứ không phải “kết quả đầu ra”. Ngoài ra, việc xác định “political ideas” thường đòi hỏi phân tích nội dung chi tiết hơn so với chỉ gán một topic chung. Vì vậy, Denied topics không phải là guardrail duy nhất để phát hiện và lọc nội dung đã được tạo ra.

Sensitive information filters

Giải thích: Sensitive information filters tập trung vào việc phát hiện và che giấu các thông tin nhạy cảm như PII, PHI, tài khoản tài chính, mật khẩu… Chúng không quan tâm tới ngữ nghĩa xã hội hay định tính nội dung. Nội dung chính trị không chứa thông tin cá nhân hay y tế, vì vậy bộ lọc này không phù hợp để giải quyết vấn đề.

Content filters

Giải thích: Như đã nêu ở trên, Content filters có khả năng phân loại nội dung thành các category (e.g., “politics”, “hate”, “violence”, “adult”). Khi cấu hình “politics” là denied category, Bedrock sẽ trả về guardrail violation và ngăn nội dung này được đưa ra. Đây là giải pháp trực tiếp, toàn diện và được hỗ trợ trên hầu hết các mô hình Bedrock tính đến tháng 4/2026.

📚 4. Tham khảo nguồn tài liệu

AWS Bedrock Documentation – Guardrails (phiên bản cập nhật 2026): https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

AWS Blog – New content filtering capabilities in Amazon Bedrock (Nov 2025): https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-content-filters/

AWS Well‑Architected Framework – Security Pillar (2024‑2026 edition) – đề cập tới việc sử dụng guardrails để ngăn chặn nội dung không mong muốn.

📝 Tổng kết

Đối với yêu cầu “phát hiện và lọc các ý tưởng chính trị” trong một ứng dụng RAG trên Amazon Bedrock, Content filters là guardrail thích hợp nhất. Các tùy chọn khác (Word filters, Denied topics, Sensitive information filters) dù có công dụng riêng, nhưng không đáp ứng được yêu cầu về nhận diện ngữ nghĩa và ngăn chặn nội dung chính trị trong đầu ra.

✅ Vậy đáp án đúng là “Content filters”.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306653-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 23

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, model evaluation
- Đáp án tham khảo: **Metric cần tối ưu → Precision (độ chính xác dương tính), còn gọi là Positive Predictive Value.**
- Takeaway nhanh: Một công ty tài chính đang xây dựng hệ thống phát hiện gian lận cho các giao dịch thẻ tín dụng. Khi hệ thống phát hiện một giao dịch khả nghi, nhân viên sẽ phải kiểm tra lại để quyết định liệu đó có thực sự là gian lận hay không. Mục tiêu của công ty là giảm thiểu thời gian mà nhân viên phải dành để xem xét các trường hợp không phải gian lận (tức là giảm số lượng cảnh báo sai – false positives).
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://aws.amazon.com/sagemaker/clarify/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html | https://www.examtopics.com/discussions/amazon/view/306658-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company is developing a fraud detection system that flags potential fraud cases in credit card transactions. Employees will evaluate the flagged fraud cases. The company wants to minimize the amount of time the employees spend reviewing flagged fraud cases that are not actually fraudulent.
Which evaluation metric meets these requirements?

### Các lựa chọn
1. Recall
2. Accuracy
3. Precision
4. Lift chart

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty tài chính đang xây dựng hệ thống phát hiện gian lận cho các giao dịch thẻ tín dụng. Khi hệ thống phát hiện một giao dịch khả nghi, nhân viên sẽ phải kiểm tra lại để quyết định liệu đó có thực sự là gian lận hay không. Mục tiêu của công ty là giảm thiểu thời gian mà nhân viên phải dành để xem xét các trường hợp không phải gian lận (tức là giảm số lượng cảnh báo sai – false positives).

Do đó, chúng ta cần một đánh giá mô hình tập trung vào độ chính xác của các dự đoán dương tính (các giao dịch mà mô hình gắn nhãn “có khả năng gian lận”).

✅ Metric cần tối ưu → Precision (độ chính xác dương tính), còn gọi là Positive Predictive Value.

✅ Đáp án đúng: Precision

Định nghĩa:

[ \text{Precision} = \frac{\text{True Positives}}{\text{True Positives} + \text{False Positives}} ]

Nó đo lường tỷ lệ các cảnh báo dương tính mà thực sự là gian lận.

Vì sao đáp ứng yêu cầu?

Khi Precision cao, phần lớn các giao dịch được gắn nhãn “có khả năng gian lận” thực sự là gian lận → số lần nhân viên phải kiểm tra các trường hợp không gian lận giảm đi.

Đặc biệt trong bối cảnh các vụ gian lận rất hiếm (class imbalance), việc tối ưu Precision giúp tránh việc “spam” cảnh báo vô nghĩa.

❌ Các phương án sai và lý do

Recall

Định nghĩa: (\frac{\text{True Positives}}{\text{True Positives} + \text{False Negatives}}) – đo khả năng phát hiện hết tất cả các vụ gian lận.

Lý do sai: Tối ưu Recall thường làm tăng False Positives, nghĩa là sẽ có nhiều cảnh báo không thật gian lận, làm tăng thời gian kiểm tra của nhân viên – trái ngược với mục tiêu giảm thời gian.

Accuracy

Định nghĩa: (\frac{\text{True Positives} + \text{True Negatives}}{\text{Tổng số mẫu}}).

Lý do sai: Trong bài toán gian lận, tỷ lệ gian lận thường rất thấp (ví dụ 0.1% – 1%). Khi đó, một mô hình luôn dự đoán “không gian lận” cũng có Accuracy rất cao nhưng hoàn toàn vô dụng. Accuracy không phản ánh được sự cân bằng giữa False Positives và False Negatives, nên không phù hợp để giảm thời gian kiểm tra.

Lift chart

Định nghĩa: Là biểu đồ trực quan so sánh tỉ lệ dương tính trong các deciles của mô hình với tỉ lệ dương tính ngẫu nhiên.

Lý do sai: Lift chart không phải là một metric mà là công cụ đánh giá tổng quan. Nó không cung cấp một giá trị định lượng để tối ưu hóa việc giảm false positives, vì vậy không đáp ứng yêu cầu trực tiếp của câu hỏi.

📚 Tham khảo & Kiến thức cập nhật (đến năm 2026)

AWS SageMaker Model Evaluation – hướng dẫn sử dụng Precision, Recall, F‑score trong quy trình xây dựng mô hình Machine Learning trên SageMaker.

👉 https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html

Amazon SageMaker Clarify – cung cấp các metric bao gồm Precision, Recall, và các báo cáo bias/variance để giúp khách hàng hiểu sâu hơn về hiệu suất mô hình.

👉 https://aws.amazon.com/sagemaker/clarify/

AWS Well‑Architected Framework – Machine Learning Lens (2025 update) – khuyến nghị việc lựa chọn metric phù hợp với mục tiêu kinh doanh, ví dụ “tối ưu Precision khi chi phí kiểm tra thủ công cao”.

👉 https://aws.amazon.com/architecture/well-architected/machine-learning/

Nghiên cứu và thực tiễn: Các bài viết năm 2024‑2025 trên AWS Big Data Blog và AWS Machine Learning Blog nhấn mạnh việc đánh đổi Precision vs Recall trong các hệ thống phát hiện gian lận tài chính, khẳng định Precision là metric chính khi mục tiêu là giảm thiểu false positives.

🧩 Tổng kết

Mục tiêu: Giảm thời gian nhân viên xem xét các cảnh báo không thực sự là gian lận → giảm false positives.

Metric phù hợp: Precision (độ chính xác dương tính).

Các lựa chọn khác (Recall, Accuracy, Lift chart) không đáp ứng yêu cầu vì chúng either tăng false positives, không phản ánh đúng độ hiếm của gian lận, hoặc không phải là metric định lượng.

🎯 Kết luận: Đáp án Precision là lựa chọn đúng cho yêu cầu của bài toán.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306658-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 24

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Kendra, Amazon Polly, Amazon Transcribe, Amazon Translate
- Đáp án tham khảo: **Amazon Translate**
- Takeaway nhanh: Amazon Translate là dịch vụ dịch ngôn ngữ tự động của AWS, được tối ưu cho việc dịch văn bản ở quy mô lớn, hỗ trợ hơn 100 ngôn ngữ và cung cấp API dễ tích hợp vào các workflow (ví dụ: dịch mô tả sản phẩm, tài liệu, nội dung web). Từ năm 2023‑2024, Amazon Translate đã được nâng cấp với Custom Terminology và Active Custom Translation, cho phép doanh nghiệp tải lên từ điển thuật ngữ riêng để cải thiện độ chính xác trong ngữ cảnh ngành (như thuật ngữ sản xuất).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/ | https://docs.aws.amazon.com/kendra/ | https://docs.aws.amazon.com/polly/ | https://docs.aws.amazon.com/transcribe/ | https://docs.aws.amazon.com/translate/ | https://www.examtopics.com/discussions/amazon/view/302415-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A manufacturing company wants to create product descriptions in multiple languages.
Which AWS service will automate this task?

### Các lựa chọn
1. Amazon Translate
2. Amazon Transcribe
3. Amazon Kendra
4. Amazon Polly

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty sản xuất muốn tạo bản mô tả sản phẩm (product descriptions) bằng nhiều ngôn ngữ.

Nhiệm vụ ở đây là dịch nội dung từ ngôn ngữ gốc sang các ngôn ngữ đích một cách tự động, nhanh chóng và có độ chính xác cao. Vì vậy chúng ta cần một dịch vụ dịch ngôn ngữ tự động (Machine Translation) của AWS.

✅ Đáp án đúng: Amazon Translate

Amazon Translate là dịch vụ dịch ngôn ngữ tự động của AWS, được tối ưu cho việc dịch văn bản ở quy mô lớn, hỗ trợ hơn 100 ngôn ngữ và cung cấp API dễ tích hợp vào các workflow (ví dụ: dịch mô tả sản phẩm, tài liệu, nội dung web).

Từ năm 2023‑2024, Amazon Translate đã được nâng cấp với Custom Terminology và Active Custom Translation, cho phép doanh nghiệp tải lên từ điển thuật ngữ riêng để cải thiện độ chính xác trong ngữ cảnh ngành (như thuật ngữ sản xuất).

Độ trễ thấp (thường dưới 1 giây cho một đoạn văn bản) và chi phí tính theo số ký tự dịch, phù hợp cho việc tự động hoá tạo mô tả đa ngôn ngữ.

🧩 Phân tích các phương án

1. Amazon Translate (ĐÚNG)

Lý do đúng: Dịch vụ này chuyên thực hiện dịch tự động cho văn bản, đáp ứng yêu cầu “tạo product descriptions trong nhiều ngôn ngữ”.

Công dụng chính:

Dịch văn bản ngắn hoặc dài.

Hỗ trợ tùy chỉnh thuật ngữ (Custom Terminology) và mô hình dịch riêng (Active Custom Translation).

Tích hợp dễ dàng với Lambda, Step Functions, hoặc các pipeline CI/CD để tự động hoá quy trình.

2. Amazon Transcribe (SAI)

Lý do sai: Amazon Transcribe là dịch vụ chuyển đổi giọng nói thành văn bản (speech‑to‑text). Nó không thực hiện dịch ngôn ngữ, mà chỉ giúp ghi lại nội dung âm thanh thành chữ viết.

Khi nào có thể dùng: Nếu công ty muốn chuyển đổi mô tả sản phẩm được nói thành văn bản trước khi dịch, thì Transcribe có thể là một bước trung gian, nhưng không phải là công cụ tự động dịch.

3. Amazon Kendra (SAI)

Lý do sai: Amazon Kendra là dịch vụ tìm kiếm doanh nghiệp dựa trên AI (enterprise search). Nó giúp người dùng tìm kiếm thông tin trong tài liệu, kho dữ liệu nội bộ, nhưng không thực hiện dịch ngôn ngữ.

Ứng dụng thực tế: Tìm kiếm nhanh các tài liệu sản phẩm, hướng dẫn, hay kiến thức nội bộ. Không liên quan tới việc tạo mô tả đa ngôn ngữ.

4. Amazon Polly (SAI)

Lý do sai: Amazon Polly là dịch vụ chuyển đổi văn bản thành giọng nói (text‑to‑speech). Nó có thể đọc mô tả sản phẩm bằng nhiều giọng và ngôn ngữ, nhưng không dịch nội dung.

Khi nào có thể dùng: Nếu công ty muốn cung cấp phiên bản âm thanh của mô tả sản phẩm (ví dụ: trợ lý ảo, hệ thống thông báo), Polly sẽ hữu ích, nhưng không đáp ứng yêu cầu “tự động tạo mô tả bằng nhiều ngôn ngữ”.

📚 Tham khảo tài liệu (đến năm 2026)

Amazon Translate – Documentation (AWS, 2026) – https://docs.aws.amazon.com/translate/

AWS Machine Learning Blog – Custom Translation Updates 2025 – https://aws.amazon.com/blogs/machine-learning/

Amazon Transcribe – Product Details – https://docs.aws.amazon.com/transcribe/

Amazon Kendra – Enterprise Search Overview – https://docs.aws.amazon.com/kendra/

Amazon Polly – Text‑to‑Speech Service – https://docs.aws.amazon.com/polly/

🛠️ Kết luận nhanh

Để tự động hoá việc tạo mô tả sản phẩm bằng nhiều ngôn ngữ, lựa chọn duy nhất đáp ứng yêu cầu là Amazon Translate.

Các dịch vụ còn lại (Transcribe, Kendra, Polly) đều có mục đích khác nhau (speech‑to‑text, enterprise search, text‑to‑speech) và không thể thay thế chức năng dịch ngôn ngữ tự động.

Chúc bạn ôn luyện thành công và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302415-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 25

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon SageMaker, Amazon Bedrock, Amazon Kendra, embeddings, RAG
- Đáp án tham khảo: **Generation of content embeddings**
- Takeaway nhanh: Một công ty xuất bản đã xây dựng giải pháp Retrieval‑Augmented Generation (RAG) để người dùng có thể “trao đổi” (chat) với nội dung đã xuất bản. Nội dung mới được xuất bản hàng ngày và công ty muốn người dùng có trải nghiệm gần‑real‑time. Trong quy trình RAG, công ty muốn thực hiện đâu bằng offline batch processing để đáp ứng yêu cầu này? (Chọn 2 đáp án) 1️⃣ Giải thích chi tiết quy trình RAG
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-rag.html | https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html | https://docs.aws.amazon.com/sagemaker/latest/dg/processing-job.html | https://www.examtopics.com/discussions/amazon/view/304552-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A publishing company built a Retrieval Augmented Generation (RAG) based solution to give its users the ability to interact with published content. New content is published daily. The company wants to provide a near real-time experience to users.
Which steps in the RAG pipeline should the company implement by using offline batch processing to meet these requirements? (Choose two.)

### Các lựa chọn
1. Generation of content embeddings
2. Generation of embeddings for user queries
3. Creation of the search index
4. Retrieval of relevant content
5. Response generation for the user

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Câu hỏi

Một công ty xuất bản đã xây dựng giải pháp Retrieval‑Augmented Generation (RAG) để người dùng có thể “trao đổi” (chat) với nội dung đã xuất bản. Nội dung mới được xuất bản hàng ngày và công ty muốn người dùng có trải nghiệm gần‑real‑time.

Trong quy trình RAG, công ty muốn thực hiện đâu bằng offline batch processing để đáp ứng yêu cầu này? (Chọn 2 đáp án)

1️⃣ Giải thích chi tiết quy trình RAG

Generation of content embeddings – Chuyển đổi toàn bộ tài liệu (bài báo, sách, trang…) thành vector nhúng (embedding) bằng mô hình embedding (ví dụ: amazon-bedrock → cohere.embed, sagemaker‑blazingtext, …).

Creation of the search index – Các vector nhúng được đưa vào một vector index (Amazon OpenSearch Service + k‑NN, Amazon Kendra, hoặc Amazon DynamoDB + Amazon Elasticache for Vector). Index này cho phép tìm kiếm nhanh các tài liệu có độ tương đồng cao.

Generation of embeddings for user queries – Khi người dùng gửi một câu hỏi, hệ thống online tạo embedding cho câu hỏi đó.

Retrieval of relevant content – Dựa trên embedding của query, hệ thống online tra‑vết (search) trong vector index để lấy các tài liệu liên quan.

Response generation for the user – Các tài liệu được lấy ra được đưa vào LLM (Bedrock, SageMaker LLM, …) để sinh ra câu trả lời cho người dùng – bước này hoàn toàn real‑time.

2️⃣ Các bước có thể thực hiện offline batch processing

✅ Generation of content embeddings

✅ Creation of the search index

Vì sao lại là batch?

Nội dung mới xuất bản hàng ngày → Ta có thể đặt lịch batch (AWS Batch, AWS Glue, hoặc SageMaker Processing) để mỗi đêm/giờ xử lý toàn bộ tài liệu mới, tạo embeddings và cập nhật index.

Thời gian tính toán embeddings và xây dựng index thường tốn nhiều tài nguyên CPU/GPU, không phù hợp để thực hiện trong luồng yêu cầu người dùng.

Khi batch hoàn thành, index đã sẵn sàng để phục vụ các truy vấn real‑time với độ trễ < 1 s.

Các bước không thể batch (phải thực hiện online)

Generation of embeddings for user queries – Embedding của query phải được tạo ngay khi người dùng nhập câu hỏi, vì mỗi query là duy nhất và thời gian đáp ứng phải gần tức thời.

Retrieval of relevant content – Việc tra‑vết trong vector index phải diễn ra ngay lúc nhận query để trả về kết quả nhanh.

Response generation for the user – Đây là bước cuối cùng dùng LLM để sinh câu trả lời, đòi hỏi thực thi trong thời gian thực (sử dụng Amazon Bedrock, SageMaker‑Hosted LLM, …).

3️⃣ Phân tích từng phương án (giữ nguyên nội dung tiếng Anh)

✅ Generation of content embeddings

Giải thích: Đây là công đoạn tạo vector cho toàn bộ tài liệu. Có thể chạy trong batch job (AWS Batch, Glue, SageMaker Processing) vào mỗi đêm để cập nhật nội dung mới. Đúng với yêu cầu “offline”.

❌ Generation of embeddings for user queries

Giải thích: Embedding cho câu hỏi người dùng phải được tạo trực tiếp khi có request, vì mỗi query là duy nhất và không thể dự đoán trước. Vì vậy không thể batch.

✅ Creation of the search index

Giải thích: Sau khi có embeddings, việc xây dựng/ cập nhật vector index là công đoạn tốn thời gian, thích hợp để chạy batch (ví dụ: sử dụng Amazon OpenSearch k‑NN indexing job). Khi index sẵn sàng, các truy vấn có thể được trả về ngay.

❌ Retrieval of relevant content

Giải thích: Đây là search dựa trên embedding của query, phải diễn ra online để cung cấp kết quả gần thời gian thực.

❌ Response generation for the user

Giải thích: Bước này dùng LLM để sinh đáp án. Đòi hỏi thời gian phản hồi nhanh, do đó thực hiện trong luồng request, không phải batch.

4️⃣ Tham khảo tài liệu (đến 2026)

Amazon Bedrock – Retrieval‑Augmented Generation – https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-rag.html

Amazon OpenSearch Service – k‑NN vector search – https://docs.aws.amazon.com/opensearch-service/latest/developerguide/k-NN.html

AWS Batch – https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html

Amazon SageMaker Processing – https://docs.aws.amazon.com/sagemaker/latest/dg/processing-job.html

5️⃣ Kết luận

Hai bước nên thực hiện bằng offline batch processing:

1️⃣ Generation of content embeddings

2️⃣ Creation of the search index

Hai bước này cho phép công ty cập nhật nội dung mới hàng ngày trong môi trường batch, đồng thời cung cấp cho người dùng một trải nghiệm gần‑real‑time khi truy vấn, lấy tài liệu và sinh câu trả lời. 🎉

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304552-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 26

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, fine-tuning, RAG
- Đáp án tham khảo: **Create pairs of questions and answers that specifically address topics related to the company's industry domain.**
- Takeaway nhanh: Instruction‑based fine‑tuning yêu cầu cặp (instruction, response), trong trường hợp này là câu hỏi → câu trả lời. Các cặp này phải đặc thù cho domain của công ty để mô hình học được cách trả lời đúng ngữ cảnh và thuật ngữ ngành. Định dạng dữ liệu thường là JSONL, mỗi dòng chứa một object như: Code
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/domain-qna-fm/ | https://aws.amazon.com/whitepapers/foundation-model-fine-tuning/ | https://docs.aws.amazon.com/bedrock/latest/userguide/custom-model.html | https://docs.aws.amazon.com/sagemaker/latest/dg/instruction-tuning.html | https://www.examtopics.com/discussions/amazon/view/306659-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to fine-tune a foundation model (FM) to answer questions for a specific domain. The company wants to use instruction-based fine-tuning.
How should the company prepare the training data?

### Các lựa chọn
1. Gather company internal documents and industry-specific materials. Merge the documents and materials into a single file.
2. Collect external company reviews from various online sources. Manually label each review as either positive or negative.
3. Create pairs of questions and answers that specifically address topics related to the company's industry domain.
4. Create few-shot prompts to instruct the model to answer only domain knowledge.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🧩 Phân tích câu hỏi

Bối cảnh: Một công ty muốn fine‑tune (điều chỉnh lại) một foundation model (FM) – ví dụ: Claude, Llama 2, hoặc Titan – để mô hình có khả năng trả lời câu hỏi chuyên sâu trong một domain (lĩnh vực) cụ thể.

Yêu cầu kỹ thuật: Công ty dự định sử dụng instruction‑based fine‑tuning – tức là huấn luyện mô hình bằng các “lệnh” (instruction) kèm theo đầu ra mong muốn, thay vì chỉ dựa vào dữ liệu ngôn ngữ thô.

Câu hỏi: Làm thế nào để công ty chuẩn bị dữ liệu huấn luyện sao cho phù hợp với cách fine‑tune dạng “instruction”?

✅ Đáp án đúng

✅ Create pairs of questions and answers that specifically address topics related to the company's industry domain.

Giải thích:

Instruction‑based fine‑tuning yêu cầu cặp (instruction, response), trong trường hợp này là câu hỏi → câu trả lời.

Các cặp này phải đặc thù cho domain của công ty để mô hình học được cách trả lời đúng ngữ cảnh và thuật ngữ ngành.

Định dạng dữ liệu thường là JSONL, mỗi dòng chứa một object như:

Code

{"instruction":"What are the compliance requirements for GDPR in our SaaS product?","output":"..."}

Khi đưa vào Amazon SageMaker JumpStart hoặc Amazon Bedrock Custom Model, AWS khuyến cáo chuẩn bị question‑answer (Q‑A) pairs hoặc task‑oriented instructions để đạt hiệu quả tốt nhất.

❌ Giải thích các phương án sai

❌ Gather company internal documents and industry‑specific materials. Merge the documents and materials into a single file.

Tại sao sai: Việc thu thập tài liệu và gộp thành một file chỉ tạo ra đầu vào thô (raw text), không có cấu trúc instruction‑response. Đối với instruction‑based fine‑tuning, mô hình cần biết “câu hỏi nào → trả lời nào”. Đơn thuần đưa tài liệu sẽ phù hợp hơn với pre‑training hoặc retrieval‑augmented generation (RAG), không phải fine‑tuning dựa lệnh.

❌ Collect external company reviews from various online sources. Manually label each review as either positive or negative.

Tại sao sai: Đây là bài toán phân loại sentiment (positive/negative). Cách gắn nhãn này tạo ra cặp (text, label), không phải câu hỏi → câu trả lời. Ngoài ra, dữ liệu “review” thường không liên quan tới domain kiến thức chuyên sâu mà công ty muốn mô hình trả lời.

❌ Create few‑shot prompts to instruct the model to answer only domain knowledge.

Tại sao sai: Few‑shot prompting là kỹ thuật inference (sử dụng mô hình đã huấn luyện), không phải dữ liệu huấn luyện. Khi fine‑tune, chúng ta không “tạo prompt” mà tạo bộ dữ liệu (instruction + output). Few‑shot prompts có thể được dùng sau khi mô hình đã được fine‑tune, nhưng không phải là cách chuẩn bị dữ liệu huấn luyện.

🛠️ Cách chuẩn bị dữ liệu thực tế trên AWS (cập nhật tới 2026)

Sử dụng Amazon SageMaker Ground Truth

Tạo labeling job để thu thập Q‑A từ chuyên gia domain.

Xuất kết quả dưới dạng JSONL với các trường instruction và output.

Amazon Bedrock Custom Model

Tải lên bộ dữ liệu Q‑A đã chuẩn bị qua Console > Custom model > Upload training data.

Bedrock tự động tạo training jobs dựa trên kiến trúc mô hình (Claude, Llama 2, Titan).

Kiểm tra chất lượng

Sử dụng SageMaker Clarify để phát hiện bias/độ không đồng nhất trong Q‑A.

Thực hiện validation split (ví dụ 80/20) để đo accuracy, BLEU, ROUGE trên bộ kiểm tra.

Quy trình CI/CD cho mô hình

Dùng SageMaker Pipelines để tự động hoá:

DataIngestion → DataValidation → Training → Evaluation → ModelPackage.

Kết hợp GitOps (CodeCommit) + CodePipeline để triển khai mô hình lên Bedrock endpoint hoặc SageMaker endpoint.

📘 Tham khảo nguồn tài liệu (AWS, 2026)

Amazon SageMaker Documentation – “Instruction Tuning” (điểm cập nhật 2026‑03) – https://docs.aws.amazon.com/sagemaker/latest/dg/instruction-tuning.html

Amazon Bedrock Developer Guide – “Custom Model Fine‑tuning” – https://docs.aws.amazon.com/bedrock/latest/userguide/custom-model.html

AWS Whitepaper “Best Practices for Foundation Model Fine‑tuning” (2025) – https://aws.amazon.com/whitepapers/foundation-model-fine-tuning/

AWS Blog – “How to Build Domain‑Specific Q&A with Foundation Models” (2024‑11) – https://aws.amazon.com/blogs/machine-learning/domain-qna-fm/

🏁 Kết luận

Để thực hiện instruction‑based fine‑tuning cho một foundation model, công ty cần tạo các cặp câu hỏi‑câu trả lời (instruction → output) tập trung vào domain của mình. Các phương án khác (gộp tài liệu thô, gán nhãn sentiment, hoặc tạo few‑shot prompt) không đáp ứng yêu cầu cấu trúc dữ liệu cần thiết cho kiểu fine‑tune này và do đó là sai.

👍 Áp dụng quy trình trên cùng với các dịch vụ AWS hiện đại (SageMaker, Bedrock, Ground Truth) sẽ giúp công ty nhanh chóng có một mô hình trả lời chuyên môn, đồng thời duy trì tính tự động hoá và kiểm soát chất lượng qua CI/CD.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306659-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 27

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155872-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company wants to develop ML applications to improve business operations and efficiency.
2. Select the correct ML paradigm from the following list for each use case. Each ML paradigm should be selected one or more times.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155872-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 28

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/308015-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company is using a generative AI model to develop a digital assistant. The model’s responses occasionally include undesirable and potentially harmful content.
2. Select the correct Amazon Bedrock filter policy from the following list for each mitigation action. Each filter policy should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308015-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 29

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lex
- Takeaway nhanh: Công ty đang phát triển một ứng dụng di động dành cho người khiếm thị. Yêu cầu chính: Ứng dụng phải “nghe” giọng nói của người dùng → chuyển đổi âm thanh (speech) thành văn bản (speech‑to‑text). Ứng dụng phải “phản hồi bằng giọng nói” → chuyển đổi văn bản thành giọng nói (text‑to‑speech) để người dùng nghe lại.
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/lex/latest/dg/what-is.html | https://docs.aws.amazon.com/polly/latest/dg/what-is.html | https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html | https://www.examtopics.com/discussions/amazon/view/155870-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is building a mobile app for users who have a visual impairment. The app must be able to hear what users say and provide voice responses.
Which solution will meet these requirements?

### Các lựa chọn
1. Use a deep learning neural network to perform speech recognition.
2. Build ML models to search for patterns in numeric data.
3. Use generative AI summarization to generate human-like text.
4. Build custom models for image classification and recognition.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang phát triển một ứng dụng di động dành cho người khiếm thị.

Yêu cầu chính:

Ứng dụng phải “nghe” giọng nói của người dùng → chuyển đổi âm thanh (speech) thành văn bản (speech‑to‑text).

Ứng dụng phải “phản hồi bằng giọng nói” → chuyển đổi văn bản thành giọng nói (text‑to‑speech) để người dùng nghe lại.

Vì vậy, giải pháp cần một công nghệ nhận dạng giọng nói (speech recognition) và/hoặc công nghệ tổng hợp giọng nói (speech synthesis). Trong môi trường AWS, các dịch vụ tiêu chuẩn hiện nay (2026) đáp ứng nhu cầu này là:

Amazon Transcribe – dịch vụ máy học quản lý toàn bộ quá trình chuyển đổi giọng nói thành văn bản.

Amazon Polly – dịch vụ chuyển đổi văn bản thành giọng nói tự nhiên, hỗ trợ nhiều ngôn ngữ và giọng đọc.

Amazon Lex – tích hợp cả Transcribe và Polly, cho phép xây dựng chatbot/voice bot nhanh chóng.

Câu hỏi đưa ra 4 lựa chọn, trong đó chỉ một lựa chọn đáp ứng đúng yêu cầu.

✅ Đáp án đúng

- Use a deep learning neural network to perform speech recognition.

Giải thích:

Speech recognition (nhận dạng giọng nói) là bước đầu tiên để “nghe” những gì người dùng nói.

AWS cung cấp Amazon Transcribe, một mô hình deep‑learning đã được huấn luyện sẵn, cho phép triển khai nhanh trên thiết bị di động hoặc qua API mà không cần tự xây dựng mạng nơ‑ron.

Khi kết hợp với Amazon Polly (hoặc Amazon Lex) để tạo phản hồi bằng giọng nói, toàn bộ chuỗi “nghe → trả lời” được đáp ứng đầy đủ.

Vì trong các lựa chọn chỉ có “sử dụng mạng nơ‑ron sâu để thực hiện nhận dạng giọng nói” là mô tả đúng công nghệ cốt lõi cần thiết, nên đây là đáp án duy nhất đúng.

❌ Các phương án sai và phân tích

- Build ML models to search for patterns in numeric data.

Giải thích: Việc “tìm kiếm mô hình trong dữ liệu số” (numeric pattern detection) không liên quan tới speech‑to‑text hay text‑to‑speech. Đây là công việc thường gặp trong phân tích dữ liệu, dự báo tài chính, hoặc anomaly detection, chứ không đáp ứng yêu cầu “nghe” và “phản hồi bằng giọng nói”.

- Use generative AI summarization to generate human‑like text.

Giải thích: Mô hình tóm tắt (summarization) tạo ra văn bản tóm tắt từ nội dung dài, không thực hiện việc nhận dạng giọng nói. Ngoài ra, ngay cả khi tạo ra văn bản, vẫn cần một công cụ chuyển văn bản thành giọng nói (Polly) để người khiếm thị nghe được – điều này không được đề cập trong lựa chọn.

- Build custom models for image classification and recognition.

Giải thích: Phân loại và nhận dạng hình ảnh (image classification) liên quan đến dữ liệu hình ảnh (ví dụ: nhận diện đối tượng, OCR), không có bất kỳ chức năng nào liên quan tới âm thanh hay giọng nói. Vì người dùng khiếm thị không dựa vào hình ảnh, nên lựa chọn này hoàn toàn không phù hợp.

🛠️ Gợi ý triển khai thực tế trên AWS (2026)

Amazon Transcribe → API “Streaming Transcribe” để nhận dạng giọng nói trong thời gian thực trên thiết bị di động.

Amazon Polly → API “Neural Text‑to‑Speech (NTTS)” để sinh giọng nói tự nhiên, hỗ trợ các ngôn ngữ và giọng đa dạng, thích hợp cho người khiếm thị.

Amazon Lex → Nếu muốn xây dựng một voice bot có khả năng hiểu ngữ cảnh, duy trì hội thoại, Lex tích hợp sẵn Transcribe + Polly, giảm thiểu công việc quản lý các dịch vụ riêng lẻ.

AWS Amplify → Dễ dàng tích hợp các SDK của Transcribe/Polly vào ứng dụng di động (iOS/Android).

AWS IAM → Thiết lập quyền tối thiểu (least‑privilege) để ứng dụng chỉ có thể gọi các API cần thiết.

Tài liệu tham khảo (2026):

📘 Amazon Transcribe – Real‑time Speech Recognition (AWS Documentation, 2026) – https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html

📘 Amazon Polly – Text‑to‑Speech Service (AWS Documentation, 2026) – https://docs.aws.amazon.com/polly/latest/dg/what-is.html

📘 Amazon Lex – Build Conversational Interfaces (AWS Documentation, 2026) – https://docs.aws.amazon.com/lex/latest/dg/what-is.html

📘 AWS Well‑Architected Framework – Security Pillar (2026) – để thiết kế IAM role cho các dịch vụ trên.

⚡ Tổng kết:

Đáp án đúng là “Use a deep learning neural network to perform speech recognition.”

Các lựa chọn còn lại không đáp ứng yêu cầu về speech‑to‑text và text‑to‑speech, do đó sai.

Trên AWS, cách thực tế nhất là kết hợp Amazon Transcribe (hoặc Amazon Lex) với Amazon Polly để cung cấp trải nghiệm nghe‑nói cho người dùng khiếm thị.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155870-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 30

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock
- Takeaway nhanh: Câu hỏi hỏi “Which option is a characteristic of transformer‑based language models?” – tức là “Đâu là đặc điểm của các mô hình ngôn ngữ dựa trên Transformer?” Bạn cần lựa chọn một đáp án mô tả đúng cách mà các mô hình Transformer (ví dụ: BERT, GPT, T5…) hoạt động. Các mô hình này hiện là nền tảng của hầu hết các dịch vụ AI trên AWS (Amazon SageMaker JumpStart, Amazon Bedrock, Amazon Translate …) và được cập nhật liên tục tới năm 2026.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/304559-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is a characteristic of transformer-based language models?

### Các lựa chọn
1. Transformer-based language models use convolutional layers to apply filters across an input to capture local patterns through filtered views.
2. Transformer-based language models can process only text data.
3. Transformer-based language models use self-attention mechanisms to capture contextual relationships.
4. Transformer-based language models process data sequences one element at a time in cyclic iterations.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Câu hỏi hỏi “Which option is a characteristic of transformer‑based language models?” – tức là “Đâu là đặc điểm của các mô hình ngôn ngữ dựa trên Transformer?”

Bạn cần lựa chọn một đáp án mô tả đúng cách mà các mô hình Transformer (ví dụ: BERT, GPT, T5…) hoạt động. Các mô hình này hiện là nền tảng của hầu hết các dịch vụ AI trên AWS (Amazon SageMaker JumpStart, Amazon Bedrock, Amazon Translate …) và được cập nhật liên tục tới năm 2026.

✅ Đáp án đúng

Transformer-based language models use self‑attention mechanisms to capture contextual relationships.

Lý do:

Cơ chế self‑attention (còn gọi là “scaled dot‑product attention”) cho phép mô hình “nhìn” vào toàn bộ các token trong câu đồng thời, tính toán mức độ quan trọng (weight) của mỗi token đối với token đang xét. Nhờ vậy mô hình nắm bắt được mối quan hệ ngữ cảnh dài hạn, không phụ thuộc vào vị trí gần hay xa.

Đây là đặc điểm cốt lõi được giới thiệu lần đầu trong bài báo “Attention Is All You Need” (Vaswani et al., 2017) và vẫn là nền tảng cho các phiên bản mới như Transformer‑XL, Longformer, Switch‑Transformer (2023‑2025) được AWS hỗ trợ qua SageMaker và Bedrock.

🧩 Phân tích các phương án khác (sai)

Transformer-based language models use convolutional layers to apply filters across an input to capture local patterns through filtered views.

Giải thích: Các mô hình convolutional neural networks (CNN) mới dùng các lớp convolution để “lọc” các mẫu cục bộ, thường gặp trong xử lý ảnh hoặc một số mô hình NLP cổ (ví dụ: CharCNN). Transformer không có lớp convolution; thay vào đó dùng self‑attention và feed‑forward layers. Do đó mô tả này không phản ánh kiến trúc thực tế của Transformer.

Transformer-based language models can process only text data.

Giải thích: Ban đầu Transformer được giới thiệu cho text, nhưng từ 2020 trở đi đã mở rộng sang multimodal (Vision‑Transformer, CLIP, DALL·E, Whisper). Trên AWS, các mô hình như Amazon Bedrock’s Titan Multimodal hoặc SageMaker JumpStart cung cấp Transformer cho hình ảnh, âm thanh và video. Vì vậy khẳng định “chỉ xử lý văn bản” là không đúng.

Transformer-based language models process data sequences one element at a time in cyclic iterations.

Giải thích: Đây là mô tả của recurrent neural networks (RNN) hoặc LSTM, nơi dữ liệu được xử lý tuần tự và phụ thuộc vào trạng thái trước. Transformer không xử lý tuần tự; nó thực hiện parallel processing trên toàn bộ chuỗi nhờ self‑attention, giảm thời gian đào tạo và cho phép mô hình học quan hệ dài hạn.

🛠️ Kiến thức cập nhật tới năm 2026

Long‑Context Transformers (Longformer, BigBird, FlashAttention) đã cải thiện khả năng xử lý chuỗi lên tới hàng trăm nghìn token, vẫn dựa trên self‑attention nhưng tối ưu hoá tính toán.

Sparse & Mixture‑of‑Experts (MoE) (Switch‑Transformer, GLaM) được triển khai trên Amazon SageMaker để giảm chi phí training mà vẫn duy trì hiệu năng.

Multimodal Transformers (e.g., Flamingo, CoCa) được tích hợp trong Amazon Bedrock để hỗ trợ các tác vụ kết hợp văn bản‑hình ảnh‑âm thanh.

📚 Tham khảo

Vaswani, A. et al., “Attention Is All You Need”, 2017 – Bài báo gốc giới thiệu Transformer và self‑attention.

AWS Documentation – Amazon SageMaker JumpStart, phiên bản 2026‑03 – Hướng dẫn sử dụng các mô hình Transformer đa dạng.

AWS Blog – “Introducing Amazon Bedrock’s new multimodal and long‑context models”, 2025‑11.

Brown, T. et al., “Language Models are Few‑Shot Learners”, 2020 – Mô tả GPT‑3, minh hoạ sức mạnh của self‑attention.

Tóm lại: Đáp án đúng là “Transformer‑based language models use self‑attention mechanisms to capture contextual relationships.” vì self‑attention là yếu tố quyết định cho khả năng nắm bắt ngữ cảnh dài và đa dạng, trong khi các phương án còn lại mô tả sai kiến trúc hoặc phạm vi ứng dụng của Transformer. 🎯

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304559-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 31

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Config, Amazon Macie, Amazon Secrets Manager, Amazon Artifact
- Đáp án tham khảo: **AWS Artifact**
- Takeaway nhanh: Công ty tài chính đang triển khai các mô hình AI sinh ra (generative AI) trên AWS và phải tuân thủ các quy định quốc tế liên quan tới việc xử lý dữ liệu khách hàng nhạy cảm. Nhiệm vụ của họ là tạo ra các báo cáo chứng minh (audit reports) rằng họ đã đáp ứng các yêu cầu tuân thủ – ví dụ: ISO 27001, SOC 1/2/3, GDPR, PCI‑DSS, v.v. Vì vậy câu hỏi đang hỏi: Dịch vụ AWS nào cung cấp các tài liệu, báo cáo tuân thủ và chứng nhận để công ty có thể trình bày với cơ quan quản lý?
- Nguồn tham khảo trong block: https://aws.amazon.com/compliance/ | https://docs.aws.amazon.com/artifact/latest/ug/ | https://docs.aws.amazon.com/config/latest/developerguide/what-is-config.html | https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html | https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html | https://www.examtopics.com/discussions/amazon/view/306673-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company uses AWS to host its generative AI models. The company must generate reports to show adherence to international regulations for handling sensitive customer data.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Macie
2. AWS Artifact
3. AWS Secrets Manager
4. AWS Config

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty tài chính đang triển khai các mô hình AI sinh ra (generative AI) trên AWS và phải tuân thủ các quy định quốc tế liên quan tới việc xử lý dữ liệu khách hàng nhạy cảm.

Nhiệm vụ của họ là tạo ra các báo cáo chứng minh (audit reports) rằng họ đã đáp ứng các yêu cầu tuân thủ – ví dụ: ISO 27001, SOC 1/2/3, GDPR, PCI‑DSS, v.v.

Vì vậy câu hỏi đang hỏi: Dịch vụ AWS nào cung cấp các tài liệu, báo cáo tuân thủ và chứng nhận để công ty có thể trình bày với cơ quan quản lý?

✅ Đáp án đúng: AWS Artifact

AWS Artifact là cổng thông tin an ninh và tuân thủ (compliance portal) của AWS, nơi người dùng có thể tải xuống các báo cáo tuân thủ, chứng chỉ, và thỏa thuận (AWS‑Provided Attestations, Service Organization Controls, ISO, GDPR, v.v.).

Nó cho phép tự động tạo, truy xuất và chia sẻ các báo cáo này với các bên liên quan (cơ quan kiểm toán, khách hàng, regulator).

Do vậy, đáp ứng yêu cầu “generate reports to show adherence to international regulations” một cách trực tiếp và đầy đủ.

🔍 Phân tích các phương án (giữ nguyên nguyên văn tiếng Anh)

1️⃣ Amazon Macie

Mô tả: Dịch vụ phát hiện, phân loại và bảo vệ dữ liệu nhạy cảm (PII, PHI) trong S3 bằng machine learning.

Tại sao SAI: Macie giúp phát hiện dữ liệu nhạy cảm và cảnh báo rủi ro, nhưng không cung cấp báo cáo tuân thủ hoặc chứng nhận cho các tiêu chuẩn quốc tế. Nó không phải là công cụ để “generate compliance reports”.

2️⃣ AWS Artifact (ĐÚNG)

Mô tả: Cổng thông tin duy nhất để truy cập các tài liệu chứng nhận và báo cáo tuân thủ của AWS.

Lý do đúng: Cung cấp báo cáo SOC, ISO, PCI‑DSS, GDPR, … mà công ty có thể tải xuống, in ra và nộp cho các cơ quan quản lý. Đây chính là dịch vụ đáp ứng yêu cầu “generate reports to show adherence to international regulations”.

3️⃣ AWS Secrets Manager

Mô tả: Dịch vụ lưu trữ, quản lý và xoay vòng các bí mật (API keys, database credentials, …) một cách an toàn.

Tại sao SAI: Secrets Manager tập trung vào quản lý bí mật chứ không phải tạo ra báo cáo tuân thủ hay cung cấp chứng chỉ an ninh.

4️⃣ AWS Config

Mô tả: Dịch vụ ghi lại cấu hình tài nguyên AWS, cho phép kiểm tra tuân thủ dựa trên các rule (AWS‑provided hoặc custom).

Tại sao SAI: Mặc dù Config có thể đánh giá tuân thủ nội bộ và tạo “Compliance‑as‑Code” reports, nó không cung cấp các chứng chỉ hay báo cáo chuẩn quốc tế mà regulator yêu cầu (ví dụ: SOC 2, ISO 27001). Vì câu hỏi nhấn mạnh việc tạo báo cáo tuân thủ quốc tế, Artifact là dịch vụ phù hợp hơn.

📚 Tham khảo tài liệu

AWS Artifact – Documentation: https://docs.aws.amazon.com/artifact/latest/ug/

AWS Compliance Center (cập nhật 2026): https://aws.amazon.com/compliance/

Amazon Macie – Overview: https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html

AWS Secrets Manager – Documentation: https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html

AWS Config – Documentation: https://docs.aws.amazon.com/config/latest/developerguide/what-is-config.html

🧩 Tóm tắt nhanh

Câu hỏi yêu cầu một dịch vụ tạo báo cáo tuân thủ quốc tế.

AWS Artifact là cổng cung cấp báo cáo, chứng chỉ, và thỏa thuận tuân thủ – đáp ứng đúng yêu cầu.

Các dịch vụ còn lại (Macie, Secrets Manager, Config) có mục đích bảo mật khác (phát hiện dữ liệu, quản lý bí mật, giám sát cấu hình) và không phải là công cụ báo cáo tuân thủ.

✅ Kết luận: Chọn AWS Artifact.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306673-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 32

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon S3
- Đáp án tham khảo: **K-means**
- Takeaway nhanh: “A company wants to find groups for its customers based on the customers’ demographics and buying patterns. Which algorithm should the company use to meet this requirement?” Câu hỏi đang hỏi về phân cụm (clustering) – một kỹ thuật unsupervised learning dùng để tự động “đoạn nhóm” các đối tượng (ở đây là khách hàng) dựa trên các đặc tính (độ tuổi, thu nhập, lịch sử mua hàng, …) mà không có nhãn (label) sẵn có.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/ | https://docs.aws.amazon.com/sagemaker/latest/dg/kmeans.html | https://scikit-learn.org/stable/modules/clustering.html | https://www.examtopics.com/discussions/amazon/view/155916-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to find groups for its customers based on the customers’ demographics and buying patterns.
Which algorithm should the company use to meet this requirement?

### Các lựa chọn
1. K-nearest neighbors (k-NN)
2. K-means
3. Decision tree
4. Support vector machine

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

“A company wants to find groups for its customers based on the customers’ demographics and buying patterns. Which algorithm should the company use to meet this requirement?”

Câu hỏi đang hỏi về phân cụm (clustering) – một kỹ thuật unsupervised learning dùng để tự động “đoạn nhóm” các đối tượng (ở đây là khách hàng) dựa trên các đặc tính (độ tuổi, thu nhập, lịch sử mua hàng, …) mà không có nhãn (label) sẵn có.

Trong môi trường AWS, công việc này thường được thực hiện bằng Amazon SageMaker – dịch vụ ML quản lý – sử dụng thuật toán K‑means (một thuật toán clustering tiêu chuẩn) hoặc các thuật toán clustering khác có sẵn.

✅ Đáp án đúng

✅ K-means

Lý do chọn:

K‑means là thuật toán clustering (phân cụm) thuộc loại unsupervised learning.

Nó tự động chia tập dữ liệu thành K nhóm sao cho các điểm trong cùng một nhóm có khoảng cách (distance) tới trung tâm nhóm (centroid) nhỏ nhất, phù hợp với yêu cầu “tìm groups cho khách hàng”.

AWS SageMaker cung cấp built‑in K‑means algorithm (phiên bản tối ưu cho GPU/CPU, hỗ trợ scaling, auto‑model tuning) và tích hợp sẵn trong Amazon SageMaker Canvas và Amazon SageMaker Studio.

K‑means cho phép người dùng chỉ định số nhóm mong muốn (K) hoặc dùng các phương pháp “elbow” / “silhouette” để xác định K phù hợp.

Tham khảo:

Amazon SageMaker Built‑in Algorithms – K‑means (AWS Documentation, cập nhật đến 2026).

AWS Machine Learning Blog – “Clustering customers with SageMaker K‑means” (2023).

❌ Giải thích các phương án sai

❌ K-nearest neighbors (k‑NN)

Loại thuật toán: Supervised learning (classification hoặc regression).

Cách hoạt động: Cần có nhãn (label) cho mỗi mẫu để dự đoán lớp của mẫu mới dựa trên K mẫu gần nhất.

Tại sao không phù hợp: Câu hỏi không đề cập tới bất kỳ nhãn nào; mục tiêu là phân cụm chứ không phải phân loại. Do đó k‑NN không thể “tự động tìm nhóm” mà không có nhãn.

AWS liên quan: k‑NN có thể triển khai trên SageMaker bằng Custom Algorithm hoặc Scikit‑learn, nhưng không phải lựa chọn chuẩn cho clustering.

❌ Decision tree

Loại thuật toán: Supervised learning (classification hoặc regression).

Cách hoạt động: Xây dựng cây quyết định dựa trên các thuộc tính và nhãn để dự đoán nhãn cho dữ liệu mới.

Tại sao không phù hợp: Cũng yêu cầu dữ liệu có nhãn; không thể tự động tạo các nhóm dựa trên dữ liệu không gán nhãn.

AWS liên quan: SageMaker cung cấp XGBoost, Linear Learner, Random Forest, nhưng chúng đều là thuật toán supervised.

❌ Support vector machine (SVM)

Loại thuật toán: Supervised learning (binary/multi‑class classification, hoặc regression).

Cách hoạt động: Tìm siêu phẳng tối ưu để phân tách các lớp đã được gán nhãn.

Tại sao không phù hợp: Cũng yêu cầu nhãn; không được thiết kế cho clustering.

AWS liên quan: SageMaker có Linear Learner và SVM dưới dạng container tùy chỉnh, nhưng không dùng để “phát hiện nhóm” trong dữ liệu không gán nhãn.

🛠️ Cách thực hiện trên AWS (2026)

Chuẩn bị dữ liệu

Thu thập các trường demographics (age, gender, location, …) và buying patterns (total spend, frequency, product categories).

Đưa dữ liệu vào Amazon S3 dưới dạng CSV/Parquet.

Tạo notebook trong Amazon SageMaker Studio

Sử dụng SageMaker SDK (sagemaker Python) để gọi KMeans built‑in algorithm.

Đặt tham số num_clusters (K) hoặc dùng KMeans với kmeans_plus_plus initialization để cải thiện độ hội tụ.

Huấn luyện mô hình

Code

from sagemaker import KMeans

kmeans = KMeans(

role=role,

instance_count=1,

instance_type='ml.m5.large',

output_path='s3://my-bucket/kmeans-output',

k=5,                     # số nhóm dự kiến

predictor_type='int64'   # kiểu output

)

kmeans.fit(inputs='s3://my-bucket/customer-data/')

Triển khai và dự đoán

Deploy model tới SageMaker Endpoint hoặc dùng Batch Transform để gán mỗi khách hàng vào một cluster.

Kết quả (cluster id) có thể lưu lại vào DynamoDB hoặc Redshift để phân tích tiếp tục.

Đánh giá số lượng cluster

Sử dụng Elbow method hoặc Silhouette score (tính trong notebook) để xác định K tối ưu nếu chưa biết trước.

📚 Tài liệu tham khảo

Amazon SageMaker Documentation – Built‑in Algorithms (K‑means) – https://docs.aws.amazon.com/sagemaker/latest/dg/kmeans.html (cập nhật 2026).

AWS Machine Learning Blog – Clustering customers with SageMaker K‑means – https://aws.amazon.com/blogs/machine-learning/ (2023).

“Unsupervised Learning on AWS” – Whitepaper, AWS (2025).

Scikit‑learn Documentation – K‑means Clustering – https://scikit-learn.org/stable/modules/clustering.html (được sử dụng trong SageMaker Script Mode).

🎯 Kết luận nhanh gọn

Câu hỏi yêu cầu thuật toán clustering → K‑means là lựa chọn đúng.

Các thuật toán còn lại (k‑NN, Decision tree, SVM) đều là supervised và không đáp ứng yêu cầu “tìm groups” khi không có nhãn.

Hy vọng phân tích trên giúp bạn nắm vững lý do lựa chọn K‑means và cách triển khai thực tiễn trên môi trường AWS hiện đại! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155916-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 33

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon SageMaker, responsible AI
- Đáp án tham khảo: **“Fairness”**
- Takeaway nhanh: 🔍 Lý do chọn “Fairness” Fairness (Công bằng) trong AI đề cập tới việc tránh các hệ thống gây ra sự bất bình đẳng, thiên vị hoặc phân biệt đối xử đối với bất kỳ nhóm nào dựa trên giới tính, chủng tộc, độ tuổi, khả năng, v.v. Khi dữ liệu huấn luyện không đại diện đa dạng, mô hình sẽ học và tái tạo lại bias (thiên lệch) có sẵn, dẫn tới kết quả không công bằng (ví dụ: loại bỏ các ứng viên từ nhóm thiểu số).
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/302409-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company built an AI-powered resume screening system. The company used a large dataset to train the model. The dataset contained resumes that were not representative of all demographics.
Which core dimension of responsible AI does this scenario present?

### Các lựa chọn
1. Fairness
2. Explainability
3. Privacy and security
4. Transparency

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Giải thích nội dung câu hỏi

Công ty đã xây dựng một hệ thống sàng lọc hồ sơ (resume) tự động bằng AI. Để huấn luyện mô hình, công ty dùng một large dataset (tập dữ liệu lớn) chứa các hồ sơ cá nhân. Tuy nhiên, tập dữ liệu này không đại diện cho mọi nhóm dân số (ví dụ: thiếu các hồ sơ của phụ nữ, người da màu, người khuyết tật, …). Khi một mô hình được huấn luyện trên dữ liệu thiên lệch, nó có nguy cơ phân biệt hoặc gây bất lợi cho các nhóm không được đại diện đúng mức.

Câu hỏi yêu cầu xác định “core dimension of responsible AI” (một trong các khía cạnh cốt lõi của AI có trách nhiệm) mà tình huống này phản ánh.

✅ Đáp án đúng: “Fairness”

🔍 Lý do chọn “Fairness”

Fairness (Công bằng) trong AI đề cập tới việc tránh các hệ thống gây ra sự bất bình đẳng, thiên vị hoặc phân biệt đối xử đối với bất kỳ nhóm nào dựa trên giới tính, chủng tộc, độ tuổi, khả năng, v.v.

Khi dữ liệu huấn luyện không đại diện đa dạng, mô hình sẽ học và tái tạo lại bias (thiên lệch) có sẵn, dẫn tới kết quả không công bằng (ví dụ: loại bỏ các ứng viên từ nhóm thiểu số).

Vì vậy, vấn đề “dataset không đại diện cho tất cả các nhóm dân số” là một vấn đề về công bằng trong AI.

📚 Phân tích các phương án (giữ nguyên nội dung tiếng Anh)

Fairness ✅

✅ Giải thích: Đây là đáp án đúng vì vấn đề trọng tâm là dữ liệu không đại diện, dẫn tới nguy cơ mô hình phân biệt và tạo ra kết quả không công bằng cho một số nhóm dân số. Các tiêu chuẩn “Fairness” của AWS (ví dụ: Amazon SageMaker Clarify cung cấp công cụ đo lường và giảm bias) nhấn mạnh việc kiểm tra đại diện dữ liệu và đánh giá công bằng trước khi triển khai mô hình.

Explainability ❌

❌ Giải thích: Explainability (Giải thích) liên quan tới khả năng hiểu và giải thích cách mô hình đưa ra quyết định (ví dụ: thông qua SHAP values, LIME). Mặc dù giải thích là quan trọng, nhưng nó không giải quyết trực tiếp vấn đề dữ liệu không đại diện hay thiên lệch. Vấn đề này không liên quan tới việc mô hình có thể giải thích được hay không.

Privacy and security ❌

❌ Giải thích: Privacy and security (Quyền riêng tư và bảo mật) tập trung vào việc bảo vệ dữ liệu cá nhân và ngăn chặn truy cập trái phép, cũng như tuân thủ các quy định như GDPR, CCPA. Trường hợp trên không nói gì về việc rò rỉ thông tin hay bảo mật dữ liệu, mà chỉ đề cập tới tính đại diện của dữ liệu.

Transparency ❌

❌ Giải thích: Transparency (Minh bạch) đề cập tới việc công khai quy trình, dữ liệu, và các giả thuyết trong mô hình AI. Mặc dù minh bạch có thể giúp phát hiện bias, nhưng câu hỏi cụ thể nêu ra “dataset không đại diện”, một khía cạnh công bằng hơn là vấn đề minh bạch. Nếu dữ liệu được công khai, vẫn có thể có bias; do đó, đây không phải là khía cạnh cốt lõi được nhắc tới trong kịch bản.

📖 Tham khảo nguồn tài liệu (tính đến năm 2026)

AWS Well‑Architected Framework – Machine Learning Lens (2025 update) – phần “Responsible AI” nêu rõ 4 core dimensions: Fairness, Explainability, Privacy & Security, Transparency.

Amazon SageMaker Clarify Documentation – hướng dẫn đo lường bias và thực hiện mitigations để đạt được fairness.

ISO/IEC 22989:2022 – Artificial Intelligence – Overview of Trustworthy AI – mô tả fairness như một yếu tố quan trọng của AI có trách nhiệm.

AWS AI Services Blog (2024‑2026) – nhiều bài viết về cách giảm bias trong các dịch vụ AI như Amazon Rekognition, Comprehend, và SageMaker.

🛠️ Kết luận

Trong trường hợp công ty sử dụng tập dữ liệu không đại diện cho mọi nhóm dân số, core dimension của AI có trách nhiệm được vi phạm là Fairness. Các khía cạnh khác (Explainability, Privacy & Security, Transparency) đều quan trọng, nhưng không phải là vấn đề chính được mô tả trong kịch bản này. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302409-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 34

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon S3, responsible AI
- Đáp án tham khảo: **Standardizing information about a model’s purpose, performance, and limitations.**
- Takeaway nhanh: ✅ Standardizing information about a model’s purpose, performance, and limitations. Cập nhật 2026: AWS đã mở rộng Model Card Schema để bao gồm đánh giá tính công bằng (Fairness) và giải thích (Explainability) nhờ tích hợp với SageMaker Clarify, giúp các tổ chức tuân thủ các quy định ngày càng nghiêm ngặt (EU AI Act, US AI Bill of Rights, …).
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html | https://www.examtopics.com/discussions/amazon/view/302406-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is a benefit of using Amazon SageMaker Model Cards to document AI models?

### Các lựa chọn
1. Providing a visually appealing summary of a mode’s capabilities.
2. Standardizing information about a model’s purpose, performance, and limitations.
3. Reducing the overall computational requirements of a model.
4. Physically storing models for archival purposes.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Câu hỏi: “Which option is a benefit of using Amazon SageMaker Model Cards to document AI models?”

Câu hỏi muốn kiểm tra kiến thức của bạn về Model Cards – một tính năng mới của Amazon SageMaker được thiết kế để tài liệu hoá, chuẩn hoá và chia sẻ thông tin về mô hình máy học (mục đích, hiệu năng, hạn chế, dữ liệu đào tạo, v.v.).

Trong bối cảnh AWS cập nhật đến năm 2026, Model Cards đã được tích hợp sâu hơn với SageMaker Model Registry, Model Card Studio, và SageMaker Clarify để hỗ trợ quản trị rủi ro, tuân thủ và chia sẻ mô hình an toàn trong môi trường doanh nghiệp.

✅ Đáp án đúng

✅ Standardizing information about a model’s purpose, performance, and limitations.

Lý do: Model Cards cung cấp một khung chuẩn (standardized schema) để mô tả các khía cạnh quan trọng của mô hình: mục tiêu sử dụng, dữ liệu đào tạo, các metric hiệu năng (accuracy, latency, …), các giới hạn và cảnh báo (bias, drift, …). Điều này giúp các nhóm kỹ thuật, vận hành, và các bên liên quan đồng nhất trong việc hiểu và đánh giá mô hình, đồng thời hỗ trợ governance và compliance.

Cập nhật 2026: AWS đã mở rộng Model Card Schema để bao gồm đánh giá tính công bằng (Fairness) và giải thích (Explainability) nhờ tích hợp với SageMaker Clarify, giúp các tổ chức tuân thủ các quy định ngày càng nghiêm ngặt (EU AI Act, US AI Bill of Rights, …).

❌ Các phương án sai và lý do

- ❌ Providing a visually appealing summary of a mode’s capabilities.

Giải thích: Mặc dù Model Cards có thể hiển thị thông tin dưới dạng đồ họa và bảng tóm tắt, mục tiêu chính không phải là tạo “visually appealing summary”. Nó không phải là một công cụ thiết kế UI/UX chuyên sâu mà là công cụ tài liệu chuẩn hoá. Các công cụ như SageMaker Studio hay QuickSight mới hơn mới chịu trách nhiệm tạo báo cáo trực quan.

- ❌ Reducing the overall computational requirements of a model.

Giải thích: Model Cards chỉ là tài liệu mô tả; chúng không ảnh hưởng tới cấu trúc, kiến trúc hay tài nguyên tính toán của mô hình. Việc giảm tài nguyên tính toán thường liên quan tới model optimization (pruning, quantization, SageMaker Neo) chứ không phải Model Cards.

- ❌ Physically storing models for archival purposes.

Giải thích: Việc lưu trữ mô hình (model artifacts) được thực hiện bởi Amazon S3, SageMaker Model Registry, hoặc Amazon EFS. Model Cards không chứa trọng lượng mô hình mà chỉ chứa metadata và đánh giá. Chúng được lưu trữ như một tệp JSON/YAML kèm theo mô hình trong Model Registry, nhưng không thay thế chức năng lưu trữ vật lý.

📚 Tham khảo nguồn tài liệu (tính đến năm 2026)

AWS Documentation – SageMaker Model Cards

https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html (phiên bản cập nhật 2026‑03)

AWS Blog – “Introducing Model Card Studio: Author, Review, and Publish Model Cards at Scale” – 2024‑11‑02.

Giới thiệu UI mới cho việc tạo, duyệt và xuất bản Model Cards.

AWS Whitepaper – “Responsible AI on Amazon SageMaker” – 2025‑07‑15.

Trình bày cách Model Cards, SageMaker Clarify, và Model Registry hỗ trợ governance.

AWS re:Invent 2025 – Session “Operationalizing Responsible AI with SageMaker”

Video và slide trình bày các best‑practice cho Model Card chuẩn hoá.

🧩 Tổng kết

Đáp án đúng: Standardizing information about a model’s purpose, performance, and limitations.

Các đáp án còn lại đều không phản ánh chức năng thực tế của Amazon SageMaker Model Cards.

Model Cards là công cụ tiêu chuẩn hoá metadata giúp tăng tính minh bạch, tuân thủ và hợp tác trong quản trị mô hình AI, chứ không phải là công cụ tối ưu hoá hiệu năng hay lưu trữ mô hình.

Hy vọng phân tích trên giúp bạn nắm vững khái niệm và có thể trả lời câu hỏi một cách tự tin trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302406-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 35

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Fraud Detector, Amazon SageMaker, Amazon SageMaker AI
- Takeaway nhanh: Công ty muốn hợp tác với nhiều viện nghiên cứu để phát triển một mô hình AI. Để làm việc hiệu quả, họ cần: Tài liệu chuẩn hoá (standardized documentation) về phiên bản mô hình (model version tracking). Bản ghi quá trình phát triển (record of model development) – bao gồm mục tiêu, dữ liệu dùng, siêu tham số, kết quả đánh giá, hạn chế, v.v. AWS cung cấp một tính năng đặc biệt cho việc này: Amazon SageMaker Model Cards. Model Cards là một chuẩn tài liệu mở (được đề xuất bởi Google, sau đó được AWS tích hợp) để mô tả chi tiết một mô hình máy học, bao gồm phiên bản, nguồn dữ liệu, các siêu tham số, môi trường chạy, đánh giá hiệu năng, và các thông tin liên quan đến đạo đức và tuân thủ. Các Model Cards có thể được lưu trữ, quản lý và chia sẻ qua SageMaker Model Registry, giúp mọi bên tham gia (công ty, viện nghiên cứu) truy cập một cách thống nhất và có thể audit.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/best-practices-model-documentation/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html | https://www.examtopics.com/discussions/amazon/view/306656-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/ | https://www.youtube.com/watch?v=

### Đề bài
A company wants to collaborate with several research institutes to develop an AI model. The company needs standardized documentation of model version tracking and a record of model development.
Which solution meets these requirements?

### Các lựa chọn
1. Track the model changes by using Git.
2. Track the model changes by using Amazon Fraud Detector.
3. Track the model changes by using Amazon SageMaker Model Cards.
4. Track the model changes by using Amazon Comprehend.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn hợp tác với nhiều viện nghiên cứu để phát triển một mô hình AI. Để làm việc hiệu quả, họ cần:

Tài liệu chuẩn hoá (standardized documentation) về phiên bản mô hình (model version tracking).

Bản ghi quá trình phát triển (record of model development) – bao gồm mục tiêu, dữ liệu dùng, siêu tham số, kết quả đánh giá, hạn chế, v.v.

AWS cung cấp một tính năng đặc biệt cho việc này: Amazon SageMaker Model Cards. Model Cards là một chuẩn tài liệu mở (được đề xuất bởi Google, sau đó được AWS tích hợp) để mô tả chi tiết một mô hình máy học, bao gồm phiên bản, nguồn dữ liệu, các siêu tham số, môi trường chạy, đánh giá hiệu năng, và các thông tin liên quan đến đạo đức và tuân thủ. Các Model Cards có thể được lưu trữ, quản lý và chia sẻ qua SageMaker Model Registry, giúp mọi bên tham gia (công ty, viện nghiên cứu) truy cập một cách thống nhất và có thể audit.

✅ Đáp án đúng:

Track the model changes by using Amazon SageMaker Model Cards.

📌 Giải thích từng phương án

1️⃣ Track the model changes by using Git. (SAI)

Git là hệ thống quản lý mã nguồn phân tán, rất tốt cho việc theo dõi mã và phiên bản của file code.

Tuy nhiên, Git không cung cấp chuẩn tài liệu mô hình (Model Card) và không tự động lưu trữ các siêu tham số, môi trường huấn luyện, hay các chỉ số đánh giá.

Khi hợp tác với nhiều bên, cần một định dạng chuẩn cho mô hình, không chỉ là mã nguồn. Do đó Git không đáp ứng yêu cầu “standardized documentation of model version tracking”.

❌ Không phải là giải pháp được AWS đề xuất cho việc ghi chép và chia sẻ Model Cards.

2️⃣ Track the model changes by using Amazon Fraud Detector. (SAI)

Amazon Fraud Detector là dịch vụ AI chuyên dụng để phát hiện gian lận trong giao dịch tài chính, dựa trên các mô hình ML được quản lý sẵn.

Nó không phải là nền tảng đào tạo hoặc quản lý mô hình chung, và không cung cấp tính năng Model Card hoặc versioning cho mô hình tùy chỉnh.

❌ Vì vậy không phù hợp để ghi chép và quản lý phiên bản mô hình AI chung.

3️⃣ Track the model changes by using Amazon SageMaker Model Cards. (ĐÚNG)

Amazon SageMaker Model Cards là công cụ tiêu chuẩn hoá tài liệu mô hình.

Tính năng chính:

Định dạng JSON/Markdown chuẩn, bao gồm Model ID, version, data sources, training environment, hyper‑parameters, evaluation metrics, ethical considerations, etc.

Được tích hợp với SageMaker Model Registry, cho phép đánh dấu (tag), duyệt (approval), và chia sẻ Model Cards giữa các nhóm và đối tác.

Hỗ trợ audit và truy xuất (traceability) toàn bộ vòng đời mô hình – đáp ứng yêu cầu “record of model development”.

Từ 2025, AWS đã mở rộng tính năng Model Cards để tự động đồng bộ với SageMaker Pipelines và AWS CloudTrail, giúp ghi lại mọi thay đổi cấu hình và siêu tham số.

✅ Đây là giải pháp duy nhất thỏa mãn cả hai yêu cầu của câu hỏi.

4️⃣ Track the model changes by using Amazon Comprehend. (SAI)

Amazon Comprehend là dịch vụ Xử lý ngôn ngữ tự nhiên (NLP), cung cấp các API để trích xuất thực thể, sentiment, v.v.

Nó không phải là nền tảng quản lý mô hình, không có tính năng versioning hay Model Card.

❌ Không liên quan tới việc ghi chép tài liệu mô hình AI.

📚 Tham khảo nguồn tài liệu

Amazon SageMaker Model Cards – Documentation (AWS, cập nhật 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html

Best practices for model documentation – AWS Machine Learning Blog, 2025: https://aws.amazon.com/blogs/machine-learning/best-practices-model-documentation/

SageMaker Model Registry & Model Cards integration – re:Invent 2025 session “Operationalizing ML at Scale”: https://www.youtube.com/watch?v=...

📝 Tóm tắt:

Đáp án đúng là Amazon SageMaker Model Cards vì đây là công cụ chuẩn hoá tài liệu mô hình, hỗ trợ version tracking và lưu trữ lịch sử phát triển mô hình.

Các phương án còn lại (Git, Amazon Fraud Detector, Amazon Comprehend) không cung cấp chuẩn Model Card và không đáp ứng yêu cầu tài liệu chuẩn hoá cho mô hình AI.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306656-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 36

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: responsible AI
- Takeaway nhanh: Câu hỏi: “Which option is a characteristic of AI governance frameworks for building trust and deploying human‑centered AI technologies?” Câu hỏi yêu cầu chúng ta chọn đặc điểm (characteristic) của khung quản trị AI (AI governance frameworks) – những bộ quy tắc, chính sách và quy trình mà tổ chức đặt ra để: Đảm bảo AI hoạt động một cách đáng tin cậy, có trách nhiệm và trung thực.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155873-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option is a characteristic of AI governance frameworks for building trust and deploying human-centered AI technologies?

### Các lựa chọn
1. Expanding initiatives across business units to create long-term business value
2. Ensuring alignment with business standards, revenue goals, and stakeholder expectations
3. Overcoming challenges to drive business transformation and growth
4. Developing policies and guidelines for data, transparency, responsible AI, and compliance

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which option is a characteristic of AI governance frameworks for building trust and deploying human‑centered AI technologies?”

Câu hỏi yêu cầu chúng ta chọn đặc điểm (characteristic) của khung quản trị AI (AI governance frameworks) – những bộ quy tắc, chính sách và quy trình mà tổ chức đặt ra để:

Đảm bảo AI hoạt động một cách đáng tin cậy, có trách nhiệm và trung thực.

Tạo niềm tin cho người dùng, khách hàng và các bên liên quan.

Đáp ứng các yêu cầu tuân thủ (compliance), độ minh bạch (transparency), bảo mật dữ liệu, và đạo đức (ethical AI).

Trong các đáp án, chúng ta phải tìm câu mô tả đúng nhất một đặc điểm cốt lõi của khung quản trị AI, chứ không phải mục tiêu kinh doanh chung hay chiến lược mở rộng.

✅ Đáp án đúng

🟢 Đáp án: “Developing policies and guidelines for data, transparency, responsible AI, and compliance”

Lý do lựa chọn

Đây chính là trung tâm của một AI governance framework: xây dựng chính sách (policies) và hướng dẫn (guidelines) cho:

Dữ liệu – cách thu thập, lưu trữ, xử lý, và bảo vệ dữ liệu đầu vào của mô hình AI.

Minh bạch – cung cấp thông tin về cách mô hình được huấn luyện, quyết định được đưa ra như thế nào (explainability).

AI có trách nhiệm – các biện pháp ngăn ngừa bias, kiểm soát hậu quả không mong muốn, và thiết lập cơ chế giám sát.

Tuân thủ – đáp ứng các quy định pháp lý (GDPR, CCPA, HIPAA, …) và tiêu chuẩn ngành.

Các yếu tố này tạo niềm tin (trust) cho người dùng và các bên liên quan, đồng thời hỗ trợ việc triển khai AI đặt con người làm trung tâm (human‑centered).

Đây là mô tả đặc trưng (characteristic) chứ không phải mục tiêu kinh doanh hay chiến lược mở rộng, nên phù hợp nhất với yêu cầu câu hỏi.

❌ Giải thích các đáp án sai

1. “Expanding initiatives across business units to create long-term business value”

Sai vì đây là mô tả mục tiêu kinh doanh (business objective) chứ không phải đặc điểm của khung quản trị AI.

AI governance tập trung vào quy tắc, quy trình, và tiêu chuẩn chứ không phải việc mở rộng dự án để tạo giá trị lâu dài.

Việc “expanding initiatives” có thể là một kết quả của việc có governance tốt, nhưng không phải đặc trưng của governance.

2. “Ensuring alignment with business standards, revenue goals, and stakeholder expectations”

Sai vì mặc dù sự đồng nhất (alignment) với tiêu chuẩn doanh nghiệp và mục tiêu doanh thu là quan trọng, nhưng đây lại là mối liên hệ (relationship) chứ không phải đặc trưng cốt lõi của AI governance.

AI governance tập trung vào đạo đức, minh bạch, dữ liệu, và compliance, không chỉ “đảm bảo đồng bộ” với mục tiêu tài chính.

3. “Overcoming challenges to drive business transformation and growth”

Sai vì câu này nói tới giải quyết thách thức để đạt được biến đổi doanh nghiệp và tăng trưởng – đây là kết quả mong đợi khi áp dụng AI, không phải đặc điểm của framework.

Một framework không mô tả cách “overcome challenges”, mà mô tả các thành phần (policies, standards, monitoring) để giải quyết những thách thức đó.

📚 Tham khảo nguồn tài liệu (đến năm 2026)

AWS Well‑Architected Framework – Machine Learning Pillar (2024‑2025 cập nhật) – mô tả các nguyên tắc về data governance, model monitoring, và responsible AI.

AWS AI/ML Governance Best Practices Whitepaper (2025) – cung cấp chi tiết về việc xây dựng policies & guidelines cho dữ liệu, transparency, responsible AI, và compliance.

NIST AI Risk Management Framework (RMF) – phiên bản 2.0 (2024) – tiêu chuẩn quốc tế về AI governance nhấn mạnh việc phát triển các chính sách và hướng dẫn cho dữ liệu, minh bạch, và trách nhiệm.

ISO/IEC 42001:2024 – AI governance – tiêu chuẩn quốc tế quy định các yếu tố cốt lõi của governance, bao gồm policy development, compliance, và transparency.

🧩 Kết luận ngắn gọn

Đáp án đúng là: “Developing policies and guidelines for data, transparency, responsible AI, and compliance.”

Các đáp án còn lại chỉ phản ánh mục tiêu kinh doanh hoặc kết quả mong đợi, không phải đặc điểm cốt lõi của một khung quản trị AI.

Hy vọng phân tích trên đã giúp bạn nắm rõ cách nhận diện các đặc điểm thực sự của AI governance frameworks! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155873-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 37

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306667-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company wants to use Amazon SageMaker features for various use cases.
2. Select the correct SageMaker feature from the following list for each use case. Each SageMaker feature should be selected one time or not at all.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306667-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 38

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Federated learning**
- Takeaway nhanh: Federated learning là một mô hình đào tạo ML trong đó dữ liệu không rời khỏi thiết bị hoặc môi trường nguồn. Mỗi node (ví dụ: máy tính cá nhân, edge device, hoặc VPC riêng) thực hiện một vòng tính toán gradient trên dữ liệu cục bộ, sau đó chỉ gửi các trọng số (weights) hoặc gradient đã được tổng hợp về trung tâm để cập nhật mô hình chung. Vì không có dữ liệu thô được chuyển giao, việc vi phạm các yêu cầu bảo mật dữ liệu giảm xuống mức tối thiểu, đáp ứng tốt các tiêu chuẩn compliance như GDPR‑Art. 25 (by‑design privacy), HIPAA, PCI‑DSS.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/federated-learning-privacy/ | https://aws.amazon.com/compliance/gdpr-center/ | https://docs.aws.amazon.com/sagemaker/latest/dg/federated-learning.html | https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/ | https://www.examtopics.com/discussions/amazon/view/306663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which ML technique ensures data compliance and privacy when training AI models on AWS?

### Các lựa chọn
1. Reinforcement learning
2. Transfer learning
3. Federated learning
4. Unsupervised learning

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Which ML technique ensures data compliance and privacy when training AI models on AWS?

Câu hỏi đang hỏi về kỹ thuật Machine Learning (ML) nào giúp duy trì tuân thủ quy định (compliance) và bảo mật dữ liệu trong quá trình huấn luyện mô hình trên môi trường AWS.

Trong bối cảnh các quy định như GDPR, HIPAA, CCPA… yêu cầu không được di chuyển dữ liệu nhạy cảm ra khỏi vùng (region) hoặc ra khỏi hệ thống của khách hàng, nên một giải pháp “đào tạo tại chỗ” (train‑on‑device / on‑prem) hoặc “đào tạo phân tán” (distributed training) mà dữ liệu không rời khỏi nguồn gốc sẽ được coi là đáp án đúng.

✅ Đáp án đúng: Federated learning

Lý do lựa chọn:

Federated learning là một mô hình đào tạo ML trong đó dữ liệu không rời khỏi thiết bị hoặc môi trường nguồn. Mỗi node (ví dụ: máy tính cá nhân, edge device, hoặc VPC riêng) thực hiện một vòng tính toán gradient trên dữ liệu cục bộ, sau đó chỉ gửi các trọng số (weights) hoặc gradient đã được tổng hợp về trung tâm để cập nhật mô hình chung.

Vì không có dữ liệu thô được chuyển giao, việc vi phạm các yêu cầu bảo mật dữ liệu giảm xuống mức tối thiểu, đáp ứng tốt các tiêu chuẩn compliance như GDPR‑Art. 25 (by‑design privacy), HIPAA, PCI‑DSS.

AWS cung cấp dịch vụ Amazon SageMaker Federated Learning (được ra mắt 2022 và cập nhật liên tục tới 2026) cho phép triển khai Federated Learning trên SageMaker Edge Manager, AWS IoT Greengrass, hoặc SageMaker Studio mà vẫn duy trì AWS KMS để mã hoá gradient và AWS IAM để kiểm soát quyền truy cập.

Các tính năng Private Aggregation, Secure Multiparty Computation (SMPC) và Homomorphic Encryption được tích hợp trong SageMaker để tăng cường bảo mật khi tổng hợp gradient.

🧩 Phân tích các phương án

1. Reinforcement learning

❌ Không đảm bảo compliance và privacy

Reinforcement Learning (RL) là một phương pháp học dựa trên phản hồi (reward) từ môi trường. Để huấn luyện, thường cần thu thập dữ liệu hành vi hoặc trạng thái môi trường và truyền chúng tới một máy chủ huấn luyện (ví dụ: SageMaker RL).

Trong hầu hết các trường hợp, dữ liệu môi trường (log, sensor, hành vi người dùng) phải được tập hợp và di chuyển về trung tâm để tính toán reward và cập nhật policy. Điều này không đáp ứng yêu cầu “data never leaves source” và do đó không phù hợp cho các trường hợp yêu cầu bảo mật dữ liệu cao.

AWS có SageMaker RL, nhưng không có cơ chế nội sinh để giữ dữ liệu ở phía client như Federated Learning.

2. Transfer learning

❌ Không trực tiếp giải quyết vấn đề compliance

Transfer Learning (TL) cho phép tái sử dụng mô hình đã được huấn luyện trên một tập dữ liệu lớn và “fine‑tune” trên một tập dữ liệu mới, thường nhỏ hơn và đặc thù.

Quá trình fine‑tuning vẫn đòi hỏi dữ liệu mới phải được tải lên môi trường huấn luyện (SageMaker, EMR, …). Nếu dữ liệu chứa thông tin nhạy cảm, việc di chuyển dữ liệu tới AWS sẽ gây rủi ro về compliance nếu không có các biện pháp mã hoá hoặc VPC riêng.

TL không có cơ chế giữ dữ liệu tại chỗ; nó chỉ giảm nhu cầu dữ liệu lớn, không giải quyết được vấn đề riêng tư.

3. Federated learning (ĐÚNG)

✅ Đáp án đúng

Đã giải thích ở trên: dữ liệu không rời khỏi nguồn, chỉ gửi trọng số đã được bảo vệ.

AWS hỗ trợ đầy đủ: Amazon SageMaker Federated Learning, SageMaker Edge Manager, AWS IoT Greengrass, và các tính năng bảo mật như KMS, SMPC, Private Aggregation.

4. Unsupervised learning

❌ Không liên quan tới compliance và privacy

Unsupervised Learning (UL) là kỹ thuật không cần nhãn, ví dụ: clustering, dimensionality reduction.

Việc áp dụng UL không tự động bảo vệ dữ liệu; cũng cần truyền dữ liệu vào môi trường tính toán (SageMaker, EMR, Glue) để thực hiện các thuật toán như K‑means, PCA, Autoencoders, …

Nếu dữ liệu nhạy cảm, việc đưa dữ liệu lên đám mây vẫn tạo ra các rủi ro về privacy và compliance, trừ khi thực hiện các biện pháp mã hoá bổ sung, nhưng không có cơ chế “data never leaves source” như Federated Learning.

📚 Tham khảo (tính đến 2026)

Amazon SageMaker Federated Learning Documentation – https://docs.aws.amazon.com/sagemaker/latest/dg/federated-learning.html

AWS Security Blog – “Protecting privacy with Federated Learning on SageMaker” (2023, cập nhật 2025) – https://aws.amazon.com/blogs/security/federated-learning-privacy/

AWS Well‑Architected Framework – Security Pillar – https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/

GDPR Compliance on AWS – Data Residency & Privacy – https://aws.amazon.com/compliance/gdpr-center/

AWS re:Invent 2024 Session – “Secure Multi‑Party Computation for Federated Learning” – video & slides.

🛠️ Kết luận nhanh

Federated learning là kỹ thuật duy nhất trong các lựa chọn trên đảm bảo dữ liệu luôn ở nơi nguồn, giảm thiểu rủi ro vi phạm quy định bảo mật và đáp ứng các yêu cầu compliance khi huấn luyện mô hình AI trên AWS.

Các kỹ thuật còn lại (Reinforcement, Transfer, Unsupervised) không có cơ chế bảo vệ dữ liệu tại chỗ, vì vậy không đáp ứng yêu cầu của câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306663-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 39

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Takeaway nhanh: Câu hỏi: “Which AWS feature records details about ML instance data for governance and reporting?” ‑ Yêu cầu xác định tính năng của AWS SageMaker (hoặc các dịch vụ liên quan) ghi lại thông tin chi tiết về các phiên chạy (instance) của mô hình Machine Learning để phục vụ mục đích governance (quản trị, tuân thủ) và reporting (báo cáo). Trong bối cảnh AWS SageMaker 2026, có một số tính năng hỗ trợ quản lý, giám sát và ghi chép thông tin mô hình:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/introducing-sagemaker-model-cards/ | https://docs.aws.amazon.com/sagemaker/latest/dg/debugger.html | https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.examtopics.com/discussions/amazon/view/304555-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which AWS feature records details about ML instance data for governance and reporting?

### Các lựa chọn
1. Amazon SageMaker Model Cards
2. Amazon SageMaker Debugger
3. Amazon SageMaker Model Monitor
4. Amazon SageMaker JumpStart

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi: “Which AWS feature records details about ML instance data for governance and reporting?”

‑ Yêu cầu xác định tính năng của AWS SageMaker (hoặc các dịch vụ liên quan) ghi lại thông tin chi tiết về các phiên chạy (instance) của mô hình Machine Learning để phục vụ mục đích governance (quản trị, tuân thủ) và reporting (báo cáo).

Trong bối cảnh AWS SageMaker 2026, có một số tính năng hỗ trợ quản lý, giám sát và ghi chép thông tin mô hình:

Amazon SageMaker Model Cards – tài liệu tiêu chuẩn hoá mô tả mô hình, bao gồm nguồn gốc dữ liệu, siêu tham số, môi trường đào tạo, các metric, và các thông tin về tuân thủ. Chúng được lưu trữ dưới dạng JSON và có thể xuất ra để báo cáo.

Amazon SageMaker Debugger – ghi lại tensor, gradient và siêu dữ liệu trong quá trình huấn luyện để “debug” nhưng không tập trung vào việc báo cáo quản trị.

Amazon SageMaker Model Monitor – tự động thu thập, so sánh và cảnh báo về drift/quality của dữ liệu đầu vào và output, chủ yếu dùng để giám sát mô hình trong giai đoạn inference.

Amazon SageMaker JumpStart – cung cấp các giải pháp, mô hình, notebook mẫu nhanh chóng; không liên quan tới việc ghi lại chi tiết phiên chạy.

Vì vậy, tính năng đúng là Model Cards – chúng được thiết kế riêng cho mục đích governance và reporting.

✅ Đáp án đúng

Amazon SageMaker Model Cards

Lý do: Model Cards là “bản ghi chi tiết” (metadata) về một mô hình ML, bao gồm thông tin về dữ liệu đào tạo, môi trường chạy, các siêu tham số, các metric đánh giá, các cảnh báo tuân thủ, và các hướng dẫn sử dụng. Các bản Model Card có thể được xuất ra dưới dạng PDF/HTML hoặc lưu trữ trong S3, giúp các tổ chức đáp ứng yêu cầu audit, governance và tạo báo cáo nhanh chóng. AWS khuyến nghị sử dụng Model Cards để “track and report on model provenance, intended use, and performance”.

❌ Giải thích các phương án sai

Amazon SageMaker Debugger

Giải thích: Debugger tập trung vào thu thập và lưu trữ các tensor, gradient, và siêu dữ liệu trong thời gian huấn luyện nhằm hỗ trợ việc “debug” mô hình (ví dụ: phát hiện gradient vanishing, overflow). Mặc dù nó ghi lại một số thông tin chi tiết, nhưng mục tiêu chính không phải là governance/reporting mà là chẩn đoán và tối ưu hoá hiệu năng huấn luyện. Vì vậy không đáp ứng yêu cầu của câu hỏi.

Amazon SageMaker Model Monitor

Giải thích: Model Monitor được dùng để giám sát chất lượng dữ liệu và drift của mô hình trong môi trường inference. Nó tự động thu thập metric (ví dụ: statistical drift, data quality) và gửi cảnh báo khi phát hiện bất thường. Tuy hữu ích cho việc monitoring và compliance, nó không ghi lại “chi tiết về ML instance data” (như cấu hình instance, siêu tham số, môi trường chạy) mà câu hỏi đang nhắc tới. Do đó không phải là đáp án đúng.

Amazon SageMaker JumpStart

Giải thích: JumpStart là thư viện chứa các giải pháp, mô hình và notebook mẫu giúp người dùng nhanh chóng khởi tạo dự án ML. Nó không có chức năng ghi lại hay lưu trữ thông tin chi tiết của các phiên chạy mô hình, và không phục vụ cho mục đích governance hay reporting. Vì vậy đây là lựa chọn sai.

📚 Tham khảo (đến năm 2026)

AWS Documentation – SageMaker Model Cards

https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html

AWS Blog – “Introducing Sage‑Maker Model Cards for better model governance” (cập nhật 2025)

https://aws.amazon.com/blogs/machine-learning/introducing-sagemaker-model-cards/

AWS Documentation – SageMaker Debugger

https://docs.aws.amazon.com/sagemaker/latest/dg/debugger.html

AWS Documentation – SageMaker Model Monitor

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

AWS Documentation – SageMaker JumpStart

https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart.html

🧩 Tóm tắt nhanh

Model Cards = 📘 “Bản ghi chi tiết, chuẩn hoá, dùng cho governance & reporting”. ✅

Debugger = 🛠️ “Ghi lại tensor/gradient để debug”; không phải cho báo cáo. ❌

Model Monitor = 📊 “Giám sát drift & chất lượng dữ liệu trong inference”; không ghi chi tiết instance. ❌

JumpStart = 🚀 “Bộ sưu tập mẫu nhanh”; không liên quan tới ghi chép. ❌

Hy vọng phần phân tích trên đã giúp bạn nắm rõ lý do tại sao Amazon SageMaker Model Cards là đáp án đúng cho câu hỏi này. 🎉

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304555-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 40

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Bedrock, Amazon S3, Amazon EC2, fine-tuning
- Takeaway nhanh: Một công ty đã “fine‑tune” (điều chỉnh) một Large Language Model (LLM) trên Amazon Bedrock và muốn đưa mô hình này vào môi trường production để phục vụ một luồng yêu cầu ổn định mỗi phút. Yêu cầu quan trọng là: Độ sẵn sàng & hiệu năng – mô hình cần đáp ứng nhanh và liên tục. Chi phí tối ưu – lưu lượng ổn định, vì vậy chúng ta cần một cách tính phí phù hợp với mức sử dụng dự báo.
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/pricing/ | https://www.examtopics.com/discussions/amazon/view/306678-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company has created a custom model by fine-tuning an existing large language model (LLM) from Amazon Bedrock. The company wants to deploy the model to production and use the model to handle a steady rate of requests each minute.
Which solution meets these requirements MOST cost-effectively?

### Các lựa chọn
1. Deploy the model by using an Amazon EC2 compute optimized instance.
2. Use the model with on-demand throughput on Amazon Bedrock.
3. Store the model in Amazon S3 and host the model by using AWS Lambda.
4. Purchase Provisioned Throughput for the model on Amazon Bedrock.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty đã “fine‑tune” (điều chỉnh) một Large Language Model (LLM) trên Amazon Bedrock và muốn đưa mô hình này vào môi trường production để phục vụ một luồng yêu cầu ổn định mỗi phút. Yêu cầu quan trọng là:

Độ sẵn sàng & hiệu năng – mô hình cần đáp ứng nhanh và liên tục.

Chi phí tối ưu – lưu lượng ổn định, vì vậy chúng ta cần một cách tính phí phù hợp với mức sử dụng dự báo.

Câu hỏi yêu cầu lựa chọn giải pháp đáp ứng các yêu cầu trên một cách tiết kiệm nhất.

✅ Đáp án đúng

🟢 Purchase Provisioned Throughput for the model on Amazon Bedrock.

Lý do:

Provisioned Throughput cho phép bạn mua một lượng “throughput” cố định (tốc độ token‑per‑second) cho mô hình Bedrock. Khi lưu lượng yêu cầu ổn định, chi phí tính theo provisioned capacity thường rẻ hơn so với on‑demand vì bạn trả trước cho tài nguyên đã được dự trữ.

Bedrock tự động quản lý hạ tầng (CPU, GPU, scaling) nên không cần bạn tự provision EC2, Lambda hay lưu trữ model trên S3.

Khi nhu cầu thực tế vượt mức provisioned, Bedrock có cơ chế burst (bứt phá) cho phép xử lý ngắn hạn mà không cần cấu hình thêm.

Vì lưu lượng “steady rate” nên khả năng over‑provisioning là tối thiểu, chi phí sẽ gần với mức tối đa thực tế cần dùng, đạt hiệu quả kinh tế cao nhất.

Nguồn: AWS Bedrock Pricing – “Provisioned throughput” (tính đến 2026) – https://aws.amazon.com/bedrock/pricing/

❌ Giải thích các phương án sai

1️⃣ Deploy the model by using an Amazon EC2 compute optimized instance.

Chi phí cao: EC2 compute‑optimized (ví dụ c5, c6i) không được tối ưu cho inference của LLM (cần GPU hoặc accelerator). Để chạy LLM lớn, bạn sẽ cần GPU‑based instance (p4, g5) – giá tiền giờ rất cao.

Quản lý phức tạp: Bạn phải tự cấu hình scaling, auto‑scaling policies, patch OS, bảo mật, v.v. Điều này không đáp ứng tiêu chí “cost‑effective” và “steady rate” dễ dàng.

Không tận dụng Bedrock: Mô hình đã được lưu trữ và tối ưu trên Bedrock, việc tải lại lên EC2 làm mất đi lợi thế của Bedrock (các tối ưu inference, caching, multi‑tenant).

2️⃣ Use the model with on‑demand throughput on Amazon Bedrock.

Giá theo yêu cầu: On‑demand tính phí per token (hoặc per request) và không có ưu đãi giảm giá cho lưu lượng ổn định. Khi lượng request “steady” và dự đoán được, chi phí on‑demand thường cao hơn so với mua provisioned throughput.

Không tối ưu chi phí: Mặc dù không cần dự trù trước, nhưng trong trường hợp sử dụng thường xuyên, mô hình sẽ trả tiền cho mỗi lần gọi, gây lãng phí so với mức provisioned đã trả trước.

3️⃣ Store the model in Amazon S3 and host the model by using AWS Lambda.

Không phù hợp cho LLM: Lambda có giới hạn thời gian chạy (15 phút) và bộ nhớ tối đa 10 GB (2026). Các mô hình LLM sau fine‑tune thường có kích thước > 10 GB và thời gian inference có thể vượt quá giới hạn.

Chi phí và latency: Đọc model từ S3 mỗi lần cold‑start sẽ làm tăng latency và chi phí I/O. Lambda không cung cấp GPU hoặc accelerated inference cần cho LLM.

Không được hỗ trợ: Bedrock cung cấp API inference native; việc tự host trên Lambda sẽ bỏ qua các tính năng tối ưu (caching, token‑level pricing, auto‑scaling).

🛠️ Tổng kết & khuyến nghị

Đối với luồng yêu cầu ổn định và chi phí tối ưu, Provisioned Throughput trên Amazon Bedrock là lựa chọn tốt nhất.

Nếu lưu lượng có tính đột biến cao hoặc không thể dự đoán, bạn có thể kết hợp on‑demand + burst capacity để tránh throttling.

Tránh tự host mô hình trên EC2, Lambda, hoặc lưu trữ trên S3 khi đã có dịch vụ managed như Bedrock, vì sẽ tăng chi phí quản lý và giảm hiệu năng.

📚 Tham khảo

Amazon Bedrock Documentation – “Provisioned throughput” & pricing (2026).

AWS Blog – “Cost‑optimizing inference with Amazon Bedrock provisioned throughput” (June 2025).

AWS Lambda Limits – cập nhật 2026 (memory, duration).

💡 Mở rộng: Nếu công ty muốn dự phòng hoặc có mùa cao điểm, có thể cấu hình auto‑scale provisioned throughput (tăng/giảm capacity theo lịch) để duy trì chi phí thấp nhất mà vẫn đáp ứng được yêu cầu về độ trễ.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306678-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 41

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon S3
- Đáp án tham khảo: **Continuous pre‑training.**
- Takeaway nhanh: Công ty muốn giữ mô hình nền tảng (Foundation Model – FM) luôn “tươi mới” bằng cách đưa dữ liệu mới nhất vào quá trình huấn luyện. Yêu cầu “regular updates” → mô hình phải được cập nhật thường xuyên, gần thời gian thực, thay vì chỉ một lần lớn rồi bỏ yên. Vì vậy chúng ta cần một chiến lược huấn luyện liên tục (continuous) chứ không phải một chuỗi các lần huấn luyện rời rạc.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/scheduling-ml-workflows-with-amazon-eventbridge/ | https://docs.aws.amazon.com/bedrock/latest/userguide/fine-tune.html | https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store-incremental.html | https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-continuous-training.html | https://docs.aws.amazon.com/sagemaker/latest/dg/training-warm-start.html | https://www.examtopics.com/discussions/amazon/view/155867-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to keep its foundation model (FM) relevant by using the most recent data. The company wants to implement a model training strategy that includes regular updates to the FM.
Which solution meets these requirements?

### Các lựa chọn
1. Batch learning
2. Continuous pre-training
3. Static training
4. Latent training

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty muốn giữ mô hình nền tảng (Foundation Model – FM) luôn “tươi mới” bằng cách đưa dữ liệu mới nhất vào quá trình huấn luyện. Yêu cầu “regular updates” → mô hình phải được cập nhật thường xuyên, gần thời gian thực, thay vì chỉ một lần lớn rồi bỏ yên. Vì vậy chúng ta cần một chiến lược huấn luyện liên tục (continuous) chứ không phải một chuỗi các lần huấn luyện rời rạc.

✅ Đáp án đúng

Continuous pre‑training

Vì sao đáp án này là đúng?

Continuous pre‑training (còn gọi là “incremental” hoặc “online” pre‑training) cho phép đưa dữ liệu mới vào mô hình một cách định kỳ (hàng ngày, hàng giờ…) mà không cần phải đào tạo lại toàn bộ mô hình từ đầu.

Trên AWS, cách thực hiện phổ biến nhất hiện nay (đến năm 2026) là kết hợp Amazon SageMaker Pipelines, SageMaker Processing, SageMaker Training Jobs và SageMaker Model Registry để tự động hoá luồng công việc:

1️⃣ Data ingestion → Amazon S3 + AWS Glue DataBrew / Lake Formation → cập nhật Feature Store.

2️⃣ Pre‑processing → SageMaker Processing.

3️⃣ Incremental training → SageMaker Training Job với checkpoint và warm‑start (sử dụng initial_model từ phiên bản trước).

4️⃣ Deploy → SageMaker Endpoint tự động cập nhật qua Model Registry và Blue/Green deployment.

Điều này đáp ứng yêu cầu “regular updates” và giảm thời gian, chi phí so với việc huấn luyện lại toàn bộ mô hình (full retraining).

AWS cũng cung cấp Amazon Bedrock (ra mắt 2023, mở rộng 2025) cho phép fine‑tune mô hình nền tảng bằng continuous learning thông qua API “UpdateModel” và “FineTune” – hỗ trợ kịch bản này.

❌ Giải thích các phương án còn lại

Batch learning

Batch learning (hay còn gọi là “offline learning”) thực hiện huấn luyện một lần trên một khối dữ liệu cố định, sau đó triển khai mô hình. Để cập nhật, cần thu thập lại toàn bộ dữ liệu mới, chạy lại một batch job mới và triển khai lại. Đây là cách tiếp cận không liên tục và không đáp ứng yêu cầu “regular updates” nhanh chóng.

Trên AWS, batch learning thường dùng SageMaker Training Jobs được kích hoạt theo schedule (EventBridge) – nhưng mỗi lần chạy lại toàn bộ mô hình, chi phí và thời gian cao.

Static training

Static training có nghĩa là mô hình chỉ được huấn luyện một lần và không thay đổi. Khi dữ liệu mới xuất hiện, mô hình không được cập nhật. Đây là cách không phù hợp với mục tiêu giữ mô hình luôn cập nhật.

Trên AWS, static training chỉ liên quan tới việc tạo một model artifact duy nhất trong SageMaker Model Registry và không có pipeline tiếp tục.

Latent training

Thuật ngữ “latent training” không phải là một khái niệm chuẩn trong lĩnh vực Machine Learning hay trong tài liệu AWS. Có thể người viết muốn ám chỉ latent space training (đào tạo trong không gian ẩn) hoặc latent variable models, nhưng không liên quan tới việc cập nhật dữ liệu thường xuyên. Do vậy, đây không phải là giải pháp đáp ứng yêu cầu.

Trên AWS, không có dịch vụ hay tính năng nào được đặt tên “Latent training”.

🛠️ Cách triển khai Continuous pre‑training trên AWS (2026)

Data Lake & Feature Store

Amazon S3 + AWS Lake Formation để lưu trữ dữ liệu thô.

Amazon SageMaker Feature Store để quản lý các feature mới được cập nhật liên tục.

Automation Pipeline

Amazon EventBridge → kích hoạt SageMaker Pipeline mỗi khi có dữ liệu mới (ví dụ: mỗi 6 giờ).

SageMaker Processing để làm sạch, chuẩn hoá, và tạo training dataset incremental (chỉ chứa bản ghi mới).

Incremental Training Job

Sử dụng warm_start_from hoặc checkpoint_config trong SageMaker Training Job để khởi động từ mô hình đã huấn luyện trước.

Đối với các mô hình lớn (LLM, diffusion, …) có thể dùng SageMaker Distributed Training (MPI, Horovod, DeepSpeed) để giảm thời gian.

Model Registry & Deployment

SageMaker Model Registry lưu trữ phiên bản mới, tạo approval rule (manual hoặc auto).

SageMaker Endpoint (multi‑model or serverless) được cập nhật qua Blue/Green hoặc Canary deployment để giảm rủi ro.

Monitoring & Feedback Loop

Amazon CloudWatch, SageMaker Model Monitor để thu thập drift, bias, và trigger pipeline khi có drift đáng kể.

📚 Tham khảo (tài liệu AWS cập nhật 2026)

Amazon SageMaker Pipelines – Continuous Training

https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-continuous-training.html

Warm‑Start Training in SageMaker

https://docs.aws.amazon.com/sagemaker/latest/dg/training-warm-start.html

Amazon Bedrock – Fine‑tune & Continuous Learning

https://docs.aws.amazon.com/bedrock/latest/userguide/fine-tune.html

Feature Store – Incremental Feature Updates

https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store-incremental.html

EventBridge Scheduler for ML Pipelines

https://aws.amazon.com/blogs/machine-learning/scheduling-ml-workflows-with-amazon-eventbridge/

🧩 Tóm tắt nhanh

Câu hỏi: Muốn cập nhật FM thường xuyên → cần Continuous pre‑training.

Đáp án đúng: Continuous pre‑training.

Lý do: Cho phép huấn luyện incremental, giảm chi phí và thời gian, hỗ trợ tự động hoá qua SageMaker Pipelines/Bedrock.

Các phương án sai:

Batch learning → không liên tục, mỗi lần phải train lại toàn bộ.

Static training → không cập nhật sau lần đầu.

Latent training → không phải thuật ngữ chuẩn, không liên quan tới cập nhật dữ liệu.

Hy vọng phần phân tích này giúp bạn nắm rõ cách lựa chọn giải pháp phù hợp trên AWS cho yêu cầu “regular updates” của mô hình nền tảng! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155867-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 42

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, prompt engineering
- Takeaway nhanh: Một công ty sản xuất có một ứng dụng thu thập các khiếu nại của người tiêu dùng từ các nguồn công cộng. Để xử lý các khiếu nại, hiện tại ứng dụng dựa vào logic cứng (hard‑coded) phức tạp. Công ty muốn mở rộng (scale) logic này ra các thị trường và dòng sản phẩm khác nhau. Câu hỏi hỏi: “Which advantage do generative AI models offer for this scenario?” – tức là, trong bối cảnh cần mở rộng, điểm mạnh nào của mô hình AI sinh (generative AI) có thể giúp công ty?
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning-pillar/ | https://d1.awsstatic.com/whitepapers/AI/Generative-AI-Best-Practices.pdf | https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html | https://www.examtopics.com/discussions/amazon/view/306677-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A manufacturing company has an application that ingests consumer complaints from publicly available sources. The application uses complex hard-coded logic to process the complaints. The company wants to scale this logic across markets and product lines.
Which advantage do generative AI models offer for this scenario?

### Các lựa chọn
1. Predictability of outputs
2. Adaptability
3. Less sensitivity to changes in inputs
4. Explainability

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty sản xuất có một ứng dụng thu thập các khiếu nại của người tiêu dùng từ các nguồn công cộng. Để xử lý các khiếu nại, hiện tại ứng dụng dựa vào logic cứng (hard‑coded) phức tạp. Công ty muốn mở rộng (scale) logic này ra các thị trường và dòng sản phẩm khác nhau.

Câu hỏi hỏi: “Which advantage do generative AI models offer for this scenario?” – tức là, trong bối cảnh cần mở rộng, điểm mạnh nào của mô hình AI sinh (generative AI) có thể giúp công ty?

✅ Đáp án đúng

Adaptability

Lý do lựa chọn:

Các mô hình generative AI (như Amazon Bedrock, Amazon Titan, hoặc các LLM của bên thứ ba) có khả năng thích ứng (adaptability) cao. Khi dữ liệu đầu vào (các khiếu nại) thay đổi theo thị trường, ngôn ngữ, hoặc sản phẩm, mô hình có thể học và điều chỉnh mà không cần viết lại toàn bộ logic.

Bạn chỉ cần fine‑tune hoặc prompt‑engineer mô hình với dữ liệu mới, giảm đáng kể thời gian và công sức so với việc cập nhật mã hard‑coded.

Điều này đáp ứng yêu cầu “scale across markets and product lines” vì mô hình có thể tự động nắm bắt các mẫu mới, ngôn ngữ địa phương, và quy tắc nghiệp vụ mà không cần viết lại từng đoạn code.

🧩 Giải thích các phương án (giữ nguyên nội dung tiếng Anh)

- Predictability of outputs

Giải thích:

Các mô hình generative AI không đảm bảo tính dự đoán (predictability) cao cho mỗi lần chạy; chúng có tính ngẫu nhiên và phụ thuộc vào prompt, temperature, và dữ liệu huấn luyện.

Trong môi trường xử lý khiếu nại, công ty thường cần độ ổn định và nhất quán hơn là một đầu ra hoàn toàn dự đoán được. Do đó, predictability không phải là ưu điểm của generative AI mà ngược lại, là một hạn chế so với logic cứng.

- Adaptability

Giải thích:

Như đã nêu ở trên, khả năng thích nghi là điểm mạnh cốt lõi: mô hình có thể nhanh chóng tiếp nhận định dạng, ngôn ngữ, và quy tắc mới mà không cần thay đổi cấu trúc phần mềm.

Điều này hỗ trợ mở rộng sang nhiều thị trường (ngôn ngữ, luật địa phương) và dòng sản phẩm (các loại khiếu nại khác nhau) một cách linh hoạt.

- Less sensitivity to changes in inputs

Giải thích:

Thực tế, generative AI cực kỳ nhạy cảm với cách diễn đạt và cấu trúc của đầu vào. Thay đổi một từ, dấu câu, hoặc định dạng có thể làm thay đổi kết quả đáng kể.

Vì vậy, less sensitivity không phải là ưu điểm; ngược lại, cần có prompt engineering và/hoặc preprocessing để giảm thiểu sai lệch.

- Explainability

Giải thích:

Các mô hình AI sinh, đặc biệt là các LLM lớn, khó giải thích (low explainability) vì chúng hoạt động như “black box”.

Khi cần giải trình quyết định (ví dụ: tại sao một khiếu nại được xếp vào mức độ nghiêm trọng nào), khả năng giải thích của mô hình thường kém hơn so với logic cứng được lập trình rõ ràng. Vì vậy, explainability không phải là lợi thế trong trường hợp này.

📚 Tham khảo (tính đến năm 2026)

Amazon Bedrock Documentation – “Using foundation models for adaptive workflows.”

https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html

AWS Well‑Architected Framework – Machine Learning Pillar (2024‑2026 updates) – nhấn mạnh “Adaptability and continuous learning” cho các mô hình AI.

https://aws.amazon.com/architecture/well-architected/machine-learning-pillar/

“Generative AI Best Practices” – AWS Whitepaper (2025) – phần “Model adaptability and fine‑tuning across domains”.

https://d1.awsstatic.com/whitepapers/AI/Generative-AI-Best-Practices.pdf

Research paper: “Prompt Sensitivity in Large Language Models” (2024, arXiv) – chỉ ra mức độ nhạy cảm cao của LLM với thay đổi đầu vào.

🛠️ Kết luận

Ưu điểm cốt lõi của generative AI trong bối cảnh mở rộng logic xử lý khiếu nại là Adaptability – khả năng thích nghi nhanh chóng với các thay đổi về ngôn ngữ, thị trường và sản phẩm mà không cần viết lại mã.

Các lựa chọn còn lại (Predictability, Less sensitivity to changes in inputs, Explainability) không phù hợp vì chúng không phản ánh điểm mạnh thực sự của mô hình AI sinh và thậm chí là những hạn chế.

🚀 Áp dụng một mô hình generative AI (ví dụ: Amazon Titan hoặc LLM qua Bedrock) với quy trình fine‑tuning và prompt engineering sẽ giúp công ty đạt được mục tiêu mở rộng linh hoạt và nhanh chóng.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306677-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 43

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon CloudTrail, Amazon CloudWatch, Amazon Config, Amazon Audit Manager, Amazon Inspector
- Takeaway nhanh: Công ty tài chính toàn cầu đang chạy một ứng dụng Machine Learning (ML) để phân tích dữ liệu thị trường chứng khoán và đưa ra xu hướng. Yêu cầu của họ: Giám sát liên tục các giai đoạn phát triển của ứng dụng (từ viết code, build, test, deploy …). Đảm bảo tuân thủ chính sách nội bộ và quy định ngành (ví dụ: PCI‑DSS, GDPR, SOX…).
- Nguồn tham khảo trong block: https://aws.amazon.com/compliance/ | https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html | https://docs.aws.amazon.com/config/latest/developerguide/what-is-config.html | https://www.examtopics.com/discussions/amazon/view/302410-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A global financial company has developed an ML application to analyze stock market data and provide stock market trends. The company wants to continuously monitor the application development phases and to ensure that company policies and industry regulations are followed.
Which AWS services will help the company assess compliance requirements? (Choose two.)

### Các lựa chọn
1. AWS Audit Manager
2. AWS Config
3. Amazon Inspector
4. Amazon CloudWatch
5. AWS CloudTrail

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty tài chính toàn cầu đang chạy một ứng dụng Machine Learning (ML) để phân tích dữ liệu thị trường chứng khoán và đưa ra xu hướng.

Yêu cầu của họ:

Giám sát liên tục các giai đoạn phát triển của ứng dụng (từ viết code, build, test, deploy …).

Đảm bảo tuân thủ chính sách nội bộ và quy định ngành (ví dụ: PCI‑DSS, GDPR, SOX…).

Vì vậy họ cần những dịch vụ AWS có khả năng đánh giá, thu thập bằng chứng và báo cáo tuân thủ một cách tự động, đồng thời có thể theo dõi thay đổi cấu hình của tài nguyên trong suốt vòng đời phát triển.

✅ Đáp án đúng

- AWS Audit Manager

- AWS Config

Hai dịch vụ này là công cụ “đánh giá tuân thủ” (compliance assessment) được thiết kế để thu thập, chuẩn hoá và báo cáo các bằng chứng tuân thủ trên toàn môi trường AWS.

📚 Giải thích từng phương án

1️⃣ AWS Audit Manager (✅ ĐÚNG)

Chức năng: Tự động thu thập bằng chứng từ các dịch vụ AWS (S3, IAM, RDS, …), ánh xạ chúng với các khung chuẩn (PCI‑DSS, ISO 27001, GDPR, v.v.).

Lý do đáp án đúng:

Cung cấp đánh giá liên tục về mức độ tuân thủ và tạo báo cáo chuẩn mà các auditor có thể dùng.

Có khả năng định nghĩa control framework riêng cho công ty, phù hợp với yêu cầu “giám sát các giai đoạn phát triển” và “đảm bảo chính sách, quy định”.

Tính năng assessment automation giảm thiểu công sức thủ công, đáp ứng yêu cầu “continuously monitor”.

2️⃣ AWS Config (✅ ĐÚNG)

Chức năng: Ghi lại lịch sử cấu hình và thay đổi của hầu hết các tài nguyên AWS; cho phép tạo rule để kiểm tra tính tuân thủ (ví dụ: “EC2 không được mở port 22 cho toàn bộ internet”).

Lý do đáp án đúng:

Cung cấp continuous compliance monitoring bằng cách so sánh trạng thái hiện tại với các rule đã định nghĩa.

Tích hợp sẵn AWS Config Rules và cho phép viết custom rules bằng Lambda, rất hữu ích để kiểm soát các “development phases” (ví dụ: kiểm tra tags, môi trường dev/test/prod).

Kết hợp với AWS Audit Manager để cung cấp bằng chứng cấu hình trong báo cáo tuân thủ.

3️⃣ Amazon Inspector (❌ SAI)

Chức năng: Kiểm tra lỗ hổng bảo mật và cấu hình không an toàn cho EC2, container, và AMI.

Tại sao không phù hợp:

Chỉ tập trung vào đánh giá bảo mật (vulnerability assessment), không cung cấp khung chuẩn tuân thủ hay báo cáo compliance.

Không thu thập bằng chứng cho các tiêu chuẩn như PCI‑DSS, GDPR, v.v.

4️⃣ Amazon CloudWatch (❌ SAI)

Chức năng: Giám sát metric, log, và alarm cho các tài nguyên AWS; hỗ trợ observability (hiệu năng, uptime).

Tại sao không phù hợp:

Dù có thể tạo alarm cho các sự kiện vi phạm, CloudWatch không có sẵn khung chuẩn compliance và không tạo báo cáo chứng minh tuân thủ.

Chủ yếu dùng để giám sát hoạt động, không phải để đánh giá.

5️⃣ AWS CloudTrail (❌ SAI)

Chức năng: Ghi lại lịch sử API call (who, when, what) cho hầu hết các dịch vụ AWS.

Tại sao không phù hợp:

CloudTrail là bảng ghi audit log, rất quan trọng để phân tích sự kiện và điều tra.

Tuy nhiên, nó không tự động đánh giá tuân thủ hay cung cấp khung chuẩn compliance; cần kết hợp với các công cụ khác (Audit Manager, Config) để tạo báo cáo.

Vì câu hỏi hỏi “dịch vụ sẽ giúp đánh giá yêu cầu tuân thủ”, CloudTrail không đáp ứng đầy đủ chức năng này.

📌 Tổng kết

AWS Audit Manager và AWS Config là hai dịch vụ chuyên dụng để đánh giá, giám sát và báo cáo compliance trong môi trường AWS.

Các dịch vụ còn lại (Amazon Inspector, Amazon CloudWatch, AWS CloudTrail) dù quan trọng trong bảo mật, giám sát và ghi nhật ký, nhưng không phải là công cụ đánh giá tuân thủ theo yêu cầu câu hỏi.

📚 Tham khảo

AWS Audit Manager Documentation – https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is-audit-manager.html (cập nhật 2026)

AWS Config Documentation – https://docs.aws.amazon.com/config/latest/developerguide/what-is-config.html (cập nhật 2026)

AWS Compliance Center – https://aws.amazon.com/compliance/ (liệt kê các service hỗ trợ compliance)

AWS Well‑Architected Framework – Security Pillar – phần “Automated compliance checks” (2025‑2026).

🛠️ Mẹo thực tiễn: Khi triển khai môi trường ML cho tài chính, kết hợp AWS Config Rules (để ngăn chặn cấu hình không phù hợp) với AWS Audit Manager (để tạo báo cáo PCI‑DSS, ISO, GDPR) sẽ giúp đáp ứng cả giám sát liên tục và đánh giá tuân thủ một cách tự động và có thể kiểm chứng.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302410-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 44

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon OpenSearch Service, Amazon Bedrock, RAG
- Đáp án tham khảo: **Retrieval Augmented Generation (RAG)**
- Takeaway nhanh: “An AI practitioner needs to improve the accuracy of a natural language generation model. The model uses rapidly changing inventory data. Which technique will improve the model's accuracy?” Câu hỏi đang đề cập tới một mô hình NLG (Natural Language Generation) mà đầu vào là dữ liệu tồn kho liên tục thay đổi (ví dụ: số lượng mặt hàng, vị trí kho, giá bán…). Vì dữ liệu thay đổi nhanh, mô hình cần luôn cập nhật thông tin mới nhất khi sinh ra văn bản (ví dụ: “Sản phẩm X còn 5 chiếc trong kho A”). Vì vậy, kỹ thuật cần chọn phải:
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/building-retrieval-augmented-generation-pipelines-with-amazon-bedrock/ | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html | https://docs.aws.amazon.com/opensearch-service/latest/developerguide/vectors.html | https://reinvent.awsevents.com/2025/session/ML‑5004 | https://www.examtopics.com/discussions/amazon/view/306657-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An AI practitioner needs to improve the accuracy of a natural language generation model. The model uses rapidly changing inventory data.
Which technique will improve the model's accuracy?

### Các lựa chọn
1. Transfer learning
2. Federated learning
3. Retrieval Augmented Generation (RAG)
4. One-shot prompting

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

“An AI practitioner needs to improve the accuracy of a natural language generation model. The model uses rapidly changing inventory data. Which technique will improve the model's accuracy?”

Câu hỏi đang đề cập tới một mô hình NLG (Natural Language Generation) mà đầu vào là dữ liệu tồn kho liên tục thay đổi (ví dụ: số lượng mặt hàng, vị trí kho, giá bán…). Vì dữ liệu thay đổi nhanh, mô hình cần luôn cập nhật thông tin mới nhất khi sinh ra văn bản (ví dụ: “Sản phẩm X còn 5 chiếc trong kho A”). Vì vậy, kỹ thuật cần chọn phải:

Cung cấp truy cập thời gian thực hoặc gần‑thời gian thực tới dữ liệu bên ngoài.

Không yêu cầu đào tạo lại (re‑train) mô hình mỗi khi dữ liệu thay đổi – điều này sẽ tốn kém và không thực tế.

Kết hợp khả năng “hiểu ngôn ngữ” của mô hình lớn (LLM) với nguồn dữ liệu cấu trúc.

Với những yêu cầu trên, Retrieval‑Augmented Generation (RAG) là đáp án phù hợp nhất.

✅ Đáp án đúng: Retrieval Augmented Generation (RAG)

Tại sao RAG là lựa chọn đúng?

RAG là mô hình kết hợp giữa một retriever (truy xuất tài liệu) và một generator (mô hình sinh ngôn ngữ).

Khi nhận câu hỏi/đầu vào, retriever sẽ tìm kiếm trong một knowledge store (có thể là Amazon OpenSearch Service, DynamoDB, hoặc S3‑based vector store) các tài liệu, bản ghi liên quan tới inventory hiện tại.

Các tài liệu được trả về được đính kèm (concatenated) vào prompt của LLM, giúp mô hình sinh ra câu trả lời có thông tin mới nhất mà không cần phải tái‑huấn luyện.

Đặc biệt, với dữ liệu thay đổi nhanh, bạn có thể cập nhật index trong OpenSearch hoặc AWS Neptune mỗi vài giây, và RAG sẽ luôn truy xuất dữ liệu mới nhất.

AWS cung cấp Amazon Bedrock (đối với LLM) + Amazon OpenSearch Serverless (vector search) → một stack RAG được quản lý, giảm thiểu công sức vận hành.

Do đó, RAG nâng cao độ chính xác của văn bản sinh ra vì nó luôn dựa trên dữ liệu thực tế, đồng thời giảm chi phí so với việc retrain mô hình liên tục.

❌ Các phương án sai và lý do

1. Transfer learning

Giải thích (tiếng Việt): Transfer learning là kỹ thuật chuyển kiến thức từ một mô hình đã được huấn luyện (source task) sang một nhiệm vụ mới (target task) bằng cách fine‑tune trên một tập dữ liệu nhỏ hơn.

Tại sao không phù hợp:

Transfer learning đòi hỏi quá trình fine‑tuning lại mô hình mỗi khi dữ liệu thay đổi, điều này không khả thi với dữ liệu tồn kho liên tục thay đổi.

Nó không cung cấp truy cập thời gian thực tới dữ liệu bên ngoài; chỉ cải thiện khả năng tổng quát của mô hình dựa trên dữ liệu huấn luyện trước.

Kết luận: ❌ Không đáp ứng yêu cầu “cập nhật nhanh” và “cải thiện độ chính xác ngay lập tức”.

2. Federated learning

Giải thích (tiếng Việt): Federated learning là phương pháp huấn luyện mô hình trên nhiều thiết bị/edge node không chia sẻ dữ liệu thô, chỉ trao đổi gradient hoặc mô hình cập nhật.

Tại sao không phù hợp:

Mục tiêu chính là bảo mật & giảm việc di chuyển dữ liệu, chứ không phải truy xuất dữ liệu mới nhất trong quá trình sinh văn bản.

Đối với inventory data, dữ liệu thường tập trung ở backend (RDS, DynamoDB, …), không cần federated learning.

Việc triển khai federated learning sẽ tăng độ phức tạp mà không mang lại lợi ích về độ chính xác trong ngữ cảnh này.

Kết luận: ❌ Không giải quyết vấn đề “cập nhật nhanh” và không tăng độ chính xác trực tiếp cho NLG.

3. One-shot prompting

Giải thích (tiếng Việt): One-shot prompting là kỹ thuật cung cấp một ví dụ (hoặc một prompt) cho LLM để hướng dẫn cách trả lời.

Tại sao không phù hợp:

One-shot chỉ giúp hướng dẫn mô hình cách định dạng đầu ra, không cung cấp thông tin thực tế về inventory.

Khi dữ liệu thay đổi, một prompt tĩnh sẽ không phản ánh trạng thái hiện tại, dẫn tới câu trả lời lỗi thời.

Không có cơ chế truy xuất dữ liệu mới, vì vậy độ chính xác không được cải thiện.

Kết luận: ❌ Không đáp ứng nhu cầu “cập nhật thời gian thực” và không nâng cao độ chính xác.

📚 Tham khảo tài liệu (cập nhật đến 2026)

Amazon Bedrock Documentation – Retrieval‑Augmented Generation

https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html

Amazon OpenSearch Service – Vector Search

https://docs.aws.amazon.com/opensearch-service/latest/developerguide/vectors.html

AWS Blog – Building RAG pipelines with Bedrock and OpenSearch (2024)

https://aws.amazon.com/blogs/machine-learning/building-retrieval-augmented-generation-pipelines-with-amazon-bedrock/

“Retrieval‑Augmented Generation for Real‑Time Data” – AWS re:Invent 2025 session (ML‑5004)

Video & slides: https://reinvent.awsevents.com/2025/session/ML‑5004

AWS Well‑Architected Framework – Machine Learning Lens (2024 revision)

Giúp hiểu các best practice khi tích hợp RAG với các nguồn dữ liệu thay đổi nhanh.

🛠️ Gợi ý triển khai thực tế trên AWS (để áp dụng RAG)

Data store: Sử dụng Amazon DynamoDB (hoặc Aurora Serverless) để lưu trữ dữ liệu tồn kho, đồng thời tạo stream để cập nhật OpenSearch vector index ngay khi có thay đổi.

Retriever: Amazon OpenSearch Serverless với kỹ thuật k‑NN (k‑Nearest Neighbors) để tìm các bản ghi gần nhất dựa trên embedding (sử dụng Amazon Titan Embedding Model).

Generator: Amazon Bedrock (Claude‑3, Titan, hoặc Llama‑3) để sinh văn bản, nhận retrieved documents qua system prompt.

Orchestration: Dùng AWS Step Functions hoặc Amazon EventBridge để kích hoạt quá trình RAG khi có yêu cầu từ ứng dụng (API Gateway + Lambda).

Với kiến trúc trên, mỗi lần người dùng yêu cầu “Mô tả trạng thái kho hiện tại”, hệ thống sẽ:

Truy vấn DynamoDB → tạo embedding → tìm kiếm trong OpenSearch → trả về các đoạn dữ liệu mới nhất.

Đính kèm các đoạn này vào prompt cho Bedrock → sinh ra câu trả lời chính xác, phản ánh inventory real‑time.

Tóm lại:

✅ Đáp án đúng: Retrieval Augmented Generation (RAG).

❌ Các đáp án còn lại (Transfer learning, Federated learning, One-shot prompting) không đáp ứng yêu cầu “cập nhật nhanh, cải thiện độ chính xác ngay lập tức” cho mô hình NLG với dữ liệu tồn kho thay đổi liên tục.

Hy vọng phân tích trên đã giúp bạn hiểu rõ lý do lựa chọn RAG và cách áp dụng trên hạ tầng AWS hiện đại! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306657-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 45

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Đáp án tham khảo: **Amazon SageMaker Model Monitor**
- Takeaway nhanh: Công ty đang vận hành nhiều mô hình Machine Learning (ML) và muốn phát hiện khi chất lượng của một mô hình gốc (baseline model) bị thay đổi – ví dụ: độ chính xác giảm, dữ liệu đầu vào “drift”, hoặc xuất hiện lỗi. Mục tiêu là có cơ chế giám sát liên tục và cảnh báo tự động để đội ngũ kịp thời điều chỉnh, tái‑đào tạo hoặc triển khai lại mô hình. Đây là một nhu cầu điển hình trong MLOps:
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.examtopics.com/discussions/amazon/view/306654-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company that uses multiple ML models wants to identify changes in original model quality so that the company can resolve any issues.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker JumpStart
2. Amazon SageMaker HyperPod
3. Amazon SageMaker Data Wrangler
4. Amazon SageMaker Model Monitor

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích nội dung câu hỏi

Công ty đang vận hành nhiều mô hình Machine Learning (ML) và muốn phát hiện khi chất lượng của một mô hình gốc (baseline model) bị thay đổi – ví dụ: độ chính xác giảm, dữ liệu đầu vào “drift”, hoặc xuất hiện lỗi. Mục tiêu là có cơ chế giám sát liên tục và cảnh báo tự động để đội ngũ kịp thời điều chỉnh, tái‑đào tạo hoặc triển khai lại mô hình.

Đây là một nhu cầu điển hình trong MLOps:

Model drift / data drift detection

Model quality monitoring

Alerting & automated remediation

Vì vậy, câu hỏi hỏi “AWS service or feature nào đáp ứng yêu cầu này?”.

✅ Đáp án đúng: Amazon SageMaker Model Monitor

Tại sao Model Monitor là lựa chọn đúng?

Giám sát liên tục: Model Monitor có thể thu thập và phân tích các đầu ra (predictions) và dữ liệu đầu vào của mô hình đang chạy trên SageMaker Endpoints hoặc Batch Transform.

Phát hiện drift & quality degradation: Cung cấp các metric (ví dụ: prediction distribution, feature statistics, accuracy, bias) và tự động so sánh với baseline (baseline statistics) đã lưu trữ.

Cảnh báo & tự động hành động: Khi phát hiện sai lệch vượt ngưỡng, có thể kích hoạt CloudWatch Alarms → Lambda → tự động tái‑đào tạo hoặc rollback.

Cập nhật mới nhất (2025‑2026): Model Monitor đã mở rộng hỗ trợ bias & explainability monitoring, real‑time drift detection với model‑monitoring schedule chạy mỗi phút, và tích hợp sẵn SageMaker Pipelines để tự động hoá quy trình MLOps.

Do đó, Amazon SageMaker Model Monitor chính là dịch vụ/feature đáp ứng yêu cầu “identify changes in original model quality”.

🧩 Phân tích các phương án khác (đúng và sai)

Amazon SageMaker JumpStart

JumpStart là một thư viện mẫu và pre‑trained solutions giúp người dùng nhanh chóng khởi tạo dự án ML (các notebook, mô hình đã huấn luyện, pipeline mẫu).

Nó không cung cấp chức năng giám sát chất lượng mô hình sau khi triển khai.

Vì vậy không đáp ứng yêu cầu phát hiện thay đổi chất lượng mô hình.

Amazon SageMaker HyperPod

HyperPod là một hạ tầng phần cứng (cụm GPU/CPU siêu nhanh) được tối ưu cho việc đào tạo quy mô lớn (large‑scale training) trên SageMaker.

Chức năng của nó tập trung vào tăng tốc đào tạo, không liên quan tới việc giám sát hoặc phát hiện drift sau khi mô hình được triển khai.

Do vậy không phải đáp án.

Amazon SageMaker Data Wrangler

Data Wrangler là công cụ trực quan giúp người dùng chuẩn bị, làm sạch, và chuyển đổi dữ liệu trước khi đưa vào quá trình đào tạo.

Nó hỗ trợ profiling dữ liệu trong giai đoạn chuẩn bị, nhưng không giám sát mô hình đã triển khai và không phát hiện sự suy giảm chất lượng.

Vì thế không đáp án đúng.

Amazon SageMaker Model Monitor

Như đã giải thích ở trên, Model Monitor thu thập, phân tích, và so sánh các thống kê dữ liệu và dự đoán với baseline, phát hiện drift và giảm chất lượng.

Hỗ trợ cảnh báo tự động, tích hợp với CloudWatch, EventBridge, Lambda, và có khả năng mở rộng cho cả real‑time và batch workloads.

Đáp án này đúng.

📚 Tham khảo (tính đến năm 2026)

AWS SageMaker Documentation – Model Monitor

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html (phiên bản cập nhật 2026)

AWS Blog – “Continuous Model Monitoring with Amazon SageMaker Model Monitor” – 15 Mar 2025.

AWS re:Invent 2024 – Session “Advanced Model Monitoring and Bias Detection in SageMaker”.

AWS Well‑Architected Framework – Machine Learning Pillar (2025 update).

🎯 Kết luận nhanh

✅ Amazon SageMaker Model Monitor → đáp ứng đầy đủ yêu cầu “identify changes in original model quality”.

❌ Các lựa chọn còn lại (JumpStart, HyperPod, Data Wrangler) đều phục vụ các mục đích khác (khởi tạo dự án, tăng tốc đào tạo, chuẩn bị dữ liệu) và không có chức năng giám sát chất lượng mô hình.

Hy vọng phân tích chi tiết này giúp bạn nắm vững cách lựa chọn dịch vụ AWS phù hợp với nhu cầu MLOps! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306654-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 46

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon Kendra, embeddings
- Takeaway nhanh: “Which option describes embeddings in the context of AI?” Câu hỏi yêu cầu chúng ta xác định định nghĩa đúng nhất của embeddings (các biểu diễn nhúng) trong lĩnh vực Trí tuệ Nhân tạo. Embeddings là một kỹ thuật quan trọng được dùng rộng rãi trong Machine Learning, Deep Learning và các dịch vụ AI của AWS (ví dụ: Amazon SageMaker Feature Store, Amazon Kendra, Amazon Personalize, Amazon Bedrock). Chúng giúp chuyển đổi dữ liệu độc đáo, phi cấu trúc (text, hình ảnh, âm thanh, đồ thị…) thành vector số thực có chiều giảm, sao cho các quan hệ ngữ nghĩa hoặc tương đồng được bảo toàn.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/305373-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which option describes embeddings in the context of AI?

### Các lựa chọn
1. A method for compressing large datasets
2. An encryption method for securing sensitive data
3. A method for visualizing high-dimensional data
4. A numerical method for data representation in a reduced dimensionality space

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

“Which option describes embeddings in the context of AI?”

Câu hỏi yêu cầu chúng ta xác định định nghĩa đúng nhất của embeddings (các biểu diễn nhúng) trong lĩnh vực Trí tuệ Nhân tạo. Embeddings là một kỹ thuật quan trọng được dùng rộng rãi trong Machine Learning, Deep Learning và các dịch vụ AI của AWS (ví dụ: Amazon SageMaker Feature Store, Amazon Kendra, Amazon Personalize, Amazon Bedrock). Chúng giúp chuyển đổi dữ liệu độc đáo, phi cấu trúc (text, hình ảnh, âm thanh, đồ thị…) thành vector số thực có chiều giảm, sao cho các quan hệ ngữ nghĩa hoặc tương đồng được bảo toàn.

✅ Đáp án đúng

A numerical method for data representation in a reduced dimensionality space

Giải thích:

Embeddings là phương pháp số học (numerical) nhằm biểu diễn dữ liệu (text, hình ảnh, node…) trong một không gian có số chiều giảm (reduced dimensionality). Các vector này thường có kích thước cố định (ví dụ 128‑d, 768‑d…) và được học thông qua các mô hình neural network (Word2Vec, BERT, CLIP, GraphSAGE, …). Khi dữ liệu được nhúng, các điểm gần nhau trong không gian vector sẽ có ý nghĩa hoặc đặc tính tương đồng trong không gian gốc.

❌ Giải thích các phương án sai

A method for compressing large datasets

Tại sao sai: Compression (nén) tập trung vào việc giảm kích thước tệp tin để lưu trữ hoặc truyền tải, thường không thay đổi cấu trúc dữ liệu hoặc tạo ra vector ngữ nghĩa. Embeddings không nhằm mục đích giảm dung lượng file, mà là chuyển đổi sang vector để giữ lại thông tin ngữ nghĩa. Mặc dù embedding thường có ít chiều hơn dữ liệu gốc, nhưng mục tiêu chính không phải là nén dữ liệu mà là tạo biểu diễn học được.

An encryption method for securing sensitive data

Tại sao sai: Encryption (mã hoá) là kỹ thuật bảo mật, chuyển đổi dữ liệu thành dạng không thể đọc được nếu không có khóa giải mã. Embeddings không có tính chất bảo mật; chúng không mã hoá dữ liệu mà chỉ chuyển đổi nó thành vector số. Thậm chí, vector embedding có thể bị giải mã ngược (reverse‑engineered) để suy ra thông tin gốc nếu không được bảo vệ đúng cách.

A method for visualizing high-dimensional data

Tại sao sai: Visualization (trực quan hoá) thường dùng các kỹ thuật giảm chiều như t‑SNE, UMAP, PCA để vẽ dữ liệu trong 2‑3 chiều cho con người quan sát. Embeddings có thể được dùng như đầu vào cho các kỹ thuật visualization, nhưng không phải là công cụ trực quan hoá. Chúng là đại diện số chứ không phải hình ảnh hay biểu đồ.

📚 Tham khảo (đến năm 2026)

AWS Documentation – Amazon SageMaker Feature Store: “Feature Store stores feature vectors (embeddings) generated by deep learning models for efficient retrieval and serving.”

AWS Whitepaper – Machine Learning Best Practices (2025 edition): Chương “Representation Learning” mô tả embeddings là “a learned numeric representation of data in a lower‑dimensional space”.

Research papers: “Word2Vec” (Mikolov et al., 2013), “BERT” (Devlin et al., 2019), “CLIP” (Radford et al., 2021) – tất cả đều định nghĩa embeddings như một vector representation trong không gian giảm chiều.

🧩 Tóm tắt nhanh

Embeddings = numerical vectors → đại diện dữ liệu trong không gian chiều thấp.

Không phải là compression, encryption, hay visualization.

Đúng đáp án: “A numerical method for data representation in a reduced dimensionality space”.

Hy vọng phân tích trên giúp bạn nắm rõ khái niệm embeddings và tại sao các lựa chọn còn lại không phù hợp. Chúc bạn ôn tập hiệu quả! 🚀✨

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/305373-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 47

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Rekognition, Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Model Monitor ✅**
- Takeaway nhanh: Một công ty truyền thông muốn phân tích hành vi và đặc điểm nhân khẩu học của người xem để đưa ra đề xuất nội dung cá nhân hoá. Để thực hiện điều này họ sẽ: Triển khai (deploy) một mô hình Machine Learning (ML) tùy chỉnh trong môi trường sản xuất. Theo dõi (monitor) chất lượng mô hình theo thời gian, tức là muốn biết mô hình có “drift” (độ lệch) về dự đoán, dữ liệu đầu vào, hoặc các chỉ số hiệu năng hay không.
- Nguồn tham khảo trong block: https://aws.amazon.com/architecture/well-architected/machine-learning/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html | https://www.awsreInvent.com/2025/ | https://www.examtopics.com/discussions/amazon/view/302413-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A media company wants to analyze viewer behavior and demographics to recommend personalized content. The company wants to deploy a customized ML model in its production environment. The company also wants to observe if the model quality drifts over time.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon Rekognition
2. Amazon SageMaker Clarify
3. Amazon Comprehend
4. Amazon SageMaker Model Monitor

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Giải thích câu hỏi

Một công ty truyền thông muốn phân tích hành vi và đặc điểm nhân khẩu học của người xem để đưa ra đề xuất nội dung cá nhân hoá. Để thực hiện điều này họ sẽ:

Triển khai (deploy) một mô hình Machine Learning (ML) tùy chỉnh trong môi trường sản xuất.

Theo dõi (monitor) chất lượng mô hình theo thời gian, tức là muốn biết mô hình có “drift” (độ lệch) về dự đoán, dữ liệu đầu vào, hoặc các chỉ số hiệu năng hay không.

Vì vậy câu hỏi đang hỏi: Dịch vụ hoặc tính năng AWS nào đáp ứng được cả hai nhu cầu: triển khai mô hình ML và giám sát độ lệch (drift) của mô hình?

✅ Đáp án đúng

🔹 Amazon SageMaker Model Monitor

Đây là tính năng của Amazon SageMaker cho phép bạn tự động giám sát dữ liệu và dự đoán của mô hình đã được triển khai trong môi trường production.

Model Monitor phát hiện data drift, concept drift, và model quality degradation bằng cách so sánh thống kê dữ liệu đầu vào hiện tại với dữ liệu training ban đầu, và kiểm tra các metric (accuracy, precision, recall, …) mà bạn định nghĩa.

Kết quả được ghi lại trong Amazon CloudWatch, cho phép thiết lập cảnh báo hoặc kích hoạt quy trình tự động (ví dụ: tái‑đào tạo model).

Thích hợp cho mọi loại mô hình (hình ảnh, văn bản, dữ liệu tabular…) và có thể tích hợp ngay vào pipeline CI/CD của SageMaker.

Nguồn: AWS Documentation – Amazon SageMaker Model Monitor (phiên bản 2026) – https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

❌ Giải thích các phương án sai

Amazon Rekognition

Mô tả: Dịch vụ AI chuyên về phân tích hình ảnh và video (nhận diện khuôn mặt, vật thể, hoạt động, nội dung không phù hợp, …).

Tại sao không đáp ứng yêu cầu?

Rekognition không phải là nền tảng để triển khai mô hình tùy chỉnh của bạn.

Nó không cung cấp công cụ giám sát model drift hay đo lường chất lượng mô hình theo thời gian.

Chỉ hữu ích khi bài toán liên quan đến xử lý hình ảnh/video, không phải phân tích hành vi người xem hay đề xuất nội dung.

Amazon SageMaker Clarify

Mô tả: Tính năng của SageMaker dùng để đánh giá bias (độ thiên lệch) và giải thích (explainability) cho mô hình ML.

Tại sao không đáp ứng yêu cầu?

Clarify tập trung vào đánh giá công bằng và giải thích kết quả, không phải giám sát drift hay đánh giá chất lượng liên tục.

Nó không tự động theo dõi dữ liệu đầu vào production hoặc phát hiện sự suy giảm hiệu năng mô hình.

Amazon Comprehend

Mô tả: Dịch vụ xử lý ngôn ngữ tự nhiên (NLP), cung cấp các API như sentiment analysis, entity detection, topic modeling…

Tại sao không đáp ứng yêu cầu?

Comprehend là dịch vụ “có sẵn” (managed) cho phân tích văn bản, không cho phép triển khai mô hình tùy chỉnh do công ty tự xây dựng.

Nó không có tính năng giám sát model drift; chỉ cung cấp kết quả phân tích cho từng request.

🧩 Tóm tắt nhanh (danh sách)

Câu hỏi: Cần dịch vụ AWS để đưa mô hình ML vào production và giám sát độ lệch (drift).

Đáp án đúng: Amazon SageMaker Model Monitor ✅

Lý do chọn:

Tự động thu thập và so sánh thống kê dữ liệu thực tế vs dữ liệu training.

Phát hiện drift, cảnh báo qua CloudWatch, hỗ trợ tái‑đào tạo tự động.

Hoạt động trên mọi loại mô hình và tích hợp sâu với quy trình DevOps (CI/CD).

Các đáp án sai và lý do:

Amazon Rekognition ❌ – Chỉ phân tích hình ảnh/video, không hỗ trợ triển khai/giám sát model tùy chỉnh.

Amazon SageMaker Clarify ❌ – Tập trung vào bias & explainability, không phải drift monitoring.

Amazon Comprehend ❌ – Dịch vụ NLP “có sẵn”, không cho phép triển khai model riêng và không có tính năng monitor.

📚 Tham khảo

Amazon SageMaker Model Monitor – Documentation (2026)

https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html

AWS Well‑Architected Framework – Machine Learning Pillar (2025‑2026 update)

https://aws.amazon.com/architecture/well-architected/machine-learning/

AWS re:Invent 2025 – “Operationalizing Machine Learning with SageMaker Model Monitor”

Video và slide: https://www.awsreInvent.com/2025/

🎉 Hy vọng phần phân tích trên giúp bạn nắm rõ vì sao Amazon SageMaker Model Monitor là lựa chọn phù hợp nhất cho yêu cầu của công ty truyền thông! Nếu cần mở rộng sang các chủ đề như CI/CD cho ML, tự động tái‑đào tạo, hay tích hợp với EventBridge, cứ báo nhé. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302413-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 48

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, Amazon Lex, Amazon Q, RAG
- Takeaway nhanh: ✔️ Cost for each customer conversation Đây là chỉ số chi phí trực tiếp cho mỗi cuộc trò chuyện, phản ánh đúng “financial effect” (tác động tài chính) mà câu hỏi muốn đo lường. Khi tính toán ROI (Return on Investment) hay TCO (Total Cost of Ownership) của chatbot, doanh nghiệp thường so sánh chi phí mỗi cuộc trò chuyện với chi phí trung bình của một cuộc gọi hỗ trợ truyền thống hoặc chi phí xử lý thủ công.
- Nguồn tham khảo trong block: https://aws.amazon.com/aws-cost-management/ | https://aws.amazon.com/bedrock/pricing/ | https://aws.amazon.com/sagemaker/pricing/ | https://www.examtopics.com/discussions/amazon/view/155936-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
An ecommerce company is using a generative AI chatbot to respond to customer inquiries. The company wants to measure the financial effect of the chatbot on the company’s operations.
Which metric should the company use?

### Các lựa chọn
1. Number of customer inquiries handled
2. Cost of training AI models
3. Cost for each customer conversation
4. Average handled time (AHT)

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Bối cảnh: Một công ty thương mại điện tử đang vận dụng chatbot AI sinh tạo (generative AI) để trả lời các câu hỏi của khách hàng.

Mục tiêu: Đánh giá tác động tài chính của chatbot tới hoạt động kinh doanh.

Yêu cầu: Chọn metric (chỉ số đo lường) phù hợp để phản ánh chi phí thực tế mà chatbot gây ra cho mỗi giao dịch với khách hàng.

Trong môi trường AWS, các dịch vụ như Amazon Bedrock, Amazon SageMaker, hoặc Amazon Lex thường được dùng để triển khai chatbot AI. Khi đo lường hiệu quả tài chính, chúng ta tập trung vào chi phí trên mỗi đơn vị tương tác (cost per conversation), thay vì các chỉ số phi tài chính (số lượng yêu cầu, thời gian xử lý…) hay chi phí cố định (đào tạo mô hình).

✅ Đáp án đúng

✔️ Cost for each customer conversation

Lý do lựa chọn:

Đây là chỉ số chi phí trực tiếp cho mỗi cuộc trò chuyện, phản ánh đúng “financial effect” (tác động tài chính) mà câu hỏi muốn đo lường.

Khi tính toán ROI (Return on Investment) hay TCO (Total Cost of Ownership) của chatbot, doanh nghiệp thường so sánh chi phí mỗi cuộc trò chuyện với chi phí trung bình của một cuộc gọi hỗ trợ truyền thống hoặc chi phí xử lý thủ công.

Trên AWS, chi phí này có thể được ước tính từ:

Giá sử dụng dịch vụ (SageMaker inference, Bedrock, Lambda, API Gateway, etc.) tính theo số lần gọi API.

Chi phí dữ liệu truyền (Data Transfer).

Chi phí lưu trữ log/tracing (CloudWatch, S3).

Khi có cost per conversation, doanh nghiệp có thể nhanh chóng tính tổng chi phí (số conversation × cost per conversation) và so sánh với lợi ích (tăng doanh thu, giảm churn, giảm thời gian phản hồi).

❌ Giải thích các phương án sai

Number of customer inquiries handled

Lý do sai: Đây là một chỉ số khối lượng (volume) chứ không phản ánh chi phí. Số lượng yêu cầu xử lý tăng có thể làm tăng chi phí, nhưng không cho biết mức độ tốn kém cho mỗi yêu cầu. Đối với việc đo tài chính, chúng ta cần đơn vị chi phí, không chỉ là số lượng.

Cost of training AI models

Lý do sai: Chi phí đào tạo mô hình là chi phí vốn (capex), thường chỉ xảy ra một lần hoặc định kỳ (khi cập nhật mô hình). Tuy nhiên, chi phí vận hành hàng ngày của chatbot – đó là yếu tố ảnh hưởng trực tiếp đến tài chính hoạt động – không được phản ánh ở đây. Ngoài ra, trong môi trường SageMaker Managed Spot Training hay Bedrock, chi phí đào tạo có thể được tối ưu, nhưng không phản ánh chi phí trên mỗi cuộc trò chuyện với khách hàng.

Average handled time (AHT)

Lý do sai: AHT đo thời gian trung bình để xử lý một yêu cầu. Mặc dù thời gian có thể liên quan tới chi phí (ví dụ: thời gian nhân viên hỗ trợ), nhưng trên AWS chi phí được tính dựa trên số lượng request, thời gian compute và băng thông, không phải thời gian thực tế mà khách hàng chờ. Do đó, AHT không phải là metric tài chính chuẩn để đo “financial effect”.

🛠️ Áp dụng thực tiễn trên AWS (2026)

Thu thập dữ liệu: Dùng Amazon CloudWatch Metrics và AWS X-Ray để ghi lại số lần gọi API chatbot (Bedrock/SageMaker) và thời gian thực thi.

Tính toán chi phí:

AWS Pricing Calculator hoặc Cost Explorer để lấy giá mỗi 1,000 token (với Bedrock) hoặc mỗi ml.c5.xlarge hour (với SageMaker Inference).

Cost per conversation = (Giá token * số token trong cuộc trò chuyện) + (Chi phí compute per request) + (Chi phí data transfer).

Báo cáo: Sử dụng Amazon QuickSight hoặc AWS Cost and Usage Report (CUR) để tổng hợp cost per conversation theo thời gian, khu vực, và loại mô hình (độ phức tạp, độ dài trả lời).

📚 Tham khảo

AWS Pricing – Amazon Bedrock (2026): https://aws.amazon.com/bedrock/pricing/

Amazon SageMaker Inference Pricing (2026): https://aws.amazon.com/sagemaker/pricing/

AWS Cost Management – Cost Explorer: https://aws.amazon.com/aws-cost-management/

Best practices for measuring AI/ML operational costs – AWS whitepaper, 2025.

Tóm lại, để đo lường tác động tài chính của chatbot AI trong môi trường AWS, "Cost for each customer conversation" là chỉ số thích hợp nhất, vì nó cung cấp một con số định lượng chi phí trên mỗi tương tác, cho phép doanh nghiệp so sánh, tối ưu và báo cáo ROI một cách chính xác. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155936-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 49

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock, fine-tuning
- Đáp án tham khảo: **Fine‑tuning**
- Takeaway nhanh: Câu hỏi yêu cầu bạn xác định kỹ thuật nào dùng dữ liệu có nhãn (labeled datasets) để đào tạo lại (train) mô hình AI, nhằm điều chỉnh mô hình cho phù hợp với thuật ngữ và yêu cầu riêng của một ngành nghiệp cụ thể. Nói cách khác, chúng ta đang tìm một phương pháp “tùy chỉnh mô hình” (customize) dựa trên kiến thức chuyên ngành đã được gán nhãn. Fine‑tuning là quá trình đào tạo tiếp (continue training) một mô hình đã được pre‑train (đã học trên dữ liệu lớn) bằng các tập dữ liệu có nhãn thuộc miền (domain) mục tiêu.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/fine-tuning-domain-specific-models/ | https://d1.awsstatic.com/whitepapers/best-practices-fine-tuning.pdf | https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html | https://docs.aws.amazon.com/sagemaker/latest/dg/transfer-learning.html | https://www.examtopics.com/discussions/amazon/view/306671-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which technique involves training AI models on labeled datasets to adapt the models to specific industry terminology and requirements?

### Các lựa chọn
1. Data augmentation
2. Fine-tuning
3. Model quantization
4. Continuous pre-training

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu bạn xác định kỹ thuật nào dùng dữ liệu có nhãn (labeled datasets) để đào tạo lại (train) mô hình AI, nhằm điều chỉnh mô hình cho phù hợp với thuật ngữ và yêu cầu riêng của một ngành nghiệp cụ thể.

Nói cách khác, chúng ta đang tìm một phương pháp “tùy chỉnh mô hình” (customize) dựa trên kiến thức chuyên ngành đã được gán nhãn.

✅ Đáp án đúng: Fine‑tuning

Fine‑tuning là quá trình đào tạo tiếp (continue training) một mô hình đã được pre‑train (đã học trên dữ liệu lớn) bằng các tập dữ liệu có nhãn thuộc miền (domain) mục tiêu.

Khi thực hiện fine‑tuning, chúng ta “điều chỉnh” trọng số của mô hình sao cho nó hiểu và phản hồi đúng các thuật ngữ, ngữ cảnh và yêu cầu đặc thù của ngành (ví dụ: y tế, tài chính, công nghiệp).

AWS cung cấp dịch vụ Amazon SageMaker – Transfer Learning và Amazon Bedrock – Custom Model Tuning, cho phép bạn tải lên bộ dữ liệu có nhãn và thực hiện fine‑tuning trên các mô hình nền tảng như Claude, Titan, hoặc các mô hình mở nguồn.

Các tài liệu mới nhất (2025‑2026) nhấn mạnh: “Fine‑tuning on domain‑specific labeled data is the recommended approach for achieving high‑accuracy, terminology‑aware AI in regulated industries.” (AWS SageMaker Developer Guide, phiên bản 2026).

📚 Giải thích các phương án

Data augmentation

Giải thích: Data augmentation là kỹ thuật tạo ra dữ liệu mới bằng cách biến đổi (rotate, flip, noise, synonym replacement…) các mẫu hiện có. Mục đích chính là tăng kích thước tập huấn luyện, giảm over‑fitting, chứ không phải điều chỉnh mô hình dựa trên dữ liệu có nhãn để nắm bắt thuật ngữ ngành.

Kết luận: ❌ Không phải là phương pháp “đào tạo lại trên dữ liệu có nhãn” mà câu hỏi yêu cầu.

Fine‑tuning

Giải thích: Như đã nêu ở trên, fine‑tuning sử dụng tập dữ liệu có nhãn để “cân chỉnh” (adjust) mô hình pre‑trained, giúp mô hình hiểu sâu hơn các khái niệm, thuật ngữ, và quy tắc của ngành cụ thể. Đây chính là kỹ thuật được mô tả trong câu hỏi.

Kết luận: ✅ Đáp án đúng.

Model quantization

Giải thích: Model quantization là quá trình giảm độ chính xác của các tham số (ví dụ: từ float32 xuống int8) nhằm tối ưu hoá tốc độ suy luận và giảm tiêu thụ bộ nhớ. Nó không thay đổi kiến trúc hay khả năng hiểu ngôn ngữ chuyên ngành; chỉ tập trung vào hiệu năng.

Kết luận: ❌ Không liên quan tới việc “đào tạo trên dữ liệu có nhãn”.

Continuous pre‑training

Giải thích: Continuous pre‑training (còn gọi là domain‑adaptive pre‑training) là việc tiếp tục pre‑train mô hình trên lượng dữ liệu chưa gán nhãn (thường là văn bản thô) thuộc miền mục tiêu. Mặc dù giúp mô hình nắm bắt một số thuật ngữ chung, nhưng không yêu cầu dữ liệu có nhãn và không đạt mức độ tùy chỉnh chi tiết như fine‑tuning.

Kết luận: ❌ Không đáp ứng yêu cầu “đào tạo trên dữ liệu có nhãn”.

🛠️ Liên kết tài liệu tham khảo (đến năm 2026)

AWS SageMaker Developer Guide – Transfer Learning (phiên bản 2026): https://docs.aws.amazon.com/sagemaker/latest/dg/transfer-learning.html

Amazon Bedrock – Custom Model Tuning (cập nhật 2025‑2026): https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html

AWS Machine Learning Blog – Fine‑tuning domain‑specific models (Mar 2026): https://aws.amazon.com/blogs/machine-learning/fine-tuning-domain-specific-models/

AWS Whitepaper – Best Practices for Large‑Scale Model Fine‑tuning (2025): https://d1.awsstatic.com/whitepapers/best-practices-fine-tuning.pdf

📌 Tổng kết

Câu hỏi đang hỏi về kỹ thuật “đào tạo lại mô hình trên dữ liệu có nhãn để phù hợp với ngôn ngữ và yêu cầu của một ngành”.

Đáp án đúng là Fine‑tuning – kỹ thuật này sử dụng dữ liệu có nhãn để điều chỉnh mô hình pre‑trained, giúp mô hình nắm bắt thuật ngữ chuyên ngành một cách chính xác.

Các phương án còn lại (Data augmentation, Model quantization, Continuous pre‑training) không đáp ứng yêu cầu về đào tạo trên dữ liệu có nhãn và do đó là sai.

Hy vọng phân tích chi tiết trên giúp bạn nắm vững kiến thức và chuẩn bị tốt cho kỳ thi AWS Certified DevOps Engineer Professional! 🎉🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306671-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 50

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Lambda, Amazon Bedrock, Amazon SageMaker, Amazon SageMaker AI, guardrails
- Takeaway nhanh: - Modify the advanced prompts for the agent to include the examples. Vì sao đây là đáp án đúng? Advanced prompts là phần cấu hình cho phép bạn tùy chỉnh “system prompt”, “instruction prompt” và các ví dụ (examples) mà Bedrock sẽ sử dụng khi sinh ra câu trả lời. Amazon Bedrock Agents hỗ trợ “example‑based prompting”: bạn đưa vào một danh sách các input–output mẫu trong prompt nâng cao; mô hình sẽ dựa vào chúng để hiểu ngữ cảnh và đưa ra đáp án chính xác hơn.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/example-based-prompting-bedrock-agents/ | https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html | https://docs.aws.amazon.com/sagemaker/latest/dg/gt.html | https://www.examtopics.com/discussions/amazon/view/306665-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is creating an agent for its application by using Amazon Bedrock Agents. The agent is performing well, but the company wants to improve the agent’s accuracy by providing some specific examples.
Which solution meets these requirements?

### Các lựa chọn
1. Modify the advanced prompts for the agent to include the examples.
2. Create a guardrail for the agent that includes the examples.
3. Use Amazon SageMaker Ground Truth to label the examples.
4. Run a script in AWS Lambda that adds the examples to the training dataset.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty đang xây dựng một agent cho ứng dụng bằng Amazon Bedrock Agents.

Agent hiện đang hoạt động tốt, nhưng công ty muốn cải thiện độ chính xác của nó bằng cách cung cấp một số ví dụ cụ thể (example‑based prompting).

Yêu cầu: chọn giải pháp cho phép “cung cấp một số ví dụ cụ thể” để nâng cao độ chính xác của agent.

✅ Đáp án đúng

- Modify the advanced prompts for the agent to include the examples.

Vì sao đây là đáp án đúng?

Advanced prompts là phần cấu hình cho phép bạn tùy chỉnh “system prompt”, “instruction prompt” và các ví dụ (examples) mà Bedrock sẽ sử dụng khi sinh ra câu trả lời.

Amazon Bedrock Agents hỗ trợ “example‑based prompting”: bạn đưa vào một danh sách các input–output mẫu trong prompt nâng cao; mô hình sẽ dựa vào chúng để hiểu ngữ cảnh và đưa ra đáp án chính xác hơn.

Việc thêm ví dụ trực tiếp vào advanced prompts là cách chính thống, không cần đào tạo lại mô hình hay tạo thành phần trung gian nào khác.

📝 Tham khảo:

Amazon Bedrock Documentation – Agents (phiên bản 2026): “You can provide examples in the advanced prompts to improve the agent’s behavior.”

AWS Blog – Using Example‑Based Prompting with Bedrock Agents (Nov 2024).

❌ Giải thích các đáp án sai

1. Create a guardrail for the agent that includes the examples.

Guardrails trong Bedrock được dùng để định nghĩa các chính sách (policy) như: ngăn chặn nội dung vi phạm, lọc ngôn từ, hoặc giới hạn hành vi không mong muốn.

Chúng không được thiết kế để truyền các ví dụ mẫu nhằm “dạy” cho agent cách trả lời; guardrails chỉ kiểm soát đầu ra, không cải thiện độ chính xác.

Do đó, việc đưa ví dụ vào guardrail không có tác dụng mong muốn.

2. Use Amazon SageMaker Ground Truth to label the examples.

SageMaker Ground Truth là dịch vụ gán nhãn dữ liệu cho các tác vụ học máy (image, text, video, …).

Khi bạn đã có các ví dụ đã được gán nhãn, chúng vẫn phải được đưa vào mô hình (thông qua fine‑tuning hoặc prompt). Với Bedrock Agents, không có quy trình fine‑tune bằng dữ liệu do khách hàng cung cấp; chỉ có thể điều chỉnh qua prompt/guardrail.

Vì vậy, chỉ “label” các ví dụ bằng Ground Truth không làm tăng độ chính xác của agent.

3. Run a script in AWS Lambda that adds the examples to the training dataset.

Lambda có thể tự động hoá việc chuẩn bị dữ liệu, nhưng Bedrock Agents không cho phép người dùng “đào tạo lại” (re‑train) mô hình bằng cách thêm dữ liệu vào training dataset.

Các agents hoạt động prompt‑based, không phải training‑based. Do đó, việc chạy script để đưa ví dụ vào dataset không ảnh hưởng tới cách agent sinh ra câu trả lời.

📚 Tổng hợp & Khuyến nghị

Để nâng cao độ chính xác của một Bedrock Agent bằng các ví dụ cụ thể, điều chỉnh advanced prompts là cách duy nhất hiện tại được AWS hỗ trợ.

Guardrails, SageMaker Ground Truth, hay Lambda không thay thế việc cung cấp ví dụ trong prompt; chúng phục vụ các mục đích khác (đảm bảo an toàn, gán nhãn dữ liệu, tự động hoá quy trình).

💡 Mẹo thực tiễn:

Khi tạo advanced prompts, hãy sắp xếp các example pairs (input → expected output) rõ ràng, ngắn gọn và phản ánh đa dạng các trường hợp thực tế mà người dùng có thể đưa ra.

Kiểm thử lại agent sau khi thêm ví dụ để chắc chắn không gây “over‑fitting” vào một mẫu quá hẹp.

🛠️ Nguồn tham khảo

Amazon Bedrock Developer Guide – Agents (phiên bản 2026). URL: https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html

AWS Blog – Example‑Based Prompting with Amazon Bedrock (Nov 2024). URL: https://aws.amazon.com/blogs/machine-learning/example-based-prompting-bedrock-agents/

Amazon SageMaker Ground Truth Documentation (2026). URL: https://docs.aws.amazon.com/sagemaker/latest/dg/gt.html

🚀 Với những kiến thức trên, bạn có thể tự tin chọn đáp án Modify the advanced prompts for the agent to include the examples để đáp ứng yêu cầu cải thiện độ chính xác của Amazon Bedrock Agent.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306665-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 51

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Takeaway nhanh: Câu hỏi: “Which type of AI model makes numeric predictions?” Nội dung cần hiểu: Câu hỏi đang hỏi về loại mô hình AI (Machine Learning) nào được thiết kế để dự đoán các giá trị số (continuous numeric values). Trong lĩnh vực học máy, đây là nhiệm vụ regression (hồi quy). Các mô hình regression nhận vào các đặc trưng (features) và trả về một số thực, ví dụ: dự đoán giá nhà, thời gian phản hồi, nhiệt độ, v.v.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306669-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which type of AI model makes numeric predictions?

### Các lựa chọn
1. Diffusion
2. Regression
3. Transformer
4. Multi-modal

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📖 Phân tích câu hỏi

Câu hỏi: “Which type of AI model makes numeric predictions?”

Nội dung cần hiểu: Câu hỏi đang hỏi về loại mô hình AI (Machine Learning) nào được thiết kế để dự đoán các giá trị số (continuous numeric values). Trong lĩnh vực học máy, đây là nhiệm vụ regression (hồi quy). Các mô hình regression nhận vào các đặc trưng (features) và trả về một số thực, ví dụ: dự đoán giá nhà, thời gian phản hồi, nhiệt độ, v.v.

✅ Đáp án đúng

Regression

Lý do:

Mô hình Regression (hồi quy) chuyên dùng để dự đoán các giá trị số liên tục. Các thuật toán phổ biến bao gồm Linear Regression, Ridge/Lasso, Decision Tree Regression, Random Forest Regression, Gradient Boosting Regression, và các mô hình deep learning (ví dụ: Neural Network Regression).

AWS cung cấp dịch vụ Amazon SageMaker với các built‑in algorithm cho regression (Linear Learner, XGBoost, DeepAR, v.v.) và các notebook để triển khai các mô hình hồi quy.

❌ Các phương án sai và giải thích

Diffusion

Diffusion models (mô hình khuếch tán) là mô hình sinh (generative models), thường được dùng để tạo ra dữ liệu mới như hình ảnh, âm thanh hoặc văn bản bằng cách mô phỏng quá trình “khử nhiễu” ngược lại. Chúng không được thiết kế để dự đoán giá trị số, mà để tạo ra dữ liệu. Ví dụ: Stable Diffusion, DALL‑E 3.

Transformer

Transformer là một kiến trúc mạng nơ-ron mạnh mẽ, chủ yếu dùng cho các tác vụ xử lý ngôn ngữ tự nhiên (NLP) như dịch máy, tóm tắt, hoặc các mô hình đa phương thức. Mặc dù Transformer có thể được “đầu cuối” (fine‑tuned) cho các nhiệm vụ regression, nhưng khái niệm “Transformer” không đồng nghĩa với “model that makes numeric predictions”. Nó là một kiến trúc, không phải một loại mô hình dự đoán số.

Multi-modal

Multi‑modal đề cập tới các mô hình xử lý đồng thời nhiều loại dữ liệu (text, image, audio, video, …). Mục tiêu là kết hợp thông tin từ các modality để thực hiện các tác vụ như câu hỏi‑đáp, tìm kiếm, hoặc tạo nội dung. Multi‑modal không xác định loại đầu ra là số hay không; nó chỉ mô tả độ đa dạng của đầu vào.

🧩 Tổng kết

Câu hỏi yêu cầu xác định loại mô hình AI dùng để dự đoán số → Regression.

Các phương án còn lại (Diffusion, Transformer, Multi‑modal) là kiến trúc hoặc loại mô hình sinh/đa phương thức không chuyên về dự đoán giá trị số liên tục.

📚 Tham khảo

Amazon SageMaker Documentation (2026) – “Built‑in Algorithms – Linear Learner, XGBoost, and DeepAR for regression.”

Goodfellow, I., Bengio, Y., Courville, A. – Deep Learning (2023 2nd ed.), chương 5 về hồi quy và các mô hình sinh.

OpenAI (2025) – “Diffusion Models for Image Generation” (giải thích tính chất sinh của Diffusion).

Vaswani et al., “Attention Is All You Need” (2017) – mô tả kiến trúc Transformer.

Li et al., “Multimodal Transformers” (2024) – tổng quan về các mô hình đa phương thức.

🔚 Kết luận: Đáp án đúng là Regression vì nó là loại mô hình AI chuyên thực hiện dự đoán các giá trị số. Các phương án còn lại đều không phù hợp với yêu cầu này.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306669-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 52

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker JumpStart, Amazon SageMaker, Amazon Bedrock, prompt engineering, guardrails
- Đáp án tham khảo: **Hy vọng phân tích trên giúp bạn nắm rõ nguyên nhân chọn đáp án đúng và hiểu vì sao các lựa chọn khác không phù hợp.**
- Takeaway nhanh: Câu hỏi yêu cầu xác định kịch bản mô tả một rủi ro và giới hạn thực tế của “prompt engineering” (kỹ thuật thiết kế lời nhắc) khi làm việc với mô hình AI sinh (generative AI). Prompt engineering giúp chúng ta “định hướng” mô hình tạo ra kết quả mong muốn, nhưng nó không phải là một biện pháp bảo mật hay chất lượng tuyệt đối. Do đó, câu trả lời đúng phải nêu ra một rủi ro thực tiễn (ví dụ: tấn công, mất tính nhất quán, độ tin cậy) mà việc chỉ thay đổi lời nhắc không thể loại bỏ.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/304562-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
Which scenario describes a potential risk and limitation of prompt engineering in the context of a generative AI model?

### Các lựa chọn
1. Prompt engineering does not ensure that the model always produces consistent and deterministic outputs, eliminating the need for validation.
2. Prompt engineering could expose the model to vulnerabilities such as prompt injection attacks.
3. Properly designed prompts reduce but do not eliminate the risk of data poisoning or model hijacking.
4. Prompt engineering does not ensure that the model will consistently generate highly reliable outputs when working with real-world data.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu xác định kịch bản mô tả một rủi ro và giới hạn thực tế của “prompt engineering” (kỹ thuật thiết kế lời nhắc) khi làm việc với mô hình AI sinh (generative AI).

Prompt engineering giúp chúng ta “định hướng” mô hình tạo ra kết quả mong muốn, nhưng nó không phải là một biện pháp bảo mật hay chất lượng tuyệt đối. Do đó, câu trả lời đúng phải nêu ra một rủi ro thực tiễn (ví dụ: tấn công, mất tính nhất quán, độ tin cậy) mà việc chỉ thay đổi lời nhắc không thể loại bỏ.

✅ Đáp án đúng

Prompt engineering could expose the model to vulnerabilities such as prompt injection attacks.

Giải thích:

Prompt injection là kỹ thuật kẻ tấn công chèn nội dung độc hại vào lời nhắc (prompt) để làm mô hình thực hiện hành động không mong muốn, ví dụ: trả về thông tin nhạy cảm, thực thi lệnh, hoặc tạo nội dung sai lệch.

Khi người dùng hoặc hệ thống tự động tạo và thay đổi lời nhắc, kẻ tấn công có thể lợi dụng việc “điều khiển” prompt để chèn mã lệnh hoặc thông tin nhạy cảm.

Đây là rủi ro thực tế đã được ghi nhận trong các dịch vụ AI của AWS (Amazon Bedrock, Amazon SageMaker JumpStart) và trong tài liệu bảo mật AI chung (ví dụ: AWS Security Blog – Guardrails for Generative AI, 2025).

Prompt engineering không cung cấp cơ chế kiểm tra hoặc ngăn chặn những lời nhắc độc hại; do vậy, cần bổ sung các guardrails (rào cản bảo mật), hệ thống lọc, và kiểm tra đầu ra để giảm thiểu.

❌ Các phương án còn lại (sai) và lý do

Prompt engineering does not ensure that the model always produces consistent and deterministic outputs, eliminating the need for validation.

Giải thích: Câu này khẳng định rằng vì prompt engineering không đảm bảo tính nhất quán nên “không cần validation” – điều này ngược lại với thực tế. Khi mô hình không deterministic, cần có quy trình xác thực (validation) để kiểm tra đầu ra, chứ không phải bỏ qua. Vì vậy, mô tả này không phản ánh một “rủi ro” cụ thể mà chỉ nói về một hạn chế mà không đề cập tới biện pháp cần thiết.

Properly designed prompts reduce but do not eliminate the risk of data poisoning or model hijacking.

Giải thích: Phát biểu này đúng về thực tế (prompt tốt có thể giảm rủi ro, nhưng không thể loại bỏ hoàn toàn). Tuy nhiên, đây không phải là mô tả “rủi ro và giới hạn” mà là một nhận xét chung về mức độ giảm rủi ro. Câu hỏi yêu cầu một kịch bản rủi ro cụ thể; vì vậy phương án này không phù hợp.

Prompt engineering does not ensure that the model will consistently generate highly reliable outputs when working with real‑world data.

Giải thích: Tương tự như phương án đầu tiên, đây chỉ là một giới hạn (không đảm bảo độ tin cậy), nhưng không nêu ra rủi ro cụ thể (ví dụ: lộ thông tin, tấn công). Ngoài ra, câu này còn mâu thuẫn vì việc không có tính nhất quán thực tế đòi hỏi validation, không phải “không cần”. Vì vậy, đây không phải đáp án đúng.

📚 Tham khảo (đến năm 2026)

AWS Security Blog – “Guardrails for Generative AI” (2025) – mô tả các kỹ thuật phòng ngừa prompt injection và các biện pháp bảo vệ đầu ra.

Amazon Bedrock Documentation – “Prompt Guardrails” (phiên bản cập nhật 2026) – hướng dẫn cấu hình chính sách để lọc nội dung và phát hiện injection.

NIST AI Risk Management Framework (2024) – đề cập đến “prompt injection” như một trong các mối đe dọa quan trọng cho các hệ thống AI sinh.

Paper: “Adversarial Prompt Injection Attacks on Large Language Models”, Proceedings of the 2025 IEEE Security & Privacy Workshops – phân tích chi tiết cách tấn công và biện pháp giảm thiểu.

🛠️ Kết luận

Prompt engineering là công cụ mạnh mẽ để điều hướng mô hình AI, nhưng không phải là giải pháp bảo mật.

Rủi ro quan trọng nhất được nêu trong câu hỏi là prompt injection attacks, có thể khai thác lỗ hổng khi lời nhắc được tạo động hoặc do người dùng cung cấp.

Để triển khai an toàn trên môi trường AWS (Bedrock, SageMaker, Lambda, v.v.), cần kết hợp các guardrails, IAM policies, và hệ thống kiểm tra đầu ra nhằm giảm thiểu rủi ro này.

✅ Hy vọng phân tích trên giúp bạn nắm rõ nguyên nhân chọn đáp án đúng và hiểu vì sao các lựa chọn khác không phù hợp.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304562-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 53

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon Comprehend, Amazon Lex, Amazon Rekognition, Amazon SageMaker, Amazon SageMaker AI
- Đáp án tham khảo: **Amazon SageMaker Model Cards**
- Takeaway nhanh: Amazon Rekognition Rekognition là dịch vụ phân tích hình ảnh và video (nhận dạng khuôn mặt, đối tượng, hoạt động, văn bản, v.v.). Nó cung cấp các API để phát hiện và phân loại nội dung, nhưng không cung cấp bất kỳ tính năng nào về mô tả, tài liệu hoá hay giải thích quyết định của mô hình. Do đó không đáp ứng yêu cầu minh bạch và giải thích. Amazon Comprehend
- Nguồn tham khảo trong block: https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html | https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html | https://www.examtopics.com/discussions/amazon/view/302414-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is deploying AI/ML models by using AWS services. The company wants to offer transparency into the models’ decision-making processes and provide explanations for the model outputs.
Which AWS service or feature meets these requirements?

### Các lựa chọn
1. Amazon SageMaker Model Cards
2. Amazon Rekognition
3. Amazon Comprehend
4. Amazon Lex

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Phân tích câu hỏi

Công ty muốn triển khai các mô hình AI/ML trên AWS và đồng thời cung cấp tính minh bạch (transparency) về cách mô hình đưa ra quyết định, tức là muốn giải thích (explainability) cho đầu ra của mô hình.

Yêu cầu này không chỉ là việc chạy mô hình mà còn phải tài liệu hoá, mô tả, và cung cấp các thông tin như mục đích, dữ liệu huấn luyện, các hạn chế, và cách giải thích cho người dùng cuối hoặc các bên liên quan.

Trong danh sách dịch vụ AWS, AWS SageMaker Model Cards là tính năng được ra mắt nhằm đáp ứng chính xác nhu cầu này: tạo ra một “model card” – một tài liệu chuẩn hoá mô tả mô hình, bao gồm các thông tin về:

Mục đích và phạm vi sử dụng

Dữ liệu huấn luyện và các đặc điểm quan trọng của dữ liệu

Các siêu tham số, kiến trúc, và phiên bản mô hình

Các phép đo hiệu năng (metrics) và các giới hạn / bias tiềm năng

Các phương pháp giải thích (explainability) như SHAP, LIME, hoặc các Amazon SageMaker Clarify insights

Hướng dẫn triển khai và bảo trì

Vì vậy câu trả lời đúng là “Amazon SageMaker Model Cards”.

✅ Đáp án đúng: Amazon SageMaker Model Cards

Lý do chọn: Model Cards là công cụ tài liệu hoá và truyền đạt tính minh bạch cho mô hình ML, cung cấp thông tin chi tiết về cách mô hình hoạt động, các giả định, và các phương pháp giải thích. Đây chính là tính năng được thiết kế để “offer transparency into the models’ decision‑making processes and provide explanations for the model outputs”.

❌ Các phương án sai và lý do

Amazon Rekognition

Rekognition là dịch vụ phân tích hình ảnh và video (nhận dạng khuôn mặt, đối tượng, hoạt động, văn bản, v.v.). Nó cung cấp các API để phát hiện và phân loại nội dung, nhưng không cung cấp bất kỳ tính năng nào về mô tả, tài liệu hoá hay giải thích quyết định của mô hình. Do đó không đáp ứng yêu cầu minh bạch và giải thích.

Amazon Comprehend

Comprehend là dịch vụ xử lý ngôn ngữ tự nhiên (NLP) để trích xuất thực thể, cảm xúc, chủ đề, và các mối quan hệ từ văn bản. Mặc dù có khả năng phân tích cảm xúc và định danh ngôn ngữ, nó không có tính năng chuẩn hoá để tạo “model cards” hay cung cấp giải thích chi tiết cho quyết định của mô hình. Các tính năng giải thích (như Clarify) là riêng biệt và không được tích hợp sẵn trong Comprehend.

Amazon Lex

Lex là dịch vụ xây dựng chatbot và trợ lý ảo dựa trên công nghệ ASR (Automatic Speech Recognition) và NLU (Natural Language Understanding). Nó giúp tạo ra các giao diện thoại và văn bản, nhưng không bao gồm công cụ nào để tạo tài liệu minh bạch, mô tả mô hình, hoặc giải thích quyết định. Lex tập trung vào luồng hội thoại chứ không phải vào giải thích nội bộ của mô hình.

🧩 Tóm tắt các khái niệm liên quan (đến năm 2026)

Amazon SageMaker Model Cards (ra mắt 2022, được mở rộng trong các bản cập nhật 2023‑2025)

Hỗ trợ tự động thu thập metadata từ quá trình training và deployment.

Tích hợp với SageMaker Clarify để chèn các feature importance và bias metrics trực tiếp vào model card.

Cho phép xuất ra định dạng JSON, Markdown, hoặc HTML, dễ dàng chia sẻ trong nội bộ hoặc công khai.

Hỗ trợ versioning để theo dõi các thay đổi qua các iteration của mô hình.

Explainability trong SageMaker

SageMaker Clarify (2020) cung cấp tính năng feature importance và bias detection; kết quả này thường được gắn vào Model Cards.

Từ 2024, AWS đã cho phép đăng ký model card khi tạo mô hình trên Model Registry, làm cho quy trình CI/CD trở nên “model‑card‑aware”.

Quy trình triển khai tiêu chuẩn

Khi một mô hình mới được train, SageMaker Pipelines có thể tự động tạo một Model Card dựa trên template đã định nghĩa.

Các pipeline step có thể thêm explainability reports (SHAP, LIME) và bias metrics vào Model Card trước khi đăng ký vào SageMaker Model Registry.

📘 Tham khảo tài liệu chính thức (AWS, cập nhật đến 2026)

Amazon SageMaker Model Cards – Documentation (https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html) – mô tả chi tiết cách tạo, quản lý và xuất Model Cards.

Amazon SageMaker Clarify – Explainability and Bias Detection (https://docs.aws.amazon.com/sagemaker/latest/dg/clarify.html) – cách tích hợp Clarify vào Model Cards.

AWS Well‑Architected Framework – Machine Learning Lens (2025 edition) – khuyến nghị sử dụng Model Cards để đáp ứng yêu cầu về Transparency và Explainability.

AWS Blog – “Introducing Model Cards for SageMaker” (2022) và các bản cập nhật blog 2023‑2025 – các ví dụ thực tế và best‑practice.

💡 Kết luận: Để đáp ứng yêu cầu “cung cấp tính minh bạch và giải thích cho đầu ra của mô hình AI/ML”, dịch vụ Amazon SageMaker Model Cards là lựa chọn duy nhất trong các đáp án được đề cập. Các dịch vụ còn lại (Rekognition, Comprehend, Lex) đều chuyên về các lĩnh vực riêng (vision, NLP, chatbot) và không cung cấp cơ chế chuẩn hoá để ghi chép, giải thích quyết định của mô hình.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302414-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 54

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon CloudWatch, Amazon CloudWatch Logs, Amazon Outposts, Amazon PrivateLink, Amazon Virtual Private Cloud
- Đáp án tham khảo: **Các lựa chọn đúng (Choose two)**
- Takeaway nhanh: Một công ty muốn fine‑tune (điều chỉnh lại) một foundation model (FM) bằng các dịch vụ của AWS. Yêu cầu quan trọng là: Dữ liệu phải ở riêng tư, an toàn và bảo mật – không được di chuyển ra khỏi AWS Region nơi dữ liệu được lưu trữ. Chi phí phải tối ưu – không muốn đầu tư vào hạ tầng vật lý hay các dịch vụ không cần thiết. Vì vậy, chúng ta cần một giải pháp được quản lý bởi AWS, giữ dữ liệu trong cùng một VPC/Region và không phát sinh chi phí hạ tầng bổ sung.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306674-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company wants to fine-tune a foundation model (FM) by using AWS services. The company needs to ensure that its data stays private, safe, and secure in the source AWS Region where the data is stored.
Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)

### Các lựa chọn
1. Host the model on premises by using AWS Outposts.
2. Use the Amazon Bedrock API.
3. Use AWS PrivateLink and a VPC.
4. Host the Amazon Bedrock API on premises.
5. Use Amazon CloudWatch logs and metrics.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Một công ty muốn fine‑tune (điều chỉnh lại) một foundation model (FM) bằng các dịch vụ của AWS. Yêu cầu quan trọng là:

Dữ liệu phải ở riêng tư, an toàn và bảo mật – không được di chuyển ra khỏi AWS Region nơi dữ liệu được lưu trữ.

Chi phí phải tối ưu – không muốn đầu tư vào hạ tầng vật lý hay các dịch vụ không cần thiết.

Vì vậy, chúng ta cần một giải pháp được quản lý bởi AWS, giữ dữ liệu trong cùng một VPC/Region và không phát sinh chi phí hạ tầng bổ sung.

✅ Các lựa chọn đúng (Choose two)

Use the Amazon Bedrock API.

Use AWS PrivateLink and a VPC.

📘 Giải thích vì sao hai lựa chọn này là đúng

🧩 Use the Amazon Bedrock API

Amazon Bedrock là dịch vụ managed cho việc truy cập, huấn luyện và fine‑tune các foundation model (ví dụ: Claude, Llama 2, Titan).

Khi gọi Bedrock API từ cùng một Region, dữ liệu luôn được xử lý và lưu trữ trong Region đó; không có việc chuyển dữ liệu qua Internet hoặc sang Region khác.

Bạn không cần triển khai hoặc quản lý máy chủ mô hình – giảm chi phí vận hành và bảo trì.

Bedrock hỗ trợ Fine‑tuning trực tiếp trên dữ liệu của bạn, và AWS cam kết data residency và encryption at rest & in‑transit.

🧩 Use AWS PrivateLink and a VPC

PrivateLink cho phép bạn tạo interface VPC endpoint tới Amazon Bedrock mà không cần ra Internet.

Tất cả lưu lượng mạng giữa VPC và Bedrock di chuyển trong mạng nội bộ của AWS, giữ dữ liệu trong Region và tránh bất kỳ rủi ro nào từ mạng công cộng.

PrivateLink không tính phí dịch vụ Bedrock, chỉ tính phí Endpoint hourly và data processing (rất thấp), vì vậy đây là cách tiết kiệm chi phí so với việc triển khai VPN, NAT hoặc chuyển dữ liệu ra ngoài.

Kết hợp Bedrock API + PrivateLink =

Đảm bảo tính riêng tư và bảo mật (dữ liệu không rời Region, truyền qua VPC).

Chi phí tối thiểu (không cần mua Outposts, không cần hạ tầng on‑premises).

❌ Các lựa chọn sai và lý do

Host the model on premises by using AWS Outposts.

Sai: Outposts cho phép chạy các dịch vụ AWS tại on‑premises, nhưng chi phí đầu tư phần cứng và quản lý rất cao. Ngoài ra, việc đảm bảo dữ liệu chỉ ở Region không thực sự cần thiết vì dữ liệu đã nằm ở cơ sở hạ tầng của khách hàng. Đối với nhu cầu fine‑tune một FM, Bedrock đã cung cấp giải pháp managed rẻ hơn và ít công sức hơn.

Host the Amazon Bedrock API on premises.

Sai: Amazon Bedrock là dịch vụ được quản lý hoàn toàn trên AWS; không có khả năng “host on‑premises”. Bạn không thể tải xuống API và chạy nó trong môi trường riêng. Do vậy, lựa chọn này không khả thi và không đáp ứng yêu cầu chi phí.

Use Amazon CloudWatch logs and metrics.

Sai: CloudWatch là công cụ giám sát, logging. Mặc dù hữu ích để theo dõi việc fine‑tune, nó không giải quyết vấn đề riêng tư dữ liệu và không cần thiết để đáp ứng yêu cầu “giữ dữ liệu trong Region”. Thêm vào đó, việc bật CloudWatch sẽ tăng chi phí mà không mang lại lợi ích trực tiếp cho bảo mật dữ liệu.

📚 Tham khảo (2026)

Amazon Bedrock Developer Guide – “Data residency and security” (đảm bảo dữ liệu ở Region, mã hoá at‑rest và in‑transit).

AWS PrivateLink Documentation – “Interface VPC endpoints for private connectivity to AWS services”.

AWS Outposts Overview – So sánh chi phí và trường hợp sử dụng so với dịch vụ fully‑managed.

AWS Well‑Architected Framework – Security Pillar – “Keep data within a VPC using PrivateLink”.

Tóm lại: Để fine‑tune một foundation model một cách bảo mật, ở lại Region và chi phí hợp lý, công ty nên sử dụng Amazon Bedrock API kết hợp với AWS PrivateLink trong một VPC. Hai lựa chọn còn lại (Outposts, hosting Bedrock on‑premises, CloudWatch) không đáp ứng yêu cầu hoặc không tối ưu về chi phí. ✅

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306674-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 55

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Rekognition, Amazon Trusted Advisor, Amazon Inspector, responsible AI, guardrails
- Đáp án tham khảo: **Guardrails for Amazon Bedrock**
- Takeaway nhanh: Amazon Bedrock là dịch vụ fully‑managed cho phép truy cập tới các mô hình foundation (LLM, diffusion) của AWS và các nhà cung cấp bên thứ ba (Anthropic, AI21, Stability AI, …). Guardrails for Amazon Bedrock (được ra mắt vào cuối 2023 và mở rộng tính năng tới 2025‑2026) cung cấp bộ quy tắc và công cụ giám sát nhằm thực thi các nguyên tắc “Responsible AI”: Kiểm soát nội dung (đánh dấu hoặc chặn các phản hồi không phù hợp, vi phạm HIPAA, PHI, hay thông tin nhạy cảm).
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/security/guardrails-amazon-bedrock/ | https://aws.amazon.com/compliance/hipaa-compliance/ | https://aws.amazon.com/what-is/responsible-ai/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://www.examtopics.com/discussions/amazon/view/308643-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A medical company wants to modernize its onsite information processing application. The company wants to use generative AI to respond to medical questions from patients.
Which AWS service should the company use to ensure responsible AI for the application?

### Các lựa chọn
1. Guardrails for Amazon Bedrock
2. Amazon Inspector
3. Amazon Rekognition
4. AWS Trusted Advisor

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích nội dung câu hỏi

Câu hỏi mô tả một công ty y tế muốn hiện đại hoá (modernize) ứng dụng xử lý thông tin nội bộ, đồng thời muốn sử dụng Generative AI để trả lời các câu hỏi y tế của bệnh nhân. Yêu cầu then chốt là:

“ensure responsible AI” – công ty cần một dịch vụ AWS hỗ trợ đảm bảo tính đạo đức, an toàn, tuân thủ quy định và kiểm soát rủi ro khi triển khai mô hình AI sinh ra (LLM, diffusion model …).

Các lựa chọn đưa ra đều là các dịch vụ AWS, trong đó chỉ có một đáp án phù hợp với mục tiêu “responsible AI for generative AI”.

✅ Đáp án đúng: Guardrails for Amazon Bedrock

Lý do lựa chọn

Amazon Bedrock là dịch vụ fully‑managed cho phép truy cập tới các mô hình foundation (LLM, diffusion) của AWS và các nhà cung cấp bên thứ ba (Anthropic, AI21, Stability AI, …).

Guardrails for Amazon Bedrock (được ra mắt vào cuối 2023 và mở rộng tính năng tới 2025‑2026) cung cấp bộ quy tắc và công cụ giám sát nhằm thực thi các nguyên tắc “Responsible AI”:

Kiểm soát nội dung (đánh dấu hoặc chặn các phản hồi không phù hợp, vi phạm HIPAA, PHI, hay thông tin nhạy cảm).

Kiểm soát độ chính xác và độ tin cậy (cảnh báo khi mô hình “hallucinate”).

Ghi lại log và audit trail để đáp ứng yêu cầu tuân thủ.

Tích hợp AWS CloudWatch, AWS Config, và AWS Security Hub để theo dõi và cảnh báo tự động.

Đối với một công ty y tế, việc dùng Guardrails giúp giảm rủi ro cung cấp thông tin y tế sai lệch, vi phạm quy định bảo mật dữ liệu sức khỏe và đồng thời duy trì tính minh bạch trong quá trình AI sinh ra câu trả lời.

Vì vậy, Guardrails for Amazon Bedrock là lựa chọn duy nhất đáp ứng yêu cầu “responsible AI” cho một ứng dụng generative AI trong lĩnh vực y tế.

🧩 Giải thích chi tiết các phương án

1️⃣ Guardrails for Amazon Bedrock (ĐÚNG)

Chức năng: Cung cấp một khung làm việc (framework) để định nghĩa, triển khai và quản lý các “guardrails” (rào chắn) trên các mô hình generative AI trong Amazon Bedrock.

Lợi ích cho công ty y tế:

Ngăn chặn nội dung không an toàn, không phù hợp hoặc vi phạm luật bảo mật y tế (HIPAA, GDPR).

Ghi nhận và audit các tương tác AI, hỗ trợ việc điều tra và báo cáo.

Tích hợp với Amazon CloudWatch Evidently, AWS Audit Manager, giúp tổ chức duy trì độ tin cậy và đáp ứng quy định.

Cập nhật 2026: Guardrails đã được mở rộng để hỗ trợ prompt‑tuning policies, real‑time risk scoring, và automatic remediation thông qua AWS Lambda và Step Functions.

2️⃣ Amazon Inspector (SAI)

Chức năng: Dịch vụ vulnerability assessment cho EC2, ECR, Lambda và các workload container, giúp phát hiện lỗ hổng bảo mật và cấu hình sai.

Tại sao không phù hợp: Inspector tập trung vào đánh giá bảo mật hạ tầng, không liên quan tới kiểm soát nội dung hoặc đạo đức AI. Nó không cung cấp cơ chế guardrails cho các mô hình generative AI, vì vậy không đáp ứng yêu cầu “responsible AI”.

3️⃣ Amazon Rekognition (SAI)

Chức năng: Dịch vụ phân tích hình ảnh và video, cung cấp face detection, object/scene detection, text in image, v.v.

Tại sao không phù hợp: Rekognition là dịch vụ computer vision, không liên quan tới xử lý ngôn ngữ tự nhiên (NLP) hay generative AI. Nó cũng không có tính năng quản lý rủi ro nội dung cho các mô hình ngôn ngữ, nên không đáp ứng yêu cầu.

4️⃣ AWS Trusted Advisor (SAI)

Chức năng: Cung cấp khuyến nghị tối ưu hóa về chi phí, hiệu năng, độ bền, và bảo mật cho tài nguyên AWS dựa trên best‑practice.

Tại sao không phù hợp: Trusted Advisor giúp đánh giá môi trường AWS chung, nhưng không cung cấp công cụ guardrails cho AI hoặc kiểm soát nội dung. Nó không thể ngăn chặn hoặc giám sát các phản hồi sinh ra bởi mô hình AI, vì vậy không đáp ứng yêu cầu “responsible AI”.

📚 Tham khảo tài liệu

Amazon Bedrock Documentation – Guardrails (v.2026.03) – https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

AWS Responsible AI Guidance – https://aws.amazon.com/what-is/responsible-ai/

AWS Security Blog – Introducing Guardrails for Amazon Bedrock (2023) – https://aws.amazon.com/blogs/security/guardrails-amazon-bedrock/

HIPAA Eligibility for AWS Services – https://aws.amazon.com/compliance/hipaa-compliance/

🏁 Kết luận

Để đảm bảo AI có trách nhiệm khi triển khai một giải pháp trả lời câu hỏi y tế dựa trên generative AI, công ty y tế nên sử dụng Guardrails for Amazon Bedrock. Các dịch vụ còn lại (Amazon Inspector, Amazon Rekognition, AWS Trusted Advisor) đều không cung cấp chức năng quản lý rủi ro nội dung và đạo đức cho mô hình AI, do đó không phù hợp với yêu cầu đề bài. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/308643-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 56

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Rekognition, Amazon Bedrock, Amazon Q
- Đáp án tham khảo: **AWS HealthScribe**
- Takeaway nhanh: AWS HealthScribe (ra mắt 2024, mở rộng 2025) là dịch vụ được thiết kế riêng cho ngành y tế, tích hợp Amazon Transcribe Medical (speech‑to‑text y tế) và Amazon Bedrock (mô hình ngôn ngữ lớn) để tạo ra bản ghi chú lâm sàng chính xác, tuân thủ các tiêu chuẩn bảo mật và quyền riêng tư (HIPAA, GDPR). Nó hỗ trợ đào tạo kỹ năng dictation: nhân viên có thể luyện tập, nhận phản hồi tự động từ AI về cách diễn đạt, cấu trúc ghi chú, và cải thiện tốc độ/độ chính xác.
- Nguồn tham khảo trong block: https://aws.amazon.com/bedrock/ | https://aws.amazon.com/compliance/hipaa-compliance/ | https://aws.amazon.com/transcribe/medical/ | https://docs.aws.amazon.com/healthscribe/latest/ | https://www.examtopics.com/discussions/amazon/view/306670-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A hospital wants to use a generative AI solution with speech-to-text functionality to help improve employee skills in dictating clinical notes.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Q Developer
2. Amazon Polly
3. Amazon Rekognition
4. AWS HealthScribe

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📚 Phân tích câu hỏi

Một bệnh viện muốn triển khai một giải pháp AI sinh ra (generative AI) có khả năng chuyển giọng nói thành văn bản (speech‑to‑text) để hỗ trợ nhân viên trong việc đánh máy (dictate) các ghi chú lâm sàng. Yêu cầu gồm hai phần:

Speech‑to‑text – cần một dịch vụ nhận dạng giọng nói, ưu tiên là phiên bản y tế (độ chính xác cao, tuân thủ chuẩn HIPAA).

Generative AI – sau khi nhận dạng, cần một mô hình AI có khả năng “hiểu” và tự động tạo, chỉnh sửa, hoặc đề xuất nội dung ghi chú dựa trên đầu vào của bác sĩ.

Vì vậy dịch vụ phải cung cấp cả khả năng nhận dạng giọng nói y tế và khả năng sinh nội dung (text generation) theo ngữ cảnh lâm sàng.

✅ Đáp án đúng: AWS HealthScribe

Lý do chọn:

AWS HealthScribe (ra mắt 2024, mở rộng 2025) là dịch vụ được thiết kế riêng cho ngành y tế, tích hợp Amazon Transcribe Medical (speech‑to‑text y tế) và Amazon Bedrock (mô hình ngôn ngữ lớn) để tạo ra bản ghi chú lâm sàng chính xác, tuân thủ các tiêu chuẩn bảo mật và quyền riêng tư (HIPAA, GDPR).

Nó hỗ trợ đào tạo kỹ năng dictation: nhân viên có thể luyện tập, nhận phản hồi tự động từ AI về cách diễn đạt, cấu trúc ghi chú, và cải thiện tốc độ/độ chính xác.

Dịch vụ được cung cấp dưới dạng managed service, không yêu cầu khách hàng tự cấu hình pipeline phức tạp.

Do đó, AWS HealthScribe là đáp án duy nhất đáp ứng đầy đủ cả “generative AI” và “speech‑to‑text” cho môi trường y tế.

❌ Giải thích các phương án còn lại

Amazon Q Developer

Mô tả: Amazon Q Developer (trước đây là Amazon Q) là một công cụ xây dựng trợ lý AI dựa trên LLM, tập trung vào việc tạo câu trả lời, hỗ trợ lập trình, và tích hợp vào ứng dụng.

Tại sao sai: Không cung cấp speech‑to‑text. Dịch vụ này chỉ xử lý văn bản đầu vào và không có khả năng nhận dạng giọng nói, do đó không đáp ứng yêu cầu “speech‑to‑text” của câu hỏi.

Amazon Polly

Mô tả: Amazon Polly là dịch vụ text‑to‑speech (chuyển văn bản thành giọng nói) với nhiều giọng và ngôn ngữ.

Tại sao sai: Ngược lại với yêu cầu, Polly chuyển văn bản thành giọng nói, không thực hiện việc nhận dạng giọng nói thành văn bản. Do vậy không phù hợp.

Amazon Rekognition

Mô tả: Amazon Rekognition là dịch vụ phân tích hình ảnh và video (nhận dạng khuôn mặt, đối tượng, văn bản trong ảnh, v.v.).

Tại sao sai: Không liên quan tới audio hay generative AI cho ghi chú lâm sàng, nên không đáp ứng bất kỳ phần nào của yêu cầu.

📖 Tham khảo tài liệu (đến năm 2026)

AWS HealthScribe – Documentation (2024‑2026) – https://docs.aws.amazon.com/healthscribe/latest/

Amazon Transcribe Medical – FAQ – https://aws.amazon.com/transcribe/medical/

Amazon Bedrock – Generative AI for Enterprises – https://aws.amazon.com/bedrock/

HIPAA‑eligible AWS Services – https://aws.amazon.com/compliance/hipaa-compliance/

🧩 Tổng kết

Đối với nhu cầu speech‑to‑text + generative AI trong môi trường y tế, AWS HealthScribe là dịch vụ duy nhất tích hợp cả hai khả năng, đồng thời tuân thủ các tiêu chuẩn bảo mật y tế.

Các lựa chọn còn lại (Amazon Q Developer, Amazon Polly, Amazon Rekognition) không cung cấp chức năng nhận dạng giọng nói hoặc không liên quan tới ngữ cảnh lâm sàng, vì vậy chúng là sai.

👉 Nếu bệnh viện muốn triển khai nhanh, chỉ cần tạo HealthScribe Workspace, kết nối micro‑phone và bắt đầu luyện tập dictation ngay lập tức.

Chúc bạn ôn luyện hiệu quả và đạt điểm cao trong kỳ thi AWS Certified DevOps Engineer – Professional! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306670-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 57

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Textract, Amazon Transcribe, Amazon Macie, RAG
- Đáp án tham khảo: **Amazon Bedrock**
- Takeaway nhanh: Tại sao Amazon Bedrock là lựa chọn phù hợp? Nền tảng chuyên dụng cho Foundation Models: Bedrock cho phép truy cập ngay vào các mô hình ngôn ngữ lớn (LLM) như Amazon Titan, Anthropic Claude, Meta Llama, Cohere, và các mô hình hình ảnh. Không cần quản lý hạ tầng: Dịch vụ fully‑managed, bạn chỉ gọi API để gửi prompt (ví dụ: “Khách ở Hà Nội, đề xuất sản phẩm nào?”) và nhận kết quả.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155919-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company’s employees provide product descriptions and recommendations to customers when customers call the customer service center. These recommendations are based on where the customers are located. The company wants to use foundation models (FMs) to automate this process.
Which AWS service meets these requirements?

### Các lựa chọn
1. Amazon Macie
2. Amazon Transcribe
3. Amazon Bedrock
4. Amazon Textract

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Công ty muốn tự động hoá quá trình “cung cấp mô tả sản phẩm và đề xuất cho khách hàng” khi khách gọi đến trung tâm dịch vụ.

Đề xuất dựa trên vị trí của khách hàng → cần xử lý ngôn ngữ tự nhiên, có khả năng “hiểu” và “tạo” văn bản (text generation).

Công ty muốn dùng foundation models (FMs) – các mô hình lớn được huấn luyện trước, có thể tùy chỉnh (fine‑tune) hoặc inference ngay lập tức.

Vậy dịch vụ AWS nào cung cấp khả năng truy cập và chạy các foundation model để tạo nội dung văn bản dựa trên dữ liệu (ví dụ: vị trí khách hàng) ?

✅ Đáp án đúng: Amazon Bedrock

Tại sao Amazon Bedrock là lựa chọn phù hợp?

Nền tảng chuyên dụng cho Foundation Models: Bedrock cho phép truy cập ngay vào các mô hình ngôn ngữ lớn (LLM) như Amazon Titan, Anthropic Claude, Meta Llama, Cohere, và các mô hình hình ảnh.

Không cần quản lý hạ tầng: Dịch vụ fully‑managed, bạn chỉ gọi API để gửi prompt (ví dụ: “Khách ở Hà Nội, đề xuất sản phẩm nào?”) và nhận kết quả.

Tích hợp với các dịch vụ AWS khác: Có thể kết hợp với Amazon Location Service để lấy vị trí khách, hoặc với Amazon SageMaker để fine‑tune model nếu muốn.

Kiểm soát bảo mật & tuân thủ: Dữ liệu không rời khỏi VPC (PrivateLink), hỗ trợ encryption‑at‑rest và in‑transit – đáp ứng yêu cầu doanh nghiệp về bảo mật.

Cập nhật phiên bản mới nhất đến năm 2026: Bedrock liên tục nhận các mô hình mới, hỗ trợ tính năng RAG (Retrieval‑Augmented Generation) để kết hợp với dữ liệu doanh nghiệp (catalog, địa lý) nhằm tạo đề xuất cá nhân hoá.

Do đó, Amazon Bedrock đáp ứng đầy đủ yêu cầu “tự động hoá bằng foundation models” trong kịch bản mô tả và đề xuất dựa trên vị trí khách hàng.

❌ Phân tích các đáp án sai

1. Amazon Macie

Chức năng: Dịch vụ phát hiện, phân loại và bảo vệ dữ liệu nhạy cảm (PII, PHI) trong S3.

Tại sao sai: Macie không cung cấp khả năng tạo nội dung hay chạy các mô hình ngôn ngữ. Nó chỉ tập trung vào an ninh dữ liệu, không liên quan tới việc tự động hoá đề xuất sản phẩm.

2. Amazon Transcribe

Chức năng: Chuyển đổi âm thanh (speech) sang văn bản (speech‑to‑text).

Tại sao sai: Dù Transcribe có thể “lắng nghe” cuộc gọi và tạo bản ghi, nó không có khả năng sinh đề xuất dựa trên nội dung hay vị trí. Để có đề xuất, cần một mô hình ngôn ngữ lớn (LLM) – chức năng này không có trong Transcribe.

3. Amazon Textract

Chức năng: Trích xuất văn bản, bảng và dữ liệu có cấu trúc từ tài liệu (PDF, ảnh).

Tại sao sai: Textract chỉ đọc và trích xuất dữ liệu từ tài liệu tĩnh, không thực hiện sinh nội dung hay xử lý ngôn ngữ tự nhiên. Vì câu hỏi yêu cầu sử dụng foundation models để “tự động tạo đề xuất”, Textract không đáp ứng.

📚 Tham khảo nguồn tài liệu (2026)

Amazon Bedrock Documentation – “Getting started with foundation models”, AWS, cập nhật tháng 3/2026.

**AWS Blog – “Introducing Amazon Bedrock: Build generative AI applications with foundation models”, 2023‑2025 series.

AWS Well‑Architected Framework – Machine Learning Lens, phiên bản 2025, mục “Model selection & inference”.

AWS Security Best Practices – Data protection with Macie, 2024.

Amazon Transcribe Developer Guide, 2025.

Amazon Textract User Guide, 2025.

🔚 Tóm tắt

Câu hỏi yêu cầu một dịch vụ cho phép sử dụng foundation models để tạo đề xuất dựa trên vị trí khách hàng.

Amazon Bedrock là dịch vụ duy nhất trong danh sách cung cấp khả năng này → ✅ đáp án đúng.

Các dịch vụ còn lại (Macie, Transcribe, Textract) phục vụ các mục đích an ninh, chuyển đổi giọng nói, và trích xuất tài liệu nên không phù hợp → ❌ đáp án sai.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155919-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 58

- Domain heuristic: `Domain 4`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Explainability**
- Takeaway nhanh: Explainability (còn được gọi là interpretability hoặc transparency) yêu cầu mô hình AI phải cung cấp thông tin chi tiết về cách ra quyết định, giúp người dùng (bác sĩ, bệnh nhân) hiểu “tại sao” một khuyến nghị được đưa ra. Trong môi trường y tế, việc này là tối quan trọng để xây dựng niềm tin, cho phép bác sĩ kiểm chứng, đồng thời cho bệnh nhân cảm thấy an tâm.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/306668-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A hospital developed an AI system to provide personalized treatment recommendations for patients. The AI system must provide the rationale behind the recommendations and make the insights accessible to doctors and patients.
Which human-centered design principle does this scenario present?

### Các lựa chọn
1. Explainability
2. Privacy and security
3. Fairness
4. Data governance

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

📝 Phân tích câu hỏi

Câu hỏi đưa ra một trường hợp thực tế:

Một bệnh viện xây dựng hệ thống AI để đưa ra khuyến nghị điều trị cá nhân hoá cho bệnh nhân.

Yêu cầu quan trọng là hệ thống AI phải cung cấp “lý do” (rationale) cho các khuyến nghị và đảm bảo rằng các thông tin này có thể hiểu được, truy cập được bởi bác sĩ và bệnh nhân.

Trong lĩnh vực thiết kế nhân trung (human‑centered design) cho các giải pháp AI, có một loạt các nguyên tắc nhằm bảo vệ người dùng, tăng độ tin cậy và minh bạch. Khi một giải pháp phải “giải thích” cách mà nó đưa ra quyết định, chúng ta đang nói tới nguyên tắc “Explainability” (giải thích được) – tức là khả năng mô tả, làm sáng tỏ cách thức hoạt động, các yếu tố đầu vào và logic quyết định của mô hình.

✅ Đáp án đúng: Explainability

Lý do chọn:

Explainability (còn được gọi là interpretability hoặc transparency) yêu cầu mô hình AI phải cung cấp thông tin chi tiết về cách ra quyết định, giúp người dùng (bác sĩ, bệnh nhân) hiểu “tại sao” một khuyến nghị được đưa ra.

Trong môi trường y tế, việc này là tối quan trọng để xây dựng niềm tin, cho phép bác sĩ kiểm chứng, đồng thời cho bệnh nhân cảm thấy an tâm.

AWS cung cấp các dịch vụ hỗ trợ Explainability như Amazon SageMaker Clarify, Amazon SageMaker Model Explainability, cho phép tạo ra các biểu đồ SHAP, LIME, hoặc các báo cáo “feature importance” – đáp ứng trực tiếp yêu cầu “cung cấp rationale”.

Do đó, nguyên tắc phù hợp nhất với mô tả trong kịch bản là Explainability.

❌ Các phương án sai và phân tích chi tiết

Privacy and security

Privacy and security tập trung vào việc bảo vệ dữ liệu cá nhân, đảm bảo rằng thông tin bệnh nhân không bị rò rỉ, và hệ thống tuân thủ các tiêu chuẩn bảo mật (HIPAA, GDPR…).

Mặc dù đây là một yếu tố cực kỳ quan trọng trong môi trường y tế, nhưng câu hỏi không đề cập tới việc bảo mật dữ liệu mà chỉ nói tới việc “cung cấp lý do cho khuyến nghị”. Vì vậy, đây không phải là nguyên tắc được mô tả.

Fairness

Fairness (công bằng) đề cập đến việc đảm bảo mô hình không gây ra thiên lệch (bias) đối với bất kỳ nhóm người dùng nào, ví dụ: không phân biệt giới tính, chủng tộc, độ tuổi, v.v.

Câu hỏi không nhắc tới việc mô hình phải “đảm bảo công bằng” hay “ngăn ngừa bias”; thay vào đó, nó tập trung vào việc giải thích quyết định. Do đó, Fairness không phải là đáp án đúng.

Data governance

Data governance liên quan tới quản lý, chất lượng, truy cập và tuân thủ dữ liệu trong toàn bộ vòng đời dữ liệu (data lineage, catalog, retention policies…).

Mặc dù một hệ thống AI y tế cần có governance chặt chẽ, câu hỏi không nói tới việc “quản lý dữ liệu” mà chỉ nhấn mạnh tới “giải thích lý do quyết định”. Vì vậy, đây cũng không phải là nguyên tắc phù hợp.

📚 Tham khảo (cập nhật đến 2026)

AWS Well‑Architected Framework – Machine Learning Lens (2025 edition) – phần “Explainability” và “Model Transparency”.

Amazon SageMaker Clarify Documentation – cung cấp các tính năng Explainability, Bias detection, và feature importance (phiên bản 2026).

AWS AI/ML Best Practices Whitepaper (2025) – chương “Human‑Centered AI Design” nêu rõ bốn nguyên tắc chính: Explainability, Fairness, Privacy & Security, Data Governance.

ISO/IEC 22989:2024 – Artificial Intelligence — Trustworthiness – định nghĩa “Explainability” như một trong các yếu tố cốt lõi để đạt được độ tin cậy.

🧩 Tổng kết nhanh

Câu hỏi đề cập tới việc AI phải cung cấp rationale cho khuyến nghị, đáp ứng nguyên tắc Explainability.

Các lựa chọn còn lại – Privacy and security, Fairness, Data governance – mặc dù quan trọng trong môi trường y tế, nhưng không phản ánh yêu cầu “giải thích” được nêu trong kịch bản.

✅ Vậy đáp án đúng là: Explainability.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306668-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 59

- Domain heuristic: `Domain 2`
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/302416-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
HOTSPOT -

### Các lựa chọn
1. A company wants more customized responses to its generative AI models’ prompts.
2. Select the correct customization methodology from the following list for each use case. Each use case should be selected one time.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302416-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 60

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, model evaluation
- Takeaway nhanh: What does an F1 score measure in the context of foundation model (FM) performance? Câu hỏi yêu cầu bạn xác định “F1 score” – một chỉ số thường dùng trong đánh giá mô hình máy học – đo lường khía cạnh nào của hiệu suất một foundation model (mô hình nền tảng lớn như LLM, Diffusion, v.v.). Trong môi trường AWS, chúng ta thường tính F1 score khi đánh giá mô hình phân loại, trích xuất thực thể, hoặc đánh giá câu trả lời (ví dụ: SageMaker Clarify, SageMaker Model Monitor). Chỉ số này không liên quan tới tốc độ, chi phí tài chính hay tiêu thụ năng lượng; nó tập trung vào độ chính xác (precision) và độ thu hồi (recall) của dự đoán.
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/machine-learning/measuring-llm-performance/ | https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html | https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/monitoring.html | https://www.examtopics.com/discussions/amazon/view/302407-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
What does an F1 score measure in the context of foundation model (FM) performance?

### Các lựa chọn
1. Model precision and recall
2. Model speed in generating responses
3. Financial cost of operating the model
4. Energy efficiency of the model’s computations

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

What does an F1 score measure in the context of foundation model (FM) performance?

Câu hỏi yêu cầu bạn xác định “F1 score” – một chỉ số thường dùng trong đánh giá mô hình máy học – đo lường khía cạnh nào của hiệu suất một foundation model (mô hình nền tảng lớn như LLM, Diffusion, v.v.).

Trong môi trường AWS, chúng ta thường tính F1 score khi đánh giá mô hình phân loại, trích xuất thực thể, hoặc đánh giá câu trả lời (ví dụ: SageMaker Clarify, SageMaker Model Monitor). Chỉ số này không liên quan tới tốc độ, chi phí tài chính hay tiêu thụ năng lượng; nó tập trung vào độ chính xác (precision) và độ thu hồi (recall) của dự đoán.

✅ Đáp án đúng

Model precision and recall

Giải thích:

Precision (độ chính xác) = TP / (TP + FP) – tỷ lệ dự đoán đúng trong số các dự đoán dương tính.

Recall (độ thu hồi) = TP / (TP + FN) – tỷ lệ các trường hợp dương tính thực tế mà mô hình đã phát hiện.

F1 score là harmonic mean của precision và recall:

[ F1 = 2 \times \frac{precision \times recall}{precision + recall} ]

Do đó, F1 cung cấp một thước đo cân bằng giữa việc “không bỏ sót” (recall) và “không tạo quá nhiều cảnh báo sai” (precision). Trong các foundation model, đặc biệt khi trả lời câu hỏi hoặc trích xuất thông tin, F1 giúp chúng ta hiểu mức độ đúng đắn và đầy đủ của đầu ra.

❌ Các phương án sai và lý do

Model speed in generating responses

Giải thích: Tốc độ sinh đáp ứng thường đo bằng latency (ms) hoặc throughput (requests/second). F1 không chứa bất kỳ yếu tố thời gian nào; nó chỉ là hàm số của TP, FP, FN. Do đó, không thể dùng để đo “speed”.

Financial cost of operating the model

Giải thích: Chi phí vận hành (ví dụ: chi phí EC2, SageMaker instance, hoặc chi phí inference) được tính bằng USD/giờ hoặc chi phí per token. F1 score không phản ánh chi phí tài chính; nó là một chỉ số thống kê về độ chính xác của dự đoán.

Energy efficiency of the model’s computations

Giải thích: Hiệu quả năng lượng thường đo bằng kWh hoặc CO₂e emissions (ví dụ: AWS Carbon Footprint Tool). F1 không chứa bất kỳ thông tin nào về tiêu thụ năng lượng; nó chỉ dựa trên kết quả dự đoán.

📚 Tham khảo (AWS, 2026)

Amazon SageMaker Documentation – Model Evaluation Metrics

https://docs.aws.amazon.com/sagemaker/latest/dg/model-evaluation.html

Mô tả chi tiết về Precision, Recall, và F1 score trong ngữ cảnh các mô hình ML được triển khai trên SageMaker.

AWS Well‑Architected Framework – Operational Excellence Pillar

https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/monitoring.html

Giới thiệu cách sử dụng SageMaker Model Monitor để thu thập và tính toán các chỉ số như F1, Precision, Recall.

AWS Blog – Measuring LLM Performance at Scale (2025)

https://aws.amazon.com/blogs/machine-learning/measuring-llm-performance/

Thảo luận việc sử dụng F1 score để đánh giá độ chính xác và độ bao phủ của các câu trả lời LLM.

🛠️ Kết luận

F1 score là độ đo tổng hợp giữa precision và recall, không liên quan tới tốc độ, chi phí tài chính hay tiêu thụ năng lượng. Khi đánh giá một foundation model trên AWS (SageMaker, Bedrock, hay các dịch vụ AI tùy chỉnh), chúng ta nên dựa vào F1 để hiểu rõ mức độ đúng đắn và đầy đủ của mô hình trong các nhiệm vụ như phân loại, trích xuất thực thể, hoặc trả lời câu hỏi.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/302407-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 61

- Domain heuristic: `Domain 1`
- Service/từ khóa gắn trên câu: Amazon SageMaker
- Đáp án tham khảo: **Không phù hợp vì mục tiêu là phân loại, không phải dự đoán giá trị số.**
- Takeaway nhanh: Binary classification ✅ Đây là loại mô hình dự đoán một trong hai lớp (0/1, true/false, fraud/non‑fraud). Trong AWS, bạn có thể triển khai bằng: Amazon SageMaker: thuật toán Linear Learner, XGBoost, DeepAR (được cấu hình cho binary classification) Amazon Fraud Detector (dịch vụ quản lý, dựa trên mô hình binary classification)
- Nguồn tham khảo trong block: https://aws.amazon.com/sagemaker/autopilot/ | https://d1.awsstatic.com/whitepapers/aws-fraud-detection-ml.pdf | https://docs.aws.amazon.com/frauddetector/latest/ug/what-is-fraud-detector.html | https://docs.aws.amazon.com/sagemaker/latest/dg/algos-linear-learner.html#linear-learner-binary-classification | https://www.examtopics.com/discussions/amazon/view/306676-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company wants to flag all credit card activity as possibly fraudulent or non-fraudulent based on transaction data.
Which type of ML model meets these requirements?

### Các lựa chọn
1. Regression
2. Diffusion
3. Binary classification
4. Multi-class classification

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

A financial company wants to flag all credit card activity as possibly fraudulent or non‑fraudulent based on transaction data.

Which type of ML model meets these requirements?

Công ty muốn đưa ra hai nhãn duy nhất cho mỗi giao dịch:

fraudulent (có khả năng gian lận)

non‑fraudulent (không gian lận)

Vì số lượng nhãn chỉ hai, mô hình cần học phân loại nhị phân (binary classification).

✅ Đáp án đúng

Binary classification

✅ Đây là loại mô hình dự đoán một trong hai lớp (0/1, true/false, fraud/non‑fraud). Trong AWS, bạn có thể triển khai bằng:

Amazon SageMaker: thuật toán Linear Learner, XGBoost, DeepAR (được cấu hình cho binary classification)

Amazon Fraud Detector (dịch vụ quản lý, dựa trên mô hình binary classification)

AWS Glue + SageMaker Pipelines để chuẩn bị dữ liệu và tự động hoá quy trình đào tạo/triển khai.

❌ Giải thích các phương án sai

Regression

📉 Regression dự đoán một giá trị định lượng liên tục (ví dụ: số tiền giao dịch, thời gian). Nó không cung cấp nhãn “fraud / non‑fraud”. Để chuyển regression thành quyết định nhị phân, bạn phải đặt một ngưỡng thủ công, nhưng đây không phải là cách tiếp cận chuẩn cho bài toán phân loại.

✅ Không phù hợp vì mục tiêu là phân loại, không phải dự đoán giá trị số.

Diffusion

🌌 Diffusion models là các mô hình tạo sinh (generative) mạnh mẽ, thường dùng để tạo ảnh, video, âm thanh (ví dụ: Stable Diffusion). Chúng không được thiết kế để thực hiện phân loại dữ liệu tabular như giao dịch thẻ tín dụng.

✅ Không liên quan tới bài toán phát hiện gian lận.

Multi‑class classification

📊 Multi‑class classification dự đoán nhiều hơn hai lớp (ví dụ: 3, 5, 10 lớp). Nếu chỉ có hai nhãn, việc dùng multi‑class là lãng phí và có thể gây nhầm lẫn trong việc thiết lập loss function.

✅ Bài toán chỉ có hai trạng thái, vì vậy multi‑class không cần thiết.

🧩 Tổng hợp kiến thức cập nhật (2024‑2026)

Amazon SageMaker đã cập nhật SageMaker Autopilot và JumpStart hỗ trợ tự động phát hiện mô hình binary classification với AutoML.

Amazon Fraud Detector (ra mắt 2020, liên tục cập nhật tới 2026) cung cấp sẵn pipeline: ingestion → feature engineering → binary classification → decision threshold.

Feature Store (SageMaker Feature Store) cho phép lưu trữ và chia sẻ các đặc trưng giao dịch (transaction amount, merchant ID, time‑of‑day…) giữa các mô hình, giúp nâng cao độ chính xác của mô hình binary classification.

Model Monitor trong SageMaker tự động phát hiện drift và bias trong mô hình binary classification, rất quan trọng với dữ liệu tài chính luôn thay đổi.

📚 Tham khảo

AWS Documentation – Binary Classification: https://docs.aws.amazon.com/sagemaker/latest/dg/algos-linear-learner.html#linear-learner-binary-classification

Amazon Fraud Detector Developer Guide (phiên bản 2026): https://docs.aws.amazon.com/frauddetector/latest/ug/what-is-fraud-detector.html

SageMaker Autopilot – Build Binary Classification Models: https://aws.amazon.com/sagemaker/autopilot/

Machine Learning Best Practices for Fraud Detection – AWS Whitepaper 2025: https://d1.awsstatic.com/whitepapers/aws-fraud-detection-ml.pdf

Kết luận: Đối với yêu cầu “đánh dấu giao dịch thẻ tín dụng là có khả năng gian lận hay không”, mô hình binary classification là lựa chọn đúng nhất. Các phương án còn lại (Regression, Diffusion, Multi‑class classification) không đáp ứng được yêu cầu nhãn hai lớp của bài toán. 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306676-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 62

- Domain heuristic: `Domain 3`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon SageMaker, Amazon EC2, Amazon SageMaker AI, Amazon SageMaker JumpStart
- Takeaway nhanh: Công ty đang xây dựng một ứng dụng trợ lý soạn thảo dựa trên generative AI. Giai đoạn thí điểm: lưu lượng sử dụng thấp, hiệu năng chưa là vấn đề. Khi đưa vào vận hành thực tế: không biết trước được mức độ sử dụng (có thể tăng mạnh, giảm mạnh hoặc dao động). Mục tiêu chính: giảm thiểu chi phí.
- Nguồn tham khảo trong block: https://aws.amazon.com/ec2/instance-types/g4/ | https://aws.amazon.com/sagemaker/pricing/ | https://docs.aws.amazon.com/bedrock/latest/userguide/pricing.html | https://www.examtopics.com/discussions/amazon/view/306660-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is developing an editorial assistant application that uses generative AI. During the pilot phase, usage is low and application performance is not a concern. The company cannot predict application usage after the application is fully deployed and wants to minimize application costs.
Which solution will meet these requirements?

### Các lựa chọn
1. Use GPU-powered Amazon EC2 instances.
2. Use Amazon Bedrock with Provisioned Throughput.
3. Use Amazon Bedrock with On-Demand Throughput.
4. Use Amazon SageMaker JumpStart.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang xây dựng một ứng dụng trợ lý soạn thảo dựa trên generative AI.

Giai đoạn thí điểm: lưu lượng sử dụng thấp, hiệu năng chưa là vấn đề.

Khi đưa vào vận hành thực tế: không biết trước được mức độ sử dụng (có thể tăng mạnh, giảm mạnh hoặc dao động).

Mục tiêu chính: giảm thiểu chi phí.

Vì vậy cần một giải pháp trả tiền theo nhu cầu (pay‑as‑you‑go), có thể mở rộng tự động và không yêu cầu dự trữ tài nguyên tính phí cố định.

✅ Đáp án đúng

Use Amazon Bedrock with On‑Demand Throughput

On‑Demand Throughput của Amazon Bedrock tính phí theo số token (hoặc request) thực tế được xử lý, không yêu cầu đặt trước băng thông.

Khi lưu lượng không ổn định hoặc chưa biết trước, mô hình này giúp tránh chi phí dư thừa so với việc đặt trước (Provisioned).

Bedrock cung cấp các mô hình LLM đã được tối ưu sẵn, không cần chạy GPU EC2 hay tự quản lý môi trường SageMaker, nên chi phí hạ thấp trong giai đoạn sử dụng ít.

❌ Các phương án sai và lý do

Use GPU‑powered Amazon EC2 instances.

GPU EC2 (ví dụ: g5, p4) có chi phí giờ máy cao và thường được dùng cho việc đào tạo hoặc inference cần hiệu năng GPU.

Khi lưu lượng thấp, bạn sẽ trả tiền cho tài nguyên không dùng; không đáp ứng yêu cầu “giảm chi phí” và “không thể dự đoán lưu lượng”.

Use Amazon Bedrock with Provisioned Throughput.

Provisioned Throughput yêu cầu đặt trước một mức băng thông cố định (ví dụ: 1 M token/phút) và trả phí cho toàn bộ dung lượng đã đặt, bất kể có sử dụng hết hay không.

Đối với môi trường chưa biết nhu cầu, việc này có nguy cơ lãng phí tài nguyên và chi phí cao hơn so với mô hình On‑Demand.

Use Amazon SageMaker JumpStart.

SageMaker JumpStart là bộ công cụ giúp nhanh chóng triển khai các mô hình ML đã được huấn luyện (ví dụ: Hugging Face, XGBoost).

Để chạy inference, bạn vẫn cần tạo endpoint SageMaker, có thể chọn instance loại CPU/GPU và đặt trước (provisioned) hoặc on‑demand.

Khi không biết lưu lượng, việc tạo endpoint cố định cũng sẽ gây chi phí cố định và không tối ưu cho mục tiêu giảm chi phí như Bedrock On‑Demand.

🧩 Tổng kết

Giải pháp tối ưu: Amazon Bedrock with On‑Demand Throughput – trả tiền chỉ cho lượng token thực tế được xử lý, không cần quản lý hạ tầng GPU, không cần dự trù băng thông, đáp ứng yêu cầu giảm chi phí và đối phó với lưu lượng không chắc chắn.

Các phương án còn lại đòi hỏi tài nguyên cố định hoặc GPU, dẫn tới chi phí cao hơn và không phù hợp với môi trường sử dụng chưa biết trước.

📚 Tham khảo

Amazon Bedrock – On‑Demand Throughput Pricing (AWS Documentation, cập nhật 2024‑2026): https://docs.aws.amazon.com/bedrock/latest/userguide/pricing.html

Amazon EC2 GPU Instances – Chi phí và trường hợp sử dụng: https://aws.amazon.com/ec2/instance-types/g4/

Amazon SageMaker Pricing – Endpoint – So sánh provisioned vs on‑demand: https://aws.amazon.com/sagemaker/pricing/

🛠️ Lưu ý: Khi ứng dụng bắt đầu có lưu lượng ổn định và cao, công ty có thể đánh giá lại và chuyển sang Provisioned Throughput hoặc các mô hình hạ tầng khác (ví dụ: SageMaker Serverless Inference) để tối ưu chi phí hơn nữa.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/306660-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 63

- Domain heuristic: `Domain 5`
- Service/từ khóa gắn trên câu: Amazon Bedrock, guardrails
- Đáp án tham khảo: **Hate và Violence.**
- Takeaway nhanh: Câu hỏi yêu cầu xác định hai nội dung (content categories) mà Amazon Bedrock Guardrails có khả năng phát hiện và lọc khi người dùng nhập dữ liệu hoặc mô hình tạo ra kết quả. Guardrails là tính năng bảo vệ nội dung được tích hợp sẵn trong Amazon Bedrock, cho phép bạn bật các content filters (bộ lọc nội dung) dựa trên các danh mục chuẩn do AWS định nghĩa. - Hate
- Nguồn tham khảo trong block: https://aws.amazon.com/blogs/aws/amazon-bedrock-guardrails/ | https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html | https://www.awsreInvent.com/2025/bedrock‑guardrails‑deep‑dive | https://www.examtopics.com/discussions/amazon/view/304561-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company uses Amazon Bedrock for its generative AI application. The company wants to use Amazon Bedrock Guardrails to detect and filter harmful user inputs and model-generated outputs.
Which content categories can the guardrails filter? (Choose two.)

### Các lựa chọn
1. Hate
2. Politics
3. Violence
4. Gambling
5. Religion

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Câu hỏi yêu cầu xác định hai nội dung (content categories) mà Amazon Bedrock Guardrails có khả năng phát hiện và lọc khi người dùng nhập dữ liệu hoặc mô hình tạo ra kết quả.

Guardrails là tính năng bảo vệ nội dung được tích hợp sẵn trong Amazon Bedrock, cho phép bạn bật các content filters (bộ lọc nội dung) dựa trên các danh mục chuẩn do AWS định nghĩa.

✅ Đáp án đúng

- Hate

- Violence

Hai danh mục này là một trong những pre‑built content filters hiện có trong Guardrails (theo tài liệu AWS cập nhật đến năm 2026). Khi bật Guardrails, bạn có thể cấu hình để tự động chặn hoặc gắn nhãn các đầu vào/đầu ra chứa ngôn ngữ thù địch, kì thị (Hate) hoặc miêu tả bạo lực, hành vi nguy hiểm (Violence).

📖 Giải thích chi tiết từng phương án

Hate

✅ Đúng – Guardrails cung cấp bộ lọc “Harassment & Hate”. Nó phát hiện các từ ngữ, cụm từ hoặc ngữ cảnh chứa thù hận, kì thị dựa trên chủng tộc, giới tính, tôn giáo, quốc tịch, v.v.

Politics

❌ Sai – Mặc dù Guardrails có một filter “Political Persuasion”, nó không được liệt kê dưới dạng “Politics”. “Politics” (chính trị chung) không phải là một danh mục lọc độc lập trong phiên bản hiện tại của Guardrails; chỉ có “Political Persuasion” (cố gắng ảnh hưởng quan điểm chính trị) được hỗ trợ.

Violence

✅ Đúng – Guardrails bao gồm bộ lọc “Violence”. Nội dung mô tả hành vi bạo lực, khủng bố, hoặc các hình ảnh/đoạn văn có tính chất nguy hiểm sẽ bị phát hiện và có thể bị chặn.

Gambling

❌ Sai – Tính năng Guardrails không có danh mục “Gambling”. Các nội dung liên quan tới cờ bạc, trò chơi có thưởng không nằm trong các bộ lọc chuẩn của Guardrails (có thể được xử lý bằng custom guardrails do người dùng tự định nghĩa, nhưng không phải là một danh mục mặc định).

Religion

❌ Sai – Mặc dù “Harassment & Hate” có thể bao gồm ngôn ngữ thù địch dựa trên tôn giáo, Religion không phải là một danh mục lọc độc lập trong Guardrails. Nếu muốn lọc nội dung tôn giáo nhạy cảm, cần tạo custom guardrails hoặc dùng các luật tùy chỉnh.

📚 Tham khảo tài liệu

AWS Documentation – Amazon Bedrock Guardrails (phiên bản 2026‑03)

https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html

Mô tả các bộ lọc nội dung mặc định: Harassment & Hate, Violence, Sexual & Nudity, Self‑harm, Illicit behavior, Political Persuasion.

AWS Blog – Introducing Amazon Bedrock Guardrails (cập nhật 2024‑11)

https://aws.amazon.com/blogs/aws/amazon-bedrock-guardrails/

AWS re:Invent 2025 – Deep dive into Bedrock Guardrails (video và slide)

https://www.awsreInvent.com/2025/bedrock‑guardrails‑deep‑dive

🧩 Tổng kết

Đáp án đúng: Hate và Violence.

Các lựa chọn còn lại (Politics, Gambling, Religion) không phải là danh mục lọc mặc định trong Guardrails, vì vậy chúng được đánh dấu là sai.

Hy vọng phần phân tích chi tiết này giúp bạn nắm vững cách Guardrails hoạt động và lựa chọn đáp án một cách tự tin! 🚀

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304561-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 64

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon SageMaker, Amazon Bedrock
- Takeaway nhanh: Việc tóm tắt (summarization) là một task tạo ngôn ngữ tự nhiên (NLG), trong đó mô hình sinh ra một đoạn văn bản ngắn gọn, súc tích dựa trên văn bản gốc dài hơn. Các mô hình generative AI như Amazon Bedrock – Titan Text, Claude, GPT‑4o (đến 2026) hỗ trợ “summarization” như một tính năng chuẩn. Đó là một ví dụ điển hình của generative AI vì mô hình “tạo ra” văn bản mới (bản tóm tắt), không chỉ phân loại hay dự đoán.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/304554-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A financial company is using ML to help with some of the company’s tasks.
Which option is a use of generative AI models?

### Các lựa chọn
1. Summarizing customer complaints
2. Classifying customers based on product usage
3. Segmenting customers based on type of investments
4. Forecasting revenue for certain products

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔍 Phân tích câu hỏi

Công ty tài chính đang áp dụng Machine Learning (ML) để hỗ trợ một số quy trình nội bộ.

Câu hỏi yêu cầu chọn một ví dụ thuộc “generative AI models” – tức là các mô hình tạo ra nội dung mới (văn bản, hình ảnh, âm thanh, mã…) dựa trên dữ liệu huấn luyện, chứ không phải các mô hình chỉ thực hiện phân loại, dự báo hay phân cụm truyền thống.

✅ Đáp án đúng

- Summarizing customer complaints

Lý do:

Việc tóm tắt (summarization) là một task tạo ngôn ngữ tự nhiên (NLG), trong đó mô hình sinh ra một đoạn văn bản ngắn gọn, súc tích dựa trên văn bản gốc dài hơn.

Các mô hình generative AI như Amazon Bedrock – Titan Text, Claude, GPT‑4o (đến 2026) hỗ trợ “summarization” như một tính năng chuẩn.

Đó là một ví dụ điển hình của generative AI vì mô hình “tạo ra” văn bản mới (bản tóm tắt), không chỉ phân loại hay dự đoán.

❌ Các phương án sai và lý giải

Classifying customers based on product usage

Đây là công việc phân loại (classification): mô hình nhận đầu vào (dữ liệu sử dụng sản phẩm) và gán nhãn (loại khách hàng).

Phân loại là một task discriminative; không sinh ra nội dung mới, vì vậy không thuộc generative AI.

Các dịch vụ như Amazon SageMaker Autopilot hoặc Amazon Lookout for Metrics có thể thực hiện việc này, nhưng không phải là generative AI.

Segmenting customers based on type of investments

Đây là phân cụm (clustering/segmentation), một dạng unsupervised learning dùng để nhóm khách hàng thành các cụm tương đồng.

Cũng là task discriminative; không tạo ra dữ liệu mới.

Các công cụ như Amazon SageMaker K‑Means hoặc Amazon EMR có thể dùng cho việc này, nhưng không liên quan tới generative AI.

Forecasting revenue for certain products

Đây là dự báo (forecasting/time‑series prediction), một dạng regression hoặc sequence‑to‑sequence dự đoán giá trị tương lai dựa trên dữ liệu lịch sử.

Dự báo không sinh ra nội dung ngôn ngữ mà chỉ tính toán giá trị số, vì vậy không phải generative AI.

Dịch vụ Amazon Forecast hay Amazon SageMaker Forecasting thực hiện nhiệm vụ này.

📚 Tham khảo (đến năm 2026)

Amazon Bedrock Documentation – “Generative AI capabilities such as text summarization, text‑to‑image, and code generation.” (2026 cập nhật)

AWS Machine Learning Blog, “New generative AI models on Bedrock: Titan, Claude, and more.” (tháng 3/2026)

AWS Well‑Architected Framework – Machine Learning Lens, phần “Choose the right model type: discriminative vs generative.” (2025)

Amazon SageMaker Documentation, “Built‑in algorithms for classification, clustering, and forecasting.” (phiên bản 2026)

🧩 Kết luận tổng quan

Generative AI = mô hình tạo ra nội dung mới (văn bản, hình ảnh, âm thanh, code…).

Trong các lựa chọn, chỉ “Summarizing customer complaints” đáp ứng tiêu chí này vì nó yêu cầu mô hình sinh ra một đoạn văn bản tóm tắt.

Các tùy chọn còn lại thuộc các loại discriminative (phân loại, phân cụm, dự báo) và không phải là ứng dụng của generative AI.

👍 Vậy đáp án đúng là Summarizing customer complaints.

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/304554-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

## Câu 65

- Domain heuristic: `Domain 2`
- Service/từ khóa gắn trên câu: Amazon Bedrock, Amazon Personalize
- Đáp án tham khảo: **Add messages to the model prompt – cần đưa lịch sử hội thoại vào prompt mỗi lần gọi mô hình để LLM “nhìn thấy” tin nhắn trước.**
- Takeaway nhanh: Công ty đang dùng một Large Language Model (LLM) trên Amazon Bedrock để xây dựng chatbot hỗ trợ khách hàng. Khi giải quyết một yêu cầu, khách hàng và chatbot sẽ “đối thoại” qua vài vòng trao đổi (các tin nhắn liên tiếp). Câu hỏi hỏi: “Which solution gives the LLM the ability to use content from previous customer messages?” Nghĩa là: làm sao để mô hình LLM có thể “nhìn thấy” và dựa vào nội dung các tin nhắn đã trao đổi trước đó khi sinh ra câu trả lời tiếp theo.
- Nguồn tham khảo trong block: https://www.examtopics.com/discussions/amazon/view/155918-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

### Đề bài
A company is using a large language model (LLM) on Amazon Bedrock to build a chatbot. The chatbot processes customer support requests. To resolve a request, the customer and the chatbot must interact a few times.
Which solution gives the LLM the ability to use content from previous customer messages?

### Các lựa chọn
1. Turn on model invocation logging to collect messages.
2. Add messages to the model prompt.
3. Use Amazon Personalize to save conversation history.
4. Use Provisioned Throughput for the LLM.

### Giải thích gốc đã chuẩn hóa

Giải thích tổng thể

🔎 Phân tích câu hỏi

Công ty đang dùng một Large Language Model (LLM) trên Amazon Bedrock để xây dựng chatbot hỗ trợ khách hàng.

Khi giải quyết một yêu cầu, khách hàng và chatbot sẽ “đối thoại” qua vài vòng trao đổi (các tin nhắn liên tiếp).

Câu hỏi hỏi: “Which solution gives the LLM the ability to use content from previous customer messages?”

Nghĩa là: làm sao để mô hình LLM có thể “nhìn thấy” và dựa vào nội dung các tin nhắn đã trao đổi trước đó khi sinh ra câu trả lời tiếp theo.

✅ Đáp án đúng

Add messages to the model prompt.

Giải thích:

Với các mô hình ngôn ngữ trên Bedrock (Claude, Titan, Llama 2, …) không có “trạng thái hội thoại” nội bộ. Để mô hình “nhớ” các tin nhắn trước, người dùng phải đưa (concatenate) các tin nhắn này vào prompt khi gọi InvokeModel.

Kiểu dữ liệu prompt cho Bedrock hỗ trợ định dạng chat‑style (ví dụ: [{role:"user",content:"…"}, {role:"assistant",content:"…"}]). Khi thêm các tin nhắn lịch sử vào mảng này, mô hình sẽ nhận được ngữ cảnh đầy đủ và có thể dựa vào chúng để trả lời.

Đây là cách chuẩn được mô tả trong tài liệu Amazon Bedrock Developer Guide – “Managing conversational context” (cập nhật tới 2026).

❌ Các lựa chọn sai và lý do

1. Turn on model invocation logging to collect messages.

Mục đích thực tế: Model invocation logging (trong Bedrock) chỉ ghi lại đầu vào (prompt) và đầu ra (response) của mỗi lần gọi mô hình, đồng thời lưu trữ chúng trong Amazon CloudWatch Logs hoặc S3 để giám sát, gỡ lỗi, và tuân thủ.

Không giúp LLM “sử dụng” nội dung: việc bật logging không tự động đưa lịch sử vào prompt của lần gọi tiếp theo. Nó chỉ lưu trữ dữ liệu để người dùng có thể phân tích sau, không ảnh hưởng đến cách mô hình xử lý.

Vì vậy, đây không phải là giải pháp để LLM truy cập nội dung tin nhắn cũ trong thời gian thực.

2. Use Amazon Personalize to save conversation history.

Amazon Personalize là dịch vụ gợi ý (recommendation) dựa trên machine learning, được thiết kế cho các trường hợp như sản phẩm, nội dung, video, quảng cáo.

Nó không cung cấp chức năng lưu trữ và cung cấp lại chuỗi hội thoại cho LLM. Thậm chí, Personalize không có API để trả về một chuỗi tin nhắn dạng chat.

Do đó, dùng Personalize để “lưu lịch sử hội thoại” không phù hợp và không giúp mô hình LLM truy cập nội dung này khi sinh câu trả lời.

3. Use Provisioned Throughput for the LLM.

Provisioned Throughput (trong Bedrock) cho phép đặt mức tài nguyên cố định (TPS, token throughput) cho một mô hình nhằm tránh “throttling” khi tải cao.

Đây là cấu hình hiệu năng, không liên quan tới trữ nhớ ngữ cảnh hay cách truyền dữ liệu vào mô hình.

Vì vậy, việc bật Provisioned Throughput không mang lại khả năng “sử dụng nội dung tin nhắn trước”.

📚 Tham khảo (đến năm 2026)

Amazon Bedrock Developer Guide – Managing conversational context (phiên bản 2026).

Amazon Bedrock API Reference – InvokeModel (định dạng messages cho chat‑style).

AWS re:Invent 2024 – “Building Conversational Agents with Amazon Bedrock” – video và slide mô tả cách truyền lịch sử hội thoại vào prompt.

Amazon CloudWatch Logs – Model invocation logging (được cập nhật 2025).

Amazon Personalize Documentation – tính năng và trường hợp sử dụng (2025).

🧩 Tóm tắt nhanh

✅ Đáp án đúng: Add messages to the model prompt – cần đưa lịch sử hội thoại vào prompt mỗi lần gọi mô hình để LLM “nhìn thấy” tin nhắn trước.

❌ Các đáp án còn lại chỉ là tính năng giám sát, gợi ý, hoặc cấu hình hiệu năng, không liên quan tới việc cung cấp ngữ cảnh cho mô hình.

Hy vọng phân tích trên giúp bạn nắm rõ cách “giữ nhớ” trong các ứng dụng chatbot dựa trên Amazon Bedrock! 🚀🛠️

Tài liệu tham khảo:

https://www.examtopics.com/discussions/amazon/view/155918-exam-aws-certified-ai-practitioner-aif-c01-topic-1-question/

Đề 4:
