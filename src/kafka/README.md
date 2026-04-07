# Apache Kafka & Event Streaming

Kafka is a distributed event store and stream-processing platform. It allows you to handle trillions of events a day, making it the backbone of real-time Data Engineering.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Kafka Docs](https://kafka.apache.org/documentation/)
* **Introduction to Kafka:** [Confluent's Kafka 101](https://developer.confluent.io/learn/apache-kafka-intro/) - *The best conceptual starting point.*
* **Interactive Course:** [Learn Apache Kafka (YouTube)](https://www.youtube.com/watch?v=R873BlNVUB4)
* **Visual Guide:** [Kafka Visualizer](https://softwaremill.com/introducing-the-kafka-visualizer/) - *Great for understanding how offsets and partitions work.*

# ⚡ Apache Kafka Practice Tasks: Real-Time Streaming

Kafka is a distributed event streaming platform. Instead of processing "batches" of data, we process "events" as they happen.

---

## 📝 Practice Tasks: Topics, Producers, and Consumers

### Task 1: Infrastructure Setup (CLI)
**Goal:** Understand the core components of a Kafka Cluster.
* **Requirement:** Start a Zookeeper and Kafka broker (using Docker or local binaries).
* **Challenge:** 1. Create a **Topic** named `grocery-sales` with 3 partitions and a replication factor of 1.
    2. List all topics to verify it exists.
    3. Describe the topic to see the partition distribution.
* **Command:** `kafka-topics.sh --create --topic grocery-sales --bootstrap-server localhost:9092 ...`

### Task 2: The Console Producer & Consumer
**Goal:** Send and receive your first messages manually.
* **Requirement:** Open two terminal windows.
* **Challenge:** 1. In Terminal A (Producer), type 3 messages representing sales: `{"id": 1, "item": "Apple"}`.
    2. In Terminal B (Consumer), read the messages from the beginning (`--from-beginning`).
* **Discussion:** What happens to the messages in Terminal B if you close it and reopen it? Do they disappear?

### Task 3: Python Integration (`confluent-kafka` or `kafka-python`)
**Goal:** Programmatically stream data.
* **Requirement:** Write a Python script to act as a **Producer**.
* **Challenge:** * Create a loop that sends a new "Sale Event" every 2 seconds to the `grocery-sales` topic.
    * Each event should have a random `price` and a `timestamp`.
* **Verification:** Use the Console Consumer to watch the live stream of data appearing in real-time.

### Task 4: Consumer Groups & Scalability
**Goal:** Understand how Kafka handles high volume.
* **Requirement:** Start **two** instances of a Python Consumer script using the same `group.id`.
* **Challenge:** Observe the output. Does each consumer see every message, or do they split the load?
* **Discussion:** Why is the number of **Partitions** the "ceiling" for how many consumers you can have in a group?

---

## 🏗️ Mini Project: The "Real-Time Alert" Pipeline

Build a small streaming application that monitors for high-value transactions.

1. **Producer:** A script that generates random sales data (0 - $100).
2. **Stream Processor (Python):** A consumer script that reads the stream.
3. **The Logic:** If a sale is greater than $80, print a "🚨 ALERT: High Value Sale Detected!" message.
4. **The Sink:** Save only the "Alert" transactions into a local file named `alerts_log.txt`.