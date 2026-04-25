# 🛠️ AIF – Domain Bổ Sung: AWS AI Services, Bedrock, SageMaker & Prompt Engineering

---

## PHẦN 1: AWS Managed AI Services – Dịch Vụ AI Có Sẵn

> **Bản chất:** Pre-trained ML services – **không cần kinh nghiệm ML**, chỉ cần gọi API. Tính tiền Pay-as-you-go.

---

### 1.1 Nhóm Xử Lý Ngôn Ngữ & Văn Bản (NLP)

| Dịch vụ | Chức năng | Tính năng nổi bật |
|---------|-----------|------------------|
| **Amazon Comprehend** | Phân tích văn bản – tìm cảm xúc (sentiment), cụm từ chính, NER (tên người, địa danh) | Custom Classification · Custom Entity Recognition (thuật ngữ doanh nghiệp) |
| **Amazon Translate** | Dịch thuật ngôn ngữ tự nhiên | Bản địa hóa nội dung ứng dụng |
| **Amazon Textract** | Trích xuất văn bản + **cấu trúc bảng & biểu mẫu (key-value)** từ ảnh quét / PDF | ⚠️ **Bẫy thi:** Hóa đơn, hồ sơ y tế dạng bản quét → chọn **Textract**, không phải Rekognition |

---

### 1.2 Nhóm Âm Thanh (Speech)

| Dịch vụ | Chiều | Tính năng quan trọng |
|---------|-------|---------------------|
| **Amazon Transcribe** | Speech → Text | PII Redaction · Toxicity Detection · Custom Vocabulary |
| **Amazon Polly** | Text → Speech | Lexicons (cách phát âm từ viết tắt) · SSML (điều chỉnh nhấn nhá, tốc độ) |

---

### 1.3 Nhóm Thị Giác Máy Tính (Vision)

**Amazon Rekognition** – phân tích hình ảnh & video:
- Content Moderation – lọc ảnh nhạy cảm
- Celebrity Recognition – nhận diện người nổi tiếng
- **Face Liveness** – phân biệt mặt thật vs ảnh chụp / video giả
- **Custom Labels** – nhận diện logo, sản phẩm riêng của doanh nghiệp (chỉ cần vài trăm ảnh mẫu)

---

### 1.4 Nhóm Phân Tích & Gợi Ý

| Dịch vụ | Chức năng | Từ khóa thi |
|---------|-----------|-------------|
| **Amazon Personalize** | Gợi ý sản phẩm / nội dung cá nhân hóa (như Amazon.com, Netflix) | *recommendations, suggest products* |
| **Amazon Forecast** | Dự báo chuỗi thời gian (time-series) – tồn kho, doanh thu | *predict future quantity, time-series forecasting* |

> ⚠️ **Bẫy thi:** "Gợi ý mua hàng" → **Personalize** · "Dự báo số lượng tháng sau" → **Forecast**

---

### 1.5 Nhóm Tìm Kiếm & Hội Thoại

| Dịch vụ | Chức năng | Thành phần chính |
|---------|-----------|-----------------|
| **Amazon Lex** | Xây dựng Chatbot (text + voice) – cùng công nghệ Alexa | Intents (ý định) · Slots (thông tin cần thu thập) · Lambda (thực thi hành động) |
| **Amazon Kendra** | Tìm kiếm doanh nghiệp thông minh bằng ngôn ngữ tự nhiên | Tìm trong hàng ngàn tài liệu nội bộ, hiểu ngữ nghĩa |

---

### 1.6 Nhóm Chuyên Biệt

| Dịch vụ | Chức năng |
|---------|-----------|
| **Comprehend Medical / Transcribe Medical** | Thuật ngữ y khoa, tuân thủ **HIPAA** |
| **Amazon A2I (Augmented AI)** | Khi AI có **độ tự tin thấp (low confidence)** → tự động chuyển sang **con người kiểm tra lại** |
| **AWS Trainium (Trn1)** | Phần cứng chuyên **huấn luyện (training)** mô hình lớn – giảm 50% chi phí vs GPU |
| **AWS Inferentia (Inf1/Inf2)** | Phần cứng chuyên **chạy dự đoán (inference)** – tăng tốc & giảm 70% chi phí |
| **SageMaker Ground Truth** | **Con người dán nhãn dữ liệu** – nhân viên nội bộ / bên thứ 3 / Amazon Mechanical Turk |

---

### 1.7 Bảng Tra Cứu Nhanh – Chọn Service Trong 5 Giây

