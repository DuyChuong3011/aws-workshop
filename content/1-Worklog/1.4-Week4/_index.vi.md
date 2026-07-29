---
title: "Worklog Tuần 4"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Lập trình kịch bản tự động hóa quá trình khởi chạy huấn luyện mô hình trên đám mây Amazon SageMaker bằng Python.

* Kết nối mã nguồn huấn luyện cục bộ (`src/train.py`) với kho lưu trữ dữ liệu S3 và máy chủ tính toán đám mây.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Khởi tạo file `aws/training_job.py`. <br> - Cấu hình đối tượng XGBoost Estimator thông qua SageMaker SDK với loại máy chủ (instance type) là `ml.m5.large` và chỉ định IAM Role. | 22/06/2026 | 22/06/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| 3   | - Cấu hình đường dẫn đầu ra (output path) trên Amazon S3 để hệ thống tự động lưu trữ model artifact sau khi quá trình huấn luyện kết thúc. | 23/06/2026 | 23/06/2026 |  <https://boto3.amazonaws.com/v1/documentation/api/latest/index.html> |
| 4   | - Định nghĩa danh sách các siêu tham số mặc định ban đầu truyền vào cho mô hình XGBoost. | 24/06/2026 | 24/06/2026 | <https://xgboost.readthedocs.io/en/stable/parameter.html> |
| 5   | - Thiết lập kênh dữ liệu đầu vào: Định nghĩa và trỏ luồng đọc dữ liệu tập `train` và `validation` trực tiếp từ Amazon S3 vào Estimator. | 25/06/2026 | 25/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/modeltrain-datatypes.html> |
| 6   | - **Thực hành:** <br>&emsp; + Gọi hàm `estimator.fit()` để kích hoạt tiến trình Training Job trên AWS. <br>&emsp; + Lập trình lệnh in tên Job và đường dẫn S3 của model artifact ra terminal sau khi job chạy thành công. | 26/06/2026 | 26/06/2026 |  <https://docs.aws.amazon.com/sagemaker/> |

### Kết quả đạt được tuần 4:

* Hoàn thành kịch bản Python (`aws/training_job.py`), cho phép tự động khởi tạo và chạy Training Job hoàn toàn bằng code, không cần thao tác thủ công trên giao diện AWS Console.

* Tích hợp thành công luồng trao đổi dữ liệu: SageMaker lấy dữ liệu từ S3, thực thi file `src/train.py` trên máy chủ cloud, và lưu trữ kết quả (model artifact) ngược lại S3.

* Hoàn thiện môi trường chạy thử nghiệm độc lập trên đám mây, làm nền tảng vững chắc để triển khai hệ thống tìm kiếm siêu tham số (HPO) tự động.