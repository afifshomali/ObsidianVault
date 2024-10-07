---
tags:
  - CS447
---
---
 FeedForward nets can only handle inputs and outputs that have a fixed size
![[{CA47C1DE-F4EF-4268-B998-6B78B5B3A092}.png]]
![[{3A19B832-354F-4F8F-8A9B-13091B89895E}.png]]
## RNN Basics
---
![[{FAF9E50F-8CD4-4DD5-AEEC-DD7D63D55289}.png]]
- Full connected between hidden layers
![[{8509F049-6A97-448D-8A07-76D3240D1107}.png]]
![[{A90838B9-6317-4363-9806-A6894AAA20F3}.png]]
![[{D30C8C92-785A-400F-BFC2-25BAEE4C7FAE}.png]]
## RNNs for Language Modeling
---
![[{F3FB1D1B-3C7F-4001-9998-B1BB6321FAE1}.png]]
![[{11633D0E-2E8D-4262-A125-DF7C0735266C}.png]]
![[{4BBCE7E4-41E5-4E9F-A8B5-6B1F0DCE7D52}.png]]
![[{4DBB538E-2F3D-476B-99AE-A63C34A05EB7}.png]]
![[{96F99BE4-434F-4E2F-BB98-B21F8DE267C9}.png]]

## Encoder-Decoder (seq2seq) Model
---
![[{B4B5724A-8E2F-4BD2-BDC0-25821772D844}.png]]
![[{501BA81D-7BC7-4618-94CA-200B84ADF340}.png]]
![[{0129779C-D2C4-41AC-933C-D5FBFEAAB6B0}.png]]
![[{5722B00E-54AD-4BDC-9A99-5510876CA1B2}.png]]
Extension: add a CRF layer to capture dependencies among labels of adjacent tokens
![[{6530BA65-B86F-4F6E-B99B-DDF948C8947C} 1.png]]
