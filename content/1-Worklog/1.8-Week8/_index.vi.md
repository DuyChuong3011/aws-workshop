---
title: "Worklog Tuần 8"
date: 2026-07-20
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Phân tích, tổng hợp đánh giá hiệu năng mô hình lần cuối phục vụ cho báo cáo tổng kết.
* Bàn giao phiên bản mô hình trên Model Registry và dọn dẹp tài nguyên để tối ưu chi phí đám mây.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Trích xuất toàn bộ biểu đồ hiệu năng, log huấn luyện từ SageMaker và CloudWatch. <br> - Định dạng lại các biểu đồ ROC, Confusion Matrix phục vụ cho báo cáo. | 20/07/2026 | 20/07/2026 | <https://docs.aws.amazon.com/cloudwatch/> |
| 3   | - Viết tài liệu kỹ thuật mô tả chi tiết: <br>&emsp; + Kiến trúc mô hình XGBoost. <br>&emsp; + Các siêu tham số tối ưu đã chọn. <br>&emsp; + Luồng xử lý dữ liệu trong script huấn luyện. | 21/07/2026 | 21/07/2026 | |
| 4   | - Phối hợp bàn giao phiên bản mô hình. <br>&emsp; + Thống nhất chuẩn đầu vào/đầu ra của mô hình. <br>&emsp; + Giải thích cách trigger pipeline CI/CD từ trạng thái `PendingManualApproval`. | 22/07/2026 | 22/07/2026 | <https://docs.aws.amazon.com/whitepapers/latest/mlops-framework/> |
| 5   | - Rà soát toàn bộ tài khoản AWS cá nhân. <br> - Xóa/Tắt các Notebook Instances, S3 buckets nháp, và các Training Jobs không còn sử dụng để tránh phát sinh chi phí. | 23/07/2026 | 23/07/2026 | <https://aws.amazon.com/aws-cost-management/> |
| 6   | - **Thực hành:** <br>&emsp; + Hoàn thiện báo cáo thực tập phần ML Engineering. <br>&emsp; + Cùng nhóm review chéo lại toàn bộ tiến trình 8 tuần vừa qua. | 24/07/2026 | 24/07/2026 | |

### Kết quả đạt được tuần 8:

* Bàn giao thành công phiên bản mô hình XGBoost hoàn chỉnh, sẵn sàng cho khâu kiểm duyệt và triển khai tự động.

* Giải phóng hoàn toàn các tài nguyên thử nghiệm trên AWS, đảm bảo tuân thủ tiêu chuẩn quản lý chi phí của dự án.

* Hoàn tất toàn bộ tài liệu kỹ thuật và báo cáo thực tập đúng thời hạn, khép lại quy trình 8 tuần thực tập ở vai trò ML Engineer.