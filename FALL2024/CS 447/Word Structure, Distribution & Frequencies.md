---
tags:
  - CS447
---
---
## Word Frequencies
---
When counting words in text we must distinguish between word types & word tokens
![[Pasted image 20240904124753.png]]
- Vocabulary of English language, which is how large the the number of distinct word types is around 1 trillion tokens from Google's N-gram corpus
- However this includes took & taking as unique words
- A few words are very frequent, like "the, be, of, to, and, a in", most commonly these are closed class
- Most words, which are in open class are very rare
- Even you look at a lot of text you will keep finding words you don't know

## Zipf's law
---
![[Pasted image 20240904125115.png]]
- The $r-th$ most common word $w_r$ has $P(w_r) \alpha \dfrac 1 r$
- In natural language a small number of words appear really frequently
- A large number of words appear with very low frequency

***Implications:***
**The good:**
- Any text will contain words that are very common, and we see these words often enough to know everything about them
**The bad:**
- Any text will contain the words that are rare. Where we know something about them, but we don't know everything about that word
**The ugly:**
- Any text will contain words that are unknown to us. We have never seen them before but still need to get the meaning from them
![[Pasted image 20240904125607.png]]
## How to represent words
---
![[Pasted image 20240904125819.png]]
![[Pasted image 20240904130005.png]]
![[Pasted image 20240904130138.png]]
## Word Structure
---
![[Pasted image 20240904131646.png]]
![[Pasted image 20240904131743.png]]
- Inflection create different forms from the same word:
	- Verbs: Be, being, I am, you are
	- Nouns: one book, two books
- Derivations creates different words from the same lemma:
	- grace -> disgrace -> disgraceful -> disgracefully 
- Compounding combines two words into a new word:
	- cream -> ice cream -> ice cream cone 
![[Pasted image 20240904131952.png]]
English is does not have as much of this as other languages:
![[Pasted image 20240904132046.png]]
![[Pasted image 20240904132143.png]]
![[Pasted image 20240904132206.png]]
![[Pasted image 20240904132300.png]]
![[Pasted image 20240904132346.png]]
![[Pasted image 20240904132412.png]]
![[Pasted image 20240904132518.png]]
