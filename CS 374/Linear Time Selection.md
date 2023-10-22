---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
---
---
### Implementation:
![[Pasted image 20231003163344.png]]
### Explanation:
![[Pasted image 20231003162401.png]]
![[Pasted image 20231003162719.png]]
Sort each column since that is $O(1)$ time for each item and there are $\frac{n}{5}$ items.
![[Pasted image 20231003162735.png]]
![[Pasted image 20231003162805.png]]
We put everything smaller than pivot to the left of it, then since we have 12 elements in the left subarray, the 10th element must be in there.
Since we are looking in $A_{lower}$ we keep the same $k$ 
![[Pasted image 20231003162938.png]]
We call [[Median of Medians|MOM]] again to get the pivot for this subarray
![[Pasted image 20231003163033.png]]
We get 6 as our pivot, but now our 10th element is in $A_{upper}$ so we have to look the 4th element in the right subarray by subtracting 6 from the original index that we are looking for.
![[Pasted image 20231003163150.png]]
Got 12 as pivot from MoM, then we have an array of length 5 to search in which is our base case so:
![[Pasted image 20231003163229.png]]
We sort the array and return the value at the index k.
### Runtime Analysis:
![[Pasted image 20231003163411.png]]
sublists and medians take $c$ and $c \cdot \frac{n}{5}$  respectively
Base case is constant time
Then we have the maximum of $c$ or $\frac{n}{5}$ depending on which case.
Then for the partitioning step we have the max of $\frac{3}{10} \cdot n$ and $\frac{7}{10} \cdot n$ .
So we end up with the recurrence above for the worst case scenario, the first term is for finding the median of medians the second term is for the partitioning step and the third term is for the linear amount of work we have to do to get the medians list.
![[Pasted image 20231003164153.png]]
![[Pasted image 20231003164146.png]]
If we have $k = 3$ then we see that we end up with a worse running time since the amount of work doesn't decrease per level.
