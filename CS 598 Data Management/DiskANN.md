---
tags:
  - CS598
---
---
DiskANN is essentially a local disk implementation of HNSW, they look to answer the same question which is when given a graph of vectors & a query vector, we want to find the k nearest or k approximate nearest neighbors.
![[{8F7EA46C-7D87-4231-B1B0-5D6BFBEC00EF}.png]]
## Potential Strategies
---
![[{16F5C9DC-367C-456B-B372-61CF2B53B1DA}.png]]![[{8D298B34-F786-450E-B755-EC4B58D4E9C8}.png]]
![[{5A730980-74C6-4A04-BE3E-2D7C11DC5595}.png]]
![[{738C267B-816D-4CBE-9970-199CE204D07A}.png]]
![[{DBBE50CF-8AAC-4D59-8471-5984DA40C00F}.png]]
Index each cluster separately then union them.
![[{3E457DF2-95B0-4470-9AA4-3188A5D1173C}.png]]
Then for each partition use Vamana Index in order to get shorter number of hops which is useful for disk based indices 

## Vamana
---
![[{2C1DAC3C-77C3-4023-954A-B4512DD4BB0D}.png]]
![[{7A2ABDA6-CB14-4E47-A985-18FB71A7435E}.png]]
![[{79C744FA-FD25-4653-8374-05FB53562EDE}.png]]
![[{A9314230-9F8A-4371-BFA9-E09D7BA3E04F}.png]]

## Performance
---
Benchmark data was small for the paper's testing
![[{BF9E97FC-FA26-4BBF-B467-6C04B7FEC5F5}.png]]
![[{998B1D2F-0D02-4421-9317-18820F32A080}.png]]
![[{0A52568E-D2D4-4F9F-B138-96F100E187BC}.png]]
