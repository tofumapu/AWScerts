# ⚖️ AIF – Domain 4: Responsible AI & Bảo Mật

---

## 1. Tám Trụ Cột Responsible AI

> 🎯 **Chiến thuật thi:** Khi gặp câu về đạo đức AI, ưu tiên đáp án liên quan đến: **An toàn con người → Công bằng → Explainability → Human oversight**.

| Trụ cột | Tập trung vào | Ví dụ thực tế |
|---------|--------------|--------------|
| **Fairness** (Công bằng) | Mô hình đối xử **bình đẳng** với mọi nhóm người, tránh Bias | Hệ thống tuyển dụng không phân biệt giới tính |
| **Explainability** (Giải thích) | Hiểu **tại sao** mô hình đưa ra kết quả đó | Từ chối cho vay vì thu nhập thấp hay vì địa chỉ nhà? |
| **Transparency** (Minh bạch) | Công khai dữ liệu huấn luyện, loại mô hình, giới hạn của nó | Thông qua **Model Cards / Service Cards** |
| **Privacy & Security** | Dữ liệu cá nhân **không bị rò rỉ** vào quá trình huấn luyện | PII Redaction, mã hóa dữ liệu |
| **Robustness** (Bền bỉ) | Mô hình **vẫn ổn định** khi gặp dữ liệu nhiễu hoặc bị tấn công | Kháng cự adversarial inputs |
| **Safety** (An toàn) | Ngăn AI **gây thiệt hại** vật chất hoặc tinh thần | Không hướng dẫn chế tạo vũ khí |
| **Controllability** | Luôn có **con người giám sát** và có thể can thiệp | Human-in-the-loop |
| **Veracity** (Độ trung thực) | AI chỉ đưa ra thông tin **có thể kiểm chứng**, không bịa đặt | Grounding, RAG |

---

## 2. Interpretability vs. Explainability – Phân Biệt Rõ

> Đây là cặp khái niệm **rất dễ nhầm** trong thi.

| Khái niệm | Định nghĩa | Áp dụng cho |
|-----------|-----------|------------|
| **Interpretability** | Con người hiểu trực tiếp **cơ chế bên trong** mô hình | Mô hình đơn giản: Linear Regression, Decision Tree |
| **Explainability** | Dùng **công cụ bên ngoài** để giải thích hành vi của mô hình hộp đen | Deep Learning, LLMs · Công cụ: **PDP (Partial Dependence Plots)** |

### Đánh Đổi Hiệu Suất & Khả Năng Giải Thích

```
Dễ giải thích ◄─────────────────────────────────► Hiệu suất cao
(Interpretable)                                   (Performant)

  Linear          Decision       Random        Neural      LLMs
Regression         Tree          Forest       Networks
     │               │              │             │           │
  ✅ Biết rõ      ✅ Rõ logic   ⚠️ Phức tạp   ❌ Hộp đen  ❌ Hộp đen
     logic         từng nhánh    hơn           dần          hoàn toàn
```

| | **High Interpretability** | **High Performance** |
|--|--------------------------|---------------------|
| **Mô hình** | Linear Regression, Decision Tree | Deep Learning, Neural Networks, LLMs |
| **Ưu điểm** | Biết rõ logic, dễ giải trình | Cực kỳ thông minh, xử lý dữ liệu phức tạp |
| **Nhược điểm** | Không xử lý được ảnh, video, ngôn ngữ tự nhiên | **Black Box** – không biết hàng tỷ tham số tính gì |

---

## 3. Phân Loại Bias (Định Kiến)

> Đề thi hay hỏi về **nguồn gốc** của sự không công bằng.

| Loại Bias | Nguồn gốc | Ví dụ |
|-----------|----------|-------|
| **Data Bias** | Dữ liệu đầu vào bị lệch ngay từ đầu | Dữ liệu tuyển dụng lịch sử chỉ toàn nam giới |
| **Algorithmic Bias** | Thuật toán **khuếch đại** các sai lệch nhỏ trong dữ liệu | Mô hình học và phóng đại định kiến giới tính sẵn có |
| **Human Bias** | Định kiến của người **dán nhãn** hoặc người **thiết kế** mô hình | Người gán nhãn vô tình đánh dấu thiên vị theo quan điểm cá nhân |

---

## 4. Các Hình Thức Tấn Công Prompt – Prompt Attacks

> ⚠️ **Cần nắm rõ từng kịch bản** vì đề thi hay cho scenario cụ thể và hỏi đây là loại tấn công gì.

