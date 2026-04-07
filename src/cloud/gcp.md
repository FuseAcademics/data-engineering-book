# Introduction to GCP (Google Cloud Platform)

GCP is a powerful and rapidly growing cloud platform by Google, offering scalable infrastructure and advanced data analytics capabilities. For a Data Engineer, GCP provides essential services like Cloud Storage for data lakes, BigQuery for analytics, and Dataflow for building scalable data pipelines.

---

##  Learning Resources
* **Official Training:** [Google Cloud Digital Leader Training](https://cloud.google.com/training/digitalleader)
* **Storage Deep-Dive:** [Cloud Storage Documentation](https://cloud.google.com/storage/docs)
* **Data Engineering Path:** [Google Cloud Skills Boost - Data Engineering](https://www.cloudskillsboost.google/paths/16)
* **BigQuery Guide:** [BigQuery Documentation](https://cloud.google.com/bigquery/docs)

---

##  Key GCP Services for Data Engineering

- **Cloud Storage** → Data lake storage for raw and processed data  
- **BigQuery** → Serverless data warehouse for analytics  
- **Dataflow** → Stream & batch data processing (Apache Beam)  
- **Pub/Sub** → Real-time messaging and event ingestion  
- **Dataproc** → Managed Spark/Hadoop clusters  
- **Cloud Composer** → Workflow orchestration (Apache Airflow)  

---

##  Practice Tasks

### 1. **The Bucket Builder**
Create a Cloud Storage bucket, upload a `.csv` file, and configure IAM permissions to allow read-only access.

### 2. **The Cost Optimizer**
Set up a lifecycle rule in Cloud Storage to move objects to Coldline or Archive storage after 30 days.

### 3. **The Query Explorer**
Load your `.csv` file into BigQuery and run SQL queries:
- Count total rows  
- Filter records  
- Aggregate data (e.g., GROUP BY)

### 4. **The Access Controller**
Create a service account with least privilege and use it to access BigQuery or Cloud Storage.

---

##  Mini Project: Build a Data Pipeline in GCP

### Objective:
Build a simple batch data pipeline from Cloud Storage → BigQuery.

### Steps:
1. Upload a sample dataset (`.csv`) to Cloud Storage  
2. Create a BigQuery dataset and table  
3. Use **BigQuery UI / bq command / Dataflow template** to load data  
4. Transform data using SQL (e.g., cleaning, filtering)  
5. Schedule pipeline (optional) using Cloud Composer or scheduled queries  

---