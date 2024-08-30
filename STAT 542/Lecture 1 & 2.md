---
tags:
  - STAT542
---
---

- Want to minimize test error since that is the error when we see a new data point/unknown data point
- Having a low training error while having a high test error means we are usually overfitting to the training data 
- We have feature matrix X is an n by p matrix and Y is a n by 1 Matrix

## LS & kNN
---
- For k Nearest Neighbor we take the k nearest points by distance to the value, and then we find the corresponding y values and either average for numeric data or majority vote for categorical data

- When we have k=1, then DF is n since $DF = \dfrac{n}{k}$ , different from T-Test which has $DF = n -1$
- When K is 1, we have most complicated model, while when K = n we have intercept only model which is the least complicated 

- For linear regression the degree of freedom will be the number of parameters/dimensions of x + 1 for the intercept
- For the T -Test for Linear regression the degree of freedom will be n -3 or n - (p+1)

## Coding assignment 1
---
- If you have 2 models with same performance pick model with less complexity, e.g. higher k value