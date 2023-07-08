Kafka Documentation url
--------------------------------
https://kafka.apache.org/quickstart

kafka-producer-example
--------------------------------------------------------------
documents
------------------------------------------------
Open Source Kafka Startup in local
----------------------------------------------
1.Start Zookeeper Server

sh bin/zookeeper-server-start.sh config/zookeeper.properties

2.Start Kafka Server / Broker

sh bin/kafka-server-start.sh config/server.properties

3.Create topic

sh bin/kafka-topics.sh --bootstrap-server localhost:9092 --create --topic NewTopic --partitions 3 --replication-factor 1

4.list out all topic names

sh bin/kafka-topics.sh --bootstrap-server localhost:9092 --list

5.Describe topics

sh bin/kafka-topics.sh --bootstrap-server localhost:9092 --describe --topic NewTopic

6.Produce message

sh bin/kafka-console-producer.sh --broker-list localhost:9092 --topic NewTopic

7.consume message

sh bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic NewTopic --from-beginning

Confluent Kafka Community Edition in local
------------------------------------------------------
1.Start Zookeeper Server

bin/zookeeper-server-start etc/kafka/zookeeper.properties

2.Start Kafka Server / Broker

bin/kafka-server-start etc/kafka/server.properties

3.Create topic

bin/kafka-topics --bootstrap-server localhost:9092 --create --topic NewTopic1 --partitions 3 --replication-factor 1

4.list out all topic names

bin/kafka-topics --bootstrap-server localhost:9092 --list

5.Describe topics

bin/kafka-topics --bootstrap-server localhost:9092 --describe --topic NewTopic1

6.Produce message

bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1

7.consume message

bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic NewTopic1 --from-beginning 

8.Send CSV File data to kafka

bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1 <bin/customers.csv

--------------------------------------------------------------------------------------------------
kafka-installation
---------------------------------------
Command uses
--------------------------------------------
Move into Kafka container
docker exec -it <kafka_conatiner_id> /bin/sh

Go inside kafka installation folder
cd /opt/kafka_<version>/bin

1.Create Kafka topic

kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic quickstart

2.Start Producer app (CLI)

kafka-console-producer.sh --topic quickstart --bootstrap-server localhost:9092

3.Start consumer app (CLI)

kafka-console-consumer.sh --topic quickstart --from-beginning --bootstrap-server localhost:9092
