---
tags:
  - CS598
---
---
Cover Google MapReduce (MR) and also [[Apache Hadoop]]/ Hadoop Distributed File System which is the open source implementation of Google Map Reduce

![[{40A37529-995F-47C4-BEF4-3234D3F24D44}.png]]

**Computational Challenges that Map Reduce Solves:**
- Relational Databases ([[Relational Databases on the Cloud]]) is hard to scale, it is slow to insert & analyze large volume of data
- Shared Memory & other High Performance Computing is not as robust
- Writing Custom programs is tedious/time consuming 

**High Level Idea:**
- Abstract away the messy details of parallelization, fault tolerance, data distribution, load balancing
- Only need to divide our task into a *Map* and *Reduce* function
- Functional Programming: parallelization & re-execution 

## MapReduce from a User's perspective:
![[{0224D78D-6EC4-409A-8725-5FF1BCB54092}.png]]
Most things we do are either one to one conversion (Map) or aggregations (Reduce), this is why we can apply the algorithm to multiple problems
Reduce needs to be communitive like addition, so order of operands don't matter 
**Examples:**
![[{EA01DD93-9E66-429C-A4B1-967CEC0FCF68}.png]]
![[{BBA671EF-FF88-4FFE-B6BD-90EFACC17208}.png]]
This uses flat map, not just a map, also uses a more advance group by aggregation
![[{511EBC52-DA74-438B-B0D7-4A9D50E1A10D}.png]]

## MapReduce Framework Internal Workings:
---
- First write Map & Reduce Functions & submit them to a master along side with the database/dataset
- Master Distributes the tasks to the works (This step can cause delays in practice)
- Phase 1 is Map, each worker reads data from DFS
- Phase 2 is Reduce, data is shuffled based on keys 
	- Example: Character count, each key (character) is assigned to just one worker and that leads to the shuffling as we give all the data associated with that key to the same worker in order for the aggregation
- Results from Phase 2 are written to disk
![[{EE25EB29-A098-42B7-857F-A7E2B437855F}.png]]
Each worker process a partition of the data and then store the intermediate mappings on local disks for the Reduce workers to be able to access them later

**Fault Tolerance:**
- This system is robust against worker failure
- Map failure: re execute map, this can affect the reduce step 
- Master Failure: start a new master (but this is improved later), reasoning for being ok with a singe point of failure is that the probability of one node going down is less likely than the probability of at least one node going down from many 
- Straggler Handling with backup tasks

## Optimization of Map Step with Combiner:
---
Data Locality: MR maximizes reads from the same machines

- Combiner function works within the Map step, essentially does a pre aggregation in the Map step
	- Examples: Counting the number of word counts across documents, for each document we sum the number of times a word occurs and emit that rather than emitting the word with a occurrence of 1 multiple times: ("foo", 1) ("foo", 1) -> ("foo", 2) 
- Combiner can reduce network transfer 
![[{29277301-BC05-47EE-A2A4-D4A9E2E6B390}.png]]
## Limitations:
---
- Master is a single point of failure
- Not best for complex computations (example: Training Neural Network)
- Read/Write to disk may be slow
- Not applicable to OLTP
## Summary
---
![[{DA7577CB-3D52-4A31-81EA-617F580ACDDE}.png]]

