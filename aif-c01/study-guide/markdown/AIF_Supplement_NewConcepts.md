# 📌 AIF – Bổ Sung: Các Khái Niệm Chưa Xuất Hiện

---

## 1. Các Kiến Trúc Neural Network – Bổ Sung

> (Domain 1 đã có RNN, GAN, ResNet – file này bổ sung phần còn thiếu)

| Kiến trúc | Chuyên dùng cho | Ghi nhớ nhanh |
|-----------|----------------|--------------|
| **WaveNet** | Tổng hợp âm thanh & giọng nói thô (Raw audio) | *"Wave = Sóng âm"* |
| **BERT** | Hiểu ngôn ngữ, phân loại văn bản, QA | Encoder-only · Đọc cả 2 chiều |
| **GPT** | Sinh văn bản | Decoder-only · Đọc 1 chiều |

---

## 2. Self-Supervised Learning – Phương Pháp Học Thứ 5

> Chưa xuất hiện trong bất kỳ domain nào trước đó.

**Định nghĩa:** Mô hình **tự tạo nhãn cho chính nó** từ dữ liệu thô – **không cần con người gán nhãn**.

```
Dữ liệu thô ──► Mô hình tự che/ẩn một phần ──► Học cách dự đoán phần bị ẩn
                (ví dụ: che từ trong câu)         → Tự tạo nhãn
```

> 💡 **Đây là nền tảng của GPT, BERT** – lý do tại sao các LLM có thể học từ lượng dữ liệu khổng lồ mà không cần gán nhãn thủ công.

**So sánh 5 phương pháp học:**

| Phương pháp | Nhãn | Ví dụ |
|------------|------|-------|
| Supervised | ✅ Con người gán | Email spam/không spam |
| Unsupervised | ❌ Không nhãn | Phân cụm khách hàng |
| Semi-supervised | ⚡ Ít nhãn + nhiều không nhãn | Pseudo-labeling |
| Reinforcement | 🎮 Reward từ environment | AlphaGo |
| **Self-Supervised** | 🤖 **Tự tạo nhãn từ dữ liệu** | GPT, BERT |

---

## 3. Edge AI vs Cloud AI

> Chưa được đề cập trong các domain trước.

| | **Edge AI** | **Cloud AI** |
|--|------------|-------------|
| **Vị trí xử lý** | Thiết bị đầu cuối (camera, sensor, điện thoại) | Máy chủ AWS |
| **Latency** | Cực thấp (không cần internet) | Cao hơn (phụ thuộc mạng) |
| **Model size** | Chỉ chạy được **SLM (Small Language Models)** | Chạy được mô hình lớn tùy ý |
| **Kết nối** | Không cần internet | Cần internet |
| **Use case** | Camera an ninh · Xe tự lái · IoT sensor | Chatbot · Phân tích dữ liệu lớn |

---

## 4. Regularization – Giải Pháp Overfitting (Bổ Sung)

> Domain 1 đã đề cập early stopping & feature selection – đây là kỹ thuật bổ sung còn thiếu.

**Regularization:** Kỹ thuật "phạt" mô hình khi trọng số quá lớn, tránh học vẹt.

| Giải pháp Overfitting | Mô tả |
|----------------------|-------|
| Thêm dữ liệu huấn luyện | Cách tốt nhất |
| Early Stopping | Dừng trước khi overfit |
| **Regularization (L1/L2)** | Phạt trọng số quá lớn ← **Mới** |
| Feature selection | Giảm bớt đặc trưng |

---

## 5. MLOps – Khái Niệm Bổ Sung

> Domain 3 có SageMaker Pipelines, Domain 5 có Governance – đây là định nghĩa tổng thể còn thiếu.

**MLOps = DevOps áp dụng cho AI**, nhưng bổ sung thêm:

```
DevOps truyền thống:   Code Version Control + CI/CD
                              +
MLOps bổ sung thêm:    Data Version Control + Model Version Control
```

| Thành phần MLOps | Công cụ AWS |
|-----------------|------------|
| Code CI/CD | SageMaker Pipelines |
| Model versioning & approval | SageMaker Model Registry |
| Data tracking | SageMaker Data Lineage |
| Production monitoring | SageMaker Model Monitor |

---

## 6. VPC Endpoints – Phân Biệt 2 Loại

> Domain 5 đề cập PrivateLink tổng quát – đây là chi tiết phân biệt 2 loại **bắt buộc nhớ**.

