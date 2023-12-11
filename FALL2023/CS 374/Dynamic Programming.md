---
tags:
  - CS374
  - CS374/Midterm2
---
---
![[Pasted image 20231005163317.png]]
![[Pasted image 20231010165451.png]]
The running time will be $O(n^3)$ 

### Fibonacci:
![[Pasted image 20231005163345.png]]
![[Pasted image 20231005163353.png]]
![[Pasted image 20231005163404.png]]
We have an imbalanced recursion tree with a lot of the sub problems being repeated.
![[Pasted image 20231005163512.png]]
We see that the iterative algorithm is much faster, but we can apply this concept to the recursive algorithm as well 
![[Pasted image 20231005163556.png]]
![[Pasted image 20231005163715.png]]
All the greyed out calculations are the ones we are saved from doing since we can use memorization.
### Memorization:
![[Memorization]]

### Dynamic Programming:
![[Pasted image 20231005163938.png]]
![[Pasted image 20231005163946.png]]
![[Pasted image 20231005164000.png]]

### LIS revisited:
![[Longest Increasing Sub-sequence#Explanation(Dynamic)|LIS]]
![[Longest Increasing Sub-sequence#Implementation(Dynamic)]]
![[Longest Increasing Sub-sequence#Runtime Analysis(Dynamic|LIS]]

### Dynamic Programming Summary:
![[Pasted image 20231005164450.png]]
![[Pasted image 20231010165520.png]]

### Edit Distance & Sequence Alignment:
![[Edit Distance & Sequence Alignment]]


### Longest Common Subsequence:
![[Longest Common Subsequence]]

### Is this in $L^k$?:
![[Is this in Lk]]