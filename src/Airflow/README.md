# Apache Airflow
# Apache Airflow

Orchestration is the "glue" that holds data pipelines together. Apache Airflow allows you to programmatically author, schedule, and monitor workflows.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Airflow Documentation](https://airflow.apache.org/docs/)
* **Airflow Quickstart:** [Running Airflow Locally](https://airflow.apache.org/docs/apache-airflow/stable/start.html)
* **Astronomer Guides:** [Airflow Concepts](https://www.astronomer.io/guides/) - *The best place to learn about DAGs, Operators, and Tasks.*

## 🧪 Practice Tasks
1. **The Hello World DAG:** Create a simple DAG that runs two `BashOperator` tasks. The first should print "Starting Pipeline" and the second should print "Pipeline Complete".
2. **Task Dependencies:** Define a DAG where `Task_A` must finish before `Task_B` and `Task_C` run in parallel.
3. **PythonOperator:** Write a DAG that uses a `PythonOperator` to call a function that prints the current execution date.