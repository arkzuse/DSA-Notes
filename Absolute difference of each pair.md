	https://codeforces.com/problemset/problem/1808/B

# simple method
Simple method is to use two for loop
Time complexity: $\Theta(n^2)$
Space complexity: $\Theta(1)$

``` c++
int sum = 0;
for (int i = 0; i < n; i++) {
	for (int j = i + 1; j < n; j++) {
			 sum += abs(a[i] - a[j]);
	}
}
```


# time optimised
Sort the array because then left side of elements are smaller than it and right elements greater.
Calculate prefix sum and suffix sum.
Then result is sum of $suffix(i) - prefix(i)$.

Time complexity: $\Theta(nlogn)$
Space complexity: $\Theta(n)$

# time and space optimise
Sorting is still necessary.
Last element will never be subtracted but will be added $n - 1$ times similarly first element will be subtracted $n - 1$ times but not added, similarly $i$th element will be added $i$ times and subtracted $n - 1 - i$ times.

$a[i] \times i - a[i] \times (n - 1 - i)$
$a[i] \times (2 \times i + 1 - n)$

```java
int sum = 0;

for (int i = 0; i < n; i++) {
	sum += a[i] * (2 * i + 1 - n);
}

```


Time complexity: $\Theta(nlogn)$
Space complexity: $\Theta(1)$