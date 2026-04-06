# Introduction to Azure

Azure is Microsoft's cloud computing platform and a leader in enterprise data solutions. For a Data Engineer, Azure provides a seamless ecosystem for storing, integrating, and managing massive data workloads using specialized tools like ADLS and Synapse.

## 🔗 Learning Resources
* **Official Training:** [Azure Data Fundamentals (DP-900)](https://learn.microsoft.com/en-us/training/paths/azure-data-fundamentals/) - *The best starting point for the Microsoft ecosystem.*
* **Storage Guide:** [Introduction to Azure Data Lake Storage (ADLS) Gen2](https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction)
* **Architecture Center:** [Azure Data Engineering Architecture](https://learn.microsoft.com/en-us/azure/architecture/browse/?filter=data-engineering)

## 🧪 Practice Tasks
1. **The Container Architect:** Create an Azure Storage Account, enable the "Hierarchical Namespace" (for ADLS Gen2), and create three containers: `raw`, `silver`, and `gold`.
2. **The Access Controller:** Use **Shared Access Signatures (SAS)** to create a temporary URL that allows a user to read a file for only 24 hours.
3. **The Data Factory Pilot:** Create a simple **Azure Data Factory (ADF)** pipeline to copy a file from one container to another based on a trigger.