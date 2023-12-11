---
tags: CS374, CS374/Midterm1
aliases: DFA, FSM
---
---
These are the simplest type of machines and are equivalent to [[Regular Expressions]].

The are also called finite state machines, hence the finite in the name
Deterministic refers to the fact that we exactly what state its going to be in given an input as the same input will always return the same output.
These programs have fixed memory and cannot "go back" on the input string.

![[Pasted image 20230829152414.png]]

The machine in the slide above is one that will accepts strings from $\sum^*=$ {0, 1}$^*$with an odd number of zeros.
$q_0$ is the starting state 
$q_1$ is an accepting state

A DFA accepts a [[Strings|string]] $w$ if and only if the unique [[Walk]] starting at the start state and spelling out $w$ ends in an accepting state.
Every [[Walk]] is unique for each input.
![[Pasted image 20230829152935.png]]

### Here is the formal way to define a DFA:
![[Pasted image 20230829153136.png]]
It's important to remember that $Q, \sum, A$ are all [[Set|Sets]]. 

### Here is how we formally define the example for finding odd zeros using a DFA:
![[Pasted image 20230829153615.png]]
### Extending Transition function to include strings:
![[Pasted image 20230829153447.png]]
![[Pasted image 20230829153453.png]]


### Complement Language:
![[Pasted image 20230829153900.png]]
We can just flip the accepting & regular states of a DFA to get the complement:
![[Pasted image 20230829153930.png]]
The theorem is that languages accepted by DFAs are closed under complement![[Pasted image 20230829154029.png]]
### 
DFAs can also be combined together through [[Product Construction]].
DFAs are also useful in [[Constructing Regular Expressions]] more easily.

Every DFA is an [[Non-Deterministic Finite Automata|NFA]] as well, and NFAs allow for us to solve some problems that end up being very complex using DFAs. DFAs are equivalent to [[Regular Expressions]].