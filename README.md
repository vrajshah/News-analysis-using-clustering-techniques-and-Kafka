# News-analysis-using-clustering-techniques-and-Kafka
INSTALLTION GUIDE

Apache Druid

Prerequisites

JAVA 8, Linux, Mac OS X (windows is not supported), 4CPU/16GB RAM environment.

Downloading

https://www.apache.org/dyn/closer.cgi?path=/druid/0.17.0/apache-druid-0.17.0-bin.tar.gz
Extract Druid by running the following commands in your terminal:

tar -xzf apache-druid-0.17.0-bin.tar.gz

cd apache-druid-0.17.0

Starting up:
From the apache-druid-0.17.0 package root, run the following command:
./bin/start-micro-quickstart
This will bring up instances of ZooKeeper and the Druid services, all running on the local machine, e.g.:
$ ./bin/start-micro-quickstart
[Fri May  3 11:40:50 2019] Running command[zk], logging to[/apache-druid-0.17.0/var/sv/zk.log]: bin/run-zk conf
[Fri May  3 11:40:50 2019] Running command[coordinator-overlord], logging to[/apache-druid-0.17.0/var/sv/coordinator-overlord.log]: bin/run-druid coordinator-overlord conf/druid/single-server/micro-quickstart
[Fri May  3 11:40:50 2019] Running command[broker], logging to[/apache-druid-0.17.0/var/sv/broker.log]: bin/run-druid broker conf/druid/single-server/micro-quickstart
[Fri May  3 11:40:50 2019] Running command[router], logging to[/apache-druid-0.17.0/var/sv/router.log]: bin/run-druid router conf/druid/single-server/micro-quickstart
[Fri May  3 11:40:50 2019] Running command[historical], logging to[/apache-druid-0.17.0/var/sv/historical.log]: bin/run-druid historical conf/druid/single-server/micro-quickstart
[Fri May  3 11:40:50 2019] Running command[middleManager], logging to[/apache-druid-0.17.0/var/sv/middleManager.log]: bin/run-druid middleManager conf/druid/single-server/micro-quickstart
Once the cluster has started, you can navigate to http://localhost:8888. The Druid router process, which serves the Druid console, resides at this address.

Apache Kafka

Kafka Download
https://www.apache.org/dyn/closer.cgi?path=/kafka/2.4.1/kafka_2.12-2.4.1.tgz
Extracting it:
> tar -xzf kafka_2.12-2.4.1.tgz
> cd kafka_2.12-2.4.1

Start the server

Kafka uses ZooKeeper so you need to first start a ZooKeeper server if you don't already have one. You can use the convenience script packaged with kafka to get a quick-and-dirty single-node ZooKeeper instance:
> bin/zookeeper-server-start.sh config/zookeeper.properties

Now start the Kafka server:
> bin/kafka-server-start.sh config/server.properties

Create Topic
Let's create a topic named "test" with a single partition and only one replica:
> bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
