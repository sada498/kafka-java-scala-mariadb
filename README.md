# kafka-java-mariadb-redis
 
# Kafka download for Windows 
## 1. Create a Kafka directory.

    mkdir kafka 
    cd kafka

[Kafka Download page ](https://kafka.apache.org/downloads)
> In this project using Kafka Scala 2.12 Binary downloads:

Scala 2.12  - [kafka_2.12-2.7.0.tgz](https://apache.mirror.digitalpacific.com.au/kafka/2.7.0/kafka_2.12-2.7.0.tgz) 

## 2. Download the binary file into **kafka** folder and extract the file.
    cd kafka_2.12-2.7.0
## 3.Make configuration edits for Kafka
### Go to 
    Kafka\kafka_2.12-2.7.0\config
### Use any editer to edit the file

    server.properties 
### Modify the only below for Socket Server Settings and Log Basics
    listeners=PLAINTEXT://localhost:9092
    log.dirs=C:/Kafka/kafka_2.12-2.7.0/kafka-logs
### save and close
## 4.Start the zookeeper service 
    .\bin\windows\zookeeper-server-start.bat .\config\server.properties
![text](https://link)
## 5.Start the kafka service
    .\bin\windows\kafka-server-start.bat .\config\server.properties
![text](https://link)    
## 6. To check all topics are created in kafka
    .\bin\windows\kafka-topics.bat --list --zookeeper localhost:2181   
  

# kafka download for Ubuntu or Mac 
    mkdir kafka
    cd kafka
## 1. Download the Kafka 
    wget https://apache.mirror.digitalpacific.com.au/kafka/2.7.0/kafka_2.12-2.7.0.tgz

    tar -xvf kafka_2.12-2.7.0.tgz
### Change directory to
    cd kafka_2.12-2.7.0
## 2. Make configuration edits for Kafka
    vi config/server.properties
### Modify the only below for Socket Server Settings

    listeners=PLAINTEXT://localhost:9092
### create Log folder
    mkdir logs
## 3. Start the zookeeper service
    ./bin/zookeeper-server-start.sh ./config/zookeeper.properties > ./logs/start_zk.log &
## 4.Start the kafka service
    ./bin/kafka-server-start.sh ./config/server.properties > ./logs/start_kafka.log &
## 5. Check the kafka running
    ps -ef|grep kafka
# Docker instal and config
