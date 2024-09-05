---
tags:
  - CS447
---
---
## Language Modeling with N-Grams
---
- A language model over a vocabulary $V$ assigns probabilities to strings drawn from $V^*$
![[Pasted image 20240904181657.png]]
![[Pasted image 20240904181714.png]]
- Unigram probability of product of each of the words
- Bigram takes conditional probability on word immediately before it
- Trigram model takes conditional probability on the 2 words immediately before a word 
![[Pasted image 20240904182116.png]]
These models become very complex very fast because they need to have a lot of parameters

## N-gram to Language Models 
---
![[Pasted image 20240904182405.png]]
- A Language model needs to be defined over strings of any length
- We add an EOS token to V
- We assume that every string ends with EOS and that EOS can only appear at the end of a string
![[Pasted image 20240904182525.png]]
Think of a language as a stochastic process:
- At each time step, randomly pick one word
- Stop generating more words when you pick the EOS token
To be able to pick the EOS token, we need to modify training data so that each sentence ends in with the EOS token
![[Pasted image 20240904182653.png]]
![[Pasted image 20240904182704.png]]
Having one distribution for all lengths lets us compare probabilities for strings of different lengths which would not be possible if we were using different distributions
This allows us to generate string of arbitrary length with just one model

## Parameter Estimation
---
To get the actual probabilities we need a large amount of text as training data to get an estimate of the probabilities
![[Pasted image 20240904183008.png]]
- [[Maximum likelihood estimation]]
We also need to handle unknown words:
![[Pasted image 20240904183144.png]]
![[Pasted image 20240904183321.png]]
![[Pasted image 20240904183414.png]]
