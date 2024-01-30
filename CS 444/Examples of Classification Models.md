---
tags:
  - CS444
---
---
![[Pasted image 20240118110154.png]]
This is supervised since we are given input-output pairs in the training data.
![[Pasted image 20240118110234.png]]
Find the distances to all training examples & find the closest one, then assign the test example the value of the nearest training example
![[Pasted image 20240118110546.png]]
![[Pasted image 20240118110650.png]]
![[Pasted image 20240118110836.png]]
![[Pasted image 20240118111122.png]]
![[Pasted image 20240118111148.png]]
![[Pasted image 20240118111346.png]]
$W$ has a 3 rows for the 3 possible classes, This pretends that the image has only 4 pixels, so the matrix has 4 columns, the number of weights will be $width \cdot height \cdot classes$
$b$ is the bias vector
$x_i$ flattens the image in a 1-D vector 
By matrix-vector multiplying we apply all 3 classifiers in parallel
![[Pasted image 20240118111407.png]]
This is a simplified analogy to how a neuron works 
![[Pasted image 20240118111608.png]]
![[Pasted image 20240118111619.png]]
Can look at these as circuit elements, each dimension of an input is binary
In this example, we draw the line in a way for $and$ such that if both $x^1$ and $x^2$ are 1 then we will return true which is how we want a logical and to function
$XOR$ is not linearly separable 
![[Pasted image 20240118111635.png]]
