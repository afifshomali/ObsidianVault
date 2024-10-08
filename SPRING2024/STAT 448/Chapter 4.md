---
tags:
  - STAT448
---
---
![[Pasted image 20240208151238.png]]
![[Pasted image 20240208151245.png]]
![[Pasted image 20240208151251.png]]
![[Pasted image 20240208151259.png]]
![[Pasted image 20240208151305.png]]
![[Pasted image 20240208151310.png]]
4 levels/categories, the only thing that is varying here is the Hardwood Concentrations.
![[Pasted image 20240208151315.png]]
IQR plots for each category, one-way Anova assumes all samples from Normal Distributions and all Samples have same variance 
![[Pasted image 20240208151321.png]]
## One-Way ANOVA
![[Pasted image 20240208151326.png]]
Each group/ level of predictor has a an $\alpha_i$ that changes the global mean $\mu$ by some amount, can be higher or lower.
More categorical predictors will lead to a model with more ways. eg. 3 categorical predictors means 3-way model.
![[Pasted image 20240208151415.png]]
This tests if having $\alpha_i$ has any effect on finding the value of the response.
![[Pasted image 20240208151421.png]]
![[Pasted image 20240208151427.png]]
![[Pasted image 20240208151448.png]]
![[Pasted image 20240208151503.png]]
![[Pasted image 20240208151509.png]]
## Two-Way Anova
![[Pasted image 20240208151515.png]]
![[Pasted image 20240208151525.png]]
Usually start from main effects model & then try to simplify it in case interaction terms don't have any effects.
The interaction model is the more general additive model.
![[Pasted image 20240208151554.png]]
$\hat\mu$ is the global sample mean. The $\hat\alpha_i$ is calculated by taking the mean of the group/level & subtracting the global mean, so that becomes the effect on the mean cause by that group/level.
![[Pasted image 20240208151600.png]]
This looks at every single term in the model to check whether each individual term is zero or something significant. The $SS_{total} = SS_{model} + SS_{error}$ . The $SS_{model}$ is the sum of squares for all the terms without the error. In this example those terms are A, B and AB.
![[Pasted image 20240208151606.png]]
## F-Test 
![[Pasted image 20240208151645.png]]
![[Pasted image 20240208151652.png]]
![[Pasted image 20240213141059.png]]
![[Pasted image 20240213141118.png]]

## Example:
![[Pasted image 20240213141131.png]]
![[Pasted image 20240213141137.png]]
![[Pasted image 20240213141142.png]]
![[Pasted image 20240213141148.png]]
![[Pasted image 20240213141153.png]]
![[Pasted image 20240213141158.png]]
![[Pasted image 20240213141204.png]]
![[Pasted image 20240213141209.png]]
![[Pasted image 20240213141215.png]]
![[Pasted image 20240213141220.png]]
![[Pasted image 20240213141225.png]]
![[Pasted image 20240213141233.png]]
![[Pasted image 20240213141244.png]]
![[Pasted image 20240213141249.png]]
![[Pasted image 20240213141256.png]]
![[Pasted image 20240213141305.png]]
![[Pasted image 20240213141313.png]]
![[Pasted image 20240213141320.png]]
![[Pasted image 20240213141327.png]]

## Three-way Anova & other exercises:
![[Pasted image 20240213141343.png]]
![[Pasted image 20240213141403.png]]
If the higher order interaction terms are significant then you should include all the lower interaction terms even if they aren't significant. 
![[Pasted image 20240213141409.png]]
![[Pasted image 20240213141415.png]]
![[Pasted image 20240213141420.png]]
![[Pasted image 20240213141426.png]]

