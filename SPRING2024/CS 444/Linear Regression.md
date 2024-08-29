---
tags:
  - CS444
---
---
![[Pasted image 20240118112911.png]]
![[Complexity Classes#Overview of Complexity Classes]]
![[Pasted image 20240118113252.png]]
Low loss if we can map all positive points close to 1 and all negative points close to -1 
![[Pasted image 20240118113258.png]]
$X$ is training vectors, with $n$ rows which is the number of observations, and it has the the same number of columns as there are features/predictive variables
$w$ is unknown 
$y$ is vector of target labels for training data
![[Pasted image 20240118113305.png]]
Find where gradient of loss function is 0, that will give us the solution for $w$. So it has a unique global minimum
Not all models will have a convex loss function so we wouldn't be able to use this to minimize loss all the time
![[Pasted image 20240118113317.png]]
![[Pasted image 20240118113326.png]]
![[Pasted image 20240118113332.png]]
Mean of Normal function depends on $x$ and the noise added is the standard devation
![[Pasted image 20240118113344.png]]
Variant of loss minimization see: [[Maximum likelihood estimation|MLE]]
![[Pasted image 20240118113351.png]]
![[Pasted image 20240118113359.png]]
This can potentially work for binary classification
![[Pasted image 20240118113612.png]]
![[Pasted image 20240118113743.png]]
![[Pasted image 20240118113747.png]]
Value close to zero means we are pretty sure the point has a negative label, 
Value close to one means we are pretty sure the point has a positive label
### Related:
[[Module 3 Generalized Linear Models (GLMS)]]