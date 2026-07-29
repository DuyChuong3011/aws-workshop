---
title: "Worklog Tuần 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Khởi chạy huấn luyện mô hình trên đám mây sử dụng Amazon SageMaker.

* Áp dụng Tối ưu hóa siêu tham số (HPO - Hyperparameter Optimization).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Khởi tạo SageMaker Training Job thông qua Boto3 SDK. <br> - Liên kết SageMaker với script `train.py` và dữ liệu trên S3. | 29/06/2026| 29/06/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| 3   | - Cấu hình bài toán Tối ưu hóa Bayes (Bayesian Optimization) trong SageMaker HPO. <br> - Định nghĩa Metric cần theo dõi (`validation:f1_score`). | 30/06/2026 | 30/06/2026 |<https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html> |
| 4   | - Xác định dải tìm kiếm siêu tham số cho XGBoost: `eta`, `max_depth`, `subsample`, `colsample_bytree`. <br> - Kích hoạt luồng chạy HPO Job. | 01/07/2026 | 01/07/2026 |<https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost-tuning.html> |
| 5   | - Phân tích logs huấn luyện trên Amazon CloudWatch. <br> - Trích xuất bộ siêu tham số tốt nhất. | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html> |
| 6   | - **Thực hành:** <br>&emsp; + So sánh F1-Score của mô hình đã tuning so với mô hình baseline cục bộ. <br>&emsp; + Đóng gói `model.tar.gz`. | 03/07/2026 | 03/07/2026 | <https://aws.amazon.com/console/> |


### Kết quả đạt được tuần 5:

* Chạy thành công quy trình huấn luyện trên máy chủ cấp phát tự động của SageMaker.

* Tìm ra bộ siêu tham số tối ưu giúp XGBoost tăng F1-score và ROC-AUC vượt ngưỡng mặc định.

* Theo dõi và phân tích thành công Log Training trực tiếp trên CloudWatch.