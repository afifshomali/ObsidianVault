---
tags: CS374, CS374/Midterm1
---
---
If $x$ & $y$ are string then $xy$ denotes their concatenation

Concatenation is defined recursively/Inductively:
	- $xy = y$ if $x = \epsilon$
	- $xy = a(wy)$ if $x = aw$

Can put dot between $x$ and $y$ or just write $xy$

Concatenation is Associative so:
	$(uv)w = u(vw) = uvw$

Concatenation is **NOT** communitive so:
	$uv$ isn't always equal to $vu$

The identity element is the empty string $\epsilon$ :
	$\epsilon \cdot u = u \cdot \epsilon = u$
