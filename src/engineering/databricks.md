# Introduction to Databricks

Databricks is a unified analytics platform built on top of Apache Spark. It pioneered the "Lakehouse" architecture, which provides the performance of a data warehouse with the massive scale and flexibility of a data lake.

## 🔗 Learning Resources
* **Official Academy:** [Databricks Lakehouse Fundamentals](https://customer-academy.databricks.com/learn/course/external/view/elearning/45/lakehouse-fundamentals) - *Free accreditation for students.*
* **Community Edition:** [Databricks Community Cloud](https://community.cloud.databricks.com/) - *Access a free micro-cluster for hands-on practice.*
* **Delta Lake Docs:** [Delta Lake Guide](https://docs.delta.io/latest/index.html) - *Understand how to bring ACID transactions to big data.*

# 🧱 Databricks Practice Tasks: The Lakehouse Challenge

Databricks is a unified data analytics platform. It combines the best of Data Warehouses (SQL/Performance) and Data Lakes (Storage/Flexibility) into a **Lakehouse**.

---

## 📝 Practice Tasks: Notebooks & Delta Lake

### Task 1: Cluster & Notebook Setup
**Goal:** Understand the Compute layer.
* **Requirement:** Spin up a "Personal Compute" or "Community Edition" cluster.
* **Challenge:** Create a New Notebook. 
    * Set the default language to **Python**.
    * Use a "Magic Command" (`%sql`) in the second cell to switch to SQL.
* **Verification:** Run `spark.version` in Python and `SELECT 1` in SQL.

### Task 2: The Magic of Delta Lake (Time Travel)
**Goal:** Understand ACID transactions on a Data Lake.
* **Requirement:** Load the grocery CSV into a **Delta Table**.
    ```python
    df.write.format("delta").saveAsTable("sales_delta")
    ```
* **Challenge:** 1. Update a price in the table: `UPDATE sales_delta SET price = 10.0 WHERE id = 1`.
    2. Use **Time Travel** to see the previous version:
    ```sql
    SELECT * FROM sales_delta VERSION AS OF 0
    ```
* **Discussion:** Why is "Time Travel" a lifesaver for Data Engineers during a pipeline failure?

### Task 3: Multi-Language Transformation (Polyglot)
**Goal:** Use the best tool for the job within one notebook.
* **Requirement:** 1. Use **PySpark** to read the raw data and filter out nulls.
    2. Register the result as a Temporary View: `df.createOrReplaceTempView("cleaned_data")`.
    3. Use **SQL** (`%sql`) to perform a `GROUP BY` on that temporary view.
* **Challenge:** Why is this "Polyglot" approach better than forcing everything into one language?

### Task 4: Databricks Utilities (`dbutils`)
**Goal:** Interact with the file system (DBFS).
* **Requirement:** Use `dbutils.fs.ls("/")` to list the root directories.
* **Challenge:** Create a new folder named `/tmp/my_project/` and move a sample file into it using `dbutils.fs.mv`.
* **Command:** `display(dbutils.fs.ls("/tmp/my_project/"))`

---

## 🏗️ Mini Project: The Medallion Architecture

Build a simplified "Medallion" pipeline in a single notebook:

1. **Bronze Layer (Raw):** Load the raw CSV exactly as it is into a Delta table named `bronze_sales`.
2. **Silver Layer (Cleaned):** Filter out negative prices, fix date formats, and deduplicate. Save as `silver_sales`.
3. **Gold Layer (Aggregated):** Create a final table `gold_category_revenue` that sums up revenue for the business dashboard.
4. **Optimization:** Run `OPTIMIZE gold_category_revenue ZORDER BY (sale_date)` to speed up queries.