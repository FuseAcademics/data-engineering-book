# Introduction to Snowflake

Snowflake is a cloud-native data warehouse known for its "near-zero" management. Its unique architecture separates storage from compute, allowing Data Engineers to scale resources up or down instantly without affecting data availability.

## 🔗 Learning Resources
* **Snowflake University:** [Hands-on Essentials - Data Warehousing](https://quickstarts.snowflake.com/guide/getting_started_with_snowflake/index.html)
* **Quickstart Guide:** [Snowflake in 20 Minutes](https://quickstarts.snowflake.com/) - *The fastest way to understand the UI.*
* **SQL Reference:** [Snowflake SQL Commands](https://docs.snowflake.com/en/sql-reference-commands) - *Comprehensive map of Snowflake-specific SQL.*

## 🧪 Practice Tasks
1. **The Warehouse Control:** Create a Virtual Warehouse (X-Small), set it to "Auto-Suspend" after 1 minute, and observe how it handles an incoming query.
2. **The Data Loader:** Create an Internal Stage, upload a local file using `PUT`, and use the `COPY INTO` command to load it into a structured table.
3. **The Time Traveler:** Delete several records from a table, then use the `AT (OFFSET => -60)` command to select the data as it existed 1 minute ago and restore it.