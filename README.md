# Real-time Financial Transactions CDC 

## Overview

This Python script is designed to generate simulated financial transactions and insert them into a PostgreSQL database. This project simply focuses on being a test environment where CDC is employed with Debezium. The financial data is generated, hence is synthetic. The library `faker` creates unreal transaction data and inserts it into a PostgreSQL table.

## Requirements
1. **Install Required Python Libraries:**

   You can install the required libraries using pip:

   ```bash
   pip install -r /path/to/requirements.txt
   ```
2. Python 3.9+
3. PostgreSQL server
4. Docker and Docker Compose

## Services in the Docker Compose File

- **Zookeeper:** A centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services.
- **Kafka Broker:** A distributed streaming platform that is used here for handling real-time data feeds. A web-based tool, Confluent Control Center monitors the changes in the Kafka broker.
- **Debezium:** An open-source distributed platform for change data capture.
- **Debezium UI:** A user interface for managing and monitoring Debezium connectors.
- **Postgres:** An open-source relational database.

## Getting Started

1. **Clone the Repository:**
   Ensure you have this Docker Compose file in your local system. If it's part of a repository, clone the repository to your local machine.

2. **Navigate to the Directory:**
   Open a terminal and navigate to the directory containing the Docker Compose file.

3. **Run Docker Compose:**
   Execute the following command to start all services defined in the Docker Compose file:

   ```bash
   docker-compose up -d
   ```

   This command will download the necessary Docker images, create containers, and start the services in detached mode.

4. **Verify the Services:**
   Check if all the services are up and running:

   ```bash
   docker-compose ps
   ```

5. **Accessing the Services:**
   - Kafka Control Center is accessible at `http://localhost:9021`.
   - Debezium UI is accessible at `http://localhost:8080`.
   - Postgres is accessible on the default port `5432`.

6. **Shutting Down:**
   To stop and remove the containers, networks, and volumes, run:

   ```bash
   docker-compose down
   ```

## Future work
For production environments, we can add data persistence and link it with Slack channel to signal us if there is any change in the incoming data, thereby, inducing prompt action dealing with data drift and its problems.
