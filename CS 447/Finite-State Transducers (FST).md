---
tags:
  - CS447
---
---
## [[Designing an FST]]
## Finite State Transducers
---
- FSA can accept a string but can't tell us about its internal structure
- Need a machine that maps (transduces) the input string into an output string that encodes its structure
![[Pasted image 20240904170255.png]]
![[Pasted image 20240904170333.png]]
- We can't enumerate all possible English words, but we can define rules for strings to determine whether or not they could be an English word
- Want a procedure that can generate or accept possible English words
- But we want to ensure that we don't generate or accept impossible English words
![[Pasted image 20240904170602.png]]
*Orange text is what is changed when compared to Finite State Automata*
![[Pasted image 20240904170646.png]]
![[Pasted image 20240904170755.png]]
![[Pasted image 20240904170849.png]]
![[Pasted image 20240904171002.png]]
![[Pasted image 20240904171014.png]]
![[Pasted image 20240904171045.png]]
![[Pasted image 20240904171408.png]]
- Generating words is generally unambiguous, but analyzing them requires disambiguation usually 
- We need a non deterministic FST but not every Non deterministic FST can be translated to a deterministic one 
- We also need a scoring function to identify which analysis is more likely, this may require us to know the context in which the word is being used in
![[Pasted image 20240904171649.png]]
- For compounds, they have a hierarchical structure
![[Pasted image 20240904171729.png]]
We will need [[Context Free Languages]] or Grammars to represent & capture the underlying compound structure