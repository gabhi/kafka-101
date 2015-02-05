# kafka-101

1) Start zookeeper
  bin/zookeeper-server-start.sh config/zookeeper.properties
2) Start Kafka server:
  bin/kafka-server-start.sh config/server.properties
3) Create a test topic
  bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
4) List topics
  bin/kafka-topics.sh --list --zookeeper localhost:2181
5) Start producer
  bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test 
This is a message
This is another message
6) Consume them 
bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning
