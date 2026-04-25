# 🧠 AIF – Domain 2: Generative AI, LLM & Amazon Bedrock

---

## 1. Kiến Trúc Transformer – "Trái Tim" của LLM

### Self-Attention Mechanism

Cơ chế giúp mô hình hiểu **mối quan hệ giữa các từ dù ở xa nhau** trong câu.

> **Ví dụ:** Trong câu *"Con mèo nằm trên thảm vì nó mệt"*, Self-Attention giúp AI biết **"nó"** đang ám chỉ **"con mèo"** chứ không phải **"cái thảm"**.

### Encoder & Decoder

| Thành phần | Chức năng | Mô hình tiêu biểu |
|-----------|-----------|-------------------|
| **Encoder** | Hiểu ngữ cảnh đầu vào (input) | BERT |
| **Decoder** | Sinh nội dung đầu ra (output) | GPT, Claude |
| **Encoder + Decoder** | Kết hợp cả hai | T5, BART |

> ⚠️ **Lưu ý thi:** Các LLM hiện đại như GPT và Claude đều dùng kiến trúc **Decoder-only**.

---

## 2. Foundation Models (FMs) trên Amazon Bedrock

### So sánh các nhà cung cấp mô hình

| Model | Nhà cung cấp | Điểm mạnh nổi bật |
|-------|-------------|-------------------|
| **Amazon Titan** | AWS | Tích hợp sẵn **Responsible AI** (lọc nội dung độc hại, bản quyền) – "nhà trồng" của AWS |
| **Claude** | Anthropic | **Context Window cực lớn** (200k+ tokens), suy luận phức tạp, viết code chuẩn |
| **Llama** | Meta | **Mã nguồn mở (Open weights)** – tùy chỉnh sâu, không phụ thuộc vendor đóng |
| **Jurassic-2** | AI21 Labs | Mạnh về **đa ngôn ngữ** và tuân thủ hướng dẫn phức tạp |
| **Command / Embed** | Cohere | Dòng Command cho text generation · **Embed** chuyên cho Embedding |
| **Mistral** | Mistral AI | Hiệu suất **cực cao so với kích thước** nhỏ (nhỏ nhưng có võ) |
| **Stable Diffusion** | Stability AI | Chuyên **tạo hình ảnh** từ văn bản |

---

## 3. Cơ Chế Tạo Hình Ảnh – Diffusion Model

```
Forward Diffusion              Reverse Diffusion
   (Thêm nhiễu)                  (Khử nhiễu)

 Ảnh gốc ──────────► Nhiễu trắng ──────────► Ảnh mới
              +noise                  -noise (dựa trên prompt)
```

| Giai đoạn | Mô tả |
|-----------|-------|
| **Forward Diffusion** | Thêm nhiễu dần dần vào ảnh gốc cho đến khi trở thành nhiễu trắng hoàn toàn |
| **Reverse Diffusion** | Dựa trên prompt, mô hình **khử nhiễu ngược** để tái tạo ảnh mới có ý nghĩa |

---

## 4. Quy Trình RAG – Retrieval-Augmented Generation

> 🎯 **Câu hỏi Scenario-based phổ biến nhất trong thi AIF** – phải nắm chắc!

```
User Query
    │
    ▼
[1. RETRIEVAL] ──► Vector Database ──► Tìm Chunks liên quan (dựa trên Embedding similarity)
    │
    ▼
[2. AUGMENTATION] ──► Ghép Chunks + Query gốc thành Prompt mới (đã được "làm giàu")
    │
    ▼
[3. GENERATION] ──► LLM nhận Prompt → Trả lời dựa trên dữ liệu nội bộ
```

### Lợi ích của RAG

| Vấn đề | Giải pháp từ RAG |
|--------|-----------------|
| AI trả lời sai sự thật (Hallucination) | Cung cấp ngữ cảnh thực tế từ dữ liệu nội bộ |
| Dữ liệu lỗi thời | Cập nhật dữ liệu mới **không cần train lại mô hình** |
| Thiếu kiến thức chuyên ngành | Inject tài liệu nội bộ vào context |

