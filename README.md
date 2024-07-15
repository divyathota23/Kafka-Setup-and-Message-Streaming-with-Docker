# Kafka-Setup-and-Message-Streaming-with-Docker
This project demonstrates the setup of a Kafka environment using Docker, creation of a Kafka topic, and implementation of a producer and consumer. The producer sends messages to the Kafka broker, and the consumer receives these messages, showcasing the basic functionality of Apache Kafka for message streaming.

## 1. Installing Docker Desktop
To begin, install Docker Desktop on your local machine. You can download Docker Desktop from the official Docker website and follow the installation instructions specific to your operating system (I used Windows).

## 2. Creating Docker Compose File
Next, create a docker-compose.yml file to define the services for Zookeeper and Kafka. This file contains the necessary configurations and images to set up Kafka on your local machine. Below is the content of the docker-compose.yml file:

![Screenshot (972)](https://github.com/user-attachments/assets/93b00f18-e9b7-4679-8f49-5ae91ce6047e)

## 3. Running Docker Containers
Start the Zookeeper and Kafka services using Docker Compose by running the following command in the terminal from the directory containing the docker-compose.yml file:

**docker-compose up**
