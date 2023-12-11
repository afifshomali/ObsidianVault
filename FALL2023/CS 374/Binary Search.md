---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
---
---
### Overview:

### Implementation:
![[Pasted image 20230929232725.png]]

### Runtime Analysis:
Since we reduce the problem to have the size in each iteration/recursion, and we do a constant amount of work per level. We have $O(log(n))$ runtime.
![[Pasted image 20230929232901.png]]
We will not call Binary Search twice because of the if-else statement, that is why we have 1 Infront of $T[{\dfrac{n}{2}}]$ not a 2 or some other number. The rest of the parts of the Algorithm take $O(1)$ time, that is why we add that term for each step of the recurrence. 