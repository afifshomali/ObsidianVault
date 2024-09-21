---
tags:
  - STAT542
---
---

## Objective Functions
---
$$ J(\beta) = \dfrac{1}{2n} ||Y - X\beta||_2^2 + \lambda|\beta|$$
$$  J(\beta) = \dfrac{1}{2n} [ ||Y - X\beta||_2^2 + 2 n\lambda|\beta|]$$\
## $\lambda$ Fixed Coordinate Descent
---
Initialize $(\beta_1, \beta_2, ... \beta_p)$ then update only one $\beta$ at a time while keeping the others fixed
![[{241F1808-4921-4A31-8D90-2E48F6D727C1}.png]]
![[{71EDBC4F-F17C-4DBC-BF82-014A1C02649A}.png]]
