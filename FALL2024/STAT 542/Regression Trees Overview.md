---
tags:
  - STAT542
---
---
![[{0F244DD1-FB33-4EE7-B298-E39EDBA04F12}.png]]
[[Decision Tree Induction]]

If $X$ is a categorical variable with $m$ levels then to evaluate all possible splits you need $2^m - 1$ total iterations. But in practice you only need to look at $m-1$ splits by looking at the average $y$ values
These $m-1$ splits will be the best among all possible splits 

$$a_1,a_2, ..., a_m$$
$$a_1 \geq a_2 \geq ... \geq a_m$$

![[{A5DAE651-43B9-452D-A71C-2990ADFDF09E}.png]]
To improve the tree we will use 2 methods:
	1. Random Forest with Bagging
	2. XGboost with Boosting 