# 🤖 AIF – Domain 1: Nền tảng Trí tuệ Nhân tạo & Học Máy

---

## 1. Bức Tranh Tổng Thể – Mối Quan Hệ Giữa Các Khái Niệm

> 💡 **Nhớ sơ đồ vòng tròn đồng tâm** để trả lời các câu hỏi về tập con.

```
┌─────────────────────────────────────────┐
│           AI (Artificial Intelligence)  │
│  ┌──────────────────────────────────┐   │
│  │       Machine Learning (ML)      │   │
│  │  ┌───────────────────────────┐   │   │
│  │  │      Deep Learning (DL)   │   │   │
│  │  │  ┌─────────────────────┐  │   │   │
│  │  │  │   Generative AI     │  │   │   │
│  │  │  │     (GenAI)         │  │   │   │
│  │  │  └─────────────────────┘  │   │   │
│  │  └───────────────────────────┘   │   │
│  └──────────────────────────────────┘   │
└─────────────────────────────────────────┘
```

| Khái niệm | Mô tả |
|-----------|-------|
| **AI** | Lĩnh vực rộng lớn nhất – mô phỏng trí tuệ con người để thực hiện các tác vụ như nhận diện hình ảnh, ra quyết định |
| **Machine Learning (ML)** | Một nhánh của AI – dùng thuật toán để máy tính **tự học từ dữ liệu** mà không cần lập trình rõ ràng các quy tắc |
| **Deep Learning (DL)** | Tập con của ML – sử dụng **mạng thần kinh đa tầng (Neural Networks)** để xử lý dữ liệu phức tạp (hình ảnh, âm thanh) |
| **Generative AI (GenAI)** | Tập con nhỏ nhất – chuyên **tạo ra nội dung mới** (văn bản, hình ảnh, mã nguồn...) dựa trên dữ liệu đã học |

---

## 2. Ba Phương Pháp Học Máy

### 2.1 Supervised Learning – Học Có Giám Sát

> Cung cấp cho thuật toán **dữ liệu đầu vào + nhãn đầu ra rõ ràng**. Thuật toán học quy luật ánh xạ để dự đoán kết quả cho dữ liệu mới.

#### 📌 Classification – Phân Loại

Phân nhóm dữ liệu vào các **danh mục rời rạc** đã được định nghĩa từ trước.

- **Phân loại nhị phân:** Email là *Spam* hay *Không spam*
- **Phân loại đa lớp:** Khối u là *lành tính* hay *ác tính*
- **Thuật toán tiêu biểu:** K-Nearest Neighbors (k-NN)

#### 📌 Regression – Hồi Quy

Dự đoán một **giá trị số liên tục** dựa trên mối quan hệ giữa các biến đầu vào.

- **Ví dụ:** Dự đoán giá nhà dựa trên diện tích, số phòng ngủ, vị trí địa lý
- Khác với Classification: trả về **con số** thay vì nhãn danh mục

---

### 2.2 Unsupervised Learning – Học Không Giám Sát

> Thuật toán tự tìm cấu trúc ẩn trong dữ liệu **không có nhãn**.

| Kỹ thuật | Mô tả | Ví dụ | Thuật toán |
|----------|-------|-------|------------|
| **Clustering** (Phân cụm) | Nhóm các điểm dữ liệu tương tự nhau | Phân khúc khách hàng | K-means |
| **Association** (Kết hợp) | Tìm mối liên hệ giữa các sản phẩm | Mua bánh mì → thường mua bơ | Apriori |
| **Anomaly Detection** (Phát hiện bất thường) | Tìm điểm khác biệt đáng kể | Phát hiện gian lận thẻ tín dụng | — |

---

### 2.3 Reinforcement Learning – Học Tăng Cường

> Học qua vòng lặp **thử – nhận phản hồi – cải thiện**.

```
Agent ──(Action)──► Environment
  ▲                     │
  └──(Reward + State)───┘
```

