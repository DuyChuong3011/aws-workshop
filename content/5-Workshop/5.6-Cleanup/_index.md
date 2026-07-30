---
title : "Resource Cleanup"
date :  2026-07-30 
weight : 6
chapter : false
pre : " <b> 5.6 </b> "
---

### System Cleanup and Cost Optimization

Cloud computing operates on a pay-as-you-go model. Therefore, after completing the MLOps project development lifecycle or finishing the course, cleaning up and revoking services is a **mandatory operation** for Cost Optimization.

Below is a list of resources you need to review and completely delete from your AWS account.

---

### Step 1: Delete SageMaker Endpoints (Highest Priority)

Although the focus of this project is automating the Training flow and Model Registry, if during practice you experimented with deploying the model to an Endpoint for trial prediction (Inference), you **must delete it immediately**. 

Endpoints use virtual servers (EC2) running 24/7 waiting for Requests; this is the most costly service if forgotten.

1. Access the **SageMaker Console** interface.
2. On the left menu, find the **Inference** section, then select **Endpoints**.
3. Select the running Endpoint of the SCADA project and click **Delete**.
4. Continue into the **Endpoint configurations** and **Models** sections (under Inference) to delete related configurations.

---

### Step 2: Cleanup SageMaker Model Registry

To keep the workspace tidy and avoid metadata storage fees:

1. In the **SageMaker Console**, navigate to **Models** → **Model Registry**.
2. Find the **Model Package Group** of the SCADA project.
3. You need to click on that Group, select all model versions inside, and delete them first.
4. Finally, delete the Model Package Group itself.

---

### Step 3: Empty and Delete S3 Bucket

Amazon S3 charges based on the volume of data you store. AWS also establishes a safety mechanism: you cannot delete a Bucket if there is still data inside.

1. Access the **S3 Console**, find the project's bucket (e.g., `scada-mlops-project-bucket-2026`).
2. Select that bucket and click the **Empty** button. AWS will require you to type the phrase `permanently delete` to confirm deleting all CSV data and `model.tar.gz` files.
3. After emptying successfully, return to the Buckets list, select the project bucket again, and click **Delete** to completely remove this container.

---

### Step 4: Delete IAM Role

Retaining unused Roles does not incur costs, but deleting them is a good habit to ensure the security environment is always clean, avoiding future authorization vulnerabilities.

1. Access **IAM Console** → **Roles**.
2. Search for the Role you created in lesson 5.5 (e.g., `SageMaker-SCADA-ExecutionRole`).
3. Select the Role and click **Delete**.

---

{{% notice warning %}}
**Cost Warning (Cloud Billing):**
Carefully check the AWS Billing Dashboard to ensure no compute resources are running in the background. MLOps automation is very convenient, but forgetting to turn off servers (especially lines with GPU or large memory like the `ml.m5` series) can cause you to be unjustly charged overnight!
{{% /notice %}}

![Cleanup Resources](/images/5-Workshop/5.6-Cleanup/cleanup.png)