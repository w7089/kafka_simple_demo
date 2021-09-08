# kafka_simple_demo

To raise Kafka demo stack run:

`docker-compose up -d`

It will start `ZooKeeper`, sing `Kafka` broker, sample Kafka producer, consumer and Kafka Manager:

```
/tmp/kafka_simple_demo$ docker-compose ps
     Name                   Command                  State                       Ports                 
-------------------------------------------------------------------------------------------------------
kafka            /opt/bitnami/scripts/kafka ...   Up (healthy)   9092/tcp                              
kafka-consumer   kafkacat -b kafka:9092 -C  ...   Up                                                   
kafka-manager    cmak-3.0.0.4/bin/cmak            Up             0.0.0.0:9000->9000/tcp                
kafka-producer   kafkacat -b kafka:9092 -t  ...   Exit 0                                               
zookeeper        /opt/bitnami/scripts/zooke ...   Up (healthy)   2181/tcp, 2888/tcp, 3888/tcp, 8080/tcp
```

Kafka producer creates topic `test` and writes 3 messages specified in `my_msgs.txt`. 

Kafka consumer is always up and consumes messages from topic `test`