- **Agent:** Đối tượng học
- **Action:** Hành động thực hiện
- **Environment:** Môi trường phản hồi
- **Reward:** Phần thưởng (+ hoặc -)
- **State:** Trạng thái mới sau hành động

**Ứng dụng tiêu biểu:** AlphaGo · Xe tự lái · Tối ưu hóa danh mục đầu tư

---

### 2.4 Semi-supervised Learning – Học Bán Giám Sát

> Phương pháp **lai** giữa Supervised & Unsupervised: dùng **ít dữ liệu có nhãn** + **nhiều dữ liệu chưa có nhãn**.

**Khi nào dùng?** Chi phí/thời gian gán nhãn thủ công quá cao.

#### 🔹 Pseudo-labeling / Self-training (Gán nhãn giả)

1. Huấn luyện mô hình cơ sở từ dữ liệu đã gán nhãn
2. Dùng mô hình dự đoán nhãn cho dữ liệu chưa gán nhãn → tạo *"nhãn giả"*
3. Giữ lại các dự đoán có **độ tin cậy cao**, gộp vào tập dữ liệu gốc
4. Huấn luyện lại mô hình chính xác hơn

> **Ví dụ:** Trong y tế, học từ vài trăm ảnh X-quang đã chẩn đoán, rồi tự phân tích hàng ngàn ảnh thô khác.

#### 🔹 Graph-based Methods (Phương pháp đồ thị)

- Biểu diễn dữ liệu dạng **đồ thị**: điểm dữ liệu = *nodes*, sự tương đồng = *edges*
- Thông tin từ điểm **đã gán nhãn** lan truyền sang điểm **chưa gán nhãn** gần chúng

> **Ví dụ:** Phân loại trang web – dùng cấu trúc hyperlink để gán nhãn hàng triệu trang từ vài trang đã biết chủ đề.

---

## 3. Đánh Giá Mô Hình – Confusion Matrix

> ⚠️ **Phần quan trọng trong thi cử** – cần nắm vững công thức và ngữ cảnh sử dụng.

### Ma trận nhầm lẫn

|  | **Predicted: Positive** | **Predicted: Negative** |
|--|------------------------|------------------------|
| **Actual: Positive** | ✅ TP (True Positive) | ❌ FN (False Negative) |
| **Actual: Negative** | ❌ FP (False Positive) | ✅ TN (True Negative) |

### Các chỉ số đánh giá

| Chỉ số | Công thức | Dùng khi nào |
|--------|-----------|--------------|
| **Precision** | `TP / (TP + FP)` | Chi phí **False Positive cao** – VD: không muốn gắn nhầm email quan trọng là spam |
| **Recall** | `TP / (TP + FN)` | Chi phí **False Negative cao** – VD: không được bỏ sót bệnh nhân ung thư |
| **F1 Score** | Trung bình điều hòa của Precision & Recall | Muốn **cân bằng cả hai**, hoặc dữ liệu mất cân bằng (imbalanced) |
| **Accuracy** | `(TP + TN) / Tổng` | Chỉ tốt khi **các lớp cân bằng** (số mẫu spam ≈ không spam) |

---

## 4. Bias & Variance – Model Fit

```
Underfitting ◄────────────────────────► Overfitting
 (High Bias)          ✅ Ideal           (High Variance)
```

| | **Underfitting** | **Overfitting** |
|--|-----------------|-----------------|
| **Biểu hiện** | Mô hình quá đơn giản, không học được ngay cả trên train data | Mô hình "học vẹt", kém trên dữ liệu mới |
| **Nguyên nhân** | Mô hình quá đơn giản, thiếu features | Mô hình quá phức tạp, quá nhạy cảm |
| **Cách khắc phục** | Dùng mô hình phức tạp hơn, thêm features | Feature selection, tăng dữ liệu, **early stopping** |

---

## 5. Vòng Đời Dự Án ML (ML Project Lifecycle)

