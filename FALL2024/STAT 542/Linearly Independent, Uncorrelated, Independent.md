---
tags:
  - STAT542
---
---
## Linearly Independent, Uncorrelated, Independent
---
![[Pasted image 20240912181221.png]]
If $X$ is not full rank where $r=p$ then we cannot take the inverse, so assume $X$ is of rank $p$ for this example

- **Linearly Independent**: means in a collection of vectors, none of the vectors in the collection can be written as a linear combination of the other vectors in that collection
- **Independent Variables:** means that  the joint distribution $$P(X_1, .., X_n) = P(X_1)\cdot ... \cdot P(X_n)$$
- **Uncorrelated:** means that $$E[ (x_1 - \mu_{1}) (x_2 - \mu_{2})] = 0$$
- Independence implies the variables are uncorrelated, however the opposite is not true since we are talking about the variables being *linearly* uncorrelated, they could still correlated with a non linear relationship, so then the variables would not be independent

