# Apache Kafka & Event Streaming

Kafka is a distributed event store and stream-processing platform. It allows you to handle trillions of events a day, making it the backbone of real-time Data Engineering.

## 🔗 Learning Resources
* **Official Documentation:** [Apache Kafka Docs](https://kafka.apache.org/documentation/)
* **Introduction to Kafka:** [Confluent's Kafka 101](https://developer.confluent.io/learn/apache-kafka-intro/) - *The best conceptual starting point.*
* **Interactive Course:** [Learn Apache Kafka (YouTube)](https://www.youtube.com/watch?v=R873BlNVUB4)
* **Visual Guide:** [Kafka Visualizer](https://softwaremill.com/introducing-the-kafka-visualizer/) - *Great for understanding how offsets and partitions work.*

## 🧪 Practice Tasks
1. **Topic Management:** Use the Kafka CLI (or a Docker-based setup) to create a topic named `telemetry_data` with 3 partitions and a replication factor of 1.
2. **The Producer:** Write a Python script using `confluent-kafka` or `kafka-python` to send 100 JSON messages (simulating temperature sensor data) to your topic.
3. **The Consumer:** Write a second script that reads these messages from the beginning of the topic (`auto.offset.reset='earlier'`) and prints them to the console.
4. **Consumer Groups:** Run two instances of your Consumer script simultaneously and observe how Kafka balances the partitions between them.