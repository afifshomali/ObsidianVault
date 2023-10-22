---
tags:
  - CS374
  - CS374/Midterm2
---
---
Adding two Binary Numbers belongs to at least the context sensitive class:
![[Pasted image 20230929225826.png]]

## General Notation/Definitions:
![[Pasted image 20230929225851.png]]
Ex: Algorithm is how to make coffee and the computer would be the person making the coffee 
![[Pasted image 20230929225857.png]]
Turing Machines, DFAs, NFAs are all models of computation.
![[Pasted image 20230929225916.png]]
Adding two numbers can be done in constant time
![[Pasted image 20230929225925.png]]

## Algorithmic Problems:
![[Pasted image 20230929225954.png]]
map set of strings to a set of strings, f is a function that does that. 
for example: $w = 111 + 1111 \rightarrow 1111111$ the arrow is what f does,
![[Pasted image 20230929230000.png]]
Examples:
- Decision: Is there a Path to a building
- Search: Find a path to the building if there is one
- Optimization: Find the shortest path to the building
![[Pasted image 20230929230008.png]]
Asymptotic means Big-O when size of problem $n \rightarrow \infty$.
An algorithm is $O(n^2)$ if $Time(A) \leq cn^2$. Big-O is an upper bound.
Algorithmic Techniques:
![[Pasted image 20230929230027.png]]

## Reductions:
![[Pasted image 20230929230105.png]]
If we can reduce A to B and we have an algorithm for B. Then we can use that algorithm to solve A. For example, if we could reduce finding the best lottery number to a graph shortest path. Then we can use the graph shortest path algorithm to solve the best lottery number.

Another example is that we can reduce checking for distinct elements to sorting an array as when we sort an array we can check if adjacent entries are the same, and if they are there are duplicate values in the array.
![[Pasted image 20230929231157.png]]

## Recursion:
Recursion is just a special case of Reduction. We are just reducing the problem into a smaller version of itself rather than a version of a different problem. We can also call this self reduction.
![[Pasted image 20230929231324.png]]
![[Pasted image 20230929231334.png]]

### Solving Recurrences:
	![[Pasted image 20230929232153.png]]![[Pasted image 20230929232218.png]]![[Pasted image 20230929232233.png]]
	
### Tower of Hanoi example:
![[Pasted image 20230929231401.png]]
![[Pasted image 20230929231407.png]]



### Merge Sort:
	![[Merge Sort]] 
### Binary Search:
	![[Binary Search]]