---
tags:
  - CS374
  - CS374/Midterm1
aliases:
  - PDA
---
---
We can modify [[Non-Deterministic Finite Automata|NFA]]s to accept [[Context Free Languages|CFG]]s by using a stack as a way of holding or keeping memory:
![[Pasted image 20230912185013.png]]
The draw transition from $q_2$ to $q_4$ allows this automata to accept when $n>0$ for binary strings with $n$ zeros followed by the same number of ones. 

The first part of the transition is what we read from the input, the second part of the transition dictates what we do to the stack.
**Formal Definition:**
![[Pasted image 20230912185159.png]]![[Pasted image 20230912185228.png]]

We can [[Convert CFG to PDA]] but it is a bit tedious.

There do exist deterministic PDA/CFGs but they are not as powerful as non-deterministic ones so we will not use deterministic ones this class.
![[Pasted image 20230912185404.png]]

PDAs represent CFGs so they follow the same [[Closure properties of CFLs]]
