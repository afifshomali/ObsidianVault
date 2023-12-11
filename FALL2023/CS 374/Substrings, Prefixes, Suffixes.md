---
tags: CS374, CS374/Midterm1
---
---

## Substrings:

$v$ is a substring of $w$ $\leftrightarrow$ there exists strings $x$, $y$ such that $w = xvy$

## Prefixes:

If $x = \epsilon$ then $v$ is a prefix of $w$

## Suffix:

If $y = \epsilon$ then $v$ is a suffix of $w$

## Subsequence:

A subsequence is not the same as a substring, it is a looser definition that just needs characters to appear in that order in the entire string, they don't have to appear next to each other in that order 

**Example:**

EE37 is a subsequence of ECE374B

In a string of length 6 there are at most $2^6$ sub-sequence, but distinct sub sequence are likely less than this.

It is $2^6$ because for each character, the char is either part of the subsequence or not part of it. Hence the 2 and we have a total of 6 chars/choices.




