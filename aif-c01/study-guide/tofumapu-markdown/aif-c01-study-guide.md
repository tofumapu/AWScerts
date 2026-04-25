# AWS Certified AI Practitioner (AIF-C01)

---

## Tổng Quan Kỳ Thi

- **65 câu hỏi** (50 câu tính điểm + 15 câu không tính điểm)
- **Thời gian**: 90 phút
- **Điểm đạt**: 700/1000
- **Dạng câu hỏi**: Multiple choice, Multiple response, Ordering, Matching, Case study

### Phân Bổ Nội Dung

| Domain | Nội dung | Tỷ trọng |
|--------|----------|----------|
| 1 | Fundamentals of AI and ML | 20% |
| 2 | Fundamentals of Generative AI | 24% |
| 3 | Applications of Foundation Models | 28% |
| 4 | Guidelines for Responsible AI | 14% |
| 5 | Security, Compliance, and Governance for AI Solutions | 14% |

---

# DOMAIN 1: FUNDAMENTALS OF AI AND ML (20%)

---

## 1.1 Khái Niệm Cơ Bản AI/ML

### 1.1.1 Phân Biệt AI → ML → Deep Learning

Ba khái niệm này có quan hệ tập con lồng nhau: AI ⊃ ML ⊃ Deep Learning.

**Artificial Intelligence (AI)**: Lĩnh vực rộng nhất — mọi kỹ thuật để máy tính mô phỏng trí tuệ con người. Bao gồm cả rule-based systems (hệ thống luật) đơn giản lẫn neural networks phức tạp.

**Machine Learning (ML)**: Tập con của AI — máy tính học từ dữ liệu, tìm patterns, đưa ra predictions mà không cần lập trình từng rule cụ thể. Algorithms tự động cải thiện performance dựa trên experience (data).

**Deep Learning (DL)**: Tập con của ML — sử dụng neural networks nhiều lớp (deep neural networks) với hàng triệu đến hàng tỷ parameters. Tự động trích xuất features từ raw data (không cần manual feature engineering). Đặc biệt hiệu quả cho image recognition, NLP, speech recognition, generative AI.

### 1.1.2 Neural Networks

**Cấu trúc**: Input layer → Hidden layers (1 hoặc nhiều) → Output layer. Mỗi neuron nhận input, áp dụng weights + bias, qua activation function, tạo output.

**Activation Functions**: ReLU (phổ biến nhất cho hidden layers), Sigmoid (output 0-1, dùng cho binary classification), Softmax (output probabilities cho multi-class classification).

**Training Process**: Forward propagation → compute loss → backpropagation → update weights via gradient descent. Lặp lại qua nhiều epochs cho đến khi loss converge.

**Key terms**: Epoch (1 pass qua toàn bộ training data), Batch size (số samples per gradient update), Learning rate (tốc độ cập nhật weights — quá cao thì diverge, quá thấp thì chậm converge).

### 1.1.3 Transformer Architecture

Kiến trúc đột phá ra đời 2017 ("Attention Is All You Need"), nền tảng của hầu hết LLMs hiện đại.

**Self-Attention Mechanism**: Cho phép model xem xét tất cả positions trong input sequence cùng lúc, thay vì xử lý tuần tự. Mỗi token "chú ý" (attend) đến mọi token khác → capture long-range dependencies.

**Encoder-Decoder**: Architecture gốc có 2 phần — Encoder (hiểu input) và Decoder (sinh output). BERT dùng encoder-only. GPT dùng decoder-only. T5 dùng encoder-decoder.

**Models dựa trên Transformer**: GPT (OpenAI), Claude (Anthropic), Llama (Meta), Titan (Amazon), BERT (Google), T5 (Google), Mistral, Cohere Command.

### 1.1.4 Các Loại Generative Models

| Model                                    | Cách hoạt động                                                                        | Ví dụ                                                            | Use case                                  |
| ---------------------------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ----------------------------------------- |
| **Transformer-based LLM**                | Predict next token dựa trên context                                                   | GPT-4, Claude, Llama, Titan                                      | Text generation, summarization, code      |
| **Diffusion Model**                      | Thêm noise rồi học cách loại bỏ noise để tạo image/video                              | Stable Diffusion, DALL-E, Amazon Titan Image, Amazon Nova Canvas | Image/video generation                    |
| **GAN (Generative Adversarial Network)** | Generator tạo fake data, Discriminator phân biệt real/fake. Cả hai cải thiện lẫn nhau | StyleGAN                                                         | Synthetic data generation, image creation |
| **VAE (Variational Autoencoder)**        | Encode data vào latent space rồi decode ra                                            | Various                                                          | Data compression, anomaly detection       |

**Đề thi**: "Generate synthetic data" → GAN. "Generate images from text" → Diffusion model. "Fill in missing text" → Masked Language Model (BERT-type).

### 1.1.5 Các Loại ML — Supervised, Unsupervised, Reinforcement

**Supervised Learning (Học có giám sát)**:
- Dữ liệu có labels (nhãn). Model học mapping input → output.
- **Classification**: Dự đán category. Binary (yes/no, fraud/not fraud) hoặc Multi-class (cat/dog/bird, 20 geneo categories).
  - Algorithms: Logistic Regression, Decision Tree, Random Forest, XGBoost, Neural Networks, SVM.
  - **Decision Tree**: Dễ giải thích (interpretable), tạo rules dạng if-then, tốt cho multi-class + cần explainability.
  - **Logistic Regression**: Binary classification, interpretable, simple.
  - **XGBoost**: Gradient boosting, rất hiệu quả cho tabular data, SageMaker built-in algorithm.
  - **Random Forest**: Ensemble of decision trees, giảm overfitting.
- **Regression**: Dự đoán giá trị liên tục (giá nhà, doanh thu, nhiệt độ).
  - Algorithms: Linear Regression, Polynomial Regression, XGBoost Regression.
- **Đề thi**: "Predict customer churn (yes/no)" → Binary Classification. "Classify genes into 20 categories" → Multi-class Classification → Decision Tree (nếu cần explainability). "Predict product price" → Regression.

**Unsupervised Learning (Học không giám sát)**:
- Dữ liệu KHÔNG có labels. Model tìm patterns/structures ẩn.
- **Clustering**: Nhóm data tương tự. K-Means là algorithm phổ biến nhất.
  - **Đề thi**: "Group customers by demographics and buying patterns" → K-Means Clustering. "Petabytes of unlabeled data, classify customers into tiers" → Unsupervised learning → Clustering.
- **Dimensionality Reduction**: Giảm số features. PCA (Principal Component Analysis) phổ biến nhất.
- **Anomaly Detection**: Phát hiện outliers.

**Reinforcement Learning (Học tăng cường)**:
- Agent tương tác với environment, nhận rewards/penalties, học optimal policy.
- **Self-improvement through interaction** — model learns from trial and error.
- **RLHF (Reinforcement Learning from Human Feedback)**: Humans đánh giá LLM outputs → train reward model → fine-tune LLM. Dùng để align LLMs với human preferences.
- **Đề thi**: "Chatbot tự cải thiện từ past interactions" → Reinforcement Learning. "Model learns from human feedback" → RLHF.

**Semi-supervised Learning**: Kết hợp ít labeled data + nhiều unlabeled data. Model học patterns từ unlabeled, dùng labels để refine.

**Transfer Learning**: Dùng pre-trained model (đã learn general features), adapt cho new task với ít data. Tránh train from scratch. **Đề thi**: "Adapt pre-trained model for new related task without training from scratch" → Transfer Learning.

### 1.1.6 Các Loại Dữ Liệu