| Từ khóa trong đề | Chọn |
|-----------------|------|
| Text analysis, sentiment, NER | **Comprehend** |
| Speech-to-text, PII removal in audio | **Transcribe** |
| Text-to-speech, SSML, lexicons | **Polly** |
| Images, faces, unsafe content | **Rekognition** |
| Forms, tables, document extraction | **Textract** |
| Chatbots, intents, slots | **Lex** |
| Enterprise search, semantic search | **Kendra** |
| Recommendations (gợi ý sản phẩm) | **Personalize** |
| Time-series forecasting (dự báo) | **Forecast** |
| Human review for predictions | **A2I** |
| Data labeling / RLHF | **Ground Truth** |
| Training cost reduction (hardware) | **Trainium** |
| Inference cost reduction (hardware) | **Inferentia** |

---

## PHẦN 2: Amazon Bedrock – Nền Tảng Foundation Model

### 2.1 Tổng Quan

| Đặc điểm | Chi tiết |
|----------|----------|
| **Fully Managed** | Không cần quản lý hạ tầng |
| **Unified API** | 1 API duy nhất gọi tất cả models |
| **Pay-per-use** | Dùng bao nhiêu trả bấy nhiêu |
| **Data Privacy** | ⚠️ Dữ liệu **KHÔNG BAO GIỜ** rời khỏi account của bạn |

### 2.2 6 Tính Năng Cốt Lõi

```
Playground → Fine-tuning → RAG/Knowledge Bases → Agents → Guardrails → FM Evaluation
```

### 2.3 Foundation Models – Các Nhà Cung Cấp

| Nhà cung cấp | Dòng model | Điểm mạnh |
|-------------|-----------|----------|
| **Amazon** | Titan Text · Titan Embeddings · Titan Image | Responsible AI tích hợp sẵn |
| **Anthropic** | Claude 3 (Haiku / Sonnet / Opus) | Context window lớn · Suy luận phức tạp |
| **Meta** | Llama 2, Llama 3 | Open weights – tùy chỉnh sâu |
| **AI21 Labs** | Jurassic-2 | Đa ngôn ngữ |
| **Cohere** | Command · Embed | Embedding chuyên biệt |
| **Stability AI** | Stable Diffusion | Sinh ảnh từ văn bản |
| **Mistral** | Mistral | Nhỏ nhưng hiệu suất cao |

---

### 2.4 RAG & Knowledge Bases – Chi Tiết Kỹ Thuật

**Luồng xử lý RAG:**
```
Files → Chunking → Embeddings → Vector DB
                                    ↑
User hỏi → Search & Retrieve → Ghép Prompt → LLM → Trả lời
```

**Nguồn dữ liệu:** Amazon S3 · Confluence · Microsoft SharePoint · Salesforce · Web Crawler

**Vector Database cho RAG:**

| DB | Khi nào dùng |
|----|-------------|
| **Amazon OpenSearch Serverless** | Mặc định · hiệu suất cao · real-time KNN |
| **Amazon DocumentDB** | NoSQL (MongoDB) · real-time |
| **Amazon Aurora** | Đang dùng sẵn PostgreSQL/MySQL |
| **Amazon Neptune** | Graph-based (dữ liệu quan hệ phức tạp) |
| **Pinecone** | Managed vector DB bên thứ 3 |
| **Redis** | In-memory · độ trễ cực thấp |

> 💡 **Embedding model** có thể **khác** với Foundation model (VD: dùng Titan Embeddings để embed, Claude để generate)

---

### 2.5 Agents – "Nghĩ + Hành Động"

> **Công thức:** `Agent = Model + Action Groups + Knowledge Bases`

| | **Model** | **Agent** |
|--|-----------|-----------|
| Khả năng | Chỉ **trả lời** | **Nghĩ + Hành động** + tác động hệ thống |
| Ví dụ | Trả lời câu hỏi | Gọi API, đọc/ghi DB, deploy tài nguyên |

**Cơ chế hoạt động:** Phân tích → Lên kế hoạch (CoT) → Gọi Action Groups → Tổng hợp
**Tracing:** Theo dõi từng bước Agent nghĩ & làm để debug

---

### 2.6 Fine-tuning – Phân Biệt 5 Phương Pháp

