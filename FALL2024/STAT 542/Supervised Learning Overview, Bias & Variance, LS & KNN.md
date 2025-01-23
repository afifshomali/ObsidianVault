---
tags:
  - STAT542
---
---

- Want to minimize test error since that is the error when we see a new data point/unknown data point
- Having a low training error while having a high test error means we are usually overfitting to the training data 
- We have feature matrix X is an n by p matrix and Y is a n by 1 Matrix
## Course Overview
---
- Supervised Learning attempts to predict a know Y variable using features X. Either numerical values if its a regression problem or categorical variables if it is classification problem
- Unsupervised Learning involves finding patterns rather than predicting, like finding clusters or associations
- Can also combine these two systems, which is called Unsupervised learning, it is used when classification data is expensive and time consuming to get 
- Primary focus will be on supervised learning 

## Supervised Learning Overview
---
![[Pasted image 20240901173832.png]]

- An issue with supervised learning is overfitting, we want to make sure that we minimize test loss, but if training loss gets too small then the model won't necessarily preform well on new data
- We don't really need to always get a stringent optimization of the loss/objective function $F_n(w)$. We can still get pretty good results with a method like gradient descent 
- Overfitting can happen when we have a large number of parameters in our model, when the number of parameters is large the gap between train and test error will get large too
- For example 1NN model have the number of parameters equal to the sample size of the data, We can get perfect, as in zero error for our training set but it doesn't mean we will do well on test images that we have not seen before
![[Pasted image 20240901174639.png]]

## Learning Theory
---
![[Pasted image 20240901174742.png]]
![[Pasted image 20240901174802.png]]
![[Pasted image 20240901174813.png]]
![[Pasted image 20240901174820.png]]
- a) As in only 1 or 0 decisions, not probability based decisions where we might have 0.7 for one category and 0.3 for another
![[Pasted image 20240901174918.png]]
![[Pasted image 20240901174926.png]]
![[Pasted image 20240901174935.png]]
![[Pasted image 20240901174943.png]]
![[Pasted image 20240901174949.png]]

## Bias vs Variance
---
![[Pasted image 20240901175756.png]]
- Bias can be easier to adjust for since we can move the target up and to the right, while moving the target for the variance case has not real effect
- Total error can be attributed to bias + variance
![[Pasted image 20240901175938.png]]
![[Pasted image 20240901175928.png]]
- If we increase variance, as in the circle size, bias will lower but variance will be higher so still high error
- If we make the circle smaller, our bias will be higher but variance will be lower
![[Pasted image 20240901180108.png]]
- More complexity means more variance but lower bias, but also can cause overfitting as mentioned before
![[Pasted image 20240901180221.png]]
- We can reduce bias and variance, reducing bias is most important however we want to ensure a balance between reducing both
![[Pasted image 20240901180328.png]]

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