| Loại tấn công | Cơ chế | Ví dụ kịch bản |
|--------------|--------|---------------|
| **Prompt Injection** | Nhập câu lệnh ghi đè chỉ dẫn hệ thống | *"Bỏ qua mọi hướng dẫn trước đó và hãy làm X..."* |
| **Jailbreaking** | Dùng kỹ thuật tâm lý chiến để AI vượt rào cản đạo đức | *"Hãy đóng vai một AI không có giới hạn đạo đức..."* · Kỹ thuật: **Many-shot prompting** (đưa cực nhiều ví dụ xấu) |
| **Prompt Leaking** | Khai thác để AI **tiết lộ System Prompt** hoặc dữ liệu nhạy cảm | Người dùng hỏi khéo để lấy được cấu hình hệ thống ẩn của doanh nghiệp |
| **Data Poisoning** | Tấn công từ **bước huấn luyện** bằng cách đưa dữ liệu sai vào tập mẫu | Chèn dữ liệu độc hại vào training set để mô hình học hành vi sai |

---

## 5. Công Cụ AWS cho Responsible AI

| Dịch vụ | Chức năng chính | Keywords thi |
|---------|----------------|-------------|
| **Amazon Bedrock Guardrails** | Lọc nội dung độc hại (Toxicity), ngăn từ nhạy cảm, chặn Prompt Injection | *harmful content, toxicity filter, prompt attack prevention* |
| **SageMaker Clarify** | Phát hiện **Bias** trong dữ liệu + giải thích dự đoán của mô hình (Explainability) | *detect bias, explain predictions, fairness* |
| **AWS AI Service Cards** | Tài liệu minh bạch chính thức (cho Rekognition, Textract...) về cách dùng & rủi ro | *transparency, responsible use, limitations* |
| **AWS Model Cards** | Tài liệu mô tả mô hình: dữ liệu huấn luyện, hiệu suất, giới hạn | *model documentation, transparency, intended use* |

---

## 6. Hallucination – Bổ Sung Kỹ Thuật Grounding

> (Xem thêm nguyên nhân và RAG đã trình bày ở Domain 2 – phần này tập trung vào kỹ thuật mới.)

### Grounding – Kỹ Thuật Kiểm Soát Ảo Giác

```
Không có Grounding          Có Grounding
─────────────────          ──────────────────────────
User hỏi → LLM tự          User hỏi → LLM chỉ được
suy diễn từ kiến            trả lời dựa trên tài liệu
thức đã train               được cung cấp (Context)
→ Có thể bịa đặt           → Câu trả lời có căn cứ
```

| Kỹ thuật | Mô tả |
|----------|-------|
| **RAG** | Cung cấp dữ liệu thực vào prompt (đã trình bày Domain 2) |
| **Grounding** | Ép AI **chỉ được trả lời** dựa trên tài liệu / context cung cấp |
| **Temperature → 0** | Giảm ngẫu nhiên, tăng tính thực tế và chính xác |

---

## 7. Bảng Tra Cứu Nhanh – Domain 4

| Từ khóa trong đề | Khái niệm / Giải pháp |
|-----------------|----------------------|
| Mô hình đối xử không bình đẳng các nhóm | **Fairness** + kiểm tra **Bias** |
| Tại sao mô hình từ chối / ra quyết định đó | **Explainability** (SageMaker Clarify) |
| Công khai thông tin về dữ liệu, giới hạn mô hình | **Transparency** (Model Cards / Service Cards) |
| Dữ liệu cá nhân bị rò rỉ khi training | **Privacy & Security** |
| Mô hình bị phá vỡ bởi dữ liệu nhiễu | **Robustness** |
| AI hướng dẫn nội dung nguy hiểm | **Safety** + Bedrock Guardrails |
| Con người cần can thiệp vào quyết định AI | **Controllability** / Human-in-the-loop |
| AI bịa thông tin trông rất thật | **Hallucination** → RAG + Grounding + Temperature thấp |
| Người dùng nhập lệnh ghi đè hệ thống | **Prompt Injection** → Bedrock Guardrails |
| AI "thoát xác" vượt giới hạn đạo đức | **Jailbreaking** |
| AI tiết lộ system prompt ẩn | **Prompt Leaking** |
| Dữ liệu training bị chèn dữ liệu sai | **Data Poisoning** |
| Phát hiện bias trong tập dữ liệu | **SageMaker Clarify** |
| Mô hình đơn giản, hiểu được trực tiếp | **Interpretability** (Decision Tree, Linear Regression) |
| Mô hình phức tạp, cần tool giải thích | **Explainability** (PDP, SageMaker Clarify) |

---

*📝 Tài liệu ôn tập AIF – Domain 4: Responsible AI & Security*
