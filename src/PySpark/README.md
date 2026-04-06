# Introduction to PySpark

PySpark allows you to use the power of Apache Spark with Python, enabling large-scale data processing across clusters.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Spark Python API (PySpark)](https://spark.apache.org/docs/latest/api/python/index.html)
* **PySpark Quickstart:** [Spark Official Guide](https://spark.apache.org/docs/latest/api/python/getting_started/index.html)
* **Free Course:** [SparkByExamples](https://sparkbyexamples.com/pyspark-tutorial/) - *An excellent blog-style reference for common PySpark functions.*

## 🧪 Practice Tasks
1. **DataFrame Basics:** Load a CSV file into a PySpark DataFrame and display its schema.
2. **Column Transformation:** Create a new column called `total_price` by multiplying `quantity` and `unit_price` columns, then filter for rows where `total_price > 1000`.
3. **PySpark SQL:** Register a DataFrame as a temporary view and run a standard SQL query against it using `spark.sql()`.