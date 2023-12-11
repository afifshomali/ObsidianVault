---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
aliases:
  - Karatsuba
---
---
### Overview:


### Implementation:
First start with idea of Friedrich Gauss:
![[Pasted image 20230930113722.png]]
This works since $(a + b)(c + d) = ac + (ad + bc) + bd$ 
![[Pasted image 20230930113932.png]]
So we only need 3 multiplications if we use more additions & subtractions which take Constant time.
### Runtime Analysis:

![[Pasted image 20230930113952.png]]
Since we only need to do 3 Multiplications, we get an algorithm faster than $O(n^2)$. 