| Loại | Mô tả | Ví dụ | Algorithm |
|------|--------|-------|-----------|
| **Tabular/Structured** | Rows/columns, schema rõ ràng | Database, CSV, spreadsheets | XGBoost, Random Forest, Linear/Logistic Regression |
| **Unstructured** | Không có schema | Text, images, audio, video | Neural Networks, CNN, RNN, Transformers |
| **Time-series** | Dữ liệu theo thời gian | Stock prices, sales/day, sensor data | DeepAR, Prophet, ARIMA |
| **Image** | Pixel data | Photos, scans, satellite | CNN (Convolutional Neural Network), Rekognition |
| **Text** | Natural language | Documents, reviews, emails | NLP, Transformers, Comprehend |
| **Labeled** | Có target/nhãn | Email + "spam" tag | Supervised Learning |
| **Unlabeled** | Chưa có nhãn | Raw photos | Unsupervised Learning |

**Đề thi**: "DeepAR forecasting cần loại data nào?" → Time-series data. "Phân loại ảnh côn trùng" → Image data. "Unsupervised, unlabeled customer data" → Clustering.

### 1.1.7 Tokenization

Quá trình chia text thành đơn vị nhỏ (tokens) để model xử lý. Tokens có thể là words, subwords, hoặc characters.

Ví dụ: "I love AWS" → ["I", " love", " AWS"] (3 tokens). Tiếng Việt/CJK: 1 ký tự có thể = 2-3 tokens.

Quan trọng vì: Chi phí API tính per token, context window = max tokens.

### 1.1.8 Inference Types (Rất hay thi)

| Type             | Latency         | Use Case                           | SageMaker                      |
| ---------------- | --------------- | ---------------------------------- | ------------------------------ |
| **Real-time**    | Milliseconds    | Chatbot, recommendation            | SageMaker Real-time Endpoints  |
| **Batch**        | Hours           | Daily reports, bulk predictions    | SageMaker Batch Transform      |
| **Asynchronous** | Seconds–minutes | Large payloads, long processing    | SageMaker Async Inference      |
| **Serverless**   | Variable        | Unpredictable traffic, pay-per-use | SageMaker Serverless Inference |

**Đề thi rất hay hỏi loại inference**:
- "Gigabytes data, 1 lần/ngày, không cần kết quả ngay" → **Batch inference**.
- "Chatbot cần response ngay lập tức" → **Real-time inference**.
- "Large payload 1GB, processing 1 hour, near real-time" → **Asynchronous inference**.
- "Traffic không ổn định, minimize cost" → **Serverless inference**.
- "Weekend batch job, gigabytes text" → **Batch inference**.

---

## 1.2 AWS AI/ML Services (Rất quan trọng — Hay thi)

### 1.2.1 AWS AI Services (Pre-built, No ML expertise needed)

| Service                              | Chức năng                                                                                                   | Use Case trong đề thi                                  |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **Amazon Comprehend**                | NLP: sentiment analysis, entity recognition, key phrases, language detection, PII detection, topic modeling | "Phân tích sentiment customer reviews"                 |
| **Amazon Comprehend Medical**        | NLP cho medical text: extract medical entities, medications, dosages                                        | "Extract medical information from clinical notes"      |
| **Amazon Transcribe**                | Speech-to-Text (ASR)                                                                                        | "Convert call center audio to text"                    |
| **Amazon Transcribe Medical**        | Speech-to-Text cho medical dictation                                                                        | "Transcribe doctor-patient conversations"              |
| **Amazon Translate**                 | Real-time machine translation (75+ languages)                                                               | "Translate product descriptions to multiple languages" |
| **Amazon Polly**                     | Text-to-Speech (neural voices)                                                                              | "Create voice responses for app"                       |
| **Amazon Lex**                       | Build chatbot/voice bot with NLU + ASR                                                                      | "Build customer service chatbot"                       |
| **Amazon Rekognition**               | Image/video: object detection, face analysis, content moderation, text in images                            | "Content moderation", "Identify animals in photos"     |
| **Amazon Rekognition Custom Labels** | Train custom image classification models without ML expertise                                               | "Custom image classification with UI"                  |
| **Amazon Textract**                  | OCR++: Extract text, tables, forms, handwriting from documents                                              | "Process invoices", "Convert PDF resumes to text"      |
| **Amazon Kendra**                    | Enterprise intelligent search                                                                               | "Search internal knowledge base"                       |
| **Amazon Personalize**               | Real-time recommendation engine                                                                             | "Product recommendations", "Content personalization"   |
| **Amazon Fraud Detector**            | Online fraud detection using ML                                                                             | "Detect credit card fraud"                             |
| **Amazon Forecast**                  | Time-series forecasting                                                                                     | "Predict product demand"                               |

**Đề thi critical mappings**:
- "Analyze customer call recordings → extract key info" → **Transcribe** (audio→text) + **Comprehend** (extract insights).
- "Build app that hears users and responds with voice" → **Transcribe** (hear) + **Polly** (speak) + **Lex** (understand intent).
- "Detect harmful language in social media without labeled data" → Dùng **Comprehend** sentiment/toxicity detection.
- "Automatically categorize feedback (product quality, service, delivery)" → **NLP Classification** → Comprehend custom classification.
- "Convert PDF resumes to plain text" → **Textract**.

### 1.2.2 Amazon SageMaker Ecosystem (Hay thi nhất)

| Component                    | Chức năng                                                                 | Câu hỏi đề thi                                                                            |
| ---------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **SageMaker Studio**         | IDE web-based cho ML workflow                                             | -                                                                                         |
| **SageMaker Canvas**         | **No-code ML** cho business users, drag-and-drop                          | "Build ML model without writing code", "Minimal ML knowledge, predict employee attrition" |
| **SageMaker Autopilot**      | **AutoML** — tự động thử algorithms, tune, chọn best model                | "Fully automated model tuning"                                                            |
| **SageMaker JumpStart**      | Thư viện pre-trained models, FMs, solution templates. Deploy 1 click.     | "Deploy foundation model within VPC", "Deploy open-source LLM"                            |
| **SageMaker Data Wrangler**  | Chuẩn bị/transform data bằng GUI, không cần code nhiều                    | "Prepare data with visual interface"                                                      |
| **SageMaker Feature Store**  | Kho lưu trữ & quản lý features, share giữa teams                          | "Share and manage variables across teams"                                                 |
| **SageMaker Ground Truth**   | Data labeling (human + ML-assisted)                                       | "User-friendly interface for data labeling"                                               |
| **SageMaker Clarify**        | **Detect bias** + **Explainability** (SHAP values)                        | "Detect bias in data/model", "Explain model predictions", "Feature importance"            |
| **SageMaker Model Monitor**  | Giám sát model trong production: data drift, model drift, bias drift      | "Monitor model performance over time", "Detect data drift"                                |
| **SageMaker Model Cards**    | Documentation cho model: metadata, intended use, performance, limitations | "Document model for governance/audit", "Transparency to stakeholders"                     |
| **SageMaker Model Registry** | Version control, approval workflows cho models                            | "Store, manage, version models"                                                           |
| **SageMaker Pipelines**      | CI/CD cho ML workflows                                                    | "Automate ML pipeline", "MLOps"                                                           |
| **SageMaker Neo**            | Compile models cho edge devices                                           | "Optimize model for edge deployment"                                                      |
| **SageMaker Edge Manager**   | Deploy & manage models on edge devices                                    | "Manage ML models on edge"                                                                |

