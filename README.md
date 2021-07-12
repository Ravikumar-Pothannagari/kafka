# kafka
Kafka

# start zookeeper

	E:\Softwares\Kafka\kafka_2.13-2.8.0\.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
	
	E:\Softwares\Kafka\kafka_2.13-2.8.0>zookeeper-server-start.bat config\zookeeper.properties
	

# Start Kafka Broker with the following command:

	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-server-start.bat config\server.properties

# Creating Kafka Topics

	kafka-topics -zookeeper localhost:2181 -topic <topic_name> -create
	
	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-topics -zookeeper localhost:2081 -topic example_topic_1 -create
	
	
	kafka-topics.bat -zookeeper localhost:2181 -topic <topic_name> --create --partitions <value> --replication-factor <value>
	
	
	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-topics --zookeeper localhost:2181 --topic example_topic_1 --create --partitions 3 --replication-factor 1
	WARNING: Due to limitations in metric names, topics with a period ('.') or underscore ('_') could collide. To avoid issues it is best to use either, but not both.
	Created topic example_topic_1.

# Listing the number of Topics

	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-topics.bat --zookeeper localhost:2181 -list
	
	example_topic_1

# Describing a topic

		E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-topics.bat --zookeeper localhost:2181 --describe --topic example_topic_1
		Topic: example_topic_1  TopicId: IASvG2eQRyWGWDJFw2YWeA PartitionCount: 3       ReplicationFactor: 1    Configs:
				Topic: example_topic_1  Partition: 0    Leader: 0       Replicas: 0     Isr: 0
				Topic: example_topic_1  Partition: 1    Leader: 0       Replicas: 0     Isr: 0
				Topic: example_topic_1  Partition: 2    Leader: 0       Replicas: 0     Isr: 0


# Deleting a topic

	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-topics.bat --zookeeper localhost:2181 --topic example_topic_1 --delete

#Sending data to Kafka Topics
	
	Kafka Console Producer
		
	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-console-producer.bat --broker-list localhost:9092 --topic example_topic_1

# Producer with Keys	
	
	'kafka-console-producer --broker-list localhost:9092 --topic <topic_name> --property parse.key=true --property key.separator=,  
	> key,value  
	> another key,another value' 
	
	E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-console-producer --broker-list localhost:9092 --topic example_topic_1 --property parse.key=true --property key.separator=,

# Kafka Console Consumer	



# Console producer:

.\bin\windows\kafka-console-producer --topic example-topic --bootstrap-server broker:9092 \
  --property parse.key=true \
  --property key.separator=":"

# Console consumer:

.\bin\windows\kafka-console-consumer --topic example-topic --bootstrap-server broker:9092 \
 --from-beginning \
 --property print.key=true \
 --property key.separator="-"


E:\Softwares\Kafka\kafka_2.13-2.8.0>zookeeper-server-start.bat config\zookeeper.properties
E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-server-start.bat config\server.properties
E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-console-producer --broker-list localhost:9092 --topic example_topic_2 --property parse.key=true --property key.separator=,
E:\Softwares\Kafka\kafka_2.13-2.8.0>kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic example_topic_2


https://www.javatpoint.com/kafka-console-consumer