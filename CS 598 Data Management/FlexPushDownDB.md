---
tags:
  - CS598
---
---
Extension of [[PushdownDB]], want a way to efficiently mitigate the network bottleneck when sending data. It does this by adding caching on top of the pushdown.
![[{F833DC58-CBAA-4254-81FF-3F4510CFF9A1}.png]]
Hybrid caching & pushdown at a fine granularity lets us 
![[{83B6D5CD-93B4-4D50-B169-3AC4ABDEE68B}.png]]
Caching + Pushdown lets get the best of both methods

## FPDB overview
---
**Design choices:**
- Cache table rather than query results for simplicity
- Segment as the caching granularity 
![[{42EC7694-51B1-447B-B95A-A64767B4F418}.png]]
![[{59CF042B-9B56-4EA6-AD4D-2CBE035D0EB5}.png]]
![[{9CFA5D08-73BE-493F-A2AA-3B4C48AA527E}.png]]
**Separable Operators:**
- Can execute separately using cached segments & cloud storage
- Example: projection, selection, aggregation, hash join (partially)
**Query execution:**
- Heuristic: exploit caching when possible, otherwise pushdown as much as possible  
![[{2DF92384-2CB6-4B2F-BA07-4EE060984BD7}.png]]
**Cache manager:**
- Traditional caching assumption: Equal-size cache misses incur the same cost
- In FPDB, misses that cannot exploit pushdown have a higher cost & should be considered for caching with a higher priority
- Weighted-LFU cache replacement policy
	- Increment the frequency counter with the estimate miss cost
	- Estimated miss cost = network cost + scan cost + compute cost
![[{F4DCB8E3-F0C3-410F-8DD0-70A8327F9E78}.png]]
![[{699B2ED6-2149-4EF0-BB19-BBAAA15555F0}.png]]
![[{C6BEEFB5-7BAF-4C3A-AE0A-F9F0E7A53022} 1.png]]
![[{7FF6862D-C7A9-4C94-801A-F1F1EA97A8E3}.png]]
![[{F0995DBC-9EF3-4062-AB3F-059DB698C269}.png]]
