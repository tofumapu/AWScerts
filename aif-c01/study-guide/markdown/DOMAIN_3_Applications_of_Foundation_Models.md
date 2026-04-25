# 🛠️ AIF – Domain 3: Tùy Chỉnh, Đánh Giá & Triển Khai AI

---

## 1. Phân Cấp Tùy Chỉnh – Customization Hierarchy

> 📌 Nhớ thứ tự: từ **dễ → khó**, từ **rẻ → đắt**

```
Cấp độ 1  ──►  Prompt Engineering      (Không thay đổi mô hình)
Cấp độ 2  ──►  RAG                     (Inject dữ liệu ngoài tại Inference)
Cấp độ 3  ──►  Fine-Tuning             (Dạy lại trên dữ liệu chuyên biệt)
Cấp độ 4  ──►  Pre-Training            (Train từ đầu – cực đắt, hiếm khi dùng)
```

| Cấp độ | Phương pháp | Khi nào dùng | Chi phí |
|--------|-------------|--------------|---------|
| **1** | **Prompt Engineering** | Muốn thay đổi định dạng câu trả lời ngay lập tức | Thấp nhất |
| **2** | **RAG** | Cần cập nhật thông tin mới nhất mà không train lại | Vừa |
| **3** | **Fine-Tuning** | Prompt + RAG không đủ; cần hiểu thuật ngữ/phong cách chuyên biệt (y khoa, luật...) | Cao |
| **4** | **Pre-Training** | Train mô hình từ đầu hoàn toàn | Cực đắt – ❌ hiếm là đáp án đúng trong thi |

---

## 2. Kỹ Thuật Prompt Nâng Cao

### Các chiến lược Prompting

| Kỹ thuật | Mô tả | Khi nào dùng |
|----------|-------|--------------|
| **Zero-shot** | Không có ví dụ mẫu, hỏi thẳng | Câu hỏi đơn giản, mô hình đủ mạnh |
| **Few-shot** | Cung cấp 2–3 ví dụ mẫu trong prompt | AI trả lời sai định dạng (JSON, bảng...) → đây là đáp án thi phổ biến |
| **Chain of Thought (CoT)** | Yêu cầu AI suy luận từng bước | Bài toán logic, toán học · Câu lệnh: *"Let's think step by step"* |
| **Persona Prompting** | Giao vai diễn cho AI | Thu hẹp không gian phản hồi, trả lời chuyên nghiệp hơn · VD: *"Hãy đóng vai chuyên gia bảo mật AWS"* |

### Tham số Prompt nâng cao

| Tham số | Cách hoạt động | Lưu ý |
|---------|----------------|-------|
| **Temperature** | Điều chỉnh độ ngẫu nhiên | — |
| **Top-P** (Nucleus Sampling) | Chọn từ trong nhóm có tổng xác suất = P | — |
| **Top-K** | Chọn trong K từ có xác suất cao nhất | — |
| **Stop Sequences** | Chuỗi ký tự (VD: `###`) ra lệnh dừng tạo văn bản | — |

> ⚠️ **Quan trọng:** Temperature, Top-P, Top-K **không ảnh hưởng đến Latency (độ trễ)**. Latency chỉ bị ảnh hưởng bởi **kích thước mô hình** và **số lượng token**.

---

## 3. Vector Databases trên AWS – Phân Biệt Dịch Vụ

| Dịch vụ AWS | Khi nào dùng | Đặc điểm |
|-------------|-------------|----------|
| **Amazon OpenSearch Service** | Lựa chọn phổ biến nhất cho tìm kiếm vector | Tìm kiếm toàn diện, scalable |
| **Amazon Aurora + pgvector** | Đã có sẵn database PostgreSQL | Tích hợp vector search vào DB hiện có |
| **Amazon Neptune Analytics** | Dữ liệu có quan hệ phức tạp | Chuyên cho **Graph data** |
| **Amazon S3** | Lưu trữ dữ liệu thô ban đầu | Đóng vai trò **Data Source** trước khi Chunking & đưa vào Vector DB |

