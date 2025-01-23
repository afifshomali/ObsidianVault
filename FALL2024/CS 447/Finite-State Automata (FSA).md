---
tags:
  - CS447
---
---
## Finite State Automata
---
[[Languages]]
![[Pasted image 20240904165001.png]]
![[Pasted image 20240904165024.png]]
- The Automata either accepts or rejects the input string
- Every automation defines a language, it is the set of string it accepts
![[Pasted image 20240904165132.png]]
- [[Deterministic-finite-automata(DFA)|DFA]]
- [[Push Down Automata]]
- [[Turing Machines]]
![[Pasted image 20240904165304.png]]
We reject string if they don't end up in the final state after the string is complete or if during the parsing of the string we can no longer take a transition/we have an undefined transition
![[Pasted image 20240904165631.png]]
- [[NFA to DFA]]
![[Pasted image 20240904165724.png]]
- [[Regular Expressions]]

## FSA for Morphology
---
![[Pasted image 20240904165821.png]]
- You don't need 4 different automata, you can merge these into one
![[Pasted image 20240904165853.png]]
- End up with 2 accepting states
![[Pasted image 20240904170058.png]]



## FST
---
![[Finite-State Transducers (FST)]]