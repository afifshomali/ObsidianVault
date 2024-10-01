---
tags:
  - CS447
---
---
![[{2A136EF5-DF82-48DA-B767-FFF610A23CAE}.png]]
Words can often have multiple parts of speech
The POS tagging tasks relies on determining the correct POS based on context
We can't just look up the POS in a dictionary due to ambiguity, and tagging words we have never seen before
One of first steps, right after tokenization and segmentation
![[{EDB2260F-5828-43BC-8C5F-7451DA4DB842}.png]]
![[{9A1AC616-B308-4D5E-A530-85E23A82FCAA}.png]]
![[{9E43220B-057A-4FEB-8981-FDB8F001C372}.png]]
![[{D73F625A-FDC5-492E-9125-503CE2622C3B}.png]]
![[{DAFCC1F7-2B21-46A0-918C-975413AC9541}.png]]
![[{AB305AB9-6CD2-4148-919F-9A69C2E03E85}.png]]
40% of the brown tokens are ambiguous
![[{2C407D84-21C8-47B7-8924-60FCABBDA9F2}.png]]
We see that the accuracy is roughly the same as human accuracy 
However, the POS tagging problem is not yet solved because other languages are much more complex and so they need much larger tagging to be useful and they often have much lower accuracies, so POS tagging still needs more work
Also: POS tagging on other English texts from other domains can be significantly lower

