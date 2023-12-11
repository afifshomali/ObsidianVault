---
tags:
  - CS374
  - CS374/Midterm1
---
---
Right above context-free languages we have context sensitive-languages:
![[Pasted image 20230918184152.png]]
![[Pasted image 20230918184213.png]]

![[Pasted image 20230918184233.png]]

Turing machines are the "most general" computer, they recognize Recursively-Enumerable or Decidable Languages. All the languages we have reviewed previously([[Regular Languages]], [[Context Free Languages]], Context sensitive) all are Decidable & thus can be recognized by Turing machine.

![[Pasted image 20230918184521.png]]
![[Pasted image 20230918184532.png]]

There are many examples of Turing machines, one example is binary increment, equal strings, palindromes.
We can formally define a Turing machine like so:
![[Pasted image 20230918184633.png]]
![[Pasted image 20230918184640.png]]
![[Pasted image 20230918184713.png]]

Some Turing machines won't need an infinite tape, like the one to recognize 
$L=${$a^nb^nc^n| n \geq 0$}:
![[Pasted image 20230918184925.png]]
![[Pasted image 20230918184937.png]]
