---
tags:
  - CS447
---
---
- Word Sense disambiguation attempts to find the word sense based on the context surrounding that word 
![[{1162E292-7D58-4EB0-BD1E-7E800A793594} 1.png]]
- We can use dictionary based methods, if we don't have a labeled corpus 
![[{247FA71B-F660-4D83-A501-6968FE71544B}.png]]
- Can use these examples to identify the sense
- It is called the Lesk algorithm, which compares the context with the dictionary definition of the sense 
![[{7B7949AC-F0DB-4A1D-8362-455A8342AA92}.png]]
![[{EFCC14D8-27DE-42A6-8830-363EC53CE0A8}.png]]
- Depends on the quality of dictionary/thesaurus that you have, we don't have to do WSD on the context words, so we avoid nested WSD searches
- This is due to the context words having a very low likelihood of having the same ambiguity as the word we are trying to find the sense for
![[{FF25FA35-BE85-4148-BF8F-D822DDE943CA}.png]]
[[Lecture 1 & 2#Supervised Learning Overview]]
![[{2D7FA9EB-44B5-4046-A522-1537FE996D2A}.png]]
![[{04844489-DA1D-493D-9FFA-60F7D5D1E188}.png]]
## Yarowsky's weakly supervised algorithm
---
![[{9DEB7379-9363-4E8B-830B-C3906620019C}.png]]


