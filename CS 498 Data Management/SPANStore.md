---
tags:
  - CS598
---
---
## Context
---
- There exists many cloud storage services, all designed for simple PUT/Get operations
- Examples are AWS S3, Microsoft Azure Blob Storage/File Storage & GCP Cloud Storage
- They don't have transaction processing which makes them cost effective
- All these cloud providers have their own pricing schemes so it can be hard to determine most cost effective scheme to manage data
## Problem/Limitation
---
- Relying on on cloud storage provider is not the most cost effective
	- Data replication strategy affects application performance
	- number of replicas, latency, cost, correctness
- Its hard to implement the strategy inside each application
	- Beyond typical app developers' need
	- different applications may need different strategies
- Might be a good idea to have common abstraction that can be accessed by all applications in a common way, you don't want to change application data access strategy every time
- Avoid Data vendor lock in
## Objectives
---
SPANStore approach is  to provide a wrapper around all cloud services and give one interface
- Minimize cost
	- which cloud storage is cheaper for my needs
- Ensure High performance 
	- Where should i put my data for low latency
- Offer consistency and fault tolerance
	- Can I always read up to date data
- Reduce overhead (for SPANStore itself)

But these objectives conflict with each other:
- Consistency & Cheapest != Fastest
- Fastest != Cheapest

## Challenges
---
Number of replicas vs how much we access the data
Complicated Pricing depends on 
- Amount of stored data
- number of PUTs & GETs
- Amount of egressed data

The opportunity from multi cloud is lower latency due to more nearby data centers and lower costs due to more cheaper data centers 

## Architecture
---
![[{AA2E6A04-CA59-4E52-9772-0391AFC7872A}.png]]
- PUTs/GETs received by local SPANStore
- PUTs/GETs may be relayed to other centers, this makes transferring data faster if 2 data centers have a faster connection between each other 
- Run SPANStore inside each of the datacenters, these datacenters can be from different cloud providers 
- SPANStore does have some overhead costs but these cost can be justified if we have a lot of data to justify it 

## Placement Manager
---
![[{4353123A-8437-4F0D-AB3A-0CB4311BC3A2}.png]]
Handles the placement of where we should be putting/getting our data from
- Takes into consideration latency between centers, pricing policy
- Application fault tolerance, consistency, latency requirements 
- Application workloads like access set & get/put rates
	- Access set is like a user preference for where the application wants to store data

**Case 1: Eventually Consistency**
- Can let consistency between data centers take a longer time and allow app to read stale/older data for a lower latency 
![[{35D8CC34-9A68-4D5D-851E-2D4A12A1E7A7}.png]]

**Case 2: Strong Consistency**
- App writes PUT request in its access set and want to make sure every other app sees PUT request, so we maintain an order of changes
![[{584D6AE7-2069-4ECC-B1BB-5BB67FC64478}.png]]

## Summary
---
- No single best cloud storage service
- Can improve cost efficiency and performance by combined multiple serivces
- SPANStore abstraction to do this
- Demonstrates we can empirically lower costs while meeting same SLO