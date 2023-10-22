---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
---
---
### Overview:

### Implementation:
![[Pasted image 20230930111001.png]]


### Runtime Analysis:
![[Pasted image 20230930111013.png]]
When we pick the median, we have a running time equal to MergeSort.
But in the worst case we have $O(n^2)$.
To find median we can sort using & pick the the median element, but that requires us to sort the list.

We can improve this by using median of medians algorithm
### Median of Medians
![[Median of Medians]] 


### How does this work with QuickSort?
![[Pasted image 20230930113056.png]]
Then with the MOM we end up with a runtime of $O(n log n)$ which is the same as MergeSort

