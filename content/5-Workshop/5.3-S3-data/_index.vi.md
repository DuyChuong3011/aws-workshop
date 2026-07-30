---
title : "Thiết lập Amazon S3 (Data Lake)"
date :  2026-07-30 
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

### Tổ chức lưu trữ dữ liệu trên AWS

Trong kiến trúc MLOps, **Amazon S3 (Simple Storage Service)** đóng vai trò là "Data Lake" trung tâm. Để huấn luyện mô hình XGBoost dự đoán lỗi SCADA bằng SageMaker, dữ liệu bắt buộc phải được tải lên S3 trước khi dịch vụ tính toán có thể truy cập.

Bài thực hành này sẽ hướng dẫn bạn khởi tạo một không gian lưu trữ an toàn, tổ chức cấu trúc thư mục chuẩn chỉ và tải tập dữ liệu lên đám mây.

---

### 1. Khởi tạo S3 Bucket

Bucket là vùng chứa tài nguyên cơ bản nhất trong S3. Mỗi bucket yêu cầu một tên gọi duy nhất trên toàn cầu (Globally Unique).

**Các bước thực hiện:**
1. Đăng nhập vào **AWS Management Console**, nhập từ khóa `S3` vào thanh tìm kiếm và mở dịch vụ **S3**.
2. Tại bảng điều khiển S3, nhấn nút màu cam **Create bucket**.
3. **General configuration:**
   * **Bucket name:** Đặt tên cho bucket. Ví dụ: `scada-mlops-project-bucket-2026` *(Bạn cần thay đổi năm hoặc thêm hậu tố ngẫu nhiên để tên không bị trùng lặp)*.
   * **AWS Region:** Chọn cùng Region với máy trạm bạn đã thiết lập ở bài trước (ví dụ: `ap-southeast-1`).
4. **Object Ownership:** Chọn **ACLs disabled (recommended)**.
5. **Block Public Access settings:** Đảm bảo tùy chọn **Block all public access** được đánh dấu tích. Hệ thống dữ liệu công nghiệp SCADA mang tính bảo mật cao, do đó tuyệt đối không được cấu hình Public.
6. Giữ nguyên các cài đặt còn lại và cuộn xuống dưới cùng, nhấn **Create bucket**.

![Create S3 Bucket](/images/5-Workshop/5.3-S3-data/create_bucket.png)

---

### 2. Xây dựng cấu trúc thư mục

Việc quản lý thư mục minh bạch giúp phân định rõ ràng luồng dữ liệu trước và sau quá trình huấn luyện.

1. Bấm vào tên Bucket bạn vừa tạo để vào bên trong.
2. Nhấn nút **Create folder** và lần lượt tạo 3 thư mục sau:
   * `raw/`: Chứa file dữ liệu cảm biến SCADA nguyên bản chưa qua xử lý.
   * `processed/`: Chứa dữ liệu đã được làm sạch, xử lý mất cân bằng nhãn cơ bản và chia tách thành các tập (Train, Validation, Test).
   * `model/`: Để trống thư mục này. SageMaker sẽ tự động lưu file nén chứa trọng số mô hình (`model.tar.gz`) vào đây sau khi kết thúc quá trình huấn luyện.

![Folder Structure](/images/5-Workshop/5.3-S3-data/structure.png)

---

### 3. Tải dữ liệu lên Data Lake

Bạn có thể tải dữ liệu lên S3 bằng giao diện Web Console hoặc thông qua AWS CLI đã cấu hình ở bài trước. Việc sử dụng AWS CLI được khuyến khích vì nó mang tính tự động hóa cao, phù hợp với tinh thần MLOps.

#### Cách 1: Sử dụng AWS CLI (Khuyến nghị)
Mở Terminal tại máy cục bộ (nơi chứa tập dữ liệu `SCADA_data.csv`) và chạy các lệnh sau để đồng bộ dữ liệu lên thư mục `processed`:

```bash
# Tải tập Train
aws s3 cp ./data/train.csv s3://scada-mlops-project-bucket-2026/processed/train.csv

# Tải tập Validation
aws s3 cp ./data/validation.csv s3://scada-mlops-project-bucket-2026/processed/validation.csv

```

*Lưu ý: Thay thế `scada-mlops-project-bucket-2026` bằng tên Bucket thực tế của bạn.*

#### Cách 2: Sử dụng AWS Console

1. Truy cập vào thư mục `processed` trên giao diện web S3.
2. Nhấn nút **Upload**, sau đó chọn **Add files**.
3. Chọn các file dữ liệu SCADA từ máy tính của bạn.
4. Nhấn **Upload** ở góc dưới cùng và chờ đến khi thanh tiến trình báo thành công (Succeeded).

![Upload files](/images/5-Workshop/5.3-S3-data/upLoadData.png)

{{% notice success %}}
**Hoàn tất:**
Xin chúc mừng! Dữ liệu của bạn đã được tải lên AWS một cách an toàn. Giờ đây, "nguồn nguyên liệu" đã sẵn sàng để đưa vào cỗ máy huấn luyện tự động trong bài lab tiếp theo.
{{% /notice %}}