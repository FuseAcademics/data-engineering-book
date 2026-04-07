# Introduction to PySpark

PySpark allows you to use the power of Apache Spark with Python, enabling large-scale data processing across clusters.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Spark Python API (PySpark)](https://spark.apache.org/docs/latest/api/python/index.html)
* **PySpark Quickstart:** [Spark Official Guide](https://spark.apache.org/docs/latest/api/python/getting_started/index.html)
* **Free Course:** [SparkByExamples](https://sparkbyexamples.com/pyspark-tutorial/) - *An excellent blog-style reference for common PySpark functions.*

# ⚙️ PySpark Practice Tasks: Big Data Processing

When data grows to Terabytes, we move from Pandas to Spark. Note: Spark uses **Lazy Evaluation**.

### Task 1: Schema Enforcement
Instead of using `inferSchema=True`, manually define a `StructType` schema for the grocery data prepared in SQL practice task.

### Task 2: Distributed Transformations
Using the Spark DataFrame API:
1. Filter rows where `quantity` is less than 1 (Data Quality check).
2. Add a column `taxed_price` which is `price * 1.15`.
3. Rename the column `item_name` to `product_description`.

### Task 3: Wide Transformations (Shuffle)
Perform a `groupBy` on the `category` column and calculate the sum of `quantity`. 
* **Discussion:** Explain why `groupBy` is considered a "Wide Transformation" compared to `filter`.

### Task 4: Optimization
Use the `.cache()` method on a DataFrame. In what scenario would a Data Engineer choose to cache a dataset?