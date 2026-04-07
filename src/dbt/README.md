# Introduction to dbt (data build tool)

dbt is the "T" (Transform) in ELT. It allows Data Engineers and Analysts to write transformations in simple SQL while dbt handles the complex work of dependency management, version control, and data testing.dbt is a development framework that combines SQL with software engineering best practices (version control, testing, CI/CD) to build data transformations.

## Core Concepts
* **T in ELT:** dbt does not move data; it transforms data already loaded into your warehouse (Snowflake, BigQuery, etc.).
* **SQL-based:** If you know `SELECT` statements, you can use dbt.
* **Modular:** It turns monolithic scripts into reusable models.

## Official Resources
* [dbt Documentation](https://docs.getdbt.com/)
* [dbt Fundamentals (Free Course)](https://courses.getdbt.com/courses/dbt-fundamentals)

## 🔗 Learning Resources
* **dbt Learn:** [dbt Fundamentals](https://courses.getdbt.com/courses/fundamentals) - *The gold standard course for learning the modern data stack.*
* **Best Practices:** [The dbt Viewpoint](https://docs.getdbt.com/docs/about/viewpoint) - *Essential reading on why dbt works the way it does.*
* **Documentation:** [dbt Core & Cloud Docs](https://docs.getdbt.com/)

# 💎 dbt (Data Build Tool) Practice Tasks

dbt sits on top of your Data Warehouse. It allows you to transform "Raw" data into "Clean" data using SQL and Jinja templating.

---

## 📝 Practice Tasks: Analytics Engineering

### Task 1: Project Initialization & Profiles
**Goal:** Set up the dbt environment.
* **Requirement:** Run `dbt init grocery_project`. 
* **Challenge:** Configure your `profiles.yml` to connect to a local SQLite database or a cloud warehouse (Snowflake/BigQuery). 
* **Verification:** Run `dbt debug` to ensure the connection is successful.

### Task 2: Building Modular Models (The `ref` function)
**Goal:** Create a dependency between two models.
* **Requirement:** 1. Create a "Staging" model `stg_sales.sql` that selects all data from your raw sales table.
    2. Create a "Fact" model `fct_daily_summary.sql` that uses the `{{ ref('stg_sales') }}` function to calculate daily totals.
* **Discussion:** Why is using `ref()` better than hardcoding the table name like `FROM my_db.my_schema.stg_sales`?

### Task 3: Data Documentation & YAML
**Goal:** Document your data for the business team.
* **Requirement:** Create a `schema.yml` file in your `models/` folder.
* **Challenge:** Add a description for the `transaction_id` and `total_revenue` columns. 
* **Command:** Run `dbt docs generate` followed by `dbt docs serve`. Can you see your documentation in the browser?

### Task 4: Automated Testing (Data Quality)
**Goal:** Catch bad data before it hits the dashboard.
* **Requirement:** In your `schema.yml`, add the following tests to the `transaction_id` column:
    * `unique`
    * `not_null`
* **Challenge:** Add an `accepted_values` test to the `category` column to ensure only 'Produce', 'Dairy', and 'Bakery' are allowed.
* **Command:** Run `dbt test` and check if your data passes.

---