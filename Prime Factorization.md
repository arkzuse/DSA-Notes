#math 

If $a \times b = n$ both numbers have to be less than or equal to $\sqrt{n}$ 

In the loop if we go greater than $\sqrt{n}$ then 




```java
HashMap<Integer, Integer> primeFactors(int n) {
	HashMap<Integer, Integer> factors = new HashMap<Integer, Integer>();

	while (n % 2 == 0) {
		factor.put(2, factor.getOrDefault(2, 0) + 1);
		n /= 2;
	}

	for (int d = 3; d <= Math.sqrt(n); i += 2) {
		while (n % d == 0) {
			factor.put(d, factor.getOrDefault(d, 0) + 1);
		}
	}

	return factors;
}
```