---

## 5. Inference Parameters – Điều Khiển Kết Quả Sinh

> Dùng để kiểm soát tính **ngẫu nhiên (Non-deterministic)** của LLM.

| Tham số | Giá trị thấp | Giá trị cao | Dùng cho |
|---------|-------------|-------------|----------|
| **Temperature** | Ổn định, chính xác, ít sáng tạo | Sáng tạo, bay bổng, đa dạng | Thấp: giải toán, trích xuất · Cao: viết văn, thơ |
| **Top-P** (Nucleus Sampling) | Chọn ít từ (xác suất tích lũy thấp) | Chọn nhiều từ hơn | Cân bằng sáng tạo & chính xác |
| **Stop Sequences** | — | — | Chuỗi ký tự để **ra lệnh dừng** trả lời |

---

## 6. Tokenization & Chi Phí

### Quy đổi Token

```
1,000 tokens  ≈  750 từ tiếng Anh
```

### Cách AWS Bedrock tính tiền

| Loại Token | Chi phí |
|-----------|---------|
| **Input Tokens** | Rẻ hơn |
| **Output Tokens** | ⚠️ Đắt hơn input |

### Context Window

> Nếu vượt quá giới hạn Context Window → AI sẽ **"quên" phần đầu** của hội thoại (bị tràn bộ nhớ).

- Claude: lên tới **200k+ tokens**
- Các mô hình khác: thường từ 4k → 32k tokens

---

## 7. Hallucination – Ảo Giác AI

### Nguyên nhân

> AI chỉ **đoán xác suất từ tiếp theo** – nó không thực sự "biết" sự thật.

### Cách xử lý

| Phương pháp | Mô tả |
|-------------|-------|
| **RAG** | Cung cấp dữ liệu thực tế làm ngữ cảnh |
| **Temperature thấp** | Giảm ngẫu nhiên, tăng độ chính xác |
| **Few-shot Prompting** | Cung cấp ví dụ mẫu trong Prompt để định hướng câu trả lời |

---

## 8. Các Dịch Vụ AI Của AWS – Phân Biệt Rõ

### Amazon Q – Hai Phiên Bản

| | **Q Business** | **Q Developer** |
|--|---------------|-----------------|
| **Mục tiêu** | Doanh nghiệp | Lập trình viên & DevOps |
| **Chức năng chính** | Dùng dữ liệu nội bộ để trả lời câu hỏi | Viết code, quét lỗi bảo mật, quản lý AWS |
| **Tích hợp** | 40+ connectors (S3, Salesforce, Microsoft 365...) | AWS Console, IDE |
| **Quản lý hóa đơn** | ❌ | ✅ Phân tích chi phí AWS |

### PartyRock

> 🧪 Chỉ là **Playground thử nghiệm** – **không phải dịch vụ AWS chính thức** và **không cần tài khoản AWS** để sử dụng.

---

## 9. Tóm Tắt Nhanh – Bảng Tra Cứu Khi Thi

| Tình huống | Giải pháp |
|-----------|-----------|
| AI trả lời sai / bịa đặt | RAG + Temperature thấp |
| Cần tùy chỉnh mô hình sâu, không phụ thuộc vendor | Llama (Open weights) |
| Cần tạo hình ảnh từ văn bản | Stable Diffusion (Stability AI) |
| Cần embedding cho Vector DB | Cohere Embed / Amazon Titan Embeddings |
| Cần context window lớn | Claude (Anthropic) |
| Cần Responsible AI tích hợp sẵn | Amazon Titan |
| Dùng dữ liệu nội bộ công ty | Amazon Q Business |
| Hỗ trợ lập trình viên | Amazon Q Developer |
| Tạo ảnh qua AI | Diffusion Model (Forward → Reverse) |

---

*📝 Tài liệu ôn tập AIF – Domain 2: Generative AI, LLM & Amazon Bedrock*
