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
 - [[#Data Visualization]]
 - [[#Measuring Data Similarity & Correlation]]
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
Since you know row sums and column sums, we have 4 total cells that a free to vary, the other 5 cells will be fixed.
![[Pasted image 20240829114401.png]]
![[Pasted image 20240829114443.png]]
![[Pasted image 20240829114429.png]]
![[Pasted image 20240903110220.png]]
![[Pasted image 20240903110228.png]]
![[Pasted image 20240903110245.png]]
### Example for $\chi^2$ 

![[Pasted image 20240903110304.png]]
![[Pasted image 20240903110310.png]]
![[Pasted image 20240903110348.png]]
![[Pasted image 20240903110400.png]]
![[Pasted image 20240903110407.png]]

## Measuring Data Similarity & Correlation
![[Pasted image 20240903110541.png]]
![[Pasted image 20240903110632.png]]
![[Pasted image 20240903110644.png]]
![[Pasted image 20240903110723.png]]
![[Pasted image 20240903110730.png]]
![[Pasted image 20240903110739.png]]
![[Pasted image 20240903110753.png]]
![[Pasted image 20240903110801.png]]
![[Pasted image 20240903110812.png]]
No not really we would have to make some transformation to the variable to be able to have it distributed like a normal distribution
![[Pasted image 20240903110916.png]]
![[Pasted image 20240903110924.png]]
![[Pasted image 20240903110929.png]]

## Data Visualization
![[Pasted image 20240903111036.png]]
![[Pasted image 20240903111044.png]]
![[Pasted image 20240903111053.png]]
![[Pasted image 20240903111059.png]]
![[Pasted image 20240903111108.png]]
![[Pasted image 20240903111118.png]]
![[Pasted image 20240903111126.png]]
![[Pasted image 20240903111143.png]]
![[Pasted image 20240903111151.png]]
![[Pasted image 20240903111158.png]]
![[Pasted image 20240903111210.png]]
![[Pasted image 20240903111233.png]]
![[Pasted image 20240903111239.png]]
![[Pasted image 20240903111247.png]]
![[Pasted image 20240903111254.png]]
![[Pasted image 20240903111302.png]]
![[Pasted image 20240903111309.png]]

