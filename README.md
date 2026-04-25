# AWScerts

Kho này gom note ôn tập và bộ đề review cho các chứng chỉ AWS. Hiện có hai bài thi chính:

- AWS Certified AI Practitioner (AIF-C01)
- AWS Certified Solutions Architect - Associate (SAA-C03)

## Bắt Đầu Nhanh

Nếu bạn mới mở repo lần đầu:

1. Chọn chứng chỉ cần học: `aif-c01/` hoặc `saa-c03/`.
2. Đọc file study guide trước để nắm kiến thức nền.
3. Làm từng đề trong thư mục `review/`.
4. Khi sai câu nào, quay lại study guide theo domain hoặc keyword tương ứng.

## AWS Certified AI Practitioner (AIF-C01)

Thư mục chính: [`aif-c01/`](./aif-c01/)

### Note Nên Đọc Trước

- Bản study guide tổng hợp dạng Markdown:
  [`aif-c01/study-guide/tofumapu-markdown/aif-c01-study-guide.md`](./aif-c01/study-guide/tofumapu-markdown/aif-c01-study-guide.md)

Bản này phù hợp để đọc liên tục từ đầu đến cuối, dùng như tài liệu nền trước khi luyện đề.

### Note Theo Domain

Markdown theo từng domain:

- Domain 1 - Fundamentals of AI and ML:
  [`DOMAIN_1_Fundamentals_of_AI_and_ML.md`](./aif-c01/study-guide/VDHieu0612-markdown/DOMAIN_1_Fundamentals_of_AI_and_ML.md)
- Domain 2 - Fundamentals of Generative AI:
  [`DOMAIN_2_Fundamentals_of_Generative_AI.md`](./aif-c01/study-guide/VDHieu0612-markdown/DOMAIN_2_Fundamentals_of_Generative_AI.md)
- Domain 3 - Applications of Foundation Models:
  [`DOMAIN_3_Applications_of_Foundation_Models.md`](./aif-c01/study-guide/VDHieu0612-markdown/DOMAIN_3_Applications_of_Foundation_Models.md)
- Domain 4 - Guidelines for Responsible AI:
  [`DOMAIN_4_Guidelines_for_Responsible_AI.md`](./aif-c01/study-guide/VDHieu0612-markdown/DOMAIN_4_Guidelines_for_Responsible_AI.md)
- Domain 5 - Security, Compliance, and Governance:
  [`DOMAIN_5_Security_Compliance_and_Governance.md`](./aif-c01/study-guide/VDHieu0612-markdown/DOMAIN_5_Security_Compliance_and_Governance.md)

Note bổ sung:

- AWS AI services, Bedrock, Amazon Q, SageMaker, prompt:
  [`AIF_BonusDomain_Services_Bedrock_Q_SageMaker_Prompt.md`](./aif-c01/study-guide/VDHieu0612-markdown/AIF_BonusDomain_Services_Bedrock_Q_SageMaker_Prompt.md)
- Khái niệm mới/bổ sung:
  [`AIF_Supplement_NewConcepts.md`](./aif-c01/study-guide/VDHieu0612-markdown/AIF_Supplement_NewConcepts.md)

### PDF Để Đọc Offline

PDF theo domain nằm tại:

[`aif-c01/study-guide/VDHieu0612-pdf/`](./aif-c01/study-guide/VDHieu0612-pdf/)

Dùng thư mục này nếu bạn muốn tải về máy, đọc trên tablet, hoặc in ra để ghi chú.

### Bộ Đề Review

Các đề ôn tập AIF-C01 nằm tại:

[`aif-c01/review/`](./aif-c01/review/)

File theo pattern:

```text
AIF-C01_De_01_OnTap.md
AIF-C01_De_02_OnTap.md
...
AIF-C01_De_06_OnTap.md
```

Mỗi file gồm câu hỏi, lựa chọn, đáp án tham khảo, giải thích và nguồn tham khảo.

## AWS Certified Solutions Architect - Associate (SAA-C03)

Thư mục chính: [`saa-c03/`](./saa-c03/)

### Note Nên Đọc Trước

- Study guide full:
  [`saa-c03/study-guide/saa-c03-study-guide-full.md`](./saa-c03/study-guide/saa-c03-study-guide-full.md)

Bản này là điểm vào chính cho SAA-C03. Nội dung được chia theo 4 domain:

- Domain 1 - Design Secure Architectures
- Domain 2 - Design Resilient Architectures
- Domain 3 - Design High-Performing Architectures
- Domain 4 - Design Cost-Optimized Architectures

Trong file cũng có các phần quan trọng để ôn nhanh:

- Từ khóa cần nhớ
- Decision tree theo domain
- Master comparison tables
- Trap catalog
- Last-minute rules

### Bộ Đề Review

Các đề ôn tập SAA-C03 nằm tại:

[`saa-c03/review/`](./saa-c03/review/)

File theo pattern:

```text
SAA-C03_De_01_OnTap.md
SAA-C03_De_02_OnTap.md
...
SAA-C03_De_16_OnTap.md
```

Mỗi file gồm câu hỏi, lựa chọn, đáp án tham khảo, takeaway nhanh, giải thích chi tiết và nguồn tham khảo.

## Cách Học Đề Xuất

### Với AIF-C01

1. Đọc `aif-c01-study-guide.md` để nắm toàn cảnh AI/ML, Generative AI, Responsible AI và Governance.
2. Đọc lại từng domain trong `VDHieu0612-markdown/` nếu domain đó còn yếu.
3. Làm từng file trong `aif-c01/review/`.
4. Ghi lại keyword hay sai: hallucination, bias, overfitting, RAG, prompt engineering, guardrails, token, embedding, model evaluation.

### Với SAA-C03

1. Đọc phần từ khóa và domain overview trong `saa-c03-study-guide-full.md`.
2. Học theo domain, ưu tiên Domain 1 và Domain 3 vì thường xuất hiện nhiều pattern.
3. Làm từng đề trong `saa-c03/review/`.
4. Khi gặp câu sai, phân loại lỗi theo tiêu chí: security, resilience, performance, cost, least operational overhead.
5. Trước ngày thi, đọc lại `Master comparison tables`, `Trap catalog` và `Last-minute rules`.

## Quy Ước Thư Mục

```text
AWScerts/
├─ aif-c01/
│  ├─ study-guide/
│  │  ├─ tofumapu-markdown/
│  │  ├─ VDHieu0612-markdown/
│  │  └─ VDHieu0612-pdf/
│  └─ review/
└─ saa-c03/
   ├─ study-guide/
   └─ review/
```

## Ghi Chú

- Các file Markdown có thể đọc trực tiếp trên GitHub.
- Các file PDF phù hợp để tải xuống hoặc đọc offline.
- Nội dung review được dùng để ôn tập và tra cứu, không nên học thuộc đáp án máy móc. Hãy tập trung vào lý do đáp án đúng và lý do distractor sai.
