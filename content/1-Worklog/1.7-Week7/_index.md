---
title: "Week 7 Worklog"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Register the best-performing XGBoost model into the Amazon SageMaker Model Registry management system.

* Manage model versions, attach metadata and evaluation metrics to establish a foundation for the approval and deployment process.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ----- | ---------- | -------- | --------- |
| Mon | - Initialize a Model Package Group on AWS SageMaker via the SDK to serve as a repository for versions of the SCADA fault prediction model. | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html> |
| Tue | - Build a workflow to read and extract evaluation metrics (F1, AUC-ROC) from the `evaluation.json` file created during the model evaluation step in Week 6. | 14/07/2026 | 14/07/2026 | <https://docs.python.org/3/library/json.html> <br> <https://boto3.amazonaws.com/v1/documentation/api/latest/index.html> |
| Wed | - Program the `aws/register_model.py` script: Create a Model Package, associate the S3 path of the model artifact, the Inference image (XGBoost container), and performance metrics. | 15/07/2026 | 15/07/2026 | <https://sagemaker.readthedocs.io/en/stable/amazon_sagemaker_model_registry.html> |
| Thu | - Set the default Approval Status for the newly registered model to `PendingManualApproval`. This ensures a strict quality review process before the DevOps Engineer (Person C) proceeds with deployment. | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/whitepapers/latest/mlops-framework/> |
| Fri | - **Practice:** <br>&emsp; + Run the `register_model.py` script to push the model to the Registry. <br>&emsp; + Access the AWS Console to verify the model version, confirming that the metrics and approval status are displayed correctly. | 17/07/2026 | 17/07/2026 | <https://aws.amazon.com/console/> |

### Week 7 Achievements:

* Finalized the automated script for registering the model into the SageMaker Model Registry.

* Successfully managed model versions with full attached metadata and metrics, ensuring transparency and traceability for the MLOps system.

* Ready to hand over the optimal model version in a pending approval status to transition to the CI/CD phase.