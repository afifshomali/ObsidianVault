---
tags:
  - CS412
---
---
![[Pasted image 20240829110056.png]]
## Getting to Know Your Data
---
 - [[#Data Objects & Attribute Types]]
 - [[#Basic Statistical Description of Data]]
 - [[#Hypothesis Testing]]
 - 
## Types of Data
---
![[Pasted image 20240829110123.png]]
- Don't make one big table with relational records, like from 411 where we use a key and foreign key to link Tables & lookup things in another table based on the 1st table
- If you are buying from Amazon, you wouldn't want to store your transaction data in a Table since you don't purchases every item on the website so most of the entries would be 0
- Most Data we observe is very sparse
![[Pasted image 20240829110130.png]]
- Not Covered much in this class, covered more in CS 512
![[Pasted image 20240829110138.png]]
- Ordered Data is becoming more and more relevant 
![[Pasted image 20240829110151.png]]
## Characteristics of Structured Data
---
- Dimensionality 
	- Curse of Dimensionality 
- Sparsity 
	- Only data that is non zero/non null matters
- Resolutions
	- Patterns depend on the scale
- Distribution
	- Centrality & Dispersion, e.g. does it follow a Normal Distribution, Binomial, Exponential, Poisson 

## Data Objects & Attribute Types
---
![[Pasted image 20240829111356.png]]
![[Pasted image 20240829111406.png]]
![[Pasted image 20240829111432.png]]
Zip Codes can be more than just nominal because they were spatially laid out in a specific way 
- [[Nominal Categorical Variables|Nominal]] 
- [[Binomial distribution|Binomial]]
- [[Ordinal Categorical Variables|Ordinal]]
![[Pasted image 20240829111536.png]]
- [[Interval Quantitative Variable|Interval]]
- [[Ratio Quantitative Variables|Ratio]]
![[Pasted image 20240829111604.png]]
Amazon Product Rating is an Ordinal variable, but we can't really quantify the difference between 1 and 3 stars for example
### Levels of Measurements
![[Levels of Measurements]]
## Basic Statistical Description of Data
---
![[Pasted image 20240829112322.png]]
![[Pasted image 20240829112545.png]]
![[Pasted image 20240829112556.png]]
![[Pasted image 20240829112656.png]]
![[Pasted image 20240829113001.png]]
- [[Multinomial distribution|Multinomial]]
![[Pasted image 20240829113108.png]]
![[Pasted image 20240829113121.png]]
![[Pasted image 20240829113138.png]]
![[Pasted image 20240829113152.png]]
![[Pasted image 20240829113159.png]]
![[Pasted image 20240829113208.png]]
![[Pasted image 20240829113223.png]]

## Hypothesis Testing
---
![[Pasted image 20240829113953.png]]
![[Pasted image 20240829114023.png]]
![[Pasted image 20240829114044.png]]
![[Pasted image 20240829114234.png]]
- [[Pearson chi-squared statistic & Test]]
![[Pasted image 20240829114341.png]]
![[Pasted image 20240829114401.png]]
![[Pasted image 20240829114443.png]]
![[Pasted image 20240829114429.png]]
