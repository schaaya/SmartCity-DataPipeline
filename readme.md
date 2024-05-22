
# Smart City Vehicle Tracking: Real-Time Data Engineering Project

## Overview
This project orchestrates the end-to-end development of a smart city solution, focusing on analyzing real-time IoT data using cloud and big data technologies. The primary goal is to deliver enhanced urban mobility, safety, and operational efficiency through agile ETL pipelines and real-time analytics.

## Table of Contents
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)

## Tech Stack
- **Languages:** Python, SQL
- **Big Data Processing:** PySpark, Apache Spark
- **Containerization:** Docker
- **Cloud Services:** AWS S3, AWS Redshift, AWS Glue, AWS Anthena
- **Streaming and Coordination:** Kafka, Zookeeper

## Architecture
The architecture of this project involves several key components:

1. **Data Ingestion:** Collects data from various vehicle related iot sources using Kafka.
2. **ETL Pipeline:** Processes the data using PySpark and transforms it into a usable format.
3. **Data Storage:** Stores the processed data in AWS Redshift for analytics.
4. **Real-Time Analytics:** Provides real-time data insights and visualization.
5. **Orchestration:** Uses Zookeeper for managing distributed applications and ensuring coordination among services.

![Architecture Diagram](C:\Users\Chaaya\PycharmProjects\SmartCity\img.png)

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/schaaya/SmartCity-DataPipeline.git
   cd SmartCity-DataPipeline
   ```

2. **Set up the Python environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

3. **Set up Docker:**
   Make sure Docker is installed and running on your machine. Then, build and run the Docker containers:
   ```bash
   docker compose up -d
   ```

## Usage
To start the ETL pipeline and process data:

1. **Run the main.py**
2. ```
   python3 jobs/main.py
   ```

3. **Execute docker.yml:**
   ```bash
    docker exec -it smartcity-spark-master-1 spark-submit \
    --master spark://spark-master:7077 \
    --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.5.0,\
   org.apache.hadoop:hadoop-aws:3.3.1,\
   com.amazonaws:aws-java-sdk:1.11.469 jobs/spark-city.py
   ```
