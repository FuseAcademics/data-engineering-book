# Apache Airflow

Orchestration is the "glue" that holds data pipelines together. Apache Airflow allows you to programmatically author, schedule, and monitor workflows.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Airflow Documentation](https://airflow.apache.org/docs/)
* **Airflow Quickstart:** [Running Airflow Locally](https://airflow.apache.org/docs/apache-airflow/stable/start.html)
* **Astronomer Guides:** [Airflow Concepts](https://www.astronomer.io/guides/) - *The best place to learn about DAGs, Operators, and Tasks.*

# 🚀 Apache Airflow Practice Tasks: Data Orchestration

Airflow uses **DAGs** (Directed Acyclic Graphs) written in Python to schedule and monitor your data pipelines.

---

## 📝 Practice Tasks: Operators & Scheduling

### Task 1: Your First DAG (The "Hello World")
**Goal:** Understand the basic structure of a DAG.
* **Requirement:** Create a Python file in your `dags/` folder.
* **Challenge:** 1. Define a DAG that runs every day at midnight (`@daily`).
    2. Use the `EmptyOperator` for a 'start' and 'end' task.
    3. Use the `BashOperator` to print "Hello Airflow" in the middle.
* **Verification:** Open the Airflow UI (localhost:8080) and trigger the DAG manually.

### Task 2: PythonOperator & XComs
**Goal:** Pass data between tasks.
* **Requirement:** Airflow tasks are isolated, so we use **XComs** (Cross-Communications) to share small amounts of data.
* **Challenge:** 1. Task A: A Python function that returns a random number.
    2. Task B: A Python function that pulls that number and prints whether it is "Even" or "Odd".

### Task 3: Task Dependencies & Branching
**Goal:** Control the flow of logic.
* **Requirement:** Use the `BranchPythonOperator`.
* **Challenge:** 1. Create a task that checks if today is a weekday.
    2. If it is a weekday, run a "Work Task".
    3. If it is a weekend, run a "Maintenance Task".

### Task 4: Catchup & Backfilling
**Goal:** Understand how Airflow handles historical data.
* **Requirement:** Set a `start_date` to 3 days ago.
* **Challenge:** 1. Set `catchup=True` and see how Airflow automatically triggers runs for the past 3 days.
    2. Change `catchup=False` and see the difference.

---