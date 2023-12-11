---
tags:
  - CS374
  - CS374/Midterm1
aliases:
  - CFA
  - CFG
  - CFL
---
---
![[Pasted image 20230912183230.png]]
This example generate Every length binary palindrome or $L =$ {$ww^R | w \epsilon \sum^*$} which is not a regular language.

V is the variables/ non-terminals, the final [[Strings|string]] we generate cannot contain a non-terminal

T is the terminals or the alphabet for the CFA

P is the production rules which dictate how to generate string inside this Language

We can formally define CFAs as Context Free Grammars (CFGs):
![[Pasted image 20230912183859.png]]
![[Pasted image 20230912183919.png]]
Some notation conventions:
![[Pasted image 20230912183945.png]]

## Derives Formalism:

![[Pasted image 20230912184112.png]]
![[Pasted image 20230912184122.png]]

## Final Formal Definition:
![[Pasted image 20230912184136.png]]

##
CFL can also represent [[Regular Languages]]: [[Convert Regular Language into CFL]]

CFLs are also represented by [[Push Down Automata]]