| Phương pháp | Dữ liệu | Thay đổi weights? | Dùng khi |
|-------------|---------|------------------|---------|
| **Prompt Engineering** | Không | ❌ | Thay đổi output format |
| **RAG** | Tài liệu ngoài | ❌ | Cần dữ liệu mới/trích dẫn |
| **Instruction Fine-tuning** | Labeled (Prompt-Response) | ✅ | Đổi tone, behavior, persona |
| **Continued Pre-training** | Unlabeled (văn bản thô) | ✅ | Học từ viết tắt, thuật ngữ ngành sâu |
| **Reinforcement Fine-tuning** | Rewards | ✅ | Tối ưu tác vụ cụ thể |

> ⚠️ **Bắt buộc nhớ:** Đã Fine-tune → **BẮT BUỘC** dùng gói giá **Provisioned Throughput**

---

### 2.7 Pricing – 3 Mô Hình Tính Giá

| Mô hình | Đặc điểm | Dùng khi |
|---------|----------|---------|
| **On-Demand** | Trả theo token, không cam kết | Workload không đoán trước |
| **Batch Mode** | Xử lý offline, **giảm giá 50%** | Không cần real-time |
| **Provisioned Throughput** | Mua khoán năng lực | Workload ổn định · **Fine-tuned models** |

**Quy tắc token:**
```
1 token ≈ 4 ký tự tiếng Anh
Tính tiền: Input Tokens (Prompt + RAG) + Output Tokens (câu trả lời)
Mẹo tiết kiệm: Prompt ngắn · Output ngắn · Model nhỏ hơn · Batch mode
```

---

### 2.8 FM Evaluation Metrics

| Metric | Dùng cho | Ghi nhớ |
|--------|---------|---------|
| **ROUGE** | Tóm tắt & Dịch thuật | Recall-oriented |
| **BLEU** | Dịch máy chuyên biệt | Exact-match n-grams |
| **BERTScore** | Semantic similarity | Hiểu nghĩa, không cần từ giống nhau |
| **Perplexity** | Độ tự tin dự đoán | Càng thấp càng tốt |

---

### 2.9 Cây Quyết Định Bedrock

| Tình huống | Giải pháp |
|-----------|-----------|
| Cần kết nối dữ liệu bên ngoài | **RAG / Knowledge Bases** |
| Cần model thực hiện actions (gọi API) | **Agents** |
| Cần kiểm soát / chặn nội dung | **Guardrails** |
| Cần model học hành vi / kiến thức mới | **Fine-tuning** |
| Có dữ liệu Prompt-Response (labeled) | **Instruction Fine-tuning** |
| Chỉ có dữ liệu thô (unlabeled) | **Continued Pre-training** |
| Data thay đổi thường xuyên / cần citation | **RAG** |
| Đổi tone / giọng văn / behavior | **Instruction Fine-tuning** |

---

## PHẦN 3: Amazon Q – Hệ Sinh Thái Trợ Lý AI

### 3.1 Tổng Quan Hệ Sinh Thái

```
Amazon Q Business  ──►  Nhân viên nội bộ + dữ liệu công ty
Amazon Q Developer ──►  Lập trình viên + quản lý AWS
Amazon Q Apps      ──►  Tạo app No-Code từ dữ liệu nội bộ
Amazon Q (Services)──►  QuickSight · EC2 · AWS Chatbot
PartyRock          ──►  Playground thử nghiệm (KHÔNG phải service thật)
```

---

### 3.2 Amazon Q Business

**Mục tiêu:** Trợ lý GenAI cho nhân viên nội bộ, dùng dữ liệu công ty

| Thành phần | Chi tiết |
|-----------|----------|
| **Data Connectors** | 40+ nguồn: S3 · RDS · Aurora · Microsoft 365 · Salesforce · Google Drive · Slack · SharePoint |
| **Plugins** | Jira · ServiceNow · Zendesk – AI có thể **TẠO, SỬA, XÓA** dữ liệu trong app bên thứ 3 |
| **Authentication** | ⚠️ **BẮT BUỘC** dùng **IAM Identity Center** (hoặc External IDP: Google, Microsoft AD) |
| **Admin Controls** | Blocked Topics · Internal Only · PII Protection · Content Filters |

---

### 3.3 Amazon Q Developer

**2 chức năng chính:**

| Chức năng | Mô tả |
|----------|-------|
| **AWS Account Assistant** | Liệt kê tài nguyên · Gợi ý CLI · Phân tích chi phí · Troubleshooting |
| **AI Code Companion** | Code Generation · Code Completion · Security Scan · Debugging · Documentation |

**Hỗ trợ:** Java · JavaScript · Python · TypeScript · C# · IDE: VS Code · Visual Studio · JetBrains

