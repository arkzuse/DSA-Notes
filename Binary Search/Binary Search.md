# Finding x

$\min i : a[i] \ge x$ closest element to right, all elements greater or equal to x
$\max i : a[i] \le x$ closest element to left, all elements lesser or equal to x

`l = -1` and `r = n`
We assume there are $-\infty$ and $\infty$ at the ends to satisfy the invariant.
## Closest element to right
Invariant:
- $a[l] \lt x$
- $a[r] \ge x$

```
while (l + 1 < r) {
	m = (l + r) / 2
	
	if (a[m] < x) {
		l = m
	}
	else {
		r = m
	}
}

return r
```

## Closest element to left
Invariant:
- $a[l] \le x$
- $a[r] \gt x$

```
while (l + 1 < r) {
	m = (l + r) / 2

	if (a[m] <= x) {
		l = m
	}
	else {
		r = m
	}
}

return l
```