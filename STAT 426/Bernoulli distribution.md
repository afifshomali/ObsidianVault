---
aliases: Bernoulli
tags: STAT426, STAT426/Midterm1, distributions 
---
---
Have an event that either happens or doesn't happen, one instance of this is a Bernoulli trial. For example flipping a coin once.
![[Pasted image 20230827170100.png]]

$\pi$ represent the probability of the event occurring, multiple Bernoulli trials summed up make a [[Binomial distribution]].   

**[[Maximum likelihood estimation|MLE, ML]] for Bernoulli:**
![[Pasted image 20230911185107.png]]
![[Pasted image 20230911185121.png]]

## Binary Regression using Bernoulli:

![[Pasted image 20230929215449.png]]
![[Pasted image 20230929215500.png]]
As we see the Canonical Link is the Logit of the parameter or log odds. In this Scenario $b(y_i)$ is equal to 1 and $a(\theta_i) = (1 - \pi_i)$ . Which is a [[Logistic regression]].