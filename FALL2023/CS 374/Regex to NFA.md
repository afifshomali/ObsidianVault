---
tags:
  - CS374
  - CS374/Midterm1
aliases:
  - Thompsons
---
---
To convert from a Regex to an NFA, we can use Thompson's Algorithm:

![[Pasted image 20230908194340.png]]

For every operator in an RegEx, we can use the corresponding NFA & break down the RegEx into it's components, then connect using epsilon transistions.

![[Pasted image 20230908194513.png]]
![[Pasted image 20230908194526.png]]
![[Pasted image 20230908194535.png]]
![[Pasted image 20230908194543.png]]

Thompson's Algorithm means that all Regular Expressions are representable by NFAs!