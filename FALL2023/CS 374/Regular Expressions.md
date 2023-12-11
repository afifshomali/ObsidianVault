---
tags: CS374, CS374/Midterm1
---
---
Regular expression are a way to denote [[Regular Languages]] in a more simple way.

- We use simple patterns to describe related strings
- This is useful in many applications:
	- text search(editors, Unix/grep, emacs)
	- compilers
	- compact way to represent interesting/useful [[Languages]]
	- dates back to 50s, invented by Stephan Kleene

## Definiton:
**Base Cases:**
A regular expression $r$ over an alphabet $\sum$ is one of the following:
- $\emptyset$ denotes the language $\emptyset$ 
- $\epsilon$ denotes the language {$\epsilon$}
- $a$ denotes the language {$a$} 

**Inductive Steps:** If $r_1$ and $r_2$ are regular expressions denoting languages $R_1$ and $R_2$ respectively then,
- $(r_1 + r_2)$ denotes the language $R_1 \cup R_2$
- $(r_1 \cdot r_2) = r_1 \cdot r_2 = r_1 r_2$ denotes the language $R_1R_2$ 
- $(r_1)^*$ denotes the language $R_1 ^*$ 

![[Pasted image 20230829151314.png]]
![[Pasted image 20230829151408.png]]

Regular Languages express the simplest type of problems & can be represented using regular expression. Regular expression are equivalent to [[Deterministic-finite-automata(DFA)]]s.  