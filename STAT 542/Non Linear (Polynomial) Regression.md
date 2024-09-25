---
tags:
  - STAT542
---
---
For $x_i \in \mathbb{R}$ with a distribution that looks like this and is fitted by a polynomial regression curve:
![[{34FFF632-3B11-478F-9DC9-78B1F5F73149}.png]]
Then we have $$y_i = \beta_0 + \beta_1 x_i + \beta_2x_i^2+\beta_3x_i^3+\epsilon_i$$
Non-Linear regression is linear regression with terms that are potentially quadratic, cubic, etc. If we pick cubic term to be in our model, we usually pick the lower order terms too. This is the hierarchy principle, similar to what we would do for interaction terms.
[[4.1 Introduction to Generalized Linear Models]]

For polynomial regression, we want to use spline models/ piecewise polynomials so we get better predictions outside the range of the data.

For $\{y_i, x_i\}_{i=1}^n$   and $x_i \in [a,b]$ 
![[{E4EA05BD-4A52-4700-8500-1B49BEEA356C}.png]]
*$\xi$ is the squiggly character not cphsi, xi

Let $g$ be a cubic spline on $[a,b]$ with respect to $\{ \xi_j\}_{j=1}^m$ then we must satisfy the following:

1) 
$g$ is cubic for $\{ \xi_i, \xi_{i+1}\}$ 
$g(x) = d_i x^3 + c_i x^2 + b_i x + a_i$  for $i=0,1,..,m$
2) 
$g(\xi_i^+) = g(\xi_i^-)$ 
$g'(\xi_i^+) = g'(\xi_i^-)$ 
$g''(\xi_i^+) = g''(\xi_i^-)$ 

So for each knot/interval boundary, we need $g$ to be continuous up until the 2nd derivative, So each of the interior know must have same derivatives on either side of the knot .
![[{E61B2145-13A4-46AA-AC12-875A911F106C} 1.png]]
