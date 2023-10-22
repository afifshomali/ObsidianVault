---
tags:
  - CS374
  - CS374/Midterm1
---
---
![[Pasted image 20230912183048.png]]

Let's look at [[Context Free Languages]] 

We can convert [[Regular Languages]] into [[Context Free Languages|CFA]]s since regular languages are a form of CFAs as we have seen in the Chomsky Hierarchy: [[Convert Regular Language into CFL]]

Context Free Languages are representable by [[Push Down Automata]] or PDAs. We can also convert [[Context Free Languages|CFG]]s to PDAs by [[Convert CFG to PDA]].

CFLs also have some important closure properties: [[Closure properties of CFLs]]

However CFLs have their limitations:
![[Pasted image 20230912185955.png]]
This language is not context free because the stack can only count one thing, we have no way of keeping track of both the count of the variables $a$ and $b$ in order to determine whether we have the same amount of $c$. 

