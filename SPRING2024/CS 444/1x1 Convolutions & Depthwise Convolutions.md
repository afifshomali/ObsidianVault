---
tags:
  - CS444
---
---
## 1x1 Convolutions
![[Pasted image 20240215114147.png]]
Useful for linear transformations across channels
![[Pasted image 20240215114205.png]]
![[Pasted image 20240215114211.png]]
1x1 Makes spatial convolutions more efficient too. Dimensions of feature volume are the same & get a 9 factor reductions. However we would be concerned in losing information with this method which could lead to worse performance, But in practice this seems not to be the case.

## Depthwise Convolutions:
![[Pasted image 20240215114250.png]]
![[Pasted image 20240215114256.png]]

## Groupwise Convolutions:
![[Pasted image 20240215114317.png]]![[Pasted image 20240215114327.png]]
![[Pasted image 20240215114336.png]]
![[Pasted image 20240215114351.png]]
![[Pasted image 20240215114358.png]]

