---
title: "Week 4 Worklog"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Program an automation script to launch the model training process on the Amazon SageMaker cloud using Python.

* Connect the local training source code (`src/train.py`) with the S3 data repository and cloud compute servers.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Create the `aws/training_job.py` file. <br> - Configure the XGBoost Estimator object via the SageMaker SDK with the instance type as `ml.m5.large` and specify the IAM Role. | 22/06/2026 | 22/06/2026 | <https://sagemaker.readthedocs.io/en/stable/> |
| Tue | - Configure the output path on Amazon S3 so the system automatically stores the model artifact after the training process finishes. | 23/06/2026 | 23/06/2026 | <https://boto3.amazonaws.com/v1/documentation/api/latest/index.html> |
| Wed | - Define the initial default list of hyperparameters passed to the XGBoost model. | 24/06/2026 | 24/06/2026 | <https://xgboost.readthedocs.io/en/stable/parameter.html> |
| Thu | - Set up the input data channels: Define and point the data reading stream for the `train` and `validation` sets directly from Amazon S3 into the Estimator. | 25/06/2026 | 25/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/modeltrain-datatypes.html> |
| Fri | - **Practice:** <br>&emsp; + Call the `estimator.fit()` function to trigger the Training Job process on AWS. <br>&emsp; + Program the command to print the Job name and the S3 path of the model artifact to the terminal after the job runs successfully. | 26/06/2026 | 26/06/2026 | <https://docs.aws.amazon.com/sagemaker/> |

### Week 4 Achievements:

* Completed the Python script (`aws/training_job.py`), allowing automatic initialization and execution of the Training Job entirely via code, eliminating the need for manual operations on the AWS Console.

* Successfully integrated the data exchange flow: SageMaker fetches data from S3, executes the `src/train.py` file on the cloud server, and stores the results (model artifact) back to S3.

* Finalized the independent testing environment on the cloud, establishing a solid foundation for deploying the automated Hyperparameter Optimization (HPO) system.