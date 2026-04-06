# Introduction to dbt (data build tool)

dbt is the "T" (Transform) in ELT. It allows Data Engineers and Analysts to write transformations in simple SQL while dbt handles the complex work of dependency management, version control, and data testing.

## 🔗 Learning Resources
* **dbt Learn:** [dbt Fundamentals](https://courses.getdbt.com/courses/fundamentals) - *The gold standard course for learning the modern data stack.*
* **Best Practices:** [The dbt Viewpoint](https://docs.getdbt.com/docs/about/viewpoint) - *Essential reading on why dbt works the way it does.*
* **Documentation:** [dbt Core & Cloud Docs](https://docs.getdbt.com/)

## 🧪 Practice Tasks
1. **The Project Init:** Initialize a new dbt project, connect it to your Snowflake account, and run `dbt debug` to verify the connection.
2. **The Modular Model:** Create a `stg_` (staging) model to clean column names and a `fct_` (fact) model that joins multiple sources together.
3. **The Data Quality Guard:** Add `unique` and `not_null` tests to your `schema.yml` file and run `dbt test` to catch any data integrity issues.