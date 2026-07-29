---
title: "Worklog Tuần 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Thử nghiệm và so sánh các thuật toán học máy trên môi trường cục bộ.

* Phân tích và đánh giá hiệu năng để chọn ra mô hình tối ưu nhất trước khi đưa lên đám mây AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Nhận dữ liệu `T1_train.csv` và `T1_test.csv` đã qua tiền xử lý. <br> - Khởi tạo `notebooks/02_modeling_local.ipynb` và `notebooks/03_modeling_dl.ipynb`. <br> - Lập trình hàm `load_features()`. | 08/06/2026 | 08/06/2026 | <https://pandas.pydata.org/docs/> |
| 3   | - Lập trình hàm `train_xgboost()`: Huấn luyện mô hình XGBoost, tính toán F1, AUC-ROC và vẽ ma trận nhầm lẫn (Confusion Matrix). | 09/06/2026 | 09/06/2026 | <https://xgboost.readthedocs.io/en/stable/python/python_api.html> |
| 4   | - Huấn luyện các mô hình phát hiện bất thường: <br>&emsp; + `train_isolation_forest()`: Không giám sát tự tìm điểm bất thường. <br>&emsp; + `train_lstm_autoencoder()`: Tính reconstruction error theo chuỗi thời gian. | 10/06/2026 | 10/06/2026 | <https://scikit-learn.org/stable/> <br> <https://www.tensorflow.org/api_docs> |
| 5   | - Lập trình hàm `compare_models()` và `plot_roc_curves()`: Vẽ biểu đồ so sánh trực quan các chỉ số F1, AUC-ROC và đường cong ROC của 3 mô hình trên cùng một đồ thị. | 11/06/2026 | 11/06/2026 | <https://matplotlib.org/stable/> <br> <https://seaborn.pydata.org/> |
| 6   | - **Thực hành:** <br>&emsp; + Đánh giá tổng quan kết quả từ notebook. <br>&emsp; + Tổng hợp kết luận và chọn mô hình tốt nhất để chuẩn bị triển khai lên SageMaker. | 12/06/2026 | 12/06/2026 | |

### Kết quả đạt được tuần 2:

* Hoàn thành kịch bản thử nghiệm cục bộ với 3 mô hình: XGBoost, Isolation Forest và LSTM Autoencoder.

* Đã xác định và lựa chọn XGBoost làm mô hình chính thức nhờ ưu điểm huấn luyện nhanh và độ chính xác cao đối với dữ liệu đã có nhãn.

* Sinh ra đầy đủ các biểu đồ đánh giá hiệu năng (ROC curves, Confusion Matrix) phục vụ trực tiếp cho việc viết báo cáo cuối kỳ.
