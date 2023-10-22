---
tags:
  - CS374
  - CS374/Midterm2
  - Algorithims
---
---
### Overview:
### Explanation:
![[Pasted image 20231010170429.png]]
![[Pasted image 20231010170517.png]]
![[Pasted image 20231010170526.png]]
![[Pasted image 20231010170539.png]]
This is used in spellcheckers, Unix diff and many other applications
![[Pasted image 20231010170627.png]]
![[Pasted image 20231010170642.png]]
![[Pasted image 20231010170649.png]]

### Implementation:
![[Pasted image 20231010170659.png]]
![[Pasted image 20231010170705.png]]
![[Pasted image 20231010170719.png]]
The value in the bottom right of this matrix is the edit distance and we can get the alignment by tracing the path to get to the top left of the matrix as seen by the highlighted path. We can then pick the appropriate alignment of the 3 choices that we have based on the path we took.![[Pasted image 20231010170901.png]]
![[Pasted image 20231010171027.png]]

### Runtime Analysis:
![[Pasted image 20231010170904.png]]
We can reduce the amount of space used by only computing the current column & previous column since that is the only thing we need to determine a position in the matrix.
![[Pasted image 20231010170958.png]]
This will only use $O(m)$ space since we don't need to ever store more than 2m items
![[Pasted image 20231010171114.png]]
