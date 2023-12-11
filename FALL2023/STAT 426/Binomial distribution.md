---
aliases: Binomial
tags: STAT426, STAT426/Midterm1, distributions
---
---
The sum of or consecutive independent and identical [[Bernoulli distribution|Bernoulli]] trials together form a Binomial distribution. 

![[Pasted image 20230827170438.png]]

$p(y)$ is the probability of $y$ successful trials happening in $n$ number of trials 
$\pi$ is the probability of one trial occurring successfully

![[Pasted image 20230827170648.png]]

The [[Skewness]] is the Third Central Moment for the Binomial Distribution
When $\pi = 0.5$, the Skewness is 0 so the distribution has symmetric behavior

When $n$ is large, the Binomial Distribution can be approximated by a [[Normal Distribution]] by using the formula to center & then divide by the standard deviation

The Binomial Distribution is also a special case of the [[Multinomial distribution]] when the number of categories in a multinomial distribution is 2.

**[[Maximum likelihood estimation|MLE]]:**
![[Pasted image 20230911192231.png]]
**[[Fisher information]]:**
![[Pasted image 20230911192339.png]]

