---
tags:
  - CS447
---
---
![[{8F0C2BF2-81B1-4ACB-BFAD-D512B995CE0C}.png]]
![[{02F64A1D-B2D2-46EF-8083-3DF5CB40F0DC}.png]]

## What are Neural Networks
---
![[{8CDF90C1-860F-409C-8B25-3560AEA27769}.png]]
[[Neural Network Training]]
![[{89C91EAC-5F78-4EAC-A393-6B91B96C36CE}.png]]
![[{52C53636-EBBD-4C30-A904-6A3F23963E6D}.png]]
[[Perceptron Training Algorithm]]

[[Linear Classifiers]]
Given $N$-dimensional inputs $x=(x_1,...x_n$ ):
Can have explicit bias term $b$:
$$f(x) = wx + b = \sum_{i=1}^N w_ix_i + b$$
Or can be without an explicit bias term $b$:
$$f(x) = wx = \sum_{i=0}^N w_ix_i$$ where $x_0 = 1$ (Decision boundary goes through origin  of (N+1) dimensional space 
![[{699DE69A-1E6A-43EC-BBDC-72CC6A69CADE}.png]]
Neural nets replace the Perceptron's linear threshold activation function with a non-linear activation function $g()...$ 
$$y=g(wx+b$$
- This is because non linear classifiers are more expressive than linear classifiers (can represent XOR)
- and any multilayer network of linear perceptron is equivalent to a single linear perceptron 
- and learning requires us to set the weights of each unit
	- Gradient descent, updates the weights based on the gradient of the loss
	- In a multi-layer feed forward neural net, we need to pass the gradient of the loss back from the output through all layers ([[Backpropagation]]) 
	- We need differentiable activation functions so we can compute gradients

![[{AEC4A035-B1B8-4D5B-B7C1-C0FFED3A5529}.png]]
![[{E3CF69B2-B82A-4E6C-B6C4-68E845EB708F}.png]]
![[{B018C70A-1CF1-4FB1-8417-58FDDE80952C}.png]]
![[{030B4936-C348-4DAC-8B21-856F25E8A294}.png]]
![[{B62DCB7C-C6A6-4A0E-8A35-BC568A32B50B}.png]]
![[{4BE5C45E-0B2E-453F-8223-334E089D9858}.png]]
[[Multi-class Classification]]
[[SoftMax]]
![[{BDB6D4FE-73AE-4DB8-B40C-6804DF5D5A28}.png]]




