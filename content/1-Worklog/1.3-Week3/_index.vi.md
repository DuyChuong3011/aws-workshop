---
title: "Worklog Tuần 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Cấu trúc hóa mã nguồn huấn luyện mô hình XGBoost.

* Chuyển đổi mã nguồn từ Jupyter Notebook sang dạng Python script độc lập để tương thích với môi trường Amazon SageMaker.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tạo tệp `src/train.py`. <br> - Viết hàm `parse_args()` sử dụng thư viện `argparse` để nhận các siêu tham số (`n_estimators`, `max_depth`, `learning_rate`, `scale_pos_weight`) từ command line. | 15/06/2026 | 15/06/2026 | <https://docs.python.org/3/library/argparse.html> |
| 3   | - Lập trình hàm `load_data(train_path, test_path)` để đọc dữ liệu CSV và phân tách X (features), y (target). <br> - Lập trình hàm `build_model(args)` khởi tạo mô hình XGBoost với các tham số đầu vào. | 16/06/2026 | 16/06/2026 | <https://pandas.pydata.org/docs/> <br> <https://scikit-learn.org/stable/> |
| 4   | - Xây dựng hàm `train()` tích hợp cơ chế *early stopping* để chống overfit. <br> - Viết hàm `evaluate()` để tính toán nhanh các chỉ số F1, AUC-ROC, Precision, Recall ngay trong quá trình huấn luyện. | 17/06/2026 | 17/06/2026 | <https://xgboost.readthedocs.io/en/stable/python/python_api.html> |
| 5   | - Thiết lập hàm `save_model(model, model_dir)`: Cấu hình lưu trữ mô hình đầu ra vào đúng thư mục môi trường biến (thường là `/opt/ml/model/`) theo chuẩn định dạng của SageMaker. | 18/06/2026 | 18/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo-output.html> |
| 6   | - **Thực hành:** <br>&emsp; + Viết hàm `main()` để liên kết toàn bộ luồng xử lý (pipeline) trên thành một chuỗi thống nhất. <br>&emsp; + Chạy thử nghiệm script cục bộ qua terminal để kiểm tra lỗi biên dịch trước khi đưa lên đám mây. | 19/06/2026 | 19/06/2026 |  |

### Kết quả đạt được tuần 3:

* Đã chuyển đổi thành công luồng huấn luyện từ môi trường thử nghiệm (Notebook) sang script Python tiêu chuẩn (`src/train.py`).

* Đảm bảo mã nguồn có khả năng nhận cấu hình tham số động, làm tiền đề bắt buộc cho quá trình Tối ưu hóa siêu tham số (HPO) tự động.

* Thiết lập đúng định dạng lưu trữ đầu ra, tuân thủ nghiêm ngặt quy định đóng gói `model.tar.gz` của môi trường huấn luyện Amazon SageMaker.