**Đề thi critical distinctions**:
- **Canvas vs Autopilot**: Canvas = no-code GUI cho business users. Autopilot = AutoML cho data scientists (generates notebooks).
- **Clarify vs Model Monitor**: Clarify = detect bias & explain predictions (pre/post-training). Model Monitor = continuous monitoring in production (data drift, model quality, bias drift over time).
- **Model Cards vs Model Registry**: Cards = documentation (describe what model does). Registry = storage/versioning (manage model artifacts & approval workflows).
- **Feature Store vs Data Wrangler**: Feature Store = lưu trữ features cho sharing/reuse. Data Wrangler = transform/prepare raw data.

### 1.2.3 AWS Custom AI Chips (Hay thi)

| Chip                            | Mục đích                    | Đặc điểm                                                                                             |
| ------------------------------- | --------------------------- | ---------------------------------------------------------------------------------------------------- |
| **AWS Trainium (Trn series)**   | **Training** ML/DL models   | Performance-per-watt tốt nhất, ít tác động môi trường nhất khi train LLMs. EC2 Trn1, Trn2 instances. |
| **AWS Inferentia (Inf series)** | **Inference** ML models     | Tối ưu cho inference workloads, lower cost vs GPU. EC2 Inf1, Inf2 instances.                         |
| **AWS Graviton**                | General compute (ARM-based) | CPU tốt cho general workloads, không chuyên cho ML.                                                  |

**Đề thi**: "Train LLM với LEAST environmental effect" → **EC2 Trn series (Trainium)**. "Cost-effective inference" → **Inferentia**. Đừng nhầm: GPU (P series, G series) đắt hơn và tiêu thụ điện hơn Trainium.

---

## 1.3 ML Pipeline & MLOps

### 1.3.1 ML Pipeline Stages

1. **Data Collection**: Thu thập từ databases, APIs, S3, streaming.
2. **EDA (Exploratory Data Analysis)**: Khám phá data — distributions, correlations, missing values, outliers. Tạo correlation matrix, statistics, visualizations. **Đề thi**: "Company created correlation matrix, calculated statistics, visualized data" → đang ở giai đoạn **EDA**.
3. **Data Pre-processing**: Cleaning, normalization, handling missing values, encoding.
4. **Feature Engineering**: Tạo/chọn features. → Data Wrangler, Feature Store.
5. **Model Training**: Chọn algorithm, train. → SageMaker Training Jobs.
6. **Hyperparameter Tuning**: Tối ưu hyperparameters. → SageMaker Automatic Model Tuning / Autopilot.
7. **Evaluation**: Test trên validation/test set. Metrics: accuracy, F1, AUC, RMSE.
8. **Deployment**: Deploy endpoint. → SageMaker Endpoints.
9. **Monitoring**: Detect drift, degradation. → Model Monitor, CloudWatch.

### 1.3.2 Model Performance Metrics (Rất hay thi)

**Classification Metrics:**

| Metric                   | Công thức                               | Ý nghĩa                                    | Khi nào dùng                                        |
| ------------------------ | --------------------------------------- | ------------------------------------------ | --------------------------------------------------- |
| **Accuracy**             | (TP+TN)/(TP+TN+FP+FN)                   | % dự đoán đúng tổng thể                    | Balanced datasets                                   |
| **Precision**            | TP/(TP+FP)                              | Trong predicted positive, bao nhiêu đúng?  | Khi false positive costly (spam filter)             |
| **Recall (Sensitivity)** | TP/(TP+FN)                              | Trong actual positive, bao nhiêu detected? | Khi false negative costly (cancer detection, fraud) |
| **F1 Score**             | 2×(Precision×Recall)/(Precision+Recall) | Harmonic mean, cân bằng P & R              | Imbalanced datasets, cần balance cả hai             |
| **AUC-ROC**              | Area Under ROC Curve                    | Khả năng phân biệt classes                 | Overall classification quality                      |
| **Specificity**          | TN/(TN+FP)                              | Trong actual negative, bao nhiêu detected? | Complement of Recall                                |

**Confusion Matrix**: Bảng 2x2 cho binary classification:

|                     | Predicted Positive  | Predicted Negative  |     |
| ------------------- | ------------------- | ------------------- | --- |
| **Actual Positive** | True Positive (TP)  | False Negative (FN) |     |
| **Actual Negative** | False Positive (FP) | True Negative (TN)  |     |

**Đề thi**:
- "Minimize time reviewing false positives in fraud detection" → **Precision** (maximize precision = minimize FP).
- "How many images classified correctly" → **Accuracy**.
- "Binary classification (churn prediction)" → **F1 Score hoặc AUC-ROC**.
- "Ratio correctly classified / total" → **Accuracy**.
- "Balance detecting and labeling classes" → **F1 Score**.
- "Evaluate model on churn vs actual behavior after 1 week" → **Accuracy** hoặc **F1**.

**Regression Metrics:**

| Metric | Ý nghĩa |
|--------|---------|
| **RMSE** | Sai số trung bình root-squared. Nhạy outliers. |
| **MAE** | Trung bình absolute error. Ít nhạy outliers. |
| **R²** | % variance explained. 1.0 = perfect fit. |

### 1.3.3 Overfitting vs Underfitting (Rất hay thi)

**Overfitting (High Variance)**: Model quá phức tạp, "memorize" training data gồm cả noise. Performance tốt trên training, kém trên test/production.
- **Dấu hiệu đề thi**: "Model performed well on training but poorly on new data / in production" → Overfitting.
- **Giải pháp**: Tăng training data volume (đa dạng hơn), regularization (L1/L2), dropout, cross-validation, early stopping, data augmentation, giảm model complexity.
- **Đề thi answer**: "Increase the volume of data used in training" hoặc "Increase regularization parameter to decrease model complexity".

**Underfitting (High Bias)**: Model quá đơn giản, không capture patterns. Kém cả trên training lẫn test.
- Giải pháp: Tăng model complexity, thêm features, giảm regularization, train longer.

### 1.3.4 Data Drift & Model Monitoring

**Data Drift**: Distribution của input data thay đổi so với training data. VD: customer behavior thay đổi theo mùa.

**Model Drift**: Model performance giảm theo thời gian do data drift hoặc concept drift.

**Khi detect drift**: Retrain model trên data mới, update training dataset, adjust features.

**Đề thi**: "Data drift beyond threshold detected by Model Monitor" → Retrain model. "Company wants to keep FM relevant with most recent data" → Regular retraining / Continued pre-training.

### 1.3.5 MLOps Concepts

- **Experimentation**: Track experiments, parameters, metrics. → SageMaker Experiments.
- **Reproducibility**: Version data, code, models.
- **CI/CD for ML**: Automate training → testing → deployment. → SageMaker Pipelines.
- **Infrastructure as Code (IaC)**: Reproducible ML infrastructure. Benefit: consistent, version-controlled deployments.
- **Model Re-training**: Trigger retrain khi performance giảm.

---

# DOMAIN 2: FUNDAMENTALS OF GENERATIVE AI (24%)

---

## 2.1 Key Terminology (Hay thi)

