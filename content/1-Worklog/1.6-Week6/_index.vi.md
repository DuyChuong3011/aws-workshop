---
title: "Worklog Tuần 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Xây dựng kịch bản đánh giá mô hình độc lập sau huấn luyện.

* Tính toán các chỉ số đo lường hiệu suất và trích xuất báo cáo định dạng JSON.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Viết hàm `load_model()` trong `src/evaluate.py` để nạp mô hình XGBoost tốt nhất từ quá trình HPO. | 06/07/2026 | 06/07/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| 3   | - Lập trình hàm `compute_metrics()`: tính toán các chỉ số F1-score, AUC-ROC, Precision, Recall và Confusion Matrix trên tập dữ liệu Test. | 07/07/2026 | 07/07/2026 | <https://scikit-learn.org/stable/modules/model_evaluation.html> |
| 4   | - Viết hàm `save_evaluation_report()`: định dạng và lưu kết quả đánh giá ra file `evaluation.json` theo đúng chuẩn đầu vào của SageMaker Pipeline. | 08/07/2026 | 08/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-model-quality-metrics.html> |
| 5   | - Lập trình hàm `plot_roc_curve()`: vẽ và lưu trữ hình ảnh biểu đồ ROC Curve cùng Confusion Matrix để phục vụ báo cáo. | 09/07/2026 | 09/07/2026 | <https://matplotlib.org/stable/> <br> <https://seaborn.pydata.org/> |
| 6   | - **Thực hành:** <br>&emsp; + Chạy thử nghiệm toàn bộ script `evaluate.py` cục bộ. <br>&emsp; + Kiểm tra tính toàn vẹn của file `evaluation.json` sinh ra. | 10/07/2026 | 10/07/2026 | <https://docs.python.org/3/library/unittest.html> |

### Kết quả đạt được tuần 6:

* Hoàn thiện toàn bộ logic của module đánh giá mô hình (`src/evaluate.py`).

* Tự động hóa việc tính toán các bộ chỉ số quan trọng (F1, AUC, Precision, Recall) thay vì phải tính thủ công.

* Trích xuất thành công file báo cáo `evaluation.json`.