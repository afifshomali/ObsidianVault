---
tags:
  - CS444
---
---
## Linear to Non-Linear Classifiers:
![[Pasted image 20240206111504.png]]
![[Pasted image 20240206113105.png]]
![[Pasted image 20240206113129.png]]
![[Pasted image 20240206113145.png]]
![[Pasted image 20240206113211.png]]

## Why to use non-linear classification:
![[Pasted image 20240206113307.png]]
The bias $b$ is used to shift the origin of the coordinate system. Linear Transformation cannot make non-linear data into llnear data, so we must use a non linear transformation.
![[Pasted image 20240206113458.png]]
ReLU compresses all the data points to one quadrant in 2-D.
![[Pasted image 20240206113415.png]]

## Two Layer Neural Network:
![[Pasted image 20240206113603.png]]
Output layer corresponds to the classification,, view it as a composition of functions
![[Pasted image 20240206113617.png]]
It's a distributed representation: Most templates are not interpretable
![[Pasted image 20240206113710.png]]
Can approximate any decision boundary using a two layer neural network but the hidden layer may have to contain a very large amount of nodes in order to so.
## Multi Layer Networks:
![[Pasted image 20240206113727.png]]
Instead of making layers larger, we just keep stacking layers. The output layer will depend on the type of result, for example classification will likely use SoftMax as the non linearity.
![[Pasted image 20240206113852.png]]

![[Pasted image 20240206113905.png]]
http://playground.tensorflow,org/

## Hyperparameter Search & Validation:
![[Pasted image 20240206114018.png]]
![[Pasted image 20240206114035.png]]
$K$ is defined by hand, 
if it is small then the training accuracy is 100% so it may not do too well on unseen data & it is sensitive to outliers
if it is too large then you will have unrelated points in the $K$ nearest neighbors, so we are less sensitive to each individual points, we end up underfitting the data
![[Pasted image 20240206114043.png]]
If $\lambda$ is too large then our margin is large & we will tend to underfit the data
If $\lambda$ is too small then our margin will be small & we will tend to overfit the data
![[Pasted image 20240206114049.png]]
Above solution may not be optimal if the blue point is an outlier
![[Pasted image 20240206114057.png]]
![[Pasted image 20240206114105.png]]
![[Pasted image 20240206114117.png]]
![[Pasted image 20240208111553.png]]
![[Pasted image 20240206114127.png]]
![[Pasted image 20240206114137.png]]
![[Pasted image 20240206114147.png]]
![[Pasted image 20240206114158.png]] 
![[Pasted image 20240206114209.png]]
Test error will tend to be higher than training error, as you increase the capacity of the model the  the error will go down but it also has the chance to go back up if we start overfitting the test data.
However Neural Networks tend to be over parametrized but they don't tend to have this error of overfitting in practice. So even if we have 0 training error, that doesn't necessarily mean that we are overfitting.
![[Pasted image 20240206114239.png]]
Test Data should be completely hidden from the person building the model. Held-Out Data is essentially the test data for when we are training the model so we how the model performs on never seen before data.
![[Pasted image 20240206114247.png]]
