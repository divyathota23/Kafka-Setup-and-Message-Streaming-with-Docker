# Kafka-Setup-and-Message-Streaming-with-Docker
This project demonstrates the setup of a Kafka environment using Docker, creation of a Kafka topic, and implementation of a producer and consumer. The producer sends messages to the Kafka broker, and the consumer receives these messages, showcasing the basic functionality of Apache Kafka for message streaming.

## 1. Installing Docker Desktop
To begin, install Docker Desktop on your local machine. You can download Docker Desktop from the official Docker website and follow the installation instructions specific to your operating system (I used Windows).

![Screenshot (971)](https://github.com/user-attachments/assets/53823607-69d8-40c0-9507-fbd35b6c0a62)


## 2. Creating Docker Compose File
Next, create a docker-compose.yml file to define the services for Zookeeper and Kafka. This file contains the necessary configurations and images to set up Kafka on your local machine. Below is the content of the docker-compose.yml file:

![Screenshot (972)](https://github.com/user-attachments/assets/93b00f18-e9b7-4679-8f49-5ae91ce6047e)

## 3. Running Docker Containers
Start the Zookeeper and Kafka services using Docker Compose by running the following command in the terminal from the directory containing the docker-compose.yml file:

**docker-compose up**

![Screenshot (973)](https://github.com/user-attachments/assets/6fa8061c-9a12-42b0-a894-0560e5712814)


## 4. Accessing the Kafka Container
Once the containers are running, log into the Kafka container to set up the producer and consumer code. Use the following commands to access the Kafka container:




**docker ps  # To list the running containers and get the Kafka container ID**

**docker exec -it <kafka_container_id> /bin/bash  # Replace <kafka_container_id> with the actual ID**


![Screenshot (977)](https://github.com/user-attachments/assets/ff7d8c92-a03f-48de-b061-06d3b44c6575)


## 5. Setting Up Kafka Topic
Inside the Kafka container, locate the Kafka binaries and create a topic named test-topic with one partition using the following commands:

**cd /opt/kafka/bin**

**./kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1**

![Screenshot (975)](https://github.com/user-attachments/assets/8e7b8912-e79f-4722-bf1f-3389bf0cc9e8)


## 6. Creating Producer and Consumer

 **Producer:** Create a producer to publish messages to **test-topic:**

**./kafka-console-producer.sh --topic test-topic --bootstrap-server localhost:9092**



![Screenshot (979)](https://github.com/user-attachments/assets/d83e1ebc-aba2-495e-98e8-cccd1d712e0a)

You can now start typing messages, and they will be sent to the Kafka topic.




**Consumer:** Open another terminal, log into the Kafka container again, and create a consumer to receive messages from **test-topic:**

**docker exec -it <kafka_container_id> /bin/bash  # Replace <kafka_container_id> with the actual ID**

**cd /opt/kafka/bin**

**./kafka-console-consumer.sh --topic test-topic --bootstrap-server localhost:9092 --from-beginning**


![Screenshot (980)](https://github.com/user-attachments/assets/1579750f-a325-481d-b234-f96476e7d387)


## 7. Creating a Topic with Multiple Partitions
To create a topic named test-topic with multiple partitions (e.g., 3 partitions), use the following commands:



**docker exec -it <kafka_container_id> /bin/bash  # Replace <kafka_container_id> with the actual ID**

**cd /opt/kafka/bin**

**./kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 3**



## 8. Producing and Consuming Messages
In the producer terminal, type messages and press Enter to send them to the Kafka server running on port 9092. In the consumer terminal, you will see the messages being received in real-time, demonstrating the process of sending and receiving messages through Kafka.


![Screenshot (970)](https://github.com/user-attachments/assets/bc1e4ef9-dd9f-4360-a3f9-721f5778562a)


