---
tags:
  - STAT542
---
---
## Notes about R
---
In R when we use $lm(Y\sim X)$, $X$ can be a vector or dataframe:  $lm(Y\sim X, data=test)$.

## Low Correlation but high predictor significance
---
We can have a significant predictor or multiple significant predictors with a very low $R^2$ value when we have a large sample size. This is due to the large sample size causing a small margin of error, so we can have something like a predictor having a 0.002 coefficient with a 0.000001 margin of error which prevents 0 from being in the confidence interval of the predictor

## Estimation vs. Testing
---
Assume we have :$$X_1, ..., X_n \sim N(\mu, 1)$$ We can take a sample & get $\bar{x}$ which would be a estimate of $\mu$.

### Estimation:

- $MSE = E [ (x-\mu)^2 ]= {Bias}^2 + Variance = \dfrac{\sigma^2}{n}$ (Bias in this case is 0, so MSE is just variance)

### Testing:

$H_o : \mu = 0$
$H_a: \mu \neq 0$

$\hat {\mu} =$ $[0$ if cannot reject Null else $\bar{x}$ if can reject Null]

If your goal is estimation, then it is usually not worth it in practice to do testing for the parameters since as $n \to \infty$  then $\mu \to \bar{x}$. This is because estimation is continuous rather than discrete like testing.


## Price for having a large model
---
![[IMG_0007.jpg]]![[IMG_0008.jpg]]
So since our test error is $n \sigma^2 + \sigma^2 p$ , more parameters in the model will result in a higher test error.
While for training error, we have $n \sigma^2 + \sigma^2 p - 2\sigma^2 p = n \sigma^2 - \sigma^2 p$, so having more parameters will result in a lower training error.

