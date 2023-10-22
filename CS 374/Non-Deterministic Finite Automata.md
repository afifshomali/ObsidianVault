---
tags:
  - CS374
  - CS374/Midterm1
aliases:
  - NFA
---
---
Here is an example of an NFA, there are a few key difference between [[Deterministic-finite-automata(DFA)|DFA]]s and NFAs.
![[Pasted image 20230831171616.png]]

An NFA will accept a [[Strings|string]] $w$ if and only if some accepting state is reach from the start state on input $w$. If just one path using a string leads to an accepting state, then the string is accepted by the NFA.

Due to this it is easier to show that a string is accepted by an NFA, but more difficult to show that a string is not accepted, because to show a string is rejected we need to show that all possible paths for a string lead to a rejecting state.

This is unlike DFAs where each input only has one possible output.

![[Pasted image 20230831172155.png]]

$P(Q)$ is the power set of Q, a [[Power Set]] is the set of all subsets of Q.

This means that the transition function doesn't just lead to one state, but it leads to a set of states.
## Example:
![[Pasted image 20230831172258.png]]

## Extending Transition Function to Strings:
![[Pasted image 20230831172616.png]]
![[Pasted image 20230831172705.png]]

## Formal Definition:
![[Pasted image 20230831172739.png]]

## Constructing Generalized NFAs:
Every [[Deterministic-finite-automata(DFA)|DFA]] is an [[Non-Deterministic Finite Automata|NFA]], so NFAs are at least as powerful as DFAs.
NFAs prove ability to "guess & verify" which simplifies design and reduces the number of states when compared to DFAs
Easy Proofs of some closure properties

### Theorem:
![[Pasted image 20230831173223.png]]

![[Pasted image 20230831173238.png]]

### Closure Properties:
**Union:**
![[Pasted image 20230831173310.png]]

**Concatenation:**
![[Pasted image 20230831173327.png]]

**Kleene Star:**
![[Pasted image 20230831173346.png]]
###
Also Note that every NFA has a corresponding [[Deterministic-finite-automata(DFA)|DFA]] but they aren't always nice to draw & often the corresponding DFAs have many more states needed. 

NFA are also equivalent to [[Regular Expressions]] 