| Thuật ngữ             | Giải thích                                                                                                                     | Đề thi                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| **Token**             | Đơn vị xử lý nhỏ nhất (~¾ word). Cost tính per token.                                                                          | "What are tokens?" → Basic units LLMs process                                  |
| **Embedding**         | Vector (mảng số) biểu diễn meaning trong high-dimensional space. Semantically similar items → vectors gần nhau.                | "Numerical representations of real-world objects" → Embeddings                 |
| **Vector**            | Mảng số đại diện cho embedding. Lưu trong vector database cho similarity search.                                               | "Embeddings stored as vectors for search"                                      |
| **Vector Database**   | Database lưu và query embeddings.                                                                                              | OpenSearch, Aurora pgvector, Neptune                                           |
| **Chunking**          | Chia document thành đoạn nhỏ cho RAG processing. Chunk size ảnh hưởng quality: quá lớn → mất precision, quá nhỏ → mất context. | "Purpose of chunking in RAG" → Break documents for efficient retrieval         |
| **Context Window**    | Max tokens model xử lý trong 1 request (input + output). Lớn hơn = xử lý documents dài hơn.                                    | "How much info fits in one prompt" → Context window                            |
| **Latent Space**      | Không gian ẩn nơi model biểu diễn data dưới dạng compact/abstract.                                                             | Model latent space concept                                                     |
| **Tokenization**      | Quá trình chia text thành tokens.                                                                                              | "What is tokenization used for in NLP?" → Breaking text into processable units |
| **Prompt**            | Input text gửi cho model.                                                                                                      | -                                                                              |
| **Foundation Model**  | Pre-trained model lớn, adaptable cho nhiều tasks.                                                                              | -                                                                              |
| **Multi-modal Model** | Model xử lý nhiều loại data (text + image + audio).                                                                            | "Search app handles text AND images" → Multi-modal FM                          |

### 2.2 Inference Parameters (Rất hay thi)

| Parameter           | Ảnh hưởng                  | Low value                          | High value                |
| ------------------- | -------------------------- | ---------------------------------- | ------------------------- |
| **Temperature**     | Randomness/creativity      | Deterministic, consistent, focused | Creative, diverse, random |
| **Top-p (nucleus)** | Probability mass cutoff    | Narrow, focused responses          | Wider, more varied        |
| **Top-k**           | Number of candidate tokens | Less diverse                       | More diverse              |
| **Max tokens**      | Output length limit        | Shorter responses                  | Longer responses          |
| **Stop sequences**  | Dừng generation            | -                                  | -                         |

**Đề thi CRITICAL patterns**:
- "More consistent, deterministic, stable responses" → **Decrease temperature** (hoặc set = 0).
- "More creative, diverse outputs" → **Increase temperature**.
- "Reduce hallucinations" → **Decrease temperature**.
- "As deterministic as possible" → **Set temperature to 0**.
- "Which parameter controls number of next words considered?" → **Top-k**.

**Stable Diffusion specific**: **CFG Scale (Classifier-Free Guidance)** — cao hơn = ảnh bám sát prompt hơn (more specific). "Increase specificity of generated images" → **Increase CFG scale**.

**Negative Prompts**: Chỉ định những gì KHÔNG muốn trong output (đặc biệt cho image generation). "Model generates unrelated images" → **Use negative prompts** để exclude unwanted elements.

---

## 2.3 AWS Generative AI Services

### 2.3.1 Amazon Bedrock (Core service — Hay thi nhất)

Fully managed service xây dựng generative AI apps bằng foundation models.

**Foundation Models Available:**
- **Amazon Titan**: Text (Titan Text), Image (Titan Image Generator), Embeddings (Titan Embeddings). AWS-owned.
- **Amazon Nova**: Nova Canvas (image generation), Nova family.
- **Anthropic Claude**: Strong reasoning, long context.
- **Meta Llama**: Open-source family.
- **Mistral**: Efficient, multilingual.
- **Cohere**: Text generation, embeddings.
- **AI21 Labs Jurassic**: Text generation.
- **Stability AI Stable Diffusion**: Image generation.

**Bedrock Features:**

| Feature                    | Chức năng                                                                                        | Đề thi                                                               |
| -------------------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| **Knowledge Bases**        | RAG — upload docs → auto chunk/embed → vector store → retrieve at query time                     | "Add company context cost-effectively" → Knowledge Bases             |
| **Agents**                 | Orchestrate multi-step tasks: reasoning → tool calling → knowledge base access → response        | "Agent helps check claims, find details, access documents"           |
| **Guardrails**             | Content filtering: harmful/toxic content, PII, denied topics, word filters, contextual grounding | "Filter harmful content", "Ensure appropriate for children"          |
| **Fine-tuning**            | Custom model training (Instruction tuning, Continued Pre-training)                               | "Customize FM for domain"                                            |
| **Model Evaluation**       | Compare models: automatic evaluation (metrics) + human evaluation                                | "Evaluate which model employees prefer"                              |
| **Provisioned Throughput** | Reserved capacity for consistent performance. **Required for custom models on Bedrock.**         | "Use custom model on Bedrock" → Must purchase Provisioned Throughput |
| **On-Demand Pricing**      | Pay per token, no commitment. Flexible.                                                          | "Limited budget, no long-term commitment" → On-Demand                |
| **Invocation Logging**     | Log model I/O to CloudWatch or S3                                                                | "Store invocation logs to monitor I/O" → Enable invocation logging   |

**Bedrock Pricing**: On-Demand (per token, flexible, no commitment) vs Provisioned Throughput (reserved, steady workload, required for custom models).

**Đề thi**: "Custom model on Bedrock, steady rate of requests, MOST cost-effective" → **Provisioned Throughput**. "Limited budget, flexibility" → **On-Demand**. "Reduce monthly cost of few-shot prompting with 10 examples" → **Reduce number of examples** (less tokens = less cost).

### 2.3.2 Amazon Q

| Variant                    | Chức năng                                                                                       | Đề thi                                                                                    |
| -------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Amazon Q Business**      | Enterprise AI assistant — search internal docs (SharePoint, S3, Confluence), Q&A, summarization | "AI assistant for employees to query internal data"                                       |
| **Amazon Q Developer**     | Code assistant — generation, debugging, explanation, security scanning, transformation          | "Increase developer productivity"                                                         |
| **Amazon Q in QuickSight** | NLP queries trên business data, auto-generate dashboards                                        | "Display total sales graphs automatically", "Build SQL from text for non-technical users" |

### 2.3.3 SageMaker JumpStart

- Deploy pre-trained FMs (Llama, Mistral, Falcon, FLAN-T5, Stable Diffusion...) nhanh chóng.
- Fine-tune trên custom data.
- Deploy within **VPC** (quan trọng cho compliance).
- **Đề thi**: "Deploy FM within VPC quickly" → JumpStart. "Rapidly deploy open-source model" → JumpStart.

### 2.3.4 PartyRock

- No-code playground thử nghiệm generative AI. Miễn phí.
- **Đề thi**: "Learn about generative AI in experimental environment, MOST cost-effectively" → **PartyRock**.

---

## 2.4 Foundation Model Customization (Cost Tradeoffs — Rất hay thi)

Sắp xếp từ rẻ → đắt, ít effort → nhiều effort:

| #   | Approach                      | Chi phí    | Data cần                                  | Khi nào                                    | Đề thi                                        |
| --- | ----------------------------- | ---------- | ----------------------------------------- | ------------------------------------------ | --------------------------------------------- |
| 1   | **Prompt Engineering**        | Thấp nhất  | 0                                         | Thay đổi behavior bằng prompt              | "Quick change without training"               |
| 2   | **In-Context Learning**       | Thấp       | Vài examples trong prompt                 | Cần format/style consistency               | "Provide examples to agent"                   |
| 3   | **RAG**                       | Trung bình | Documents (không cần labeled)             | Thêm external knowledge, real-time updates | "Add company docs, cost-effective"            |
| 4   | **Fine-tuning**               | Cao        | Labeled dataset (prompt+completion pairs) | Domain-specific style, terminology         | "100 examples of conversations to match tone" |
| 5   | **Continued Pre-training**    | Rất cao    | Massive unlabeled domain data             | Entire new domain vocabulary               | "Adapt FM to complex scientific terms"        |
| 6   | **Pre-training from scratch** | Cao nhất   | Enormous dataset                          | Build custom FM                            | Rarely needed                                 |

