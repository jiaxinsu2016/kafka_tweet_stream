+ Open terminal & go into kafka installation folder 

+ Run the following commands
  + start zookeeper from one terminal: 
  ```
  bin/zookeeper-server-start.sh config/zookeeper.properties
  ```
  + start kafka from another terminal: 
  ```
  bin/kafka-server-start.sh config/server.properties
  ```
  + create a topic name `test`: 
  ```
  bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
  ```
  + show list of topics: 
  ```
  bin/kafka-topics.sh --list --zookeeper localhost:2181
  ```

+ Run the following two commands from two other terminals, or run Producer.py and Consumer.py from two terminals respectively instead
  + run producer to send message to topic `test`: 
  ```
  bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
  ```
  + run consumer on topic `test`: 
  ```
  bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
  ```