> **Khác GitHub Copilot:** Q Developer tích hợp tài khoản AWS + gợi ý lệnh CLI

---

### 3.4 Amazon Q Apps

- **No-Code:** Tạo app bằng ngôn ngữ tự nhiên, không cần viết code
- Dùng **dữ liệu nội bộ công ty** + tích hợp Plugins
- Cần **tài khoản AWS**

---

### 3.5 PartyRock

> ⚠️ **KHÔNG PHẢI dịch vụ AWS thật** – chỉ là Playground

| | **PartyRock** | **Q Apps** |
|--|--------------|-----------|
| Tài khoản AWS | ❌ Không cần | ✅ Cần |
| Dữ liệu công ty | ❌ Không | ✅ Có |
| Backend | Amazon Bedrock | Amazon Bedrock |
| Mục đích | Thử nghiệm cá nhân | Công việc thật |

---

### 3.6 Cây Quyết Định Amazon Q

| Tình huống | Chọn |
|-----------|------|
| Nhân viên + dữ liệu nội bộ + chat | **Q Business** |
| Tạo app nội bộ không cần code | **Q Apps** |
| Lập trình viên + code + quản lý AWS | **Q Developer** |
| Thử nghiệm không cần tài khoản | **PartyRock** |
| Dashboard / biểu đồ | **Q for QuickSight** |
| Kiểm soát toàn diện, chọn model, fine-tune | **Bedrock** (thay vì Q Business) |

---

## PHẦN 4: Amazon SageMaker – Nền Tảng ML All-in-One

> **Định nghĩa:** Fully managed · Dành cho Developers & Data Scientists · Build → Train → Deploy

### 4.1 Core Features

| Tính năng | Chức năng |
|----------|-----------|
| **SageMaker Studio** | IDE trung tâm: code · debug · deploy · tự động hóa |
| **Automatic Model Tuning (AMT)** | Tự động tìm **best hyperparameters** · Hỗ trợ early stopping |

---

### 4.2 Data Tools

| Tool | Chức năng | Từ khóa thi |
|------|-----------|-------------|
| **Data Wrangler** | Chuẩn bị · Làm sạch · Biến đổi dữ liệu (Feature Engineering) trước khi train | *prepare, cleanse, transform data* |
| **Feature Store** | Kho lưu trữ trung tâm – **lưu trữ & tái sử dụng features** giữa nhiều models | *store, share, reuse features* |

---

### 4.3 Models & Humans

| Tool | 3 Chức Năng Chính | Từ khóa thi |
|------|------------------|-------------|
| **SageMaker Clarify** | ① Model Evaluation · ② Explainability (tại sao mô hình dự đoán thế?) · ③ Bias Detection | *detect bias, explain predictions, compare models* |
| **Ground Truth** | Con người dán nhãn dữ liệu (RLHF) | *human labeling, data annotation* |

---

### 4.4 Governance & MLOps

| Tool | Chức năng | Từ khóa thi |
|------|-----------|-------------|
| **Model Cards** | Ghi chép tài liệu về mô hình (mục đích, rủi ro, training) | *document model* |
| **Model Dashboard** | Tổng quan TẤT CẢ mô hình đang có | *view all models* |
| **Model Registry** | Quản lý **phiên bản & trạng thái phê duyệt** trước khi lên production | *version control, approval status* |
| **Model Monitor** | Giám sát chất lượng **KHI ĐANG CHẠY THỰC TẾ** · Phát hiện Model Drift & Bias Drift | *detect drift in production* |
| **Pipelines** | CI/CD cho ML – tự động hóa toàn bộ quy trình | *automate ML workflow* |
| **Role Manager** | Phân quyền theo vị trí (Data Scientist, MLOps Engineer) | — |

---

### 4.5 Deployment – Phân Biệt 4 Loại

| | **Real-Time** | **Serverless** | **Asynchronous** | **Batch Transform** |
|--|--------------|---------------|-----------------|---------------------|
| **Latency** | Thấp | Thấp (Cold Start!) | Gần real-time | Cao |
| **Payload** | < 6MB | < 6MB | **< 1GB** | Không giới hạn |
| **Infra** | Tự quản lý | AWS lo hết | Tự quản lý | Tự quản lý |
| **Use case** | Chatbot, API | Traffic lúc có lúc không | File lớn | Xử lý offline tập dữ liệu lớn |

---

### 4.6 Phân Biệt Các Tool Dễ Nhầm

