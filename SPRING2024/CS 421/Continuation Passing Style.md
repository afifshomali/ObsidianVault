---
tags:
  - CS421
  - CS421/Midterm1
---
---
![[Pasted image 20240206095631.png]]
![[Pasted image 20240206095639.png]]
![[Pasted image 20240206095647.png]]
![[Pasted image 20240206095659.png]]
![[Pasted image 20240206095714.png]]
![[Pasted image 20240206095900.png]]

## Nesting Continuations
![[Pasted image 20240206100012.png]]
![[Pasted image 20240206100028.png]]
![[Pasted image 20240206100040.png]]
![[Pasted image 20240206100059.png]]
![[Pasted image 20240206100113.png]]
![[Pasted image 20240206100126.png]]
![[Pasted image 20240206100150.png]]
![[Pasted image 20240206100202.png]]
![[Pasted image 20240206100213.png]]
$k$ is the function we pass the value of length of the list to.
$r$ is the result, and we add 1 to it, addk(1, r) adds 1 & r  and then passes it to k. Which is the addk is the CPS style of adding two values.
Report function prints the integer which is the value of the length of the list
![[Pasted image 20240206100228.png]]
![[Pasted image 20240206100236.png]]
![[Pasted image 20240206100255.png]]
The first example is tail recursion and the accumulator is carried through by whether you are in the if branch or else branch.
pk x is passed in as the value b. Then if b is true we will continue down the list. 


