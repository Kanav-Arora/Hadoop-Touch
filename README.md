# Hadoop-Touch

This repository is a hands-on exploration of **Hadoop architecture**, **MapReduce programming model**, and **data processing with both Java and Python**.  
It uses a **Docker-based Hadoop cluster** (with YARN, HDFS, and MapReduce) so you can quickly run, test, and extend exercises without manual setup.


## Jobs


### 1. Word Count
The classic MapReduce program that counts the frequency of each word in a given dataset.  
Implemented in:
- **Java** (`jobs/WordCount/java/WordCount.java`)


## Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/Hadoop-Touch.git
cd Hadoop-Touch
```

### 2. Start Hadoop Cluster
```bash
docker-compose up -d
```

### 3. Connect to the NameNode Container
Run all HDFS and Hadoop commands from inside the NameNode container.

-> List running services:
```bash
docker ps
```

-> Attach to NameNode (replace `namenode` with your container name if different):
```bash
docker exec -it namenode bash
```


## Running a Hadoop Job

Once inside the NameNode container, use the following command pattern:

```bash
hadoop jar {jar_path} {classname} {input_data_path as per hdfs} {output_path as per hdfs}
```

`Example:`
```bash
hadoop jar /jobs/WordCount/wordcount.jar WordCount /input/WordCount /output/WordCount
```

## YARN UI

Once the cluster is running, access the YARN ResourceManager UI at:
http://localhost:8088

## HDFS UI

Once the cluster is running, access the HDFS NameNode UI at:
http://localhost:9870