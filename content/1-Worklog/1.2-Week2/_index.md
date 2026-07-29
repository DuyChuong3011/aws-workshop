---
title: "Week 2 Worklog"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Experiment with and compare machine learning algorithms in a local environment.

* Analyze and evaluate performance to select the optimal model before deploying to the AWS cloud.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Receive the pre-processed `T1_train.csv` and `T1_test.csv` data. <br> - Initialize `notebooks/02_modeling_local.ipynb` and `notebooks/03_modeling_dl.ipynb`. <br> - Program the `load_features()` function. | 08/06/2026 | 08/06/2026 | <https://pandas.pydata.org/docs/> |
| Tue | - Program the `train_xgboost()` function: Train the XGBoost model, calculate F1, AUC-ROC, and plot the Confusion Matrix. | 09/06/2026 | 09/06/2026 | <https://xgboost.readthedocs.io/en/stable/python/python_api.html> |
| Wed | - Train anomaly detection models: <br>&emsp; + `train_isolation_forest()`: Unsupervised method to automatically find anomalous points. <br>&emsp; + `train_lstm_autoencoder()`: Calculate reconstruction error over the time series. | 10/06/2026 | 10/06/2026 | <https://scikit-learn.org/stable/> <br> <https://www.tensorflow.org/api_docs> |
| Thu | - Program the `compare_models()` and `plot_roc_curves()` functions: Visually compare the F1, AUC-ROC metrics, and ROC curves of the 3 models on the same chart. | 11/06/2026 | 11/06/2026 | <https://matplotlib.org/stable/> <br> <https://seaborn.pydata.org/> |
| Fri | - **Practice:** <br>&emsp; + Evaluate the overall results from the notebook. <br>&emsp; + Synthesize conclusions and select the best model to prepare for deployment on SageMaker. | 12/06/2026 | 12/06/2026 | |

### Week 2 Achievements:

* Successfully completed local testing scenarios with 3 models: XGBoost, Isolation Forest, and LSTM Autoencoder.

* Identified and selected XGBoost as the official model due to its fast training capabilities and high accuracy on labeled data.

* Generated a comprehensive set of performance evaluation charts (ROC curves, Confusion Matrix) directly serving the final report writing.