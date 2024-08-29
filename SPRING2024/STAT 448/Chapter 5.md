---
tags:
  - STAT448
---
---
![[Pasted image 20240220145239.png]]
![[Pasted image 20240220145245.png]]
![[Pasted image 20240220145258.png]]
![[Pasted image 20240220145308.png]]
For B the Sum of squares is the Sum of Squares after we have already included A in the model. So it builds sequentially.
![[Pasted image 20240220145318.png]]
Start with full model & only "remove" the one variable & calculate the sum of squares. Need to be careful when using these.
![[Pasted image 20240220145327.png]]
![[Pasted image 20240220145334.png]]
![[Pasted image 20240220145344.png]]
Days is a count variable
![[Pasted image 20240220145349.png]]
![[Pasted image 20240220145355.png]]
![[Pasted image 20240220145402.png]]
![[Pasted image 20240220145409.png]]
![[Pasted image 20240220145416.png]]
Degrees of freedom for the model are the df for origin + df for grade + df origin * df grade
At least one of the terms in the model is significant is the conclusion of the test from the first table.
![[Pasted image 20240220145423.png]]
Origin has 2 levels while Grade has 4. Since the lines are not parallel we have an interaction effect between Origin and Grade. The gap between A and N for Grade 2 is larger than the gap for the other Grades.
![[Pasted image 20240220145458.png]]![[Pasted image 20240220145504.png]]
![[Pasted image 20240220145510.png]]
When we have a balanced case, proc glm will give us the same Type I and Type III sum of squares because the data is balanced
![[Pasted image 20240220145517.png]]
![[Pasted image 20240220145524.png]]
![[Pasted image 20240220145531.png]]
![[Pasted image 20240220145537.png]]
