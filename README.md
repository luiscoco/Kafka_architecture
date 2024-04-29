# Apache Kafka architecture

https://developer.confluent.io/courses/apache-kafka-for-dotnet/overview/

![image](https://github.com/luiscoco/Kafka_architecture/assets/32194879/52e8e823-b675-46cd-8f51-73687adfc93e)

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

## 6. Kafka installation

Download Kafka (**kafka_2.13-3.6.1.tgz**) from Apache web page: https://kafka.apache.org/downloads

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/3a9121f2-9fe7-4a1f-a386-e91d288dfb94)

We uncompress the **kafka_2.13-3.6.1.tgz** and copy the folder in the C:/

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/79cf7efe-6c7f-4be9-925e-02bbad5c3ee1)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/c71fde3b-fa3f-4118-9378-a1f0b36f4fbd)

We create add the **C:\kafka_2.13-3.6.1\bin\windows** in the **PATH** environmental variable

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e2bd5826-a890-451c-a4ae-aaa89fb2dc4c)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e072ba06-e055-406b-abf4-1d5e0062b0bb)

**VERY IMPORTANT:** Set the **bootstrap_server** in the **server.properties** file

```
advertised.listeners=PLAINTEXT://localhost:9092
```

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/fa9f4aaa-6b5e-4d4e-8465-7768d5008d52)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/fb8e761d-57fb-4044-914e-39d1233e9a4c)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/64cd9941-54a3-4456-afca-a9eff0e24b0c)

Run and Test Kafka

In a command prompt window we first **run Zookeper** 

```
zookeeper-server-start C:\kafka_2.13-3.6.1\config\zookeeper.properties
```

In another command prompt window we **run Kafka server**

```
kafka-server-start C:\kafka_2.13-3.6.1\config\server.properties
```

We **create a topic**

```
kafka-topics --create --partitions 1 --replication-factor 1 --topic test --bootstrap-server localhost:9092
```

We **creata a producer**

```
kafka-console-producer --topic test --bootstrap-server localhost:9092
```

We **create a consumer**

```
kafka-console-consumer.bat --topic test --from-beginning --bootstrap-server localhost:9092
```

We input a message in the Producer prompt and we get it in the consumer prompt, see this picture

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e3524cac-6602-4705-817e-edbc966a68d1)

**IMPORTANT NOTE**: in case you you get an error when you run the Kafka server go to the C:/tmp directore and **delete** the subdirectories **kafka-logs** and **zookeeper**

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/a2fdb38c-8d30-48e5-bfd2-dacb751709f5)
##
