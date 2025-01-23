---
tags:
  - CS447
---
---
## Generating Text with Language Models
---
- Independently we can make a random sentence generator, but in practice this is not useful
- Can also use the model as a sentence ranker:
	- Used in machine translation, speech recognition, spell checking, generation

To generate or sample from a distribution:
![[Pasted image 20240904183938.png]]
![[Pasted image 20240904184013.png]]
![[Pasted image 20240904184116.png]]
- The model can't really generate anything new
If we used the UNK token:
	1. If we set the frequency threshold too high for which words to replace, a very large fraction of tokens become UNK
	2. Even with a low threshold, UNK will have a very high probability, due to a small corpus having many words that only appear once
	3. But we would still only observe a small fraction of possible bi grams 

- MLE doesn't capture unseen events, so on a model with 885k word tokens we only have 30,000 word types occur in the training data so only 0.04% of all possible bigrams occur in the training data
- Any bigram not occurring in the training data will have a zero probability

To assign non zero probability to unseen events is called smoothing, so we have to reserve some probability mass for the unseen events
![[Pasted image 20240904184623.png]]
We need to define what the unseen events are and how much probability we should assign to them
![[Pasted image 20240904184637.png]]
![[Pasted image 20240904185001.png]]
