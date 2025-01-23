---
tags:
  - CS498
---
---
![[{AB1EB005-BEE5-4494-9F18-BD4D524B43DC}.png]]

**Industry**: Enterprise Database systems have significant upfront costs that includes both hardware & software costs
**Academia:** Manage, process & share mass produced data in the cloud so that it is available to many people

Many "Cloud Killer Apps" are in fact data intensive, so it make sense to use cloud to work with these processes:
	- Batch processing like [[Google MapReduce]]
	- Online Transaction Processing as in automated business applications
	- Online Analytical Processing as in data mining or machine learning


## Scaling Databases:
---
Examples of database scalability:
	- Lots of small transactions
	- Lots of copies of data
	- Lots of processors running on a single query (computer intensive tasks)
	- extremely large data set for one query (data intensive tasks)

Data Replication:
	- Move Data where it is needed
	- Managed replication for availability & reliability, such as backing up data or putting data on a server closer to the user to reduce latency 

## Cloud Characteristics for DBs:
---
![[{239EEAD3-11C6-4082-A290-5D918B38ACB6}.png]]![[{1F8A31A9-4F5E-47B4-B989-464EB048E22B}.png]]
Only Share Nothing Architecture is good for cloud while the other ones are better for local/on site databases
![[{54A4E82A-6AFC-4F4E-A2CE-CB4637DBDFDE}.png]]
![[{33129308-F90A-40A9-BF4D-52B6B8F1A944}.png]]

## Challenges
---
![[{246A3438-EF32-4E77-9EEB-EA9A69CE993B}.png]]
![[{F25706F8-EEB2-4EFF-9A48-7ADC37857523}.png]]
![[{401093AB-EAC9-4411-813F-CFD600262D04}.png]]

## Cloud or Not?:
---
- Transactional data like banking, airline reservations, e commerce, etc. needs consistency and does not use shared nothing, also risks with storing data on an untrusted host, So it is not appropriate for the cloud 

- Analytical Data Management is used to query data from a store to plan, solve problems & decision support, this data is large scale & is most read only. This uses shared nothing architecture & sensitive data can be left out so it is appropriate for the cloud 
![[{80033653-4AAB-4926-92E0-34389F125488}.png]]

![[{B6865246-19A3-432B-A2BF-F94BE3D04B79}.png]]
![[{2A8C065E-A32E-4158-BF51-072D051EBCE3}.png]]
![[{1D96D530-E4CB-493F-8950-926140BD77D6}.png]]

## Why NoSQL?
---
- Value of relational databases:
	- persistent data
	- concurrency/transactions
	- integration
	- mostly standard model
- Impedance mismatch 
- Application vs Integration databases

Need to accommodate data growth (links, social networks, logs, users) and need to scale 

Traditional RDBMS don't scale well due to shared disk
Licensing costs increase technical issues

No SQL, doesn't use SQL, is typically open source & oriented towards clusters
It operates without a schema for the database

There are various types of NoSQL databases:
	- Key-value stores
	- Document stores
	- Extensible record stores