---

## 4. Các Chỉ Số Đánh Giá – Evaluation Metrics

### 📊 Nhóm 1: Phân Loại (Classification Metrics)

> Dùng khi: Dự đoán đối tượng thuộc **nhãn** nào (Chó/Mèo, Spam/Không spam, Rời bỏ/Không rời bỏ...)

| Chỉ số | Tập trung vào | Keywords thi | Use case |
|--------|--------------|-------------|----------|
| **Confusion Matrix** | Bảng chi tiết TP/FP/TN/FN | *detailed insights, classification errors, identify where model confuses* | Nhìn sâu vào điểm mô hình nhầm lẫn – không phải một con số tổng quát |
| **Precision** | Giảm thiểu **False Positive (FP)** | *minimize false positives, cost of false alarm is high* | Bộ lọc Spam: thà để lọt thư rác vào inbox hơn đưa nhầm email hợp đồng vào thùng rác |
| **Recall** | Giảm thiểu **False Negative (FN)** | *minimize false negatives, identify all instances, high cost of missing* | Chẩn đoán ung thư, phát hiện xâm nhập mạng – thà báo nhầm còn hơn bỏ lọt |
| **F1 Score** | Cân bằng Precision & Recall | *imbalanced data, binary classification, customer churn* | Phát hiện gian lận thẻ tín dụng (0.1% giao dịch là gian lận) |

---

### 📈 Nhóm 2: Hồi Quy (Regression Metrics)

> Dùng khi: Dự đoán **con số cụ thể, liên tục** (Giá nhà, Nhiệt độ, Doanh thu...)

| Chỉ số | Đặc điểm | Keywords thi | Use case |
|--------|----------|-------------|----------|
| **MAE** (Mean Absolute Error) | Ít bị ảnh hưởng bởi outliers | *average error, absolute differences, robust to outliers* | Dự báo thời tiết – đo sai số trung bình chung |
| **RMSE** (Root Mean Squared Error) | Nhạy cảm với sai lệch lớn (bình phương sai số) | *penalize large errors, sensitive to outliers* | Dự đoán lực kéo máy bay – sai lệch lớn gây hậu quả nghiêm trọng |

---

### 🤖 Nhóm 3: AI Tạo Sinh & NLP (Generative AI & NLP Metrics)

> Dùng khi: Làm việc với **văn bản** hoặc **hình ảnh**

| Chỉ số | Đặc điểm | Keywords thi | Use case |
|--------|----------|-------------|----------|
| **BLEU** | So khớp từ vựng **chính xác** (exact-match n-grams) | *machine translation, translate manual/documents, bilingual* | Đánh giá hệ thống dịch thuật Anh → Việt |
| **ROUGE** | Tập trung vào **Recall** – AI có bao quát hết ý chính không | *text summarization, gisting, recall-oriented* | Đánh giá tính năng "Tóm tắt bài báo" |
| **BERTScore** | Đo **tương đồng ngữ nghĩa** – không cần từ giống nhau | *semantic similarity, creative spelling, shortened words, phrasing differently* | Chatbot với tuổi teen dùng teencode; câu khác từ nhưng cùng nghĩa |
| **CFG Scale** *(Sinh ảnh)* | Điều chỉnh mức độ AI bám sát prompt | *generate images from text, increase specificity, reduce randomness, Stable Diffusion* | Tăng CFG Scale khi AI vẽ ảnh sản phẩm lung tung, không theo mô tả |

---

### 💼 Nhóm 4: Hiệu Quả Kinh Doanh (Business & UX Metrics)

> Dùng khi: Đánh giá tác động của AI đối với **doanh nghiệp hoặc người dùng**

