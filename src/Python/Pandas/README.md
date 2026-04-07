# Pandas for Data Engineering

Pandas is a fast, powerful, and flexible open-source data analysis and manipulation tool built on top of the Python programming language.

## 🔗 Learning Resources
* **Official Documentation:** [Pandas Documentation](https://pandas.pydata.org/docs/)
* **Pandas Getting Started:** [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html) - *The best "first stop" for beginners.*
* **Kaggle Course:** [Pandas Tutorial](https://www.kaggle.com/learn/pandas) - *Interactive and specifically focused on data manipulation.*
* **Visualization:** [Pandas Plotting Guide](https://pandas.pydata.org/docs/user_guide/visualization.html)

## 📝 Practice Tasks (The Basics)

### 1. The Schema Validator
**Goal:** Ensure incoming data matches your requirements.
* **Scenario:** You have a CSV of "Sales" data. You need to ensure no prices are negative and all dates are valid.
* **Requirements:**
    * Load `sales.csv`.
    * Use `df.info()` to check data types.
    * Use boolean indexing to find rows where `price < 0` and drop them.
    * Convert the `transaction_date` column to `datetime64[ns]`.
    * **Output:** A report of how many rows were deleted during cleaning.

### 2. The Aggregator (Group-By)
**Goal:** Create a summary report from raw events.
* **Scenario:** A CSV contains `store_id`, `product_category`, and `revenue`.
* **Requirements:**
    * Group the data by `store_id`.
    * Calculate the **Total Revenue** and **Average Revenue** per store.
    * Sort the results so the highest-earning store is at the top.
    * **Output:** Save the summary to `store_performance.csv`.

---