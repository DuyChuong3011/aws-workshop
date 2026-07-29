---
title: "Week 3 Worklog"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Structure the XGBoost model training source code.

* Convert the source code from a Jupyter Notebook into an independent Python script to ensure compatibility with the Amazon SageMaker environment.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Create the `src/train.py` file. <br> - Write the `parse_args()` function using the `argparse` library to receive hyperparameters (`n_estimators`, `max_depth`, `learning_rate`, `scale_pos_weight`) from the command line. | 15/06/2026 | 15/06/2026 | <https://docs.python.org/3/library/argparse.html> |
| Tue | - Program the `load_data(train_path, test_path)` function to read CSV data and separate X (features) and y (target). <br> - Program the `build_model(args)` function to initialize the XGBoost model with input parameters. | 16/06/2026 | 16/06/2026 | <https://pandas.pydata.org/docs/> <br> <https://scikit-learn.org/stable/> |
| Wed | - Build the `train()` function integrating the *early stopping* mechanism to prevent overfitting. <br> - Write the `evaluate()` function to quickly calculate F1, AUC-ROC, Precision, and Recall metrics right during the training process. | 17/06/2026 | 17/06/2026 | <https://xgboost.readthedocs.io/en/stable/python/python_api.html> |
| Thu | - Set up the `save_model(model, model_dir)` function: Configure saving the output model to the correct environment variable directory (usually `/opt/ml/model/`) according to the SageMaker standard format. | 18/06/2026 | 18/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo-output.html> |
| Fri | - **Practice:** <br>&emsp; + Write the `main()` function to link the entire processing pipeline above into a unified sequence. <br>&emsp; + Run a local test of the script via the terminal to check for compilation errors before uploading it to the cloud. | 19/06/2026 | 19/06/2026 |  |

### Week 3 Achievements:

* Successfully converted the training workflow from a testing environment (Notebook) to a standard Python script (`src/train.py`).

* Ensured the source code can receive dynamic parameter configurations, serving as a mandatory prerequisite for the automated Hyperparameter Optimization (HPO) process.

* Established the correct output storage format, strictly complying with the `model.tar.gz` packaging regulations of the Amazon SageMaker training environment.