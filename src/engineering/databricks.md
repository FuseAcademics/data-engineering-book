# Introduction to Databricks

Databricks is a unified analytics platform built on top of Apache Spark. It pioneered the "Lakehouse" architecture, which provides the performance of a data warehouse with the massive scale and flexibility of a data lake.

## 🔗 Learning Resources
* **Official Academy:** [Databricks Lakehouse Fundamentals](https://customer-academy.databricks.com/learn/course/external/view/elearning/45/lakehouse-fundamentals) - *Free accreditation for students.*
* **Community Edition:** [Databricks Community Cloud](https://community.cloud.databricks.com/) - *Access a free micro-cluster for hands-on practice.*
* **Delta Lake Docs:** [Delta Lake Guide](https://docs.delta.io/latest/index.html) - *Understand how to bring ACID transactions to big data.*

## 🧪 Practice Tasks
1. **The Cluster Launch:** Create a cluster in the Databricks Community Edition and import a sample CSV file into the Filestore.
2. **The Silver Transformation:** Write a PySpark notebook to read raw data, drop duplicates, handle null values, and save the result as a **Delta Table**.
3. **The SQL Analyst:** Use the Databricks SQL editor to write a query that joins two Delta tables and creates a visualization (Bar Chart) of the results.