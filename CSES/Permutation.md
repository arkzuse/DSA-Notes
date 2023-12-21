#implementation

Print numbers from $1..n$ such that adjacent numbers don't have difference of 1.

https://cses.fi/problemset/task/1070/

Print even numbers then odd numbers.


```python
n = int(input())

if n == 1:
	print(1)
elif n < 4:
	print("NO SOLUTION")
else:
	print(*range(2, n + 1, 2), *range(1, n + 1, 2), sep=" ")
```