---
title: "Week 6 Worklog"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Build an independent post-training model evaluation script.

* Calculate performance measurement metrics and extract a JSON formatted report.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Write the `load_model()` function in `src/evaluate.py` to load the best XGBoost model from the HPO process. | 06/07/2026 | 06/07/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| Tue | - Program the `compute_metrics()` function: calculate F1-score, AUC-ROC, Precision, Recall, and Confusion Matrix metrics on the Test dataset. | 07/07/2026 | 07/07/2026 | <https://scikit-learn.org/stable/modules/model_evaluation.html> |
| Wed | - Write the `save_evaluation_report()` function: format and save the evaluation results to an `evaluation.json` file according to the standard input format of SageMaker Pipeline. | 08/07/2026 | 08/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-model-quality-metrics.html> |
| Thu | - Program the `plot_roc_curve()` function: draw and save the ROC Curve and Confusion Matrix charts for reporting purposes. | 09/07/2026 | 09/07/2026 | <https://matplotlib.org/stable/> <br> <https://seaborn.pydata.org/> |
| Fri | - **Practice:** <br>&emsp; + Run a local test of the entire `evaluate.py` script. <br>&emsp; + Check the integrity of the generated `evaluation.json` file. | 10/07/2026 | 10/07/2026 | <https://docs.python.org/3/library/unittest.html> |

### Week 6 Achievements:

* Finalized the entire logic of the model evaluation module (`src/evaluate.py`).

* Automated the calculation of critical metric sets (F1, AUC, Precision, Recall) instead of manual computation.

* Successfully extracted the `evaluation.json` report file.