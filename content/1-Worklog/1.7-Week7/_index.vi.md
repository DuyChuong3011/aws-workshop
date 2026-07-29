---
title: "Worklog Tuần 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Đăng ký mô hình XGBoost có hiệu năng tốt nhất vào hệ thống quản lý Amazon SageMaker Model Registry.
* Quản lý phiên bản mô hình, gắn kèm các siêu dữ liệu (metadata) và chỉ số đánh giá (metrics) để tạo tiền đề cho quá trình kiểm duyệt và triển khai.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Khởi tạo Model Package Group trên AWS SageMaker thông qua SDK để làm nơi chứa các phiên bản của mô hình phát hiện lỗi SCADA. | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html> |
| 3   | - Xây dựng luồng đọc và trích xuất các chỉ số đánh giá (F1, AUC-ROC) từ tệp `evaluation.json` đã được tạo ra trong bước đánh giá mô hình ở tuần 6. | 14/07/2026 | 14/07/2026 | <https://docs.python.org/3/library/json.html> <br> <https://boto3.amazonaws.com/v1/documentation/api/latest/index.html> |
| 4   | - Lập trình script `aws/register_model.py`: Tạo Model Package, liên kết đường dẫn S3 của model artifact, Inference image (XGBoost container) và các chỉ số hiệu năng. | 15/07/2026 | 15/07/2026 | <https://sagemaker.readthedocs.io/en/stable/amazon_sagemaker_model_registry.html> |
| 5   | - Thiết lập trạng thái phê duyệt (Approval Status) mặc định cho mô hình mới đăng ký là `PendingManualApproval`. Nhằm đảm bảo quy trình kiểm duyệt chất lượng nghiêm ngặt trước khi kỹ sư DevOps (Người C) tiến hành triển khai. | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/whitepapers/latest/mlops-framework/> |
| 6   | - **Thực hành:** <br>&emsp; + Chạy kịch bản `register_model.py` để đẩy mô hình lên Registry. <br>&emsp; + Truy cập AWS Console để xác minh phiên bản mô hình, xác nhận các chỉ số và trạng thái phê duyệt đã hiển thị chính xác. | 17/07/2026 | 17/07/2026 | <https://aws.amazon.com/console/> |

### Kết quả đạt được tuần 7:

* Hoàn thiện kịch bản tự động đăng ký mô hình vào SageMaker Model Registry.

* Quản lý thành công phiên bản mô hình với đầy đủ metadata và metric đính kèm, đảm bảo tính minh bạch và khả năng truy vết cho hệ thống MLOps.

* Sẵn sàng bàn giao phiên bản mô hình tối ưu nhất ở trạng thái chờ phê duyệt để chuyển sang giai đoạn CI/CD.