
# Realtime Logs Processing with Apache Airflow, Kafka & Elasticsearch

This project demonstrates a real-time logs processing system built using Apache Airflow, Apache Kafka, and Elasticsearch. It covers everything from setting up Kafka and Elasticsearch clusters to ingesting, processing, and indexing logs in real-time.

## System Architecture
![Screenshot 1](screenshots/ss1.png)
- Apache Kafka is used as the messaging backbone for log streaming.
- Apache Airflow manages the orchestration of ETL workflows.
- Elasticsearch stores and indexes logs for real-time search and analytics.

## Features

- Real-time ingestion and processing of logs
- Automated workflow orchestration with Airflow DAGs
- Scalable Kafka clusters on Confluent Cloud
- Log indexing and search with Elasticsearch
- Secrets management using AWS Secrets Manager
- Deployment automation with CI/CD support

## Setup Instructions

1. **Apache Kafka**: Create an account on Confluent Cloud, create an environment and provision a Kafka cluster. Create topics and generate API keys for authentication.
2. **Elasticsearch**: Create an Elasticsearch account, setup an index with partitions, and obtain the API key and URL.
3. **AWS Setup**:
   - Create an IAM user with appropriate permissions.
   - Create an S3 bucket to store DAGs and dependencies.
   - Setup AWS Secrets Manager to store Kafka and Elasticsearch credentials.
4. **Apache Airflow (MWAA)**:
   - Create a new Managed Workflows for Apache Airflow (MWAA) environment.
   - Configure it to access your DAGs folder on S3.
   - Run Airflow commands to initialize the database, migrate, create users, and start the webserver and scheduler.
5. **Configuration**:
   - Store the following secrets in AWS Secrets Manager: `KAFKA_SASL_USERNAME`, `KAFKA_SASL_PASSWORD`, `KAFKA_BOOTSTRAP_SERVER`, `ELASTICSEARCH_URL`, `ELASTICSEARCH_API_KEY`.
   - Configure DAGs to use these secrets for connecting to Kafka and Elasticsearch.

## Usage

- Trigger the Airflow DAGs to start streaming logs from producers to Kafka topics.
- Logs are consumed and indexed into Elasticsearch in near real-time.
- Use Kibana or Elasticsearch API to search and visualize the logs.

## Screenshots


![Screenshot 2](Screenshots/ss2.png)
![Screenshot 3](Screenshots/ss3.png)
![Screenshot 4](Screenshots/ss4.png)
![Screenshot 5](Screenshots/ss5.png)
![Screenshot 6](Screenshots/ss6.png)

## Requirements

- Python 3.x
- Apache Airflow (Managed Workflows for Apache Airflow recommended)
- Confluent Kafka Cloud account
- Elasticsearch Cloud account
- AWS account with Secrets Manager, S3, and IAM configured

## Keywords

realtime, logs, processing, airflow, kafka, elasticsearch, python, dataengineering, mwaa, aws, cloud, devops

---
Created by Shreyas Gopi Koundinya
