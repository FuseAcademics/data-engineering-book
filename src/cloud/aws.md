# Introduction to AWS (Amazon Web Services)

AWS is the world's most comprehensive and broadly adopted cloud platform. For a Data Engineer, AWS provides the foundational storage (S3) and compute (EC2/Lambda) layers needed to build robust data pipelines.

## 🔗 Learning Resources
* **Official Training:** [AWS Cloud Practitioner Essentials](https://explore.skillbuilder.aws/learn/course/external/view/elearning/134/aws-cloud-practitioner-essentials)
* **Storage Deep-Dive:** [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
* **Interactive Workshop:** [AWS Data Engineering Immersion Day](https://catalog.us-east-1.quicksight.aws/workshops/6011400a-810a-4a6c-851f-5061405e3a24/en-US)

# ☁️ AWS Practice Tasks: Cloud Data Engineering

AWS is the most widely used cloud provider. In this module, you will build a "Data Lake" and a serverless ETL pipeline.

---

## 📝 Practice Tasks: S3, Lambda, and Glue

### Task 1: The S3 Data Lake Setup
**Goal:** Master object storage and permissions.
* **Requirement:** Log into the AWS Console (or use LocalStack for local practice).
* **Challenge:** 1. Create an S3 Bucket named `raw-grocery-data-unique-id`.
    2. Upload your `grocery_sales.csv` manually.
    3. Create a folder structure inside the bucket: `inbound/`, `processed/`, and `archive/`.
* **Command:** `aws s3 cp grocery_sales.csv s3://raw-grocery-data-unique-id/inbound/`

### Task 2: Serverless ETL with AWS Lambda
**Goal:** Trigger code based on an event (File Upload).
* **Requirement:** Create a Python Lambda function.
* **Challenge:** 1. Set an **S3 Trigger** so the Lambda runs every time a `.csv` is dropped into the `inbound/` folder.
    2. Write Python code (using the `boto3` library) to read the file's metadata and print the file name to CloudWatch Logs.

### Task 3: AWS Glue Crawler & Data Catalog
**Goal:** Automatically discover the schema of your data.
* **Requirement:** Point an AWS Glue Crawler at your S3 bucket.
* **Challenge:** 1. Run the Crawler to scan your CSV files.
    2. Check the **AWS Glue Data Catalog** to see if a table was created automatically.
    3. Use **Amazon Athena** to run a SQL query (`SELECT * FROM ...`) directly against the files sitting in S3.
* **Concept:** This is the "Schema-on-Read" pattern.

### Task 4: IAM Roles & Security
**Goal:** Understand the "Principle of Least Privilege."
* **Requirement:** Your Lambda function needs permission to read from S3.
* **Challenge:** Create an **IAM Role** that only has `AmazonS3ReadOnlyAccess`. Attach it to your Lambda.
* **Verification:** Try to make the Lambda *delete* the file. It should fail. This proves your pipeline is secure.

---

## 🏗️ Mini Project: The "S3-to-Athena" Pipeline

Build a production-ready serverless analytics layer:

1. **Storage:** Landing zone in S3 (`/raw`).
2. **Transformation:** An **AWS Glue Job** (PySpark) that reads the raw CSV, converts it to **Parquet** format, and saves it to a `/parquet` folder.
3. **Cataloging:** A Glue Crawler that updates the metadata for the Parquet files.
4. **Analysis:** Use **Amazon Athena** to calculate the total monthly revenue. Compare the speed of querying the CSV vs. the Parquet version.