---
tags:
  - CS598
---
---
Intuition is Skip list search & greedy graph nearest neighbor search combined. Leverage the small world phenomena, meaning that we can leverage local connections to reach a far destination
## Background: Small World Network
---
![[{18323FAD-0F5D-4757-8F22-D2972FDCF345}.png]]
![[{944E9997-9FE1-4CA9-8512-9457DBBB4865}.png]]
![[{B2D7B631-0900-421B-B2CD-84C219CA7EE1}.png]]
![[{41426F8D-A00B-4EC3-9D1C-B28F793E142E}.png]]
![[{B7889714-254A-43C0-A76A-D42DAEFAFD30}.png]]
![[{A7FF80CD-4B5A-458C-A3D0-B062AA444119}.png]]
![[{18C9BD8D-91F6-426D-8A25-1A7C82D3B034} 1.png]]
![[{FA4551A0-02DD-4555-A384-7654551D3465}.png]]
![[{C0261FF9-4CF8-4963-860A-13B0DA74F7A5}.png]]


## HNSW Index
---
![[{A0A5E726-8B70-4968-8155-5CBE0FF55295}.png]]
We don't have any convergence guarantee, But we are able to find approximate nearest neighbors
![[{72CE0984-27EE-4E71-BD1D-4799DB31D1DE}.png]]
![[{10A62C1F-2C53-4A8E-9088-A95B1C42736A}.png]]
![[{D4B23638-B409-472E-8955-49A1B169C214}.png]]
![[{E947A004-B9F8-44B3-96D6-31676FDA65F7}.png]]
The candidate $e_2$ is closer to the query than it is to the other nearest neighbors of the query.

Want to add edges to avoid disconnected clusters, that way if our entry point is not connected to a separate cluster, we add a connection to that cluster from the cluster containing the entry point. 
![[{C5BA4428-6972-478F-BDE7-8CDEA607E510}.png]]
![[{E343C5D7-B177-499F-ADAE-C98C46113F91}.png]]
Inserting a vector is still approximate because we aren't doing an exhaustive search rather a greedy search. 

## Evaluating Parameters
---
![[{2634B348-01D7-409E-9A0E-BD4EEF9EB592}.png]]
![[{8A2A7FFD-E36F-4679-B78A-CD1A49385F40}.png]]
![[{A49BB70E-8FF4-46BA-BDD8-15AF7967112E}.png]]
![[{F276CD88-4835-4B8A-9BCF-D4A458CA4F77}.png]]


## Evaluating Search Strategy & Conclusions
---
![[{97C2C610-771C-40D6-BA20-1916E0856DF3}.png]]
![[{D6862D5A-35B7-4DCB-BDD6-49BAF19AE3F4}.png]]
![[{497DEBB5-FF15-43B3-9DA5-127B696FED2E}.png]]
