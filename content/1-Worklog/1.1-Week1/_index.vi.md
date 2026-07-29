---
title: "Worklog Tuần 1"
date: 2026-06-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI chuẩn bị cho hạ tầng dự án MLOps.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập                                                                                            | 01/06/2026   | 01/06/2026      |<https://hcm-rules.awsfcaj.com/>|
| 3   | - Tìm hiểu AWS và các loại dịch vụ <br>&emsp; + Compute (EC2, Lambda) <br>&emsp; + Storage (S3, EBS) <br>&emsp; + Networking (VPC, API Gateway) <br>&emsp; + Machine Learning (SageMaker)   | 02/06/2026   | 02/06/2026      | <https://aws.amazon.com/getting-started/> |
| 4   | - Tạo AWS account <br> - Tìm hiểu AWS Console & AWS CLI <br> - **Thực hành:** <br>&emsp; + Tạo AWS account <br>&emsp; + Cài AWS CLI & cấu hình <br> &emsp; + Cách sử dụng AWS CLI | 03/06/2026   | 03/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu EC2 & IAM cơ bản: <br>&emsp; + Instance types <br>&emsp; + IAM Roles/Policies (Cấp quyền cho SageMaker) <br> - Các cách remote SSH vào EC2                                       | 04/06/2026   | 04/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo IAM Role cho ML Engineer <br>&emsp; + Cấu hình truy cập S3 Bucket thông qua CLI                                                                           | 05/06/2026   | 05/06/2026      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 1:

* Hiểu AWS là gì và nắm được các nhóm dịch vụ cơ bản cần cho dự án: 
  * Compute (EC2, Lambda)
  * Storage (S3)
  * Networking (API Gateway)
  * Machine Learning (SageMaker)

* Đã tạo và cấu hình AWS account thành công.

* Làm quen với AWS Management Console và biết cách tìm, truy cập, sử dụng dịch vụ từ giao diện web.

* Cài đặt và cấu hình AWS CLI trên máy tính bao gồm:
  * Access Key
  * Secret Key
  * Region mặc định

* Hiểu rõ cơ chế phân quyền IAM Role để chuẩn bị cấp quyền cho môi trường huấn luyện mô hình học máy.