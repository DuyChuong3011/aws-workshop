---
title: "Week 5 Worklog"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Launch model training on the cloud using Amazon SageMaker.

* Apply Hyperparameter Optimization (HPO).

### Tasks to be implemented this week:
| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Initialize the SageMaker Training Job via Boto3 SDK. <br> - Link SageMaker with the `train.py` script and data on S3. | 29/06/2026 | 29/06/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| Tue | - Configure the Bayesian Optimization problem in SageMaker HPO. <br> - Define the Metric to track (`validation:f1_score`). | 30/06/2026 | 30/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html> |
| Wed | - Define the hyperparameter search space for XGBoost: `eta`, `max_depth`, `subsample`, `colsample_bytree`. <br> - Trigger the HPO Job run. | 01/07/2026 | 01/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost-tuning.html> |
| Thu | - Analyze training logs on Amazon CloudWatch. <br> - Extract the best hyperparameter set (Best Training Job). | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html> |
| Fri | - **Practice:** <br>&emsp; + Compare the F1-Score of the tuned model against the local baseline model. <br>&emsp; + Package `model.tar.gz`. | 03/07/2026 | 03/07/2026 | <https://aws.amazon.com/console/> |


### Week 5 Achievements:

* Successfully executed the training process on SageMaker's dynamically provisioned servers.

* Discovered the optimal set of hyperparameters, helping XGBoost increase the F1-score and ROC-AUC beyond the default thresholds.

* Successfully monitored and analyzed Training Logs directly on CloudWatch.