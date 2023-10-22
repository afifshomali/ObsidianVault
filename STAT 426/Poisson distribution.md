---
tags:
  - STAT426
  - STAT426/Midterm1
  - distributions
aliases:
  - Poisson
---
---
Counts number of events happening in given space or period of time. For example the number of phone calls an office receives in day.
![[Pasted image 20230827171943.png]]
![[Pasted image 20230827172105.png]]

Poisson is an approximation for the [[Binomial distribution]] when $n$ is large and $\pi$ is small, such that $\mu = n\pi$.

The Sum of independent Poisson Distributions will be another Poisson distribution where the $\mu$ of the sum will be $\mu = \sum_i \mu_i$. 
This sum of Poisson distributions when the sum equal some fixed $n$ is also connected to the [[Multinomial distribution]] distribution in an interesting way, see
[[Connection Between Poisson & Multinomial Distributions]]. 

For some applications, it is difficult to assume the it satisfies $E[Y] = var[Y] = \mu$ or mean equal to variance. Having higher variability than the mean/what we expected is called [[Overdispersion]]. The opposite of this is, is when we have less variability than expected is called [[Underdispersion]], but it is rare in practice. 

## Poisson Regression

When we have a count variable we can use Poisson, but this is not always the case. If we cannot guarantee $E[Y] = Var[Y]$ then it is better to use the Negative Binomial Distribution instead.
![[Pasted image 20230929220401.png]]
Here we have $a(\theta_i) = e^{-\mu_i}$ , then $b(y_i) = \dfrac{1}{y_i!}$ and the Canonical link is the natural log of the parameter.
![[Pasted image 20230929220407.png]]
This gives us a [[Loglinear Model]]