| Cặp dễ nhầm | Phân biệt |
|------------|----------|
| **Data Wrangler vs Feature Store** | Wrangler: *chế biến* dữ liệu · Feature Store: *lưu & tái sử dụng* |
| **Model Cards vs Model Registry** | Cards: *viết tài liệu* · Registry: *lưu version & phê duyệt* |
| **Model Monitor vs Clarify** | Clarify: phân tích *trước khi chạy* · Monitor: giám sát *khi đang chạy* |
| **Clarify vs Ground Truth** | Clarify: *công cụ tự động/metrics* · Ground Truth: *sức con người* |

---

### 4.7 Từ Khóa → Đáp Án SageMaker

| Từ khóa | Chọn |
|---------|------|
| Automate ML workflow | **Pipelines** |
| Store features for reuse | **Feature Store** |
| Detect model drift in production | **Model Monitor** |
| Detect bias / Explain / Compare models | **Clarify** |
| Human labeling / RLHF | **Ground Truth** |
| Tune hyperparameters automatically | **AMT** |
| Large payload / 1GB file | **Asynchronous Inference** |
| No infrastructure / Occasional traffic | **Serverless Inference** |

---

## PHẦN 5: Prompt Engineering – Kỹ Thuật Tối Ưu Câu Lệnh

### 5.1 Cấu Trúc Prompt Chuẩn (4 Thành Phần)

```
┌─────────────────────────────────────────────┐
│  INSTRUCTIONS   ← Bắt buộc: làm gì, cách nào│
│  CONTEXT        ← Tùy chọn: bối cảnh, nền   │
│  INPUT DATA     ← Tùy chọn: dữ liệu cần xử lý│
│  OUTPUT FORMAT  ← Bắt buộc: định dạng, độ dài│
└─────────────────────────────────────────────┘
```

---

### 5.2 Các Kỹ Thuật Prompt – Phân Nhóm

#### Nhóm 1: Kỹ Thuật Cơ Bản

| Kỹ thuật | Cách dùng | Khi nào dùng |
|----------|-----------|-------------|
| **Zero-shot** | Hỏi thẳng, không ví dụ | Tác vụ đơn giản, kiến thức phổ thông |
| **Few-shot (One-shot)** | Cho 2–3 ví dụ cặp input-output rồi mới hỏi | AI trả lời sai format (JSON, CSV...) |
| **Role / Persona Prompting** | "Hãy đóng vai một chuyên gia bảo mật AWS..." | Thiết lập tone, từ vựng chuyên nghiệp |

#### Nhóm 2: Tối Ưu Suy Luận

| Kỹ thuật | Cơ chế | Khi nào dùng |
|----------|--------|-------------|
| **Chain of Thought (CoT)** | Câu thần chú: *"Think step by step"* – ép AI viết từng bước | Bài toán logic, toán học |
| **Self-Consistency** | Sinh câu trả lời nhiều lần → chọn đáp án xuất hiện nhiều nhất (Majority vote) | Logic phức tạp, cần độ chính xác cao |
| **Generated Knowledge** | Bước 1: AI sinh kiến thức về chủ đề · Bước 2: Dùng kiến thức đó để trả lời | Giảm ảo giác (hallucination) |

#### Nhóm 3: Nâng Cao & Cấu Trúc

| Kỹ thuật | Cơ chế |
|----------|--------|
| **Tree of Thoughts (ToT)** | Nhiều nhánh giải pháp → tự đánh giá → backtrack nếu sai. Dùng cho cờ, kế hoạch chiến lược |
| **ReAct** | Suy nghĩ → Hành động (dùng tool) → Quan sát → Suy nghĩ tiếp. Cốt lõi của **AI Agents** |
| **Directional Stimulus** | Cung cấp "gợi ý từ khóa" định hướng kèm theo đầu vào |

#### Nhóm 4: Điều Hướng & Giới Hạn

| Kỹ thuật | Cơ chế | Ví dụ |
|----------|--------|-------|
| **Negative Prompting** | Liệt kê rõ những gì AI **KHÔNG** được làm | *"Không dùng từ 'đột phá'. Không dùng dấu chấm than. Không quá 3 câu."* |
| **Least-to-Most** | Chia bài toán lớn thành câu hỏi nhỏ, kết quả bước trước làm đầu vào bước sau | Giải toán nhiều bước phức tạp |

#### Nhóm 5: Nặng Đô (Dành cho Lập Trình & Agent)

