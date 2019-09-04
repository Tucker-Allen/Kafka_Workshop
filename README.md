# Near Real-Time Data: The Beauty of Pub/Sub Systems and Getting Started with Kafka
**RE-WORK, AI In Insurance Summit @ NYC** </br>
https://www.re-work.co/events/ai-in-insurance-summit-new-york-2019

For the Hands-on Kafka portion of the Kafka Workshop, it will be supremely helpful to have the following installed ahead of time. (Full disclosure: I do not own a Windows machine, so I cannot guarantee that I'll be able to provide competent technical support for Windows-related issues)

## Download These Ahead of Time!
### 1. Java (most important)

Check to see if you already have Java installed. In Terminal (or Windows equivalent, such as Bash), try:

`java --version`

If you see something other than an error message, you should be all set.
Otherwise, please continue to:

https://www.oracle.com/technetwork/java/javase/downloads/jdk12-downloads-5295953.html

Toward the bottom, for "Java SE Development Kit 12.0.2", select the "Accept License Agreement" radio button, and click to download the OS version that is appropriate for you (macOS or Windows).

After downloading, find it in your Downloads folder, and open. Walk through the installation wizard.

Check that installation completed succesfully by opening a Terminal (or Bash, etc.) window and typing:
`java --version`

You should see something like:
```
java 12.0.2 2019-07-16
Java(TM) SE Runtime Environment (build 12.0.2+10)
Java HotSpot(TM) 64-Bit Server VM (build 12.0.2+10, mixed mode, sharing)
```

### 2. Apache Kafka

Follow "Step 1: Download the code" provided here: https://kafka.apache.org/quickstart.
I recommend placing the unzipped `kafka_2.12-2.3.0` folder somewhere on your desktop.

And that's it. We'll walk through a modified form of Steps 2 to Step 5 together as a class, and we'll demonstrate the importance of certain configuration settings, and how changing them will impact your Kafka implementation.

## Day of Workshop

## Executables

- **Window 1 (Zookeeper Service)**
  - `bin/zookeeper-server-start.sh config/zookeeper.properties`
- **Window 2 (Kafka Service)**
  - `bin/kafka-server-start.sh config/server.properties`


- *Create Topics*
  - `bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic TestTopicA`
  - `bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic TestTopicB`


- **Window 3 (Producer)**
  - `bin/kafka-console-producer.sh --broker-list localhost:9092 --topic TestTopicA`
- **Window 4 (Producer)**
  - `bin/kafka-console-producer.sh --broker-list localhost:9092 --topic TestTopicB`


- **Window 5 (Consumer)**
  - `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic TestTopicA --from-beginning`
- **Window 6 (Consumer)**
  - `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic TestTopicB --from-beginning`

#### Advanced (If there's time)
- **Window 5**
  - (Ctrl+C to halt)
  - `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic TestTopicA --from-beginning --consumer-property group.id=MyGroup`
- **Window 6**
  - (Ctrl+C to halt)
  - `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic TestTopicB --from-beginning --consumer-property group.id=MyGroup`
  - (Ctrl+C to halt)
  - `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092  --from-beginning --consumer-property group.id=MyGroup --whitelist "[a-zA-Z]*"`

## Key Config Files

- conf
  - zookeeper.properties
  - server.properties
  - producer.properties
  - consumer.properties
- bin
  - zookeeper-server-start/stop.sh
  - kafka-server-start/stop.sh
  - kafka-topics.sh
  - kafka-console-producer.sh
  - kafka-console-consumer.sh
