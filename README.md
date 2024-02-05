# Apache Kafka architecture

## 1. Why Apache Kafka?

Apache Kafka is capable of handling millions of data or messages per second

Apache Kafka has a source system that generates data (like a producer), and you want that data to go to a target system (like a consumer)

Apache Kafka acts as the middle person

It takes the data from the source, kind of like unhooking two LEGO pieces, and then the target system grabs it 

Apache Kafka is lightning-fast. It can deliver data in less than 10 milliseconds, which is really quick

It’s like sending a text message and having the other person read it almost instantly 

Apache Kafka is super reliable, like a sturdy bridge that never breaks 

Organizations like, Netflix, Uber, Walmart, and many more make use of Apache Kafka

## 2. Kafka Terminologies: 

**Producer**: A producer can be any application that can publish a message on a topic. 

**Consumer**: A consumer can be any application that subscribes to a topic and consumes the messages. 

**Partition**: Topics are broken up into ordered commit logs called partitions.

**Broker**: Kafka cluster is a set of servers, each of which is called a broker.

**Topic**: A topic is a category or feed name to which records are published. 

**Zookeeper**: Zookeeper is used for managing and coordinating Kafka broker.

## 3. Kafka Cluster:  

Here, we can see multiple Producer produces data to Kafka broker and those Kafka broker reside inside a Kafka cluster

Again we have multiple consumers, consuming the data from the kafka broker and this kafka broker is managed by the zookeeper

![image](https://github.com/luiscoco/Kafka_architecture/assets/32194879/24162f13-340d-4f7c-a312-61b5820df574)