**Fine-tuning Data Format**: **Labeled data** dạng JSONL với fields: prompt (input) + completion (desired output). **Đề thi**: "How should company prepare training data for instruction-based fine-tuning?" → **Labeled data with prompt field and completion field**.

**Fine-tuning on Bedrock Security**: Data stays within VPC, encrypted, không share cross-customers. **Đề thi**: "Data stays private, safe, secure in source Region" → Fine-tune on Bedrock.

**Continued Pre-training Benefits**: Model học new domain knowledge, improve performance over time, keep model relevant. **Đề thi**: "Keep FM relevant with most recent data" → Regular continued pre-training / retraining.

---

## 2.5 Small Language Models (SLMs) & Edge

- **SLM**: Models nhỏ (millions vs billions parameters), optimized cho edge devices.
- Deploy trực tiếp trên device → **lowest latency** (no network roundtrip).
- Optimized via: quantization, pruning, knowledge distillation.
- **Đề thi**: "Inference on edge devices with lowest latency" → **Deploy optimized SLMs on edge devices**.
- KHÔNG deploy LLMs on edge (quá lớn, resource constraints).

---

# DOMAIN 3: APPLICATIONS OF FOUNDATION MODELS (28%)

Domain lớn nhất — RAG, Prompt Engineering, Fine-tuning, Evaluation.

---

## 3.1 RAG (Retrieval Augmented Generation) — Hay thi nhất

### 3.1.1 RAG Pipeline

1. **Ingestion (Offline batch processing)**:
   - Documents → **Chunking** → **Embedding model** → Vectors → **Vector database**.
   - Steps: chunk documents + generate embeddings = offline batch steps.
2. **Query (Online)**:
   - User question → Embed question → **Similarity search** in vector DB → Retrieve relevant chunks.
3. **Augmentation**: Attach retrieved chunks to LLM prompt as context.
4. **Generation**: LLM generates grounded response.

### 3.1.2 AWS RAG Implementation

- **Bedrock Knowledge Bases**: Managed RAG. Upload docs to S3 → auto chunk → embed (Titan Embeddings) → store (OpenSearch Serverless) → retrieve + respond.
- **Vector DB options**: OpenSearch Service (k-NN plugin), Aurora (pgvector), Neptune, DocumentDB, RDS PostgreSQL (pgvector), MemoryDB.
- **Đề thi**: "Store embeddings in vector database" → **Amazon OpenSearch Service** (most frequent answer). "Which feature of OpenSearch gives vector database ability?" → **k-NN plugin**.

### 3.1.3 RAG Benefits

- Giảm hallucination (grounded in real documents).
- No model retraining needed → cost-effective.
- Knowledge updates real-time (add/remove docs).
- Source citation possible.
- **Đề thi**: "Improve accuracy of FM responses cost-effectively" → **RAG / Knowledge Bases**. "Company policies updated frequently, chatbot must reflect changes near real-time" → **RAG** (not fine-tuning). "Decrease hallucinations" → **Implement RAG**. "Advantage of RAG for NLP?" → Access up-to-date info without retraining.

---

## 3.2 Prompt Engineering (Hay thi)

### 3.2.1 Techniques

| Technique                  | Mô tả                             | Đề thi Use Case                                                                                                       |
| -------------------------- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **Zero-shot**              | Chỉ instruction, không example    | Simple tasks model hiểu sẵn                                                                                           |
| **One-shot / Single-shot** | 1 example                         | Basic format guidance                                                                                                 |
| **Few-shot**               | 2-5+ examples                     | "100 examples → match tone", "Provide specific examples to improve accuracy", "Generate descriptions matching format" |
| **Chain-of-Thought (CoT)** | "Think step by step"              | "Complex problem-solving", "Numerical reasoning", "Detailed reasoning + step-by-step explanation"                     |
| **Prompt Templates**       | Reusable templates with variables | Standardize across applications                                                                                       |
| **Negative Prompts**       | Specify what NOT to include       | "Decrease unrelated images"                                                                                           |

**Đề thi specific**:
- "Classify sentiment positive/negative with examples" → **Few-shot prompting** (provide labeled examples in prompt).
- "Complex math/reasoning problems" → **Chain-of-Thought**.
- "Break complex task into smaller subtasks sent sequentially" → **Prompt chaining** (related to CoT).
- "Improve agent accuracy by providing specific examples" → **Few-shot** (add examples to agent prompt).
- "Generate descriptions matching a format" → **Few-shot** (give format examples).

### 3.2.2 Prompt Risks & Attacks (Hay thi)

| Risk                            | Mô tả                                                                          | Đề thi                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------- |
| **Prompt Injection**            | Malicious input thay đổi model behavior. VD: "Ignore previous instructions..." | "Prevent LLM from being manipulated" → Guardrails, input validation             |
| **Prompt Jailbreaking**         | Bypass safety filters. VD: "Pretend you have no restrictions"                  | "Testing to get around safety features and make harmful content" → Jailbreaking |
| **Prompt Leaking / Extraction** | Trích xuất system prompt/instructions                                          | "Directly exposes configured behavior" → Extracting the prompt template         |
| **Prompt Poisoning**            | Manipulate training data để corrupt model behavior                             | Data-level attack during training                                               |

**Mitigation**: Guardrails for Bedrock, input validation, output filtering, regular testing.

---

## 3.3 Bedrock Agents (Multi-step Tasks)

Agents cho phép FM thực hiện complex, multi-step tasks:
1. Parse user request → plan steps.
2. Call **Action Groups** (external APIs, Lambda functions).
3. Access **Knowledge Bases** for context.
4. Chain multiple steps.
5. Return final response.

**Đề thi**: "Check open customer claims, identify details, access documents" → **Bedrock Agents**. "Key benefits of Bedrock Agents for retailer" → Automated multi-step task execution, integration with existing systems.

---

## 3.4 Evaluating Foundation Models (Hay thi)

### 3.4.1 Automated Metrics

| Metric         | Dùng cho                | Mô tả                                                                                                                                  | Đề thi                                                                        |
| -------------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **ROUGE**      | **Summarization**       | So sánh n-gram overlap giữa generated và reference summary. ROUGE-1 (unigram), ROUGE-2 (bigram), ROUGE-L (longest common subsequence). | "Evaluate text summarization quality" → ROUGE                                 |
| **BLEU**       | **Translation**         | So sánh n-gram precision giữa translation và reference.                                                                                | "Evaluate translation accuracy" → BLEU                                        |
| **BERTScore**  | **Semantic similarity** | Dùng BERT embeddings đo semantic similarity. Captures meaning tốt hơn ROUGE/BLEU.                                                      | "Evaluate if output resembles provided examples" → BERTScore                  |
| **Perplexity** | Language modeling       | Model's uncertainty. Lower = better.                                                                                                   | "Runtime efficiency of operating AI models" → related to inference efficiency |
| **F1 Score**   | Classification          | Balance of precision and recall                                                                                                        | "F1 score in FM performance" → Balance precision & recall                     |

**Đề thi critical mapping**:
- "Summarization task evaluation" → **ROUGE**.
- "Translation quality comparison" → **BLEU**.
- "LLM output should resemble provided examples" → **BERTScore** (semantic similarity).
- "Fine-tuned model accuracy evaluation" → **BLEU or ROUGE** depending on task.

### 3.4.2 Human Evaluation & Bedrock Model Evaluation

- **Human evaluation**: Humans rate output quality, relevance, tone preference.
- **Amazon Bedrock Model Evaluation**: Automatic (ROUGE, BLEU, BERTScore, accuracy, robustness, toxicity) + Human (preference ranking).
- **Benchmark datasets**: Standard test sets cho model comparison.
- **Đề thi**: "Identify model employees prefer" → **Human evaluation** qua Bedrock Model Evaluation. "Evaluate LLM with least admin effort" → **Built-in Bedrock automatic evaluation with benchmark datasets**.

### 3.4.3 Business Metrics

- Productivity, user engagement, conversion rate, average revenue per user, customer lifetime value, cost per user, ROI.
- **Đề thi**: "Evaluate effect of LLM chatbot on call center" → **Decrease in actions employees need to take** (operational efficiency).
- "Assess FM alignment with specific use cases" → **Stakeholder interviews to refine use cases and set measurable goals**.

---

## 3.5 Model Selection Criteria

| Tiêu chí | Ý nghĩa | Đề thi |
|----------|---------|--------|
| **Context window** | Max tokens per request | "How much info fits in prompt", "App fails to summarize some books" → **Input exceeds context size** |
| **Latency** | Response speed | "Real-time app needs fast responses" → Choose low-latency model |
| **Cost** | Per-token pricing | Budget constraints → smaller model hoặc on-demand |
| **Modality** | Text, image, multi-modal | "Handle text AND images" → Multi-modal FM |
| **Model size** | Parameters count | Larger = more capable but slower/costlier |
| **Multi-lingual** | Language support | International apps |
| **Customization** | Fine-tuning support | Domain adaptation needs |

**Đề thi**: "App fails to summarize some books" → **Input tokens exceed model's context size** (some books too long).

---

# DOMAIN 4: GUIDELINES FOR RESPONSIBLE AI (14%)

---

## 4.1 Responsible AI Principles

| Feature                   | Mô tả                                                            | Đề thi                                                                         |
| ------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Fairness**              | Model không discriminate based on protected attributes           | "Ensure equitable hiring decisions"                                            |
| **Bias**                  | Systematic error from data/model                                 | "Model flags specific ethnic group disproportionately" → Bias                  |
| **Inclusivity**           | AI phục vụ đa dạng users, diverse datasets                       | "Diverse dataset from different genders, ethnicities, locations" → Inclusivity |
| **Robustness**            | Model resists adversarial attacks, performs in varied conditions | "Model works across different scenarios"                                       |
| **Safety**                | AI không gây hại                                                 | "Ensure appropriate for children"                                              |
| **Veracity/Truthfulness** | Output accurate, không hallucinate                               | "Factual responses for regulatory compliance"                                  |
| **Transparency**          | Users hiểu how AI works                                          | "Make decision-making process transparent"                                     |
| **Explainability**        | Có thể giải thích WHY specific prediction                        | "Explain loan approval decisions" → Explainability                             |
| **Privacy**               | Protect personal data                                            | "Remove PII before fine-tuning"                                                |

### 4.1.1 Types of Bias in Đề Thi

- **Training data bias**: Dataset not representative of all demographics. "Resume screening system trained on non-representative data" → **Fairness/Bias dimension**.
- **Selection bias**: Over/under-representation of groups.
- **Societal bias**: Historical prejudices reflected in data.
- **Measurement bias**: Inconsistent data collection.

**Mitigation**: "Balanced and diverse data collection", "Data augmentation to balance underrepresented groups", "SageMaker Clarify for bias detection".

**Đề thi**: "AI generates biased images of professions → input data biased" → **Data augmentation** to balance attributes. "Ensure responsible data collection to decrease bias" → **Ensure data is balanced and collected from diverse group**.

### 4.2 AWS Responsible AI Tools

### 4.2.1 SageMaker Clarify

**Pre-training bias detection**: Analyze training data BEFORE training. Metrics: Class Imbalance, Difference in Proportions.

**Post-training bias detection**: Analyze model predictions AFTER training. Metrics: Disparate Impact, Demographic Parity.

**Explainability**: **SHAP values** (SHapley Additive exPlanations) — quantify contribution of each feature to prediction. "Show how different input features influence model behavior" → **SageMaker Clarify**.

**Feature Importance**: Rank which features most influence model output.

**Đề thi**: "Detect bias AND explain predictions" → **Clarify**. "Feature importance analysis" → **Clarify (SHAP)**. "Identify potential bias during data preparation" → **Clarify**.

### 4.2.2 Guardrails for Amazon Bedrock

**Content Categories (hay thi)**:
- **Hate/Discrimination**: Content targeting protected groups.
- **Violence/Threats**: Harmful or violent content.
- **Sexual content**: Inappropriate sexual material.
- **Insults**: Offensive language.
- **Misconduct**: Instructions for illegal activities.
- **Denied Topics**: Custom blocked topics.
- **PII filtering**: Detect/mask/block personally identifiable information.
- **Word filters**: Block specific words/phrases.
- **Contextual grounding**: Check output factuality.

Áp dụng cho cả **input** (filter user prompts) AND **output** (filter model responses).

**Đề thi**: "Ensure appropriate for children" → **Guardrails**. "Filter harmful content" → **Guardrails**. "Politically influenced ideas in newsletters" → **Denied Topics guardrail**. "Content moderation for chatbot" → **Guardrails**. "Reduce manipulation/prompt injection with LEAST effort" → **Guardrails**.

### 4.2.3 Amazon A2I (Augmented AI)

- **Human review workflows** cho ML predictions.
- Route low-confidence predictions cho human reviewer.
- Define confidence thresholds, adjust over time.
- **Đề thi**: "Build workflows for human review with confidence thresholds" → **Amazon A2I**.
- "Minimize model mistakes on new data" → A2I human review.

### 4.2.4 SageMaker Model Cards

- Document model metadata: purpose, performance metrics, intended use, limitations, ethical considerations.
- **Transparency & accountability** for stakeholders.
- **Đề thi**: "Document model for governance/audit" → **Model Cards**. "Standardized documentation of model version tracking" → **Model Cards** + **Model Registry**. "Transparency and explainability report for stakeholders" → Include **Model Cards**.

### 4.2.5 Amazon Bedrock Watermarking

- Amazon Titan models can add **watermarks** to generated images.
- Invisible watermark identifies AI-generated content.
- **Đề thi**: "Identify if image was generated by Amazon Titan" → Check watermark.

---

## 4.3 Legal & Ethical Risks

| Risk                | Mô tả                                                      |
| ------------------- | ---------------------------------------------------------- |
| **Plagiarism**      | "Student copying AI content for essays" → Plagiarism       |
| **IP Infringement** | Output contains copyrighted content                        |
| **Hallucinations**  | "Content sounds plausible but incorrect" → Hallucination   |
| **Bias**            | Discriminatory outputs                                     |
| **Privacy**         | Exposing PII                                               |
| **Loss of Trust**   | Inaccurate/biased outputs erode confidence                 |
| **Nondeterminism**  | "Different responses for same input" → Nondeterminism risk |

---

# DOMAIN 5: SECURITY, COMPLIANCE, AND GOVERNANCE (14%)

---

## 5.1 Security

### 5.1.1 IAM for AI

- IAM Roles cho SageMaker, Bedrock — principle of least privilege.
- **Bedrock access control**: IAM policies restrict which models employees can access. "Restrict employee access to specific models" → **IAM policies**.
- **SageMaker execution roles**: Control what SageMaker can access (S3, KMS, etc.).
- **Đề thi**: "Control employee access to publicly available FMs" → **IAM policies on Bedrock**. "Restrict access to specific models on Bedrock" → **IAM policies**. "Each team access only own customer data" → **IAM policies with S3 bucket restrictions**.

### 5.1.2 Encryption & Data Privacy

