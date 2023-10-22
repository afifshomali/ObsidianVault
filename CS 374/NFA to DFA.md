---
tags:
  - CS374
  - CS374/Midterm1
aliases:
  - Subset Construction
---
---
To better understand how to convert from a NFA to a DFA, we should first take a different perspective on [[Non-Deterministic Finite Automata|NFA]]s. 
![[Pasted image 20230908195155.png]]
We can look at each NFA state being either On or Off, a state is on if it is reachable by what we have already seen of the string.
A state can be turned off like we see with the second zero, this is because we have to move the light from $q_1$ to $q_2$. But in $q_2$ we can't move anywhere with the zero so the state is turn off or burned out. But in this example we don't see $q_2$ turn off because the light from $q_1$ moved to it.

We can treat NFAs as knowing many states on one input.
![[Pasted image 20230908195612.png]]

So to simulate an NFA using a [[Deterministic-finite-automata(DFA)|DFA]], we treat each set of states of an NFA as one state in the DFA:
![[Pasted image 20230908200150.png]]
![[Pasted image 20230908200219.png]]
This isn't all possible combinations of green states from the NFA because some of them are unreachable from the start state (Example: only $q_1$ and $q_2$ lit up green).
Then the accept states of the DFA are the ones where the corresponding set of states for the NFA have an accepting state lit up.

Formal Notation Example:
![[Pasted image 20230908200712.png]]

