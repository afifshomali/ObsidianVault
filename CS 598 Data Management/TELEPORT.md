---
tags:
  - CS598
---
---

## Overview/ High level ideas/ Background
---
- Compute (including memory) disaggregation is common today
	- Ex: Presto, Spark, Snowflake, BigQuery
- Moving data between compute pool & memory pool is too slow
- Push compute to the memory pool
	- This comes with a bunch of technical challenges

**Problems of Current Cloud Data Centers:**
- Coarse Grained resources allocation
- Coarse Grained data center expansion
- Coarse Grained failures between hardware resources
![[{8AE47328-00D8-4760-B5FB-7A632BBC8FD8}.png]]

**Future Clouds are Disaggregated**
- Disaggregated data centers (DDCs) mean separate compute, memory & storage into resource pools that are connected by a fast network
![[{1436F668-E715-4736-8135-4C502E97448C} 1.png]]
**Data Processing in DDCs**
![[{4BB3EFDA-1026-4E49-B547-C2AB60095402}.png]]
![[{74E08892-0C15-4503-93D5-D85793D98E45}.png]]

**Performance, Oppurtunity & limitation:**
![[{11320763-F91B-48F9-979A-BE88C2255FC5}.png]]
![[{76151773-18D9-452A-BFBC-B93445BFAFE3}.png]]

## TELEPORT
---
**Motivation:**
- Brining Data to compute pool incurs overhead
![[{D61B8FF8-02B7-4A7D-9164-B41CA3167309}.png]]
![[{5970F557-84DA-4ACD-B423-5A9D78A4B00D}.png]]
![[{CDEA4DC7-A327-4C86-854D-4E6683AECFF1}.png]]

**Overview:**
- Compute pushdown framework for memory disaggregation
![[{26945B23-00C9-4076-924D-8558B35C3159}.png]]
![[{2B525ACE-42B4-4264-9977-3CE7C3B6DD79}.png]]
![[{074D89A5-2541-494C-92E8-8D23F3CABB82}.png]]
![[{6EE6765C-17B1-4D34-9585-D01573EA878D}.png]]

**Data Synchronization:**
- Memory consistent between compute pool & memory pool
- Inconsistent time points: before pushdown, after pushdown, during pushdown
- Without proper synchronization, pushdown may be executed incorrectly
- During pushdown refers to if multiple clients make a pushdown request that try to access the same part of the data 
![[{1BAB7495-5E9A-4312-9129-337F98D03AB2}.png]]

The **baseline approach** evicts all local pages & push down all threads in the same process.
But this comes with performance issues since not all compute local pages are accessed in the pushdown & we overwhelm the memory pools limited compute resources.

Instead use **On-Demand Coherence Protocol**, where we synchronize pages only when they are needed, and make sure it is invariant as in only one writable copy of a page between pools at any moment.

This means there are only 3 possible page states:
- Writable and only in the compute pool
- Writable and only in the memory pool
- Read only and anywhere
![[{E626D3F5-38E3-4E68-9771-097AFACA1198}.png]]

## Evaluation Results
---
![[{D9F4BEA9-C769-459A-886C-05DFEC962F37}.png]]
![[{0A398796-6627-4632-9E5A-E866CA0692AF}.png]]
![[{F16743EE-E467-49AE-810E-FFD2D85768DF}.png]]
![[{B050CE5A-7140-4F39-A20F-E945DDF07106}.png]]
