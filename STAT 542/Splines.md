---
tags:
  - STAT542
---
---
## General Notes
---
If $g_1,g_2$ are both cubic splines as defined previously, then a linear combination of the two will also be a cubic spline

Cubic spline functions with respect to $\{\xi_i\}_{i=1}^m$  will form a linear subspace (basis) with $$df=4(m+1) -3m = m+ 4$$
## Finding Basis with $m+4$ equations
---
![[{9422B57F-7D10-41C3-AF85-CD68290D52C2}.png]]
So we have $m+4$ functions that are a basis since they cannot be formed as linear combinations of each other.
$$g(x) \in Cubic\ Spline \implies \sum_{j=1}^4 \beta_j h_j(x)$$

## Regression Spline
---
We can just use OLS for fitting a regression with splines which allows us to make predictions![[{A780DA81-82ED-4D21-B15C-D7CC3D200B19}.png]]

## Selecting Knots in R
---
basis spline = `bs(df =m, intercept= T or F)`
This specifies knots at the quantiles of the x observations

if $df = 10 = m + 4$ the number of knots will be $6$ 
if `bs(df =6, intercept= T)` then we get $n$x$6$ matrix 
if `bs(df =m, intercept= F)` then we still get $n$x$6$ matrix but our $df$ will be 7 since we need to add back the intercept term later when predicting

## Natural Cubic Spline
---
$g$ is linear in $[a, \xi_1]$ and $[\xi_m, b]$ 
$g$ is cubic in $[\xi_1, \xi_m]$ 

$g$ also must follow [[Non Linear (Polynomial) Regression#Cubic Spline Rules|Cubic Spline Rules]]
This cause us to lose 4 degrees of freedom so $df$ will be $m$ for Natural Cubic splines which is the number of knots

## Smoothing Spline
---
![[{633B7367-82E0-43BE-B019-913BD2BC871C}.png]]
![[{FDBED243-BFC0-49A3-8CA5-4011EEC906A1}.png]]


