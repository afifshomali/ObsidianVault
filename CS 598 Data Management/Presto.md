---
tags:
  - CS598
---
---
Presto is a widely used analytics engine, used by companies like IBM, Intel & Meta

## Context
---
- Ability to quickly & easily extract insights from large amounts of data is becoming increasingly more important (insights = analytics & large amount of data is OLAP (Online Analytical Processing) not OLTP)
- Using  a popular query language like SQL can make data analytics accessible to more people (as in the user interface is SQL not MapReduce or something else) 

- Paper for Presto has no clear problem statement, it is an open source distributed SQL query engine, the paper describes the design of the Presto Engine 
- Approach or Proposal:
	- Distributed SQL engine
	- "adaptive, flexible & extensive"
	- Can read data from many sources 
	- "Responsible for supporting much of the SQL analytic workload at Meta/Facebook"

## Use Cases 
---
- Interactive Analytics 
	-  Interactively analyze data in HDFS or Hive
	- Meaning we want quick outputs that don't take a lot of time 
- Batch ETL (Extract Transform Load)
	- For example Data ingestion 
- A/B Testing 
	- Latency between 5-30s for arbitrary slice & dice 
- Advertiser Analytics
	- For example: Facebook Analytics 

## Architecture, & compared to Google File System
---
![[{49141C3D-0F1C-4005-AFA5-2055412BE7CF}.png]]
- Presto uses a Planner/Optimizer & Scheduler to find the locations of the data & assigns individual works to read data in parallel 
- Then Process query/aggregation/analytics in parallel too in order to produce the results
![[{14736DC2-37A6-48B3-B460-41BD91D4B2DB}.png]]
![[{29934338-A316-49E2-9AEF-8225E5CB2C3E}.png]]
Note that Presto does support multiple different types of data sources by using a different connector type

## Query Processing & System Design
---
![[{4F74969B-1122-4872-8C9D-6121C6937E1F}.png]]
![[{5A255998-130A-411F-AAF4-AD6C1A7EB95D}.png]]

## Query Optimization
---
- Logical to Physical Plan (which involves stages)
- Logical Planning: rule based transformations
	- predicate & limit pushdown
	- column pruning
	- decorrelation
- Physical Planning:
	- Stage := tasks that can run in parallel (as in by multiple workers)

![[{5AADF214-9068-4416-8586-634AF976B3BC}.png]]
![[{4736EFB3-7D04-45A3-A5C8-23367DD26520}.png]]

## Stage Scheduling
---
- Stages - Tasks (including Pipelines) - Node Placement 
- Stage Scheduling can be all at once or phased
	- Phased waits until a build (hash) table is built 
- Build phase runs in a separate pipeline after the query optimization 
![[{B08E16AB-427E-4880-B728-E40C3A4C9B14} 1.png]]

![[{F4E16C4A-029B-4FA1-AEE5-100D20F6CD61}.png]]

## Task Scheduling
---
- leaf stages or intermediate stages

- leaf stages: co locate tasks & data sources
- intermediate stage: on any worker nodes 

Making worker nodes co located with storage nodes allows them to eliminate needs for shuffles when doing joins  
![[{3600D566-8781-439B-B313-A673A8BB71C3}.png]]

**Limitations:**
- No fault tolerance mechanism
	- Ok for short queries on 10s-100s of worker nodes
	- Not desirable for week long computing
- Inherits limitations of Java
	- consumes more memory for JVM
	- may be slower for compute intensive tasks (matrix multiplication)
![[{2EED9584-6D92-4A9D-B5F7-87D2D61D928B}.png]]
