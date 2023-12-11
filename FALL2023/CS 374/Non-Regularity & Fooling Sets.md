---
tags:
  - CS374
  - CS374/Midterm1
---
---
## Overview:
![[Pasted image 20230908212143.png]]
Not all languages are regular!
![[Pasted image 20230908210801.png]]
Here is the most basic example:
![[Pasted image 20230908210824.png]]
But we also need formal proofs for this, where we have 3 main methods:
![[Pasted image 20230908210919.png]]
Here is the proof by contradiction:
![[Pasted image 20230908210954.png]]
## When are two states equivalent?
![[Pasted image 20230908211200.png]]
![[Pasted image 20230908211207.png]]
![[Pasted image 20230908211218.png]]
![[Pasted image 20230908211330.png]]
## Proof using Fooling Sets
Now that we have the background for when states are equivalent, we can use [[Fooling Sets]] to prove non-regularity.
![[Pasted image 20230908211737.png]]
So if we end up having an infinite fooling set for a language, then that language cannot be regular by this theorem.
![[Pasted image 20230908212207.png]]
## Proof using Closure Properties
We can also construct a proof using closure properties if we have a language that we already know is not regular. 
![[Pasted image 20230908212346.png]]
We use another proof by contradiction here.
![[Pasted image 20230908212417.png]]
But its also important to be careful![[Pasted image 20230908212443.png]]
