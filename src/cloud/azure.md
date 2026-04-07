# Introduction to Azure

Azure is Microsoft's cloud computing platform and a leader in enterprise data solutions. For a Data Engineer, Azure provides a seamless ecosystem for storing, integrating, and managing massive data workloads using specialized tools like ADLS and Synapse.

## 🔗 Learning Resources
* **Official Training:** [Azure Data Fundamentals (DP-900)](https://learn.microsoft.com/en-us/training/paths/azure-data-fundamentals/) - *The best starting point for the Microsoft ecosystem.*
* **Storage Guide:** [Introduction to Azure Data Lake Storage (ADLS) Gen2](https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction)
* **Architecture Center:** [Azure Data Engineering Architecture](https://learn.microsoft.com/en-us/azure/architecture/browse/?filter=data-engineering)

# ☁️ Azure Practice Tasks: Enterprise Data Engineering

Azure is the cloud of choice for many enterprise organizations. In this module, you will build a scalable data ingestion and transformation pipeline.

---

## 📝 Practice Tasks: Data Lake, Data Factory, and Synapse

### Task 1: ADLS Gen2 Hierarchy
**Goal:** Master "Hierarchical Namespaces" for data organization.
* **Requirement:** Create an Azure Storage Account (Standard V2).
* **Challenge:** 1. Enable **Hierarchical Namespace** (this turns it into ADLS Gen2).
    2. Create a "Container" named `landing-zone`.
    3. Upload `grocery_sales.csv` using **Azure Storage Explorer** or the Portal.
* **Concept:** Understand why a "True Directory" structure is faster for Big Data than a "Flat" S3-style bucket.

### Task 2: Azure Data Factory (ADF) - The Copy Activity
**Goal:** Your first "No-Code" ETL pipeline.
* **Requirement:** Provision an Azure Data Factory instance.
* **Challenge:** 1. Create a **Linked Service** to your Storage Account.
    2. Create a **Pipeline** with a **Copy Data Activity**.
    3. Source: `grocery_sales.csv`. Sink: A new folder named `/processed/`.
* **Verification:** Trigger the pipeline and check if the file moved successfully.

### Task 3: Azure Key Vault Security
**Goal:** Secure your credentials (Secret Management).
* **Requirement:** Create an Azure Key Vault.
* **Challenge:** 1. Store your Storage Account Access Key as a **Secret**.
    2. Link your Data Factory to the Key Vault.
    3. Configure the Data Factory to pull the secret instead of hardcoding the password in the connection string.

---

## 🏗️ Mini Project: The "ADF-to-SQL" Pipeline

Build an end-to-end automated ingestion layer:

1. **Storage:** Landing zone in ADLS Gen2.
2. **Orchestration:** An **Azure Data Factory** pipeline triggered by a "Storage Event" (when a file is uploaded).
3. **Transformation:** A **Mapping Data Flow** in ADF that:
    * Removes rows with `NULL` prices.
    * Converts `item_name` to lowercase.
4. **Loading:** Sink the cleaned data into an **Azure SQL Database** table.
5. **Monitoring:** Use the ADF Monitor tab to verify the run time and rows processed.