| | **Gateway Endpoint** | **Interface Endpoint (PrivateLink)** |
|--|--------------------|------------------------------------|
| **Chi phí** | ✅ **MIỄN PHÍ** | ❌ **Có phí** |
| **Dùng cho** | **S3** và **DynamoDB** | Tất cả dịch vụ AI: **Bedrock, SageMaker**, v.v. |
| **Cơ chế** | Route table | Network Interface (ENI) trong VPC |

> 🎯 **Từ khóa thi:** *"Kết nối riêng tư với Bedrock/SageMaker"* → **Interface Endpoint (có phí)**
> *"Kết nối riêng tư với S3"* → **Gateway Endpoint (miễn phí)**

---

## 7. Bộ Công Cụ Bảo Mật AWS – Phân Biệt Rõ

> Domain 5 đã có CloudTrail, Macie, Artifact, Audit Manager – bổ sung 2 dịch vụ còn thiếu.

| Dịch vụ | Chức năng | Từ khóa thi |
|---------|-----------|-------------|
| **CloudTrail** | Ghi lại **API calls** – ai làm gì, lúc nào | *"Ai đã xóa / sửa resource?"* |
| **AWS Config** | Theo dõi **thay đổi cấu hình** tài nguyên theo thời gian | *"Cấu hình bị thay đổi lúc nào?"* ← **Mới** |
| **Amazon Macie** | Quét tìm **PII** trong S3 | *"Dữ liệu nhạy cảm trong S3"* |
| **Amazon Inspector** | Quét **lỗ hổng phần mềm** (vulnerabilities) trong EC2, container | *"Vulnerability scan"* ← **Mới** |
| **AWS Artifact** | Tải báo cáo chứng nhận (ISO, SOC, PCI) + ký thỏa thuận (BAA, HIPAA) | *"Compliance report download"* |
| **AWS Audit Manager** | Tự động thu thập bằng chứng kiểm toán liên tục | *"Continuous audit evidence"* |
| **AWS Trusted Advisor** | Lời khuyên tối ưu chi phí, bảo mật cho tài khoản AWS | *"Account assessment, best practices"* ← **Mới** |

---

## 8. IAM – Phân Biệt 4 Thành Phần

> Chưa được giải thích chi tiết trong các domain trước.

| Thành phần | Là gì | Ghi nhớ |
|-----------|-------|---------|
| **Users** | Người dùng thật (cá nhân) | 1 người = 1 user |
| **Groups** | Nhóm chứa Users | Gán policy 1 lần cho cả nhóm |
| **Policies** | Văn bản **JSON** định nghĩa quyền Allow/Deny | Gắn vào User, Group hoặc Role |
| **Roles** | Quyền **tạm thời** gán cho **AWS Services** | EC2 gọi S3, Lambda gọi Bedrock... |

> 🔑 **Nguyên tắc vàng:** **Least Privilege** – chỉ cấp đúng quyền tối thiểu cần thiết

**Phân biệt quan trọng:**
- **Users/Groups** → dành cho **con người**
- **Roles** → dành cho **AWS Services** (Lambda, EC2, SageMaker gọi Bedrock)

---

## 9. Bảng Tra Cứu Nhanh – Toàn Bộ Bổ Sung

| Từ khóa trong đề | Đáp án |
|-----------------|-------|
| Mô hình tự tạo nhãn, không cần con người | **Self-Supervised Learning** |
| Tổng hợp giọng nói thô (raw audio) | **WaveNet** |
| Thiết bị đầu cuối, không internet, latency thấp | **Edge AI + SLM** |
| Tránh overfitting bằng "phạt" trọng số | **Regularization (L1/L2)** |
| Kết nối riêng tư với S3 (miễn phí) | **Gateway Endpoint** |
| Kết nối riêng tư với Bedrock/SageMaker | **Interface Endpoint (PrivateLink)** |
| Ai đã xóa / sửa resource AWS? | **CloudTrail** |
| Cấu hình resource thay đổi lúc nào? | **AWS Config** |
| Quét lỗ hổng bảo mật phần mềm | **Amazon Inspector** |
| Lời khuyên tối ưu tài khoản AWS | **AWS Trusted Advisor** |
| Quyền tạm thời cho AWS Service | **IAM Role** |
| DevOps + Data & Model version control | **MLOps** |

---

*📝 Tài liệu bổ sung AIF – Các khái niệm chưa xuất hiện trong Domain 1–5 & Bonus*
