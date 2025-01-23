---
tags:
  - CS598
---
---
Open source implementation of [[Google MapReduce]] and also [[Google File System]] (GFS)

Hadoop Project = Distributed file system + MR engine (But MR engine was replaced by Spark)
![[{0D497BC5-3D24-4D8A-8BCF-5A78CA22C013}.png]]

## Hadoop Architecture
---
- Shared Nothing (SN) Architecture
- SN is suitable for fault tolerance & it is also used by many others (Spark, Hive, Presto)
![[{63D32259-337A-42BB-AE4C-BBEEA8CAFA2A}.png]]
- Map Reduce runs at CPU/RAM Memory level
- Hadoop Distributed File System runs at the storage/disk level 
## Installing & Running Hadoop
---
![[{F68007DA-7840-40AC-80A2-1692ED6BB805}.png]]
![[{9EE788FB-B6A1-462E-8E31-E484B731DA87}.png]]
- Master node also coordinates which worker nodes access which parts of the data set
![[{AA97CC10-D92A-44DD-8330-C78DE936D856} 1.png]]
- Spark engine runs SQL queries on HDFS, spark replaced Hive since it was better 
- Cloudera Impala & Presto are also both engines for SQL queries that run a Map Reduce style data processing on top of HDFS
- Can also use Spark, Presto & Impala process data from non HDFS sources using connectors like AWS S3
