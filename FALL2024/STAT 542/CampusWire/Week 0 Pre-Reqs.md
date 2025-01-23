---
tags:
  - STAT542
---
---
In case you want to refresh your knowledge on linear algebra, probability, and statistics, please check the following:
- Chap 2-5 from the online book for STAT 420 (developed by Prof. David Dalpiaz)
[Applied Statistics with R](https://daviddalpiaz.github.io/appliedstats/)

- Some beginning chapters from the [Deep Learning Book](https://www.deeplearningbook.org/lecture_slides.html).
Chap 2: Linear Algebra [html](https://www.deeplearningbook.org/contents/linear_algebra.html) [pdf](https://www.deeplearningbook.org/slides/02_linear_algebra.pdf) [youtube](https://youtu.be/mJ5PSaHeA0k)]
Chap 3: Probability and Information Theory [html](https://www.deeplearningbook.org/contents/prob.html) [pdf](https://www.deeplearningbook.org/slides/03_prob.pdf) [youtube](https://youtu.be/lAkUEnR3fKw)


- The Linear Algebra tutorial slides from CS 445 are also helpful.
[slides from CS 445](https://courses.engr.illinois.edu/cs445/fa2019/lectures/linear_algebra_review.pdf)[another review](http://cs229.stanford.edu/section/cs229-linalg.pdf)

**Probability**
- Conditional probability, Bayes Theorem
- How to describe a random variable: pdf (continuous), pmf (discrete), CDF
- Discrete distributions: Bernoulli, Binomial, Multinomial
- Continuous distributions: Normal including multivariate normal
- How to compute mean, variance, and covariance

**Statistics**
- Sample mean, sample variance
- LLN (Law of large numbers) and CLT (central limit theorem)
- Estimation: MSE (mean squared error), unbiased estimator, MLE
- Hypothesis testing

**Linear Algebra**
- Vector, co-linearity, linear subspace
- Matrix product, matrix inverse, trace, determinant, SVD
- SVD: this [website](http://databookuw.com/page-2/page-4/) is recommended by a student from the prior year. 
- I may (in videos) call the "2ab" term (in the quadratic expansion $$(a+b)^2=a^2+2ab+b^2$$) the cross product term, but it is not related to the "[cross product](https://en.wikipedia.org/wiki/Cross_product)" defined for two vectors, which we should never encounter in this course.

**Numerical Optimization**
- Continuous vs differentiable
- How to compute the derivative of a function?
- Find the minimizer of
  - $$ f(x) = w_1 (x - a_1)^2 + \cdots + w_m (x-a_m)^2, $$ [Ans](https://math.stackexchange.com/questions/1352726/minimizing-a-function-sum-of-squares)
   
  - $$ f(x) =  |x - a_1| + \cdots +|x-a_m|$$ [Ans](https://math.stackexchange.com/questions/113270/the-median-minimizes-the-sum-of-absolute-deviations-the-ell-1-norm)
- Convex function and Jensen's inequality