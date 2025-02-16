---
tags:
  - CS598
---
---

## Inverted Index, TF-IDF
---
![[{995EDD5E-03A5-4A1A-B857-177FAE6B3C62}.png]]
- For each term T, we must store a list of all documents that contain T.
- Do we want to use an array or list?
![[{F1F8096E-3AB1-494F-86C8-64542C3FA237}.png]]
![[{6D88200C-4F30-4BAA-902B-DF90B61C216B}.png]]

## Modern Vector Embedding
---
![[{8EE0E6B0-E514-4555-8780-E38426B5CCA5}.png]]
Very high dimension for the embedding , but it is a dense embedding so there are not many zeros in this embedding vector

## Locality Sensitive Hashing
---
- Given a query, how do we find similar items from a large search set quickly
- Define a measure for similarity of the items, then hash them into buckets of similar items
	- Items which are similar will be in the same bucket 
- Then given a query q, we hash it and return items in the same bucket

- Its a way of doing an approximate Nearest Neighbor search
	- Item signatures used are approximate
	- Item hashing to the same bucket is probabilistic 
- So multiple hash tables are composed for better accuracy 

- There are many similarity/distance measures
	- Jaccard
	- Euclidean
	- Hamming 
	- Cosine
- Allows sublinear query time
- Preprocessing varies based on data & representation
 
![[{651E14ED-AFEF-468A-A325-8A6A04E7CB2C}.png]]
![[{EBBF6CB6-83AB-4BF8-A38B-1813A3568279}.png]]
![[{9DF10194-46EC-4825-BB64-E0932D549620}.png]]
Gaussian/Normal Distribution is a stable distribution since we can take linear combinations of normal distributions and getting a normal distribution as the result. 
![[{35DE2992-DC2B-4D39-B988-CFC614F451B6}.png]]

A weakness of this approach is we can potentially pick a projection vector randomly that maps two close points to separate buckets even though they are close. Similarly, two far points can end up being mapped to the same bucket even though they are far away due to the probabilistic nature of this approach.  

Another is, If we have two points near the same border of buckets in different buckets, they are the nearest neighbor to each other compared to the other points in the buckets.
## Practical Implementation
---
Each hash table employees multiple hash functions
- data points really close to each other map to the same bucket 
- might be too conservative
Multiple independent hash tables following the above guidelines




