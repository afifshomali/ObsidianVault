---
tags:
  - CS447
---
---
- WordNet is a very large publicly available lexical database of English
	- Each word has a POS tag and one or more word senses
	- Word senses are grouped into synonym sets
	- Synsets are connected in a network and defined by conceptual semantic relations
		- Hyper/hypo nym relations (IS-A)
		- holo/mero nym relation (HAS-A)
	- Also contains lexical relations and lemmatization
![[{2224757B-5717-470D-8D39-93A46B1BB3B6}.png]]
![[{6021972E-1750-4C8C-B654-4A9B80DEF8A0}.png]]
![[{2076A13B-DF40-4983-9387-614FB63FAD5B}.png]]
![[{9E7EB645-2097-4E1F-8026-D3CF43513643}.png]]
![[{49C7BA2B-77C0-4839-A138-EF487D6D15A6}.png]]
![[{12F40C87-727B-41DC-B952-6677FAE62AB4}.png]]
![[{755A1A23-FECC-444F-9B2D-F4B90F0336EF}.png]]
- WordNet can be used to compute word similarity
	- Classic approaches use the distance or path length between Synsets and possibly augmented with corpus statistics 
	- More recent neural approaches aim to learn non-Euclidean embeddings that capture the hierarchical hypernym/hyponym structure of WordNet

- There are many aspects of word sense similarity
	- Synonymy, synonyms, as in do these two words have the same meaning, or hypernym/hyponyms
	- Association, how related are the two words like cup and coffee, get Semantic fields 
![[{D7DA383F-06EB-4C73-A4BE-F7E5D7F9C7B5}.png]]
- We don't really want to have nickel and Richter scale to be associated 
![[{03301028-0AAA-4DBB-B39A-D525E2062E6A}.png]]
![[{91F11336-6F90-4500-9391-AFB0A5507512}.png]]
