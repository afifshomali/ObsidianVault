---
tags:
  - CS444
---
---
![[Pasted image 20240208110218.png]]

## Computation Graphs
![[Pasted image 20240208110245.png]]
![[Pasted image 20240208110251.png]]
![[Pasted image 20240208110301.png]]

## Chain Rule:
![[Pasted image 20240208113034.png]]
![[Pasted image 20240208113040.png]]
![[Pasted image 20240208113047.png]]
![[Pasted image 20240208113054.png]]
![[Pasted image 20240208113103.png]]
The last node is the loss. y is the target label. 

## General Backpropagation Algorithm:
![[Pasted image 20240208113110.png]]
You get the upstream gradient as input, then you compute the two local gradients, one for the weight update and one for the downstream gradient. Then we update the weights & pass the gradient downstream
![[Pasted image 20240208113125.png]]
![[Pasted image 20240208113137.png]]
You apply Chain rule to the individual paths & then sum the derivatives. Kind of like taking the derivative of $x^2 + x^3$. You can take the individual derivatives & then sum them.
![[Pasted image 20240208113144.png]]

## Examples of Backwards Pass:
![[Pasted image 20240208113256.png]]
![[Pasted image 20240208113313.png]]
Use the values from forward pass when calculating the local gradient.
![[Pasted image 20240208113325.png]]
Derivative of $w2$ plus a constant is just a constant so we keep the same gradient
![[Pasted image 20240208113338.png]]
Still have a plus node, so the local derivative is 1 so we pass down the upstream derivative
![[Pasted image 20240208113352.png]]
$x1$ is argument & $w1$ is constant. So $-3 * 0.2$ gives us the value of $x1$ and then for $w1$ we do $-2 * 0.2$. 
For $x1$ we do $\dfrac{d w1}{d x1}$ so we then multiply by value of $w1$. We then do the opposite when we calculate $w1$.
![[Pasted image 20240208113417.png]]
$z$ would get a gradient of 2 because of the max.
The multiply gate switches. 
Add gate gives the same gradient to both inputs.
## Matrix-Vectors Calculations: ReLU, Linear Layer
![[Pasted image 20240208113509.png]]
![[Pasted image 20240208113514.png]]
Using Row vectors, not column vectors in order to have the correct multiplication order. Derivative is now the Jacobian. 
Need to have dimensions match for upstream gradient since we use it to update the weights.
![[Pasted image 20240208113530.png]]
![[Pasted image 20240208113540.png]]
Jacobian is a diagonal matrix. We just need indicator function to compute the gradient, so due to structure we don't need the full matrix. If Data is not normalized, the ReLU will end messing up the gradient so we don't have any updates. 
![[Pasted image 20240213114450.png]]

![[Pasted image 20240208113553.png]]
![[Pasted image 20240208113601.png]]
![[Pasted image 20240208113609.png]]
![[Pasted image 20240208113621.png]]
![[Pasted image 20240208113629.png]]
![[Pasted image 20240208113640.png]]
![[Pasted image 20240208113648.png]]
![[Pasted image 20240208113659.png]]

