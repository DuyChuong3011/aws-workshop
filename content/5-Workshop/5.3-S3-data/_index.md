---
title : "Setting up Amazon S3 (Data Lake)"
date :  2026-07-30 
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

### Data Storage Organization on AWS

In the MLOps architecture, **Amazon S3 (Simple Storage Service)** acts as the central "Data Lake". To train the XGBoost model for predicting SCADA anomalies using SageMaker, data must be uploaded to S3 before the computing service can access it.

This practice session will guide you on how to initialize a secure storage space, organize a standard folder structure, and upload the dataset to the cloud.

---

### 1. Initializing S3 Bucket

A Bucket is the most basic resource container in S3. Each bucket requires a globally unique name.

**Steps to perform:**
1. Log in to the **AWS Management Console**, enter the keyword `S3` in the search bar, and open the **S3** service.
2. At the S3 dashboard, click the orange **Create bucket** button.
3. **General configuration:**
   * **Bucket name:** Name the bucket. For example: `scada-mlops-project-bucket-2026` *(You need to change the year or add a random suffix to avoid duplicate names)*.
   * **AWS Region:** Choose the same Region as the workstation you set up in the previous lesson (e.g., `ap-southeast-1`).
4. **Object Ownership:** Select **ACLs disabled (recommended)**.
5. **Block Public Access settings:** Ensure the **Block all public access** option is checked. Industrial SCADA data systems are highly secure, so public configuration is absolutely prohibited.
6. Keep the remaining settings as default, scroll to the bottom, and click **Create bucket**.

![Create S3 Bucket](/images/5-Workshop/5.3-S3-data/create_bucket.png)

---

### 2. Building Folder Structure

Transparent folder management helps clearly distinguish the data flow before and after the training process.

1. Click on the name of the Bucket you just created to go inside.
2. Click the **Create folder** button and sequentially create the following 3 folders:
   * `raw/`: Contains original, unprocessed SCADA sensor data files.
   * `processed/`: Contains data that has been cleaned, undergone basic class imbalance handling, and split into sets (Train, Validation, Test).
   * `model/`: Leave this folder empty. SageMaker will automatically save the compressed file containing model weights (`model.tar.gz`) here after the training process concludes.

![Folder Structure](/images/5-Workshop/5.3-S3-data/structure.png)

---

### 3. Uploading Data to Data Lake

You can upload data to S3 using the Web Console interface or via the AWS CLI configured in the previous lesson. Using AWS CLI is recommended because it is highly automated, aligning with the MLOps spirit.

#### Method 1: Using AWS CLI (Recommended)
Open Terminal on the local machine (where the `SCADA_data.csv` dataset is located) and run the following commands to synchronize data to the `processed` folder:

```bash
# Upload Train set
aws s3 cp ./data/train.csv s3://scada-mlops-project-bucket-2026/processed/train.csv

# Upload Validation set
aws s3 cp ./data/validation.csv s3://scada-mlops-project-bucket-2026/processed/validation.csv

```

*Note: Replace `scada-mlops-project-bucket-2026` with your actual Bucket name.*

#### Method 2: Using AWS Console

1. Access the `processed` folder on the S3 web interface.
2. Click the **Upload** button, then select **Add files**.
3. Select the SCADA data files from your computer.
4. Click **Upload** at the bottom corner and wait until the progress bar reports success (Succeeded).

![Upload files](/images/5-Workshop/5.3-S3-data/upLoadData.png)

{{% notice success %}}
**Completion:**
Congratulations! Your data has been securely uploaded to AWS. Now, the "raw materials" are ready to be fed into the automated training machine in the next lab.
{{% /notice %}}