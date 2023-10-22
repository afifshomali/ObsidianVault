---
tags: CS374, CS374/Midterm1
---
---
We want to figure out if [[Languages]] accepted by [[Deterministic-finite-automata(DFA)|DFA]]s are [[Closed|closed]] under union  and intersection.

This is if we want to take two DFAs and combine them into one in order to solve a more complex problem.

![[Pasted image 20230829154435.png]]
The thing is we can only read the input once so we need a way to combine the two machines into one by running them in parallel & keeping track of state in both machines.
Here is how this is done:
![[Pasted image 20230829154623.png]]
Now using the Formal definition for DFAs:
![[image1[2616].jpeg]]
![[image0[2615].jpeg]]
