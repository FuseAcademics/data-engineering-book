# Python Practice Tasks

These tasks are designed to build the foundational logic required for Data Engineering pipelines.

---

## 🛠️ Data Engineering Prep Tasks
## 📝 Practice Tasks (Standard Library)

### 1. The CSV to JSON Converter
**Goal:** Master the `csv` and `json` modules.
* **Scenario:** A legacy system exports data in CSV, but your modern API only accepts JSON.
* **Requirements:**
    * Read a file `users.csv` without using external libraries.
    * Convert each row into a Dictionary.
    * Handle "dirty" data: if a numeric field contains text, default it to `0`.
    * **Output:** A beautifully formatted `users.json` file.

### 2. The Memory-Efficient Log Scanner
**Goal:** Use **Generators** to handle "Big Data" on a small machine.
* **Scenario:** You have a 5GB log file, but your computer only has 4GB of RAM.
* **Requirements:**
    * Use a generator function (`yield`) to read the file line-by-line.
    * Count occurrences of keywords like `ERROR`, `WARNING`, and `INFO`.
    * **Output:** A summary dictionary: `{'ERROR': 450, 'WARNING': 120, 'INFO': 2000}`.

---