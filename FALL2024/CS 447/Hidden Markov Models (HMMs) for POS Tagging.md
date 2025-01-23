---
tags:
  - CS447
---
---
[[Hidden Markov Models]]
![[{77A2A590-1BD2-46BC-BDD1-1DD65E0C2948}.png]]
Want to find the POS tagging with the maximum probability
![[{86FDA647-5FCD-49E8-85FF-D6D31DAEBDE9}.png]]
HMMs are the most common used generative model for POS tagging and in other tasks (speech recognition)
HMMs make specific independence assumptions in $P(t)$ and $P(w | t)$:
![[{346C15A3-79FD-470B-9C6E-07757EA1478D}.png]]
These probabilities don't depend on the position in the sentence but are defined over word and tag types
![[{CCAF8B18-3441-44FC-827F-8E214714F5BA}.png]]

## HMMs as Probabilistic Automata
---
![[{64AAFB05-306F-48E9-A295-02E2D9A24AA4}.png]]
![[{CA96E6C7-4732-4D4F-9DE0-74673D0FE875}.png]]
![[{4D319FEE-2D2F-4B53-970C-9C89D971761B}.png]]
[[Finite-State Automata (FSA)]]
![[{299AAEAC-A83B-4FC6-8467-BE6E73718E83}.png]]
![[{7C8B4F7D-E9B5-4744-938B-7F288C7A4642}.png]]

## Building HMM Taggers
---
![[{57765947-6E19-4921-A4A1-3660723F412A}.png]]
![[{86C3E06F-8A1D-4792-B2FF-117B52A7845C}.png]]
![[{8E24E934-72D3-4B26-B8AA-FB4E254877A3}.png]]
Forward-Backward Algorithm, not Inside Outside Algorithm
![[{3353CBEF-ECE1-41CD-8304-D60052D7A82F}.png]]