- **At Rest**: KMS encryption cho S3, EBS, model artifacts. **SSE-S3** (S3 managed keys) for data in S3 buckets.
- **In Transit**: TLS/SSL cho API calls.
- **AWS KMS**: Manage encryption keys. "Encrypt model customization job artifacts with company key" → **AWS KMS customer managed key**.
- **Amazon Bedrock data privacy**: Customer data NOT used to train Bedrock models. Data NOT shared across customers. "How Bedrock protects privacy" → Data isolation, not used for model improvement.

### 5.1.3 Network Security

- **VPC Endpoints / PrivateLink**: Access Bedrock/SageMaker APIs privately, NO internet traffic.
- **Đề thi**: "No internet traffic allowed (regulatory compliance)" → **VPC Endpoint for Bedrock**. "API calls must not travel across public internet" → **AWS PrivateLink**. "SageMaker in isolated environment without internet" → **VPC mode with no internet access**.
- **SageMaker VPC mode**: Training/inference jobs within VPC, no internet access. For compliance.

### 5.1.4 Threat Detection

- **AWS CloudTrail**: Audit ALL API calls. "Identify unauthorized users trying to access Bedrock" → **CloudTrail** (audit log of who called what).
- **Amazon Macie**: Detect sensitive data (PII) in **S3 buckets**. "Upload customer emails to S3, detect sensitive info automatically" → **Macie**.
- **Amazon GuardDuty**: Threat detection (IP from suspicious source). "Check if IP from suspicious source" → **GuardDuty**.

### 5.1.5 AI-Specific Security

| Threat               | Mô tả                       | Mitigation                                        |
| -------------------- | --------------------------- | ------------------------------------------------- |
| **Prompt Injection** | Manipulate model via input  | Guardrails, input validation                      |
| **Jailbreaking**     | Bypass safety filters       | Guardrails, regular testing                       |
| **Data Poisoning**   | Corrupt training data       | Data validation, access control                   |
| **Model Extraction** | Reverse-engineer model      | Rate limiting, access control                     |
| **PII Exposure**     | Model reveals personal data | Remove PII before training, Guardrails PII filter |

### 5.1.6 AWS Shared Responsibility for AI

**AWS responsible for**: Infrastructure security, physical security, Bedrock platform security, model hosting.

**Customer responsible for**: Data security, IAM configuration, encryption keys, VPC settings, model selection, prompt design, output validation, responsible AI practices, compliance validation.

**Đề thi**: "Which security aspect is company responsible for when using Bedrock?" → Data encryption, IAM access, VPC configuration, content filtering.

### 5.1.7 Generative AI Security Scoping Matrix

4 Scopes từ ít → nhiều security ownership:

| Scope | Mô tả | Ownership |
|-------|--------|-----------|
| **Scope 1** | Third-party SaaS with embedded AI | Lowest (vendor handles most) |
| **Scope 2** | FM-as-a-Service (like Bedrock base models) | Moderate |
| **Scope 3** | Fine-tuned FM on managed service | High |
| **Scope 4** | Build & train custom model from scratch | **Highest** (full-stack ownership) |

**Đề thi**: "Which scope gives MOST security ownership?" → **Building and training own model** (Scope 4).

---

## 5.2 Compliance & Governance

### 5.2.1 Compliance Standards

| Standard                                                        | Mô tả                        | Đề thi                                                                                      |
| --------------------------------------------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------- |
| **GDPR - General Data Protection Regulation**                   | EU data privacy regulation   | "Financial company expanding to new geographic area" → Review local compliance (GDPR if EU) |
| **HIPAA - Health Insurance Portability and Accountability Act** | US healthcare data           | "Healthcare patient data privacy"                                                           |
| **SOC 1/2/3**                                                   | System controls audit        | General compliance                                                                          |
| **PCI DSS**                                                     | Payment card data            | Financial transactions                                                                      |
| **ISO 27001**                                                   | Info security management     | Security compliance                                                                         |
| **ISO 42001**                                                   | AI management systems        | AI-specific governance                                                                      |
| **Algorithm Accountability Laws**                               | Transparency in AI decisions | Emerging regulations                                                                        |

### 5.2.2 AWS Governance Services

| Service                 | Chức năng                                      | Đề thi                                                                                                 |
| ----------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **AWS CloudTrail**      | Audit API call logs                            | "Log Bedrock API calls", "Retain logs 5 years"                                                         |
| **Amazon CloudWatch**   | Monitor metrics, logs, alarms                  | "Monitor ML system performance at scale"                                                               |
| **AWS Config**          | Track resource configuration, compliance rules | "Track configuration changes"                                                                          |
| **AWS Audit Manager**   | Automated evidence collection for audits       | "Generate compliance reports"                                                                          |
| **AWS Artifact**        | Download compliance reports (SOC, ISO, PCI)    | "ISV compliance reports notifications" → Artifact. "Adherence to international regulations" → Artifact |
| **AWS Trusted Advisor** | Best practice recommendations                  | "Review security best practices"                                                                       |

**Đề thi**: "Log Bedrock API calls, retain 5 years lowest cost" → **CloudTrail + S3 Glacier** (cheapest long-term storage). "Assess compliance requirements" → **AWS Audit Manager + AWS Artifact**.

### 5.2.3 Data Governance Strategies

| Strategy                 | Mô tả                                     | Đề thi                                                      |
| ------------------------ | ----------------------------------------- | ----------------------------------------------------------- |
| **Data Residency**       | Data stays in specific Region             | "Store PII within company's AWS Region" → Data residency    |
| **Data Retention**       | How long data stored before deletion      | "Guidelines for data storage and deletion" → Data retention |
| **Data Lineage**         | Track data origin, transformations, usage | "Document data origins" → Data lineage                      |
| **Data Cataloging**      | Organize metadata                         | AWS Glue Data Catalog                                       |
| **Data Lifecycle**       | End-to-end data management                | Collection → use → archive → deletion                       |
| **Logging & Monitoring** | Record all data access                    | CloudTrail, CloudWatch                                      |

**Data compliance techniques**: "Ensure data compliance and privacy when training AI" → **Data anonymization / de-identification**, **encryption**, **access controls**, **VPC isolation**.

### 5.2.4 Model Governance

- **Model Cards**: Documentation for audit/transparency.
- **Model Registry**: Version control + approval workflows. "Multiple ML models, store/manage/version" → **Model Registry**.
- **ML Lineage Tracking**: Track full lineage from data → training → model → deployment.
- **Governance Frameworks**: Policies, review cadence, team training on responsible AI. "AI governance framework characteristic?" → **Developing policies and guidelines for data, transparency, responsible AI, and compliance**.
- **Đề thi**: "Company wants AI system fair and explainable, require team training" → **Training on bias awareness and responsible AI**.

---

# PHỤ LỤC: BẢNG TỔNG HỢP

---

## Bảng Mapping Service → Use Case (Complete)

