List all topic:
---------------
/opt/kafka/bin/kafka-topics.sh --list --zookeeper kaf1:2181,kaf2:2181,kaf3:2181
/opt/kafka/bin/kafka-topics.sh --describe --zookeeper kaf1:2181,kaf2:2181,kaf3:2181

Delete topic:
-------------
/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --delete --topic collectd

Create topic:
-------------
/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --create --topic collectd --partitions 1 --replication-factor 1 --if-not-exists
/opt/kafka/bin/kafka-topics.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --create --topic collectd --partitions 10 --replication-factor 2 --config retention.bytes=1074000000 --config segment.bytes=105000000 --if-not-exists

Consumer / producer:
--------------------
/opt/kafka/bin/kafka-console-consumer.sh --zookeeper kaf1:2181,kaf2:2181,kaf3:2181 --topic mytopic
/opt/kafka/bin/kafka-console-producer.sh --broker-list kaf1:9092 --topic mytopic

How to know offset:
-------------------
Old version: /opt/kafka/bin/kafka-run-class.sh kafka.tools.ConsumerOffsetChecker --zookeeper localhost:2181 --group logstash_collectd

New version: /opt/kafka/bin/kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group IMPORT_SERVICE_PLACES --describe --new-consumer

List group id:
--------------
/opt/kafka/bin/kafka-consumer-groups.sh --zookeeper localhost:2181 --list

Reassignment partitions:
------------------------
/opt/kafka/bin/kafka-reassign-partitions.sh --zookeeper hubkaf1-ppd:2181  --reassignment-json-file /tmp/increase-replication-factor.json --execute

/opt/kafka/bin/kafka-reassign-partitions.sh --zookeeper hubkaf1-ppd:2181 --generate --topics-to-move-json-file /tmp/topics-to-move.json --broker-list 1001,1003


Client zookeeper:
-----------------
CLASSPATH=/zookeeper-3.4.8/zookeeper.jar:/zookeeper-3.4.8/lib/* /zookeeper-3.4.8/bin/zkCli.sh -server kaf1:2181,kaf2:2181,kaf3:2181

https://github.com/edenhill/librdkafka/issues/437
