---
tags: CS374, CS374/Midterm1
---
---
A regular language is defined using Kleene's Theorem:
> A language is regular if and only if it can be obtained from **finite languages** by applying the three operations:
> 	- Union
> 	- Concatenation
> 	- Repetition
> A finite number of times 

So we start off with any number of finite languages & do these operations a finite number of times

The set of regular languages over some [[Alphabet]] $\sum$ is defined inductively:

**Base Cases:**
- $\emptyset$ is a regular language
- {$\epsilon$} is a regular language
- {$a$} is a regular language for each $a \in \sum$. Interpreting $a$ as a string of length 1.

**Inductive Step:**
![[Pasted image 20230829145728.png]]

Regular languages are [[Closed]] under operations of union, concatenation & Kleene Star.
Here are some Lemmas for Regular Languages:
![[Lemmas#Lemma 1]]
![[Lemmas#Lemma 2]]
![[Lemmas#Lemma 3]]

There is a shorthand method for denoting regular languages, they are called [[Regular Expressions]]. Regular Languages can also be represented with [[Deterministic-finite-automata(DFA)|DFA]]s.
