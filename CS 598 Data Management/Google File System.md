---
tags:
  - CS598
---
---
**Context:**
- Want file system for distributed computing (like [[Google MapReduce]])
- Scalability: High Bandwidth
- Reliability: Want it to almost always be working, even if some nodes go down we have some backup of the data to be able to access it 
- Google File system is the underlying system for Map Reduce

## Naive Approach:
---
![[{757690BB-AEFF-4F01-B7A7-3C616ED2A39A}.png]]
![[{806550D6-3D07-4DC7-A972-C7210381205C}.png]]
Storage cost too high, want to implement some sort of sharding in order to avoid replicating the full data every time. 
![[{EB68AF71-E6B6-40B8-ABDF-929F546B6A39}.png]]
## GFS Approach:
---
**Want Architecture to have:**
- No complete data duplication, only partial duplication at most
- Access data with filename & offset from start of file & size of data to read, which is a high level way of accessing the data, same way we would access files locally using code 

**Additionally:**
- Component Failures are norm, so we want to a way to recover data from any node failures
- Files are huge (like large text or videos), for example analyzing a large amount of historical data to make a business decision 
- Append rather than overwriting (no in place updates), don't want to use this if we have something like a transactional 

![[{F64EEE9A-507C-479C-889B-A174FE152391}.png]]
![[{EC08EA8D-B6EC-4268-9FB9-7A3417D64986}.png]]
- GFS master only has metadata on where files are stored, the Response is that metadata
- The bandwidth for each node is limited so we use multiple nodes to be able to work with a large amount of data, with each node taking a small chunk
- Don't need to request metadata from same chunk of data multiple times because the location of chunks stays the same, this prevents master from getting congested
![[{7D60A641-2946-413E-970D-9E81C40DEE86}.png]]
- Order of writing doesn't necessarily start with the primary replica, instead we write to the closest replica first, then the second closest, etc.
- After pushing to the closest node, send a message to the primary replica to then duplicate the data among the rest of the replicas, from the users perspective, the data mutation is done, primary replica will send a final control message when the mutation is done
- Primary replica informs the other replicas how to duplicate the mutations, it is always the decision maker to avoid conflicts
- Replication factor of 3 is quite common in practice to avoid cost getting too high
![[{B5068714-F7A5-46A1-853A-A17BFF4033DE}.png]]


