---
title : "Dọn dẹp tài nguyên"
date :  2026-07-30 
weight : 6
chapter : false
pre : " <b> 5.6 </b> "
---

### Dọn dẹp hệ thống và tối ưu chi phí

Điện toán đám mây hoạt động theo mô hình chi trả theo mức sử dụng thực tế. Do đó, sau khi hoàn tất vòng đời phát triển dự án MLOps hoặc khi kết thúc môn học, việc dọn dẹp và thu hồi các dịch vụ là **thao tác bắt buộc** để tối ưu hóa chi phí (Cost Optimization).

Dưới đây là danh sách các tài nguyên bạn cần rà soát và xóa bỏ hoàn toàn khỏi tài khoản AWS của mình.

---

### Bước 1: Xóa SageMaker Endpoints (Ưu tiên cao nhất)

Mặc dù trọng tâm của dự án này là tự động hóa luồng Huấn luyện (Training) và Quản lý phiên bản (Model Registry), nhưng nếu trong quá trình thực hành bạn có thử nghiệm triển khai (Deploy) mô hình ra Endpoint để dự đoán thử (Inference), bạn **phải xóa nó ngay lập tức**. 

Endponts sử dụng máy chủ ảo (EC2) chạy 24/7 chờ Request, đây là dịch vụ gây tốn kém nhất nếu bạn để quên.

1. Truy cập giao diện **SageMaker Console**.
2. Ở menu bên trái, tìm mục **Inference**, sau đó chọn **Endpoints**.
3. Chọn Endpoint đang chạy của dự án SCADA và nhấn **Delete**.
4. Tiếp tục vào mục **Endpoint configurations** và **Models** (trong phần Inference) để xóa các cấu hình liên quan.

---

### Bước 2: Dọn dẹp SageMaker Model Registry

Để giữ cho không gian làm việc gọn gàng và không tốn phí lưu trữ siêu dữ liệu (metadata):

1. Trong **SageMaker Console**, điều hướng đến **Models** → **Model Registry**.
2. Tìm **Model Package Group** của dự án SCADA.
3. Bạn cần nhấp vào Group đó, chọn tất cả các phiên bản (Model versions) bên trong và xóa chúng trước.
4. Cuối cùng, xóa chính Model Package Group.

---

### Bước 3: Làm trống và xóa S3 Bucket

Amazon S3 tính phí dựa trên dung lượng dữ liệu bạn lưu trữ. AWS cũng thiết lập cơ chế an toàn: bạn không thể xóa một Bucket nếu bên trong vẫn còn dữ liệu.

1. Truy cập **S3 Console**, tìm đến bucket của dự án (ví dụ: `scada-mlops-project-bucket-2026`).
2. Chọn bucket đó và nhấn nút **Empty** (Làm trống). AWS sẽ yêu cầu bạn gõ chữ `permanently delete` để xác nhận việc xóa toàn bộ dữ liệu CSV và các file `model.tar.gz`.
3. Sau khi Empty thành công, quay lại danh sách Buckets, chọn lại bucket dự án và nhấn **Delete** để xóa hoàn toàn vùng chứa này.

---

### Bước 4: Xóa IAM Role

Việc lưu giữ các Role không còn sử dụng không tốn chi phí, nhưng việc xóa chúng là một thói quen tốt để đảm bảo không gian bảo mật luôn sạch sẽ, tránh các lỗ hổng phân quyền về sau.

1. Truy cập **IAM Console** → **Roles**.
2. Tìm kiếm Role bạn đã tạo ở bài 5.5 (ví dụ: `SageMaker-SCADA-ExecutionRole`).
3. Chọn Role và nhấn **Delete**.

---

{{% notice warning %}}
**Cảnh báo Chi phí (Cloud Billing):**
Hãy kiểm tra thật kỹ AWS Billing Dashboard để đảm bảo không còn tài nguyên tính toán nào đang chạy ngầm. Quá trình tự động hóa MLOps rất tiện lợi, nhưng việc quên tắt máy chủ (đặc biệt là các dòng máy có GPU hoặc bộ nhớ lớn như dòng `ml.m5`) có thể khiến bạn bị trừ tiền oan uổng chỉ sau một đêm!
{{% /notice %}}

![Cleanup Resources](/images/5-Workshop/5.6-Cleanup/cleanup.png)