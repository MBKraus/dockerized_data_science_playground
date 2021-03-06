# Containerized data science / -engineering playground (w/ Kafka, Airflow, MLFlow, Tensorflow-Keras and SKLearn) for simulating a microservices-oriented architecture

Key containers:

* Airflow container (port 8080) for scheduling / automating tasks. This container has your go-to data science tools installed (i.e. Tensorflow, Keras, and SKLearn).
* Kafka container (port 9032) for facilitating streaming data. The current setup is structured along one topic ('TopicA') with one partition. Along the airflow container one could automate data retrieval from the Kafka topic by having the container communicate with the 'kafka:9092' address
* MLFlow container (port 5000) for logging parameters and metrics of trained models (through 'mlflow:5000')

Supporting containers

* Postgres container (port 5432) for Airflow
* Zookeeper container (port 2181) for Kafka (keeps track of status of the Kafka cluster nodes, topics, and partitions)