```
1. Business Problem → 2. Data Collection → 3. EDA → 4. Pre-processing
                                                              ↓
8. Monitoring ← 7. Evaluation & Tuning ← 6. Model Training ← 5. Feature Engineering
```

### Bước 1 – Business Problem Formulation
- Định nghĩa mục tiêu kinh doanh rõ ràng
- Xác định tiêu chí thành công
- ⚠️ **Xác định yêu cầu tuân thủ pháp lý & bảo mật ngay từ đầu**

### Bước 2 – Data Collection
- Thu thập dữ liệu thô từ: Database · CSV · API · Log hệ thống

### Bước 3 – Exploratory Data Analysis (EDA)
- Làm quen với dữ liệu bằng:
  - Scatter plots (biểu đồ phân tán)
  - Histograms (biểu đồ cột)
  - Correlation matrix (ma trận tương quan)
- Mục tiêu: Tìm xu hướng, phân phối, **outliers**

### Bước 4 – Data Pre-processing
Làm sạch và chuẩn bị dữ liệu:
- **Missing value imputation** – Xử lý dữ liệu bị thiếu
- **Normalization / Standardization** – Đưa giá trị về cùng thang đo
- **Label Encoding / One-Hot Encoding** – Chuyển chữ thành số

### Bước 5 – Feature Engineering
- Tạo biến mới có ý nghĩa từ dữ liệu cũ
- **Ví dụ:** Từ GPS → tính *"khoảng cách đến trung tâm thành phố"*
- Cân bằng dữ liệu bằng kỹ thuật **SMOTE**

### Bước 6 – Model Training
- Chọn thuật toán phù hợp: Random Forest · SVM · Neural Networks...
- Chia dữ liệu: **Train / Validation / Test**

### Bước 7 – Model Evaluation & Tuning
- Đánh giá trên **Test data** bằng: Accuracy · F1 Score · RMSE · BLEU...
- Nếu chưa đạt → **Hyperparameter Tuning**: thử các bộ tham số khác nhau
  - Learning rate · Batch size · Số lớp ẩn · Epochs

### Bước 8 – Deployment & Monitoring
- Deploy mô hình thành **API endpoint**
- Giám sát liên tục để phát hiện **Data Drift** (dữ liệu thực tế thay đổi so với lúc huấn luyện)
- Lên lịch **retrain** mô hình định kỳ

---

## 6. Kiến Thức Bổ Sung

### Thuật toán ML theo Use Case

| Bài toán | Thuật toán phù hợp |
|----------|-------------------|
| Dữ liệu chuỗi / Time series | **RNN** (Recurrent Neural Network) |
| Xử lý hình ảnh | **ResNet** (Residual Network) |
| Tạo dữ liệu giả / Data Augmentation | **GAN** (Generative Adversarial Network) |

### ❌ Khi KHÔNG nên dùng ML

> Nếu bài toán có thể giải bằng **quy tắc toán học xác định (Deterministic)** hoặc có **công thức rõ ràng** → Viết code truyền thống thay vì dùng ML.

### Hyperparameters

Thông số được thiết lập **trước khi huấn luyện**:

| Hyperparameter | Ý nghĩa |
|----------------|---------|
| **Learning Rate** | Tốc độ học |
| **Batch Size** | Kích thước lô dữ liệu mỗi lần cập nhật |
| **Epochs** | Số lần lặp qua toàn bộ tập dữ liệu |

### Quy Trình RLHF (Reinforcement Learning from Human Feedback)

```
1. Thu thập dữ liệu
       ↓
2. Fine-tuning mô hình cơ sở
       ↓
3. Xây dựng Reward Model (dựa trên xếp hạng của con người)
       ↓
4. Tối ưu hóa mô hình bằng Reinforcement Learning
```

---

*📝 Tài liệu ôn tập AIF – Domain 1: Foundations of AI & Machine Learning*