| Chỉ số | Tập trung vào | Keywords thi | Use case |
|--------|-------------|-------------|----------|
| **Conversion Rate** | Hành động thực tế mang lại lợi nhuận | *sales revenue, business impact, purchases* | Đánh giá Recommendation System – khách có mua hàng không |
| **User Satisfaction** | Trải nghiệm & cảm xúc người dùng | *UX, customer feedback, rating* | Đánh giá sự thân thiện của chatbot CSKH |
| **Average Handling Time** | Thời gian xử lý trung bình | *reduce time, AI efficiency, fewer tickets* | Đo hiệu quả AI trong quy trình hỗ trợ khách hàng |

---

## 5. Tư Duy Business & Đánh Đổi (Trade-offs)

> 🎯 AWS muốn ông bạn là một **Practitioner thực dụng** – không phải nhà nghiên cứu.

| Tình huống | Ưu tiên |
|-----------|---------|
| Chatbot CSKH trực tuyến | **Latency thấp** > Độ chính xác tuyệt đối (không để khách chờ 30 giây) |
| Ngân sách hạn chế | Dùng **SLM (Small Language Models)** hoặc **Data Distillation** thay vì mô hình khổng lồ |
| Cải thiện mô hình liên tục | Tích hợp **User Feedback Loop** (Like/Dislike) để thu thập dữ liệu cải thiện |

> 💡 **Nguyên tắc:** AI không **thay thế** quy trình – AI **tối ưu hóa** quy trình.

---

## 6. Dịch Vụ AWS Managed AI – Chi Tiết Nâng Cao

### Amazon Polly
- **Lexicons:** Tùy chỉnh cách phát âm từ viết tắt
- **SSML:** Điều khiển giọng điệu, nhấn nhá, tốc độ đọc

### Amazon Rekognition
- **Face Liveness:** Phân biệt **mặt thật** với ảnh chụp / video giả mạo

### Amazon Transcribe
- **Toxicity Detection:** Phát hiện ngôn từ độc hại
- **PII Redaction:** Tự động xóa thông tin cá nhân nhạy cảm

---

## 7. Amazon SageMaker – Công Cụ Chuyên Sâu

| Công cụ | Chức năng |
|---------|-----------|
| **Data Wrangler** | Chuẩn bị & biến đổi dữ liệu (Feature Engineering) |
| **Feature Store** | Kho lưu trữ trung tâm để **chia sẻ và tái sử dụng features** giữa nhiều mô hình |

### Deployment – Phân Biệt Hai Chế Độ

| Chế độ | Đặc điểm | Khi nào dùng |
|--------|----------|-------------|
| **Asynchronous Inference** | File lớn tới **1GB**, xử lý trong **1 giờ** | Yêu cầu không cần phản hồi ngay lập tức |
| **Batch Transform** | Dự đoán cho **toàn bộ tập dữ liệu ngoại tuyến** | Xử lý hàng loạt, không cần real-time |

---

## 8. Bảng Tra Cứu Nhanh – Chọn Metric Đúng Khi Thi

| Từ khóa trong đề | Metric cần chọn |
|-----------------|----------------|
| Dịch thuật, bilingual | **BLEU** |
| Tóm tắt văn bản | **ROUGE** |
| Teencode, từ đồng nghĩa, ngữ nghĩa | **BERTScore** |
| Sinh ảnh, bám sát prompt | **CFG Scale** |
| Spam, false alarm cao | **Precision** |
| Ung thư, bỏ lọt nguy hiểm | **Recall** |
| Dữ liệu mất cân bằng | **F1 Score** |
| Sai lệch lớn gây hậu quả | **RMSE** |
| Sai số trung bình chung | **MAE** |
| Mô hình nhầm ở đâu | **Confusion Matrix** |
| Khách hàng mua hàng | **Conversion Rate** |
| Người dùng hài lòng | **User Satisfaction** |
| AI trả lời sai định dạng | **Few-shot Prompting** |
| Bài toán logic/toán | **Chain of Thought** |

---

*📝 Tài liệu ôn tập AIF – Domain 3: Customization, Evaluation & Deployment*
