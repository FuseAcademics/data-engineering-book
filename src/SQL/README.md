# Introduction to SQL

SQL is the language of data. For a Data Engineer, it is essential for performing transformations (the 'T' in ETL) and querying data warehouses.

## 🔗 Learning Resources
* **Official Documentation:** [PostgreSQL Documentation](https://www.postgresql.org/docs/)
* **Interactive Learning:** [SQLZoo](https://sqlzoo.net/) - *Great for hands-on practice in the browser.*
* **SQL Crash Course:** [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/) - *Highly recommended for data professionals.*

# 📊 SQL Practice Tasks: Retail Database

In this module, you will build a relational structure for a grocery store and perform data audits.

### Task 1: Table Architecture (DDL)
Create a table named `store_sales` with the following requirements:
* `transaction_id`: Integer, Primary Key.
* `item_name`: String, cannot be null.
* `price`: Float, must be greater than 0.
* `category`: String, default to 'General'.
* `sale_date`: Date.

### Task 2: Data Ingestion (DML)
Insert 5 rows of data. Ensure at least one row has a `NULL` category to test your default constraint, and one row has a high quantity (over 10) for future filtering.

### Task 3: The "Revenue" Report
Write a query to calculate:
1. The **Total Revenue** (Price * Quantity) per category.
2. The **Average Price** of items in the 'Produce' category.
3. Sort the results so the highest-earning category is at the top.

### Task 4: Conditional Flagging
Use a `CASE` statement to create a new column `sale_type`:
* If quantity > 10, label as 'Wholesale'.
* Otherwise, label as 'Retail'.