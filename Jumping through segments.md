#codeforces 

[D. Jumping Through Segments](https://codeforces.com/contest/1907/problem/D)

To check whether it is possible to pass level with k, we maintain a segment in which we can find ourselves. After each move, it expands by k in both directions and is reduced to the intersection with the segments where the player must be at that move.

```python
def check(k):
	l, r = 0, 0

	for e in seg:
		l = max(l - k, e[0])
		r = min(r + k, e[1])

		if l > r:
			return False

	return True
```

