---
tags:
  - CS598
---
---

## Map Reduce
---
![[{AE194919-A38F-4218-A688-7AC1147C0DBA}.png]]
High level abstraction of providing just map & reduce function to hide messy details needed for parallelization, fault tolerance, data distribution & load balancing. 
Example usage could be character frequency, Map would flatten strings to list of chars and reduce would count chars in the list.

Each work has a part of the data, the outputs at the very end are written to disk
Fault tolerance by re executing map & affected reduce as well as master restarting if it goes down.
Can be optimized with a combiner which maximizes reads from the same machine which can reduce network transfer.
Master is single point of failure, not good for complex computation like NN training, Read Write to disk can be slow and doesn't apply to online transaction process 

Hadoop is open source version of Map Reduce and Google file system replaced by HDFS
HDFS also works with Spark, Hive, Presto , etc. 
Hadoop has shared nothing architecture 
![[{10A84A7A-345F-43F8-AC34-AC4B7B2E5554}.png]]

## Google File System
---
![[{2D504DE7-A690-4FAC-BCB8-110699790AA9}.png]]
Primary node receives the notification of first change/mutation, these changes are then propagated to the replicas. But the data is actually sent to the closest node, replica or primary.

File system to run Map Reduce on top of, needs to be scalable and reliable 
Access data with standard methods, filename, offset & size
No complete data duplication
Component failures are normal, files can be huge like text or video, append rather than overwrite so no in place updates. 
![[{043CFE22-9C4B-48A6-953F-9A82B012BE9C}.png]]
![[{933633A5-3174-4AB1-938F-08121243B3D6}.png]]

## Presto
---
![[{E5FF57F5-E6A8-4665-B799-218D598DC931}.png]]
GFS is not open source compared to the other options.

Presto is an analytics engine for large amounts of data, OLAP and uses SQL query interface compare to MR like in the previous papers. 
It can read from multiple data sources 
![[{25877BBF-52FE-4052-AF78-305741AABC3A}.png]]
![[{26DED8D0-D55F-40A1-87D2-68C75A00F799}.png]]


## Span Store
---
![[{BD17DEA2-81F2-4F3C-ACE4-1CCFB47BE919}.png]]
Store data/use compute by using multiple cloud providers & leverage best deals from each one. Spanstore is abstraction for this so you store your data using spanstore & it determines how to best distribute
![[{048D1297-9E7E-4E42-ADF8-11F88BC5CACD}.png]]
![[{497F9EF8-E91C-456F-ACA0-224AE7F2E8EF}.png]]
![[{F3293065-C7E2-40F1-8305-89374A503753}.png]]
## FlexPushdownDB
---
![[{D54A2BEB-9510-4FEC-983C-909DA262DA3D}.png]]
We disaggregate storage from compute when using cloud services, this can lead to network bottleneck when trying to send data from storage to compute. 

So we move part of compute down to storage/server level. Also can cache frequently used/highly used parts of the data at the compute so we get a hybrid approach since caches generally aren't that big.

PushdownDB caches columns which are called segments rather than aggregated results. Want to leverage caching when possible, otherwise pushdown as much computation as reasonable/possible
![[{55E4432F-3BF4-474A-8FD8-3122D39904EC}.png]]
.
## Teleport
---
![[{2E8C6C34-D721-495F-AB17-39825EDCFE28}.png]]
Similar background/justification to pushdownDB, disaggregation is become the norm. 

So teleport allows us to scale compute, memory & storage independently, rather than usual where if we scale compute we will also need to scale memory. 
![[{B052A1DF-FF6E-4161-AC5C-6ABCD8F23A46}.png]]
## Locality Sensitive Hashing: LSH
---
![[{447805DF-085E-4835-9ACA-B8FABF7ACB38}.png]]
Answers is 1 bc original distance was 2 and we halved the distances when projecting 

Want to find similar items to a query quickly, we need to define a similarity measure and then hash items into buckets using that similarity measure, then given a query we can compute this hash for the query and return the items in the same bucket

