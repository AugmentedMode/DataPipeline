# DataPipeline


### Description

Implementation of a scalable distributed image stream processer using Kafka, Tensorflow, and Spark. 

This project will demostrate an ETL architecture which will:

1) Extract many traffic related images coming from multiple different sources (cars)
2) Transform each image into its predicted image embeddings based on OPENAI's CLIP model
3) Load all image embeddings into a database for it to be used for analytics (Image search using NLP)
4) Provide real-time analytics / reporting on our ETL 

### Goals/Tasks

* Implement an end to end solution for a real world business case scenario within big data and computer vision
* Showcase the power of distributed processing within Big Data

### Install Dependencies

Below is the installation guide of all dependencies on Ubunto 20.04

1) get pip requriements 

```console
$ pip3 install -r requirements.txt
```

2) Install Java: 

```console
$ sudo apt install default-jre 
```

```console
$ sudo apt install default-jdk
```

```console
$ java -version
```

```console
$ javac -version
```

3) [Download Kafka from here ](https://www.apache.org/dyn/closer.cgi?path=/kafka/2.8.0/kafka_2.13-2.8.0.tgz)


4) Extract it

```console
$ tar -xzf kafka_2.13-2.8.0.tgz
```

### How to Run locally 

1) CD into Kafka directory

```console
$ cd kafka_2.13-2.8.0
```

2) Start Kafka Environment

```console
# Start the ZooKeeper service
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```

```console
# Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties
```

3) Start a single Faust worker

```console
$ faust -A pipeline worker -l info
```

4) OPTIONAL start many Faust workers (each workers needs a unique data directory and web port)


```console
$ faust --datadir=workers/worker1 -A pipeline -l info worker --web-port=6066

```

```console
$ faust --datadir=workers/worker2 -A pipeline -l info worker --web-port=6067

```
