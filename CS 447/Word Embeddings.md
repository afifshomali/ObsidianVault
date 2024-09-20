---
tags:
  - CS447
---
---
- A Static word embedding is a function that maps each word type to a single vector
	- These vectors are typically dense and have a much lower dimensionality than the size of the vocab
	- This mapping function typically ignores that the same string of letters may have different senses or parts of speech
	- Theis mapping typically assumes a fixed sized vocab so UNK token is needed
![[{45AA220F-E0FF-4881-A663-EC895F087CFB}.png]]
![[{2FEFE7A2-81B1-4B77-AE0F-E201066FE0BF}.png]]
![[{4686CC15-C667-43D1-AD05-195D31091F63}.png]]
![[{D34084B2-9964-423A-BD1B-E355BABCCCB7}.png]]
![[{3A33C6DF-455F-4D06-BBB2-3B64A82311CF}.png]]
![[{EF5FE319-D7DE-4AB3-82D3-10925B8E6C95}.png]]
![[{43BC4FC6-49A0-48C8-A309-3DCA9D56672B}.png]]
![[{B7081DBE-4784-41D7-94B1-131849D46B43}.png]]

## The Skip-Gram Classifier
---
![[{BB736441-769B-4B0C-9051-B63E7738DF68}.png]]
- high if $t,c$ are very similar for probability of positive
- probability of negative is very high is $t.c$ are very dissimilar 
![[{1570DA9A-C8F1-4A6E-B0E4-1E55CA2165CD}.png]]
![[{E6EBDF67-9B06-4F3E-B397-704A383C9042}.png]]
![[{2C528A07-9DF5-4E8A-A47D-00CC5FCB2086}.png]]
![[{271DCB4F-596F-43E8-87EA-7EFC5E4BA05E}.png]]
![[{D806EF05-C373-4B0B-BB4F-9B5498100351}.png]]
![[{194E45F0-AD22-4431-ABD2-B4D88B3EF1A9}.png]]
