#Cloudera Administrator
##Introduction
Distributed systems usually imply
- Fault-tolerant hardware (which doesn't come cheap)
- Complex coding/programming schemes
- High-performance storace and built-in replication
Hadoop has a different approach since:
- is based on the open-source Apache project
- addresses fault-tolerant cheap hardware
- is inspired by GFS (Google File System) and Google's MapReduce
- is horizotally scalable
in particular **horizontal scalability** entails that adding a node
improves the overall performances of the cluster while 
components are cheap and affordable server machines. 
Storage and computation are both performed on the same network
of machines. Improve scheduling allows the cluster to 
elaborate data on the node (or one of the nodes) where 
hard-copied data actually resides.

Java is used to produce MapReduce while providing abstract methods
which reduce the coding complexity. In particular no code is 
devoted to I/O operations and network comunications amongst nodes.
Replication in Hadoop will serve as a backup in case of 
hardware failure.
###Ecosystem
Hadoop uses a distributed file system (Hadoop DFS - HDFS) to 
achieve data storage and replication. The network of the 
cluster is managed by the resource manage of YARN (Yet Another
Resource Manager) which include MapReduce v2 (MRv2) to elaborate 
data. 
Hadoop also provides web UIs to check the environment which are 
tipically at port :8088 (YARN) and :9870 (NameNode of HDFS). 
Also many tools are built around the Hadoop basement:
- Data processing: Spark, Tez
- Data analisys: Hive, Pig, Impala
- Data discovery: Solr
- Machine Learning: MLib, Mahout
- Data ingestion: Sqoop, Flume, Kafka
- Cluster coordinator: ZooKeeper
- Front-end data analisys: Hue
- Workflow management: Oozie
- Cluster management: Cloudera Manager

