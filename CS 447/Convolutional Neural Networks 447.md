---
tags:
  - CS447
---
---
[[Convolutional neural networks]]
![[{613FF030-D5F2-4A42-BDE4-CFB3979F3E34}.png]]
-  CNNs are a standard architecture for image data
- CNNs are inspired by receptive fields in the visual cortex: Individual neurons respond to small regions of the visual field
- Neurons in deeper layers respond to larger regions
- Neurons in the same layer share the same weights
- This parameter tying allows CNNs to handle variable size inputs with a fixed number of parameters
CNNs can be used as input to fully connected nets
- In NLP, CNNs are used mainly for classification 
## 2D CNNs for images
---
![[{B8444F48-26FC-4062-BF0C-44A5DBAE500E}.png]]
We can apply these patches to all $N$x$N$ patches in the input image, but this shrinks the matrix size 
![[{78047A9B-F2E2-483C-AB7F-1C516509457B}.png]]
Convolutional layers are typically followed by ReLus
![[{6313B5F8-346E-4623-AA73-B4480D849617}.png]]
![[{BFCDE06D-F43F-41F1-A04D-2702FC6D58FC}.png]]
![[{31451F0F-8C4A-406E-8F0D-109B2A938B66}.png]]
![[{E56AF73B-BBCE-4211-805D-8A4430AA68C4}.png]]
![[{88E4CB74-A3D0-48ED-888E-F8000304540B}.png]]
![[{3359C5ED-F06B-47F2-8ED1-A25E3164B08D}.png]]
![[{40BEC95C-B021-4411-ABF8-1BBCAE04D0E7}.png]]

## 1D CNNs for text
---
![[{1519A85D-0817-45FD-B86C-BD49DDE8917E}.png]]
Filter size now specifies the N-gram size and stride how we skip around and what N-grams we will select
![[{C13B3876-61AB-49B7-ABCE-AE362D809B77}.png]]
![[{4154BC5A-F56D-4307-9401-11AB65E07A38}.png]]
