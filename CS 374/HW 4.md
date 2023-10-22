---
tags:
---
---
Source: https://www.geeksforgeeks.org/find-first-and-last-positions-of-an-element-in-a-sorted-array/ 

binSearchFirstOccurence(A[0...n-1], x, L, R):
	if (R>= L):
		mid = L + (R - L) / 2
		if ((mid == 0 OR x > A[mid - 1]) AND A[mid] == x):
			return mid
		else if (x > A[mid]):
			return binSearchFirstOccurence(A, x, (mid + 1), R)
		else:
			return binSearchFirstOccurence(A, x,  L, (mid - 1))
	else:
		return -1

binSearchLastOccurence(A[0..n-1], x, L, R):
	if (R >= L):
		mid = L + (R - L) / 2
		if ((mid == (n - 1) OR  x < A[mid + 1]) AND A[mid] == x):
			return mid
		else if (x < A[mid]):
			return binSearchLastOccurence(A, x, L, (mid - 1))
		else:
			return binSearchLastOccurence(A, x, (mid + 1), R)
	else:
		return -1

numOccurences(A[0..n-1], x):
	first_idx = binSearchFirstOccurence(A, x, 0, n-1) 
	last_idx = binSearchLastOccurence(A, x, 0, n-1)
	if (first_idx != -1 AND last_idx != -1):
		return last_idx - first_idx
	else if (first_idx == -1 AND last_idx == -1):
		return 0
	else:
		return 1

---
---
