/opt/kafka/bin/kafka-topics.sh --list --zookeeper kaf1:2181,kaf2:2181,kaf3:2181
/opt/kafka/bin/kafka-topics.sh --describe --zookeeper kaf1:2181,kaf2:2181,kaf3:2181

/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --delete --topic collectd
/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --create --topic collectd --partitions 1 --replication-factor 1 --if-not-exists

/opt/kafka/bin/kafka-console-consumer.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --topic mytopic
/opt/kafka/bin/kafka-console-producer.sh --broker-list kaf1:9092 --topic mytopic

/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --create --topic collectd --partitions 10 --replication-factor 2 --config retention.bytes=1074000000 --config segment.bytes=105000000 --if-not-exists

https://github.com/edenhill/librdkafka/issues/437



CLASSPATH=/zookeeper-3.4.8/zookeeper.jar:/zookeeper-3.4.8/lib/* /zookeeper-3.4.8/bin/zkCli.sh -server kaf1:2181,kaf2:2181,kaf3:2181
