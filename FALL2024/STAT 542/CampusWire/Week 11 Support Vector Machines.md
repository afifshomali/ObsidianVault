---
tags:
  - STAT542
---
---

**Notes**:
chap 9 (ISLR); chap 12.2-12.3 (ESL)

**Slides**:
https://liangfgithub.github.io/PSL/

\[[lec_W11_SVM_intro.pdf](https://liangfgithub.github.io/Notes/lec_W11_SVM_intro.pdf)\] A gentle introduction to SVM
\[[lec_W11.1_SVM.pdf](https://liangfgithub.github.io/Notes/lec_W11.1_SVM.pdf)\]
\[[lec_W11.2_SVM.pdf](https://liangfgithub.github.io/Notes/lec_W11.2_SVM.pdf)\]
\[[lec_W11.3_SVM.pdf](https://liangfgithub.github.io/Notes/lec_W11.3_SVM.pdf)\]
\[[lec_W11.4_SVM.pdf](https://liangfgithub.github.io/Notes/lec_W11.4_SVM.pdf)\]

Appendix: 
\[[lec_W11_appendix_SVM.pdf](https://liangfgithub.github.io/Notes/lec_W11_appendix_SVM.pdf)\] \[[lec_W11_appendix_RKHS.pdf](https://liangfgithub.github.io/Notes/lec_W11_appendix_RKHS.pdf)\] (feel free to ignore)

**R Packages**: :
Review paper: \[[SVMinR_JSS2006.pdf](https://www.jstatsoft.org/article/view/v015i09)\]
\[[e1071 svm doc](https://cran.r-project.org/web/packages/e1071/vignettes/svmdoc.pdf)\]
\[[SVM Code by Hastie](https://web.stanford.edu/~hastie/ISLR2/Labs/Rmarkdown_Notebooks/Ch9-svm-lab.html)\]

**Python**
https://scikit-learn.org/stable/modules/svm.html

**Contents** \[[Videos](https://mediaspace.illinois.edu/playlist/dedicated/100591911/1_l9es9xsa/1_3pie269j)\]
1. Linear SVM for separable case
1.1 The max-margin problem
1.2 KKT conditions
1.3 Primal and dual relationship
1.4 Summary for the separable case

2. The non-separable case
2.1 How to handle non-separable data
2.2 Soft-margin SVM

3. Practical Issues
3.1 From the binary decision to probabilities
3.2 Multi-class SVMs

4. Nonlinear SVMs
4.1 Nonlinear SVMs and the kernel trick
4.2 Choice of Kernels
4.3 Kernel machines
4.4 Reproducing kernel Hilbert space (optional)

5. Summary

Additional Fall 2018 Campus Lecture Videos:
\[[Nov 07](https://youtu.be/gu2an5xC7uU)\]
-- around 19:50: regarding max-margin formulation, we should minimize beta-norm, not maximize
-- should be "complementarity condition" not "compatibility condition"

\[[Nov 09](https://youtu.be/UjxkhnE60ss)\]
-- Expansion of exp(x) should contain k=0. 

\[[Nov 12](https://youtu.be/n6azsIK2AW4)\]
-- Review SVM
-- Compare LDA, Logistic and linear SVM
-- Imbalanced data