| Yêu cầu đề thi                                | Đáp án                                              |
| --------------------------------------------- | --------------------------------------------------- |
| Phân tích sentiment text                      | Amazon Comprehend                                   |
| Extract medical entities from clinical text   | Amazon Comprehend Medical                           |
| Speech → Text                                 | Amazon Transcribe                                   |
| Text → Speech                                 | Amazon Polly                                        |
| Dịch ngôn ngữ                                 | Amazon Translate                                    |
| Build chatbot                                 | Amazon Lex                                          |
| OCR documents, extract tables/forms           | Amazon Textract                                     |
| Convert PDF resumes to text                   | Amazon Textract                                     |
| Image/video analysis, content moderation      | Amazon Rekognition                                  |
| Custom image classification (no ML expertise) | Rekognition Custom Labels                           |
| Enterprise search                             | Amazon Kendra                                       |
| Product recommendations                       | Amazon Personalize                                  |
| Fraud detection ML                            | Amazon Fraud Detector                               |
| Time-series forecasting                       | Amazon Forecast / SageMaker DeepAR                  |
| Deploy foundation model managed API           | Amazon Bedrock                                      |
| RAG + company documents                       | Bedrock Knowledge Bases                             |
| Multi-step AI tasks (orchestration)           | Bedrock Agents                                      |
| Filter harmful/toxic content                  | Guardrails for Amazon Bedrock                       |
| Deploy open-source FM                         | SageMaker JumpStart                                 |
| Deploy FM within VPC                          | SageMaker JumpStart                                 |
| No-code ML (business users)                   | SageMaker Canvas                                    |
| AutoML (automated tuning)                     | SageMaker Autopilot                                 |
| Detect bias + explain predictions             | SageMaker Clarify                                   |
| Feature importance / SHAP                     | SageMaker Clarify                                   |
| Monitor model in production                   | SageMaker Model Monitor                             |
| Detect data drift                             | SageMaker Model Monitor                             |
| Document model metadata                       | SageMaker Model Cards                               |
| Version control models                        | SageMaker Model Registry                            |
| ML pipeline CI/CD                             | SageMaker Pipelines                                 |
| Data labeling                                 | SageMaker Ground Truth                              |
| Share features across teams                   | SageMaker Feature Store                             |
| Data preparation GUI                          | SageMaker Data Wrangler                             |
| AI coding assistant                           | Amazon Q Developer                                  |
| Enterprise AI assistant (internal docs)       | Amazon Q Business                                   |
| NLP dashboard from natural language           | Amazon Q in QuickSight                              |
| Detect PII in S3                              | Amazon Macie                                        |
| Audit API calls                               | AWS CloudTrail                                      |
| Threat detection (suspicious IPs)             | Amazon GuardDuty                                    |
| Private access to Bedrock                     | VPC Endpoint / PrivateLink                          |
| Compliance reports                            | AWS Artifact                                        |
| Automated audit evidence                      | AWS Audit Manager                                   |
| Monitor system metrics                        | Amazon CloudWatch                                   |
| Human review for ML predictions               | Amazon A2I                                          |
| Encrypt model artifacts with own key          | AWS KMS                                             |
| Vector database for embeddings                | Amazon OpenSearch Service                           |
| No-code generative AI playground              | PartyRock                                           |
| Generate images from text                     | Stable Diffusion / Amazon Nova Canvas / Titan Image |
| Train LLM eco-friendly                        | EC2 Trn series (Trainium)                           |
| Cost-effective inference                      | EC2 Inf series (Inferentia)                         |
| AWS Glue help for non-experts                 | Amazon Q Developer                                  |
|                                               |                                                     |

---

## Patterns Câu Hỏi — Quick Reference

### "Which metric?"
- Summarization → **ROUGE**
- Translation → **BLEU**
- Semantic similarity / resemble examples → **BERTScore**
- Classification accuracy → **F1 / AUC-ROC / Accuracy**
- Minimize false positives → **Precision**
- Minimize false negatives → **Recall**
- Balance P & R → **F1**
- Regression error → **RMSE / MAE**
- Total correct / total → **Accuracy**

### "Which inference type?"
- Real-time chatbot → **Real-time**
- Gigabytes daily batch → **Batch**
- 1GB payload, 1 hour processing → **Asynchronous**
- Variable traffic → **Serverless**
- Weekend text processing job → **Batch**

### "Which learning type?"
- Labeled data → **Supervised**
- No labels, group customers → **Unsupervised (Clustering)**
- Agent + rewards → **Reinforcement**
- Pre-trained model, new task → **Transfer Learning**
- Fine-tune with small labeled set → **Fine-tuning** (type of supervised)
- Human feedback → **RLHF**

### "How to reduce hallucination?"
→ RAG, lower temperature, Guardrails grounding, human review

### "How to customize FM cost-effectively?"
→ Prompt engineering (cheapest) → Few-shot → RAG → Fine-tuning (most expensive)

### "Model good on train, bad on production?"
→ **Overfitting** → Increase training data / Regularization

### "Content not appropriate for children?"
→ **Guardrails for Amazon Bedrock**

### "No internet access (compliance)?"
→ **VPC Endpoint** / PrivateLink / SageMaker VPC mode

### "Share features across ML teams?"
→ **SageMaker Feature Store**

### "Explain model predictions?"
→ **SageMaker Clarify** (SHAP values)

### "App fails to summarize some books?"
→ **Context window exceeded** (input too long)

### "Custom model on Bedrock?"
→ Must purchase **Provisioned Throughput**

### "Limited budget, no commitment?"
→ **On-Demand pricing**

### "Documents missing words, predict fill?"
→ **Masked Language Model** (BERT-type)

---

## Thuật Ngữ Hay Bị Nhầm — Extended

| A               | B              | Khác biệt                                                                                 |
| --------------- | -------------- | ----------------------------------------------------------------------------------------- |
| Feature Store   | Data Wrangler  | Store = lưu trữ & share. Wrangler = transform/prepare                                     |
| Clarify         | Model Monitor  | Clarify = detect bias + explain. Monitor = continuous production monitoring               |
| Model Cards     | Model Registry | Cards = documentation. Registry = versioning + approval                                   |
| Knowledge Bases | Agents         | KB = RAG retrieval. Agents = multi-step orchestration                                     |
| RAG             | Fine-tuning    | RAG = external knowledge at runtime, no weight update. Fine-tuning = update model weights |
| ROUGE           | BLEU           | ROUGE = summarization (recall). BLEU = translation (precision)                            |
| Temperature     | Top-p          | Temperature = overall randomness. Top-p = probability cutoff                              |
| Hallucination   | Bias           | Hallucination = false info. Bias = unfair discrimination                                  |
| Injection       | Jailbreaking   | Injection = manipulate via input. Jailbreak = bypass safety                               |
| Extraction      | Injection      | Extraction = reveal system prompt. Injection = change behavior                            |
| JumpStart       | Bedrock        | JumpStart = deploy on SageMaker infra. Bedrock = managed FM API                           |
| Canvas          | Autopilot      | Canvas = no-code GUI. Autopilot = AutoML                                                  |
| Trainium        | Inferentia     | Trainium = training. Inferentia = inference                                               |
| On-Demand       | Provisioned    | On-Demand = pay-per-use. Provisioned = reserved capacity                                  |
| Macie           | GuardDuty      | Macie = sensitive data in S3. GuardDuty = threats/suspicious activity                     |
| CloudTrail      | CloudWatch     | CloudTrail = API audit logs. CloudWatch = metrics/monitoring                              |
| Artifact        | Audit Manager  | Artifact = download compliance reports. Audit Manager = automated evidence collection     |
| Supervised      | Unsupervised   | Supervised = labeled data. Unsupervised = no labels                                       |
| Classification  | Regression     | Classification = categories. Regression = continuous values                               |
| Overfitting     | Underfitting   | Over = too complex, good train/bad test. Under = too simple, bad both                     |
| Precision       | Recall         | Precision = FP costly. Recall = FN costly                                                 |
| GAN             | Diffusion      | GAN = generator+discriminator. Diffusion = noise→denoise                                  |
| Accuracy        | F1             | Accuracy = total correct. F1 = balance P&R (better for imbalanced)                        |
| SLM             | LLM            | SLM = small, edge-friendly. LLM = large, cloud-based                                      |
| Data drift      | Model drift    | Data drift = input changes. Model drift = performance degrades                            |
| Data residency  | Data retention | Residency = where stored. Retention = how long stored                                     |

---

> **Chúc các bạn thi đạt kết quả cao! Điểm mục tiêu: 700+/1000**
