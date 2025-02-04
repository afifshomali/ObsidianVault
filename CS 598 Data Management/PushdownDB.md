---
tags:
  - CS598
---
---
## Storage Disaggregation Architecture
---
![[{2ADA814A-4AEA-4566-9CE6-721EDB29CA0F}.png]]

**How to mitigate the network bottleneck?:**
- Solution 1: Move data to computation
	- Cache storage in the computation layer, like AWS snowflake
- Solution 2: Move computation to data
	- Pushdown computations to storage layer, that way we send less data over the network

We need to address:
- How to implement relational operators to leverage existing cloud services 
- What are performance & cost tradeoffs?
![[{94D04D92-ABF2-46C4-9A7F-911F0A814908}.png]]
- Using S3 gives us virtually infinite storage capacity with relatively low costs
- Partition input relations into multiple shards & each shard is stored as a separate object in S3
- S3 vs EBS vs Local Store
	- S3 has virtually infinite capacity, its shared across all nodes, lower cost & durable

## Apache Parquet & S3 Select
---
- Column oriented data format 
- The same attribute is stored together 
- Open source of Google's Dremel
![[{F434DFBE-CA04-4516-A809-05B9607B6902}.png]]
We can optimize for time series data, as we can filter data added more recently very easily at the storage level since we can use the metadata
![[{B4185720-748F-4C56-9090-76C4475F8C54}.png]]
S3 Select supports limited SQL queries on CSV & Parquet Data formats
- S3 select recognizes schemas for both data formats
- simple queries with predicates & aggregations (no join, group-by, sort etc.)
![[{B1A9F111-BEB2-4C27-B624-7BFE3F02ED1A}.png]]
Azure also offers similar features
## Pushdown DB
---
PushdownDB supports:
- Filter 
- Project 
- **Top-K**
- **Join**
- **Group-by**
The bold values are what PushdownDB supports over S3 select
![[{D9096614-B13E-4789-A10A-13269154F308}.png]]
![[{97ECD0CC-932D-440F-9B3B-0FA84D074271}.png]]
![[{DA806BBC-B77D-43A4-BF72-E9B9D86DE9D0}.png]]
![[{98FBC1C2-7765-4A04-BC25-5C96570891F0}.png]]
![[{0854E4BB-C3F5-4A75-9E6D-F11D9CE04AD6}.png]]
