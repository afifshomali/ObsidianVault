---
tags:
  - CS447
---
---
Tokenization is identifying word boundaries
Text is just a sequence of characters, so we need to find how to split text in words and sentences
![[Pasted image 20240904123952.png]]

Main Problems with defining words by blanks:

1. Compounding: ice cream, web site, New York-based
2. Other writing systems have no blanks
3. Contractions and Clitics: doesn't, I'm

## Tokenization Standards
---
Any actual NLP system will assume a particular tokenization standard, and since we train on particular corpora we use the standard provided by these corpora
![[Pasted image 20240904124253.png]]
![[Pasted image 20240904124432.png]]
![[Pasted image 20240904124555.png]]

