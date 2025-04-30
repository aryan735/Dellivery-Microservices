Kafka Integration with DeliveryBoy and EndUser
This project demonstrates how to integrate Apache Kafka with the DeliveryBoy and EndUser microservices, enabling efficient messaging and data flow between them. The project is built using Spring Boot and includes both producer and consumer implementations.

Features
Kafka Producer & Consumer setup for two microservices: DeliveryBoy and EndUser.

Kafka Configuration for both microservices in application.yml files.

New Kafka Service implementations for managing message flow.

Integration of Kafka topics for communication.

Project Structure
DeliveryBoy Microservice:
KafkaConfig.java: Configures Kafka producer and consumer.

LocationController.java: Handles incoming requests related to location.

KafkaService.java: Kafka producer and consumer logic.

application.yml: Configuration for Kafka, including topic names and other settings.

EndUser Microservice:
KafkaConfig.java: Configures Kafka producer and consumer.

AppConstants.java: Defines constants used across the application.

application.yml: Configuration for Kafka, including topic names and other settings.

Setup Instructions
1. Prerequisites
Ensure you have the following installed:

Java 17 or above

Apache Kafka and Zookeeper running on your local machine or remote servers.

Maven for building the project.

2. Running Kafka & Zookeeper
Before running the application, start Zookeeper and Kafka:

bash
Copy
Edit
# Start Zookeeper
bin\windows\zookeeper-server-start.bat config\zookeeper.properties

# Start Kafka
bin\windows\kafka-server-start.bat config\server.properties
3. Running the Microservices
To run the services locally, navigate to the deliveryboy and enduser directories and run:

bash
Copy
Edit
# For DeliveryBoy microservice
mvn spring-boot:run

# For EndUser microservice
mvn spring-boot:run
4. Creating Topics in Kafka
You may need to create topics for communication between the services. Use the Kafka CLI to create topics:

bash
Copy
Edit
# Create Kafka topics (Example)
bin\windows\kafka-topics.sh --create --topic delivery-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
bin\windows\kafka-topics.sh --create --topic enduser-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
5. Testing the Communication
Once both services are running and topics are created, test communication by sending messages through the Kafka producer and consuming them with the consumer logic in both microservices.

Technologies Used
Spring Boot

Apache Kafka

Java 17

Maven

Contributing
Feel free to fork the repository and submit pull requests. Any contributions are welcome!

License
This project is licensed under the MIT License - see the LICENSE file for details.
