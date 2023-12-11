---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
---
---
### Overview:

### Implementation:
![[Pasted image 20230929231555.png]]

![[Pasted image 20230929231618.png]]

### Runtime Analysis:
![[Pasted image 20230929231725.png]]

There are $Log_2n$ levels in this tree to get the problem down to size 1 at the leaf level.

For each of these levels we have to do $O(n)$ work because that is the run time of Merge.
So then the the overall runtime is $O(nlog(n))$. 
![[Pasted image 20230929231957.png]]
If we show that we have the lower bound equal to the upper bound then we know what the exact running time is of an algorithm as $n$ gets big.

If we split the array into more elements, our Big-O running time stays the same. For example if we split into 3 arrays the running time will be $O(nlog_3n)$ but: $log_3n = log_32 * log_2n$ . So then we can just move that constant out since we don't care about additional constants that don't depend on $n$ for Big-O and the run time will remain the same.