LSH does an approximate nearest neighbor search, use multiple hash tables for better accuracy
![[{6A5B1B12-114C-4AB9-A1C3-88AD4B50B811}.png]]
Instead of computing distances we project onto some lower dimension space and use that to determine the buckets 
## Product Quantization: PQ
---
![[{783D11B6-7FA7-43EB-BA57-FEC33D6F580A}.png]]
Approximate nearest neighbor, efficient and more accurate compare to LSH since it also considers the distribution of the data
![[{5C6626AA-4234-4B55-9196-892DD6B5599F} 1.png]]

## Hierarchal Navigable Small Worlds: HNSW
---
![[{A44C2DD9-E46E-42D7-903C-2585D23E2DDF} 1.png]]
![[{9BBEBD09-4E9F-4267-B6A3-A69F35F1E7C9}.png]]
![[{C7A8E469-2CDC-4BB3-8B7E-DDBC63BB4DB0}.png]]
![[{3199975C-72FF-4145-9FF8-8D744062D9D2}.png]]
![[{D1FD07FD-075F-4461-BDF1-4FDEF48D32FB}.png]]

## DiskANN
---
![[{D35379E1-BBDB-4ACF-BB8D-0C263A2D9D59}.png]]
Divide 1 million data points to 40 clusters, but the since $\ell$ is 2 we replicate/add each data point to the nearest 2 clusters 

Nodes won't fit in memory if we have a really large amount of data
![[{A772C899-75DC-4E04-AD90-15AC3A9AF9C6}.png]]
Uses PQ to compress data
Keep original data & full precision edges on SSD/storage rather than memory 
![[{204FEFF7-6375-4EAC-BB5A-B8071063A808}.png]]

## ACORN
---
![[{CEA37EC4-2F07-4C92-8755-316D713B8055}.png]]
![[{08DE49E8-F81F-4187-A581-F65D11267E9F}.png]]

![[{D9E5B12F-C280-4747-A55C-BC2D6734879D}.png]]
ACORN Filters while traversing, retrieval is on an induced graph so some nodes are pruned dynamically while searching and neighbors are expanded by some factor just in-case we filter out a certain neighbor

If too sparse then need to resort to brute force approach 
## DB-Bert
---
![[{1F5AD7D1-54B3-4FF2-9C3E-9897377D1C20}.png]]
Tune database parameters using manuals. guides & online blog posts. Use NLP Bert model to extract these hints and also suggest hints based on the specific workload type. 
## Air Index
---
![[{459CFF23-754A-47AE-BC19-B28FC3501AF6}.png]]
![[{A2316EBB-F003-4D84-90AA-56012DFFA6AA}.png]]
![[{9C50218A-F61C-45A3-A7BD-CB7831312008}.png]]
![[{B302EEB4-A666-455F-B497-DBA8E69E48E3}.png]]
But need to consider the number of layers so for quiz example:
$4  \cdot (50 + 4/1) = 216$ 
But can also separate out the data layer access if it is stored somewhere else like in the slide examples 
Air Index is used to tune indexes based on the various parameters like I/O, difference layer page sizes and using machine learning/regression

Uses Piecewise linear model to for difference ranges of values of keys we need to find 

## Bao
---
![[{BE210B6E-849E-4F83-AF4A-6A6BCB8C5623}.png]]
Multi Armed Bandit is the problem type. Thompson Sampling is the technique used to work on the multi armed bandit problem. 

Tree CNN is the structure of the learning model used for this, Tree CNN preserves the hierarchy of Queries like joins, filters etc allowing for a more accurate model
## QueryFormer
---
![[{C4A429F0-1C1B-4D47-8FF4-DA38BD3E48EF}.png]]

6 is a self attention dependency link, other nodes should have it too.
Rest of arcs follow parent of structure. 
4 is removed because c is not a parent of b/isn't linked to b 