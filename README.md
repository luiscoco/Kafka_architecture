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

## 2. Kafka Terminologies

**Producer**: A producer can be any application that can publish a message on a topic. 

**Consumer**: A consumer can be any application that subscribes to a topic and consumes the messages. 

**Partition**: Topics are broken up into ordered commit logs called partitions.

**Broker**: Kafka cluster is a set of servers, each of which is called a broker.

**Topic**: A topic is a category or feed name to which records are published. 

**Zookeeper**: Zookeeper is used for managing and coordinating Kafka broker.

## 3. Kafka Cluster

Here, we can see multiple Producer produces data to Kafka broker and those Kafka broker reside inside a Kafka cluster

Again we have multiple consumers, consuming the data from the kafka broker and this kafka broker is managed by the zookeeper

![image](https://github.com/luiscoco/Kafka_architecture/assets/32194879/24162f13-340d-4f7c-a312-61b5820df574)

## 4. Kafka Features  

**High Throughput**: Provides support for hundreds of thousands of messages with modest hardware 

**Scalability**: Highly scalable distributed systems with no downtime

**Data Loss**: Kafka ensures no data loss once configured properly

**Stream Processing**: Kafka can be used along with real-time streaming applications like Spark and Strom

**Durability**: Provides support to persisting messages on disk. 

**Replication**: Messages can be replicated across clusters, which supports multiple subscribers


## 5. Apache Kafka Architecture

Here we have a producer, producing messages to a topic and this topic has 3 partitions. Now there are 3 consumers who are consuming from these partitions 

So, we have 2 producers, Producer A and Producer B. Producer A produces partition1 and partition2, and Producer B which is producing partition3

Then we can see that we have one consumer for each partition. So this is the best-case scenario where you have total palladium in processing those messages

![image](https://github.com/luiscoco/Kafka_architecture/assets/32194879/bae996c6-0a63-4a92-a5cb-2e6a3e2bdf41)