| Kỹ thuật | Cơ chế |
|----------|--------|
| **Meta Prompting / APE** | Dùng AI viết và tối ưu prompt thay cho con người |
| **PAL / PoT** | AI viết code Python để giải toán → chạy code lấy kết quả (không tự tính) |
| **Graph of Thoughts (GoT)** | Nâng cấp ToT: các nhánh suy nghĩ có thể **đan chéo, gộp lại** với nhau |
| **Active-Prompt** | Hệ thống đo uncertainty → chọn câu AI bối rối nhất → con người viết few-shot mẫu |

---

### 5.3 Inference Parameters – Tổng Hợp

| Tham số | Phạm vi | Thấp | Cao | Ảnh hưởng Latency? |
|---------|---------|------|-----|-------------------|
| **Temperature** | 0.0 – 1.0 | Chính xác, lặp lại | Sáng tạo, đa dạng | ❌ KHÔNG |
| **Top-P** | 0 – 1 | Chọn ít từ | Chọn nhiều từ | ❌ KHÔNG |
| **Top-K** | Số nguyên | Ít lựa chọn | Nhiều lựa chọn | ❌ KHÔNG |
| **Max Length (tokens)** | — | Output ngắn | Output dài | ✅ CÓ |

> ⚠️ **Bẫy cực nặng trong thi:** Temperature / Top-P / Top-K **KHÔNG ảnh hưởng đến Latency**. Latency chỉ bị ảnh hưởng bởi **kích thước model** và **số lượng token (input + output)**.

---

### 5.4 Cây Quyết Định Prompt Engineering

| Tình huống | Kỹ thuật |
|-----------|---------|
| Cần output theo format cụ thể | **Few-shot** |
| Giải logic / toán phức tạp | **Chain of Thought** |
| Tránh nội dung không mong muốn | **Negative Prompting** |
| Cần độ chính xác cao, thực tế | **Temperature thấp (0.0–0.3)** |
| Cần sáng tạo, đa dạng | **Temperature cao (0.7–1.0)** |
| Giảm latency | **Giảm tokens** (prompt ngắn + output ngắn) hoặc dùng **model nhỏ hơn** |
| Muốn AI thực hiện hành động | **ReAct** |
| AI tự tạo & tối ưu prompt | **APE / Meta Prompting** |

---

### 5.5 Từ Khóa Vàng – Phần Prompt Engineering

| Từ khóa trong đề | Đáp án |
|-----------------|-------|
| No example, trả lời thẳng | **Zero-shot** |
| 2–3 examples, làm theo mẫu | **Few-shot** |
| Tránh ảo giác, trả lời thực tế | **Temperature thấp** |
| Không đề cập technical terms | **Negative Prompting** |
| Giải toán / lập luận phức tạp | **Chain of Thought** |
| Bài toán chia nhỏ từng bước | **Least-to-Most** |
| AI dùng tool, tương tác hệ thống | **ReAct / Agents** |
| Latency cao / chạy chậm | Giảm **số token** – KHÔNG phải chỉnh Temperature |

---

## 🏆 Master Cheat Sheet – Bảng Tổng Hợp Cuối

### RAG vs Fine-tuning

| | **RAG** | **Fine-tuning** |
|--|---------|----------------|
| Thay đổi weights? | ❌ | ✅ |
| Dữ liệu cần | Tài liệu ngoài | Training data có nhãn / thô |
| Chi phí | Rẻ hơn | Đắt hơn |
| Dùng khi | Dữ liệu mới, cần citation, chống ảo giác | Đổi behavior, tone, học thuật ngữ ngành |

### Comprehend vs Lex vs Kendra

| | Comprehend | Lex | Kendra |
|--|-----------|-----|--------|
| Mục đích | Phân tích văn bản có sẵn | Xây chatbot nói chuyện qua lại | Tìm kiếm tài liệu nội bộ |
| Input | Văn bản tĩnh | Hội thoại | Câu hỏi ngôn ngữ tự nhiên |

### Clarify vs Monitor vs Ground Truth

| | Clarify | Model Monitor | Ground Truth |
|--|---------|--------------|-------------|
| Thời điểm | **Trước** khi deploy | **Sau** khi deploy (production) | Thu thập nhãn |
| Công cụ | Tự động / Metrics | Tự động / Alerts | Con người |
| Chức năng | Bias + Explainability | Drift detection | Data labeling |

---

*📝 Tài liệu ôn tập AIF – Phần bổ sung: AWS AI Services · Bedrock · Amazon Q · SageMaker · Prompt Engineering*
