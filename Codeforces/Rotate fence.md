![[Pasted image 20230830002118.png]]

```kotlin
f = readInts()
nf = Array(5) { 0 }
```

# $O(n^2)$ approach
Make new array and increment nf[i], where i in range(0, nf[i]).

# $O(n)$ approach
Not my
Start from end and add i to nf till nf.size < f[i].
nf.size represents horizontal distance and we compare it with f[i] because height in f[i] with become horizontal, so f[i] is telling horizontal reach.

```kotlin
n = readInt()
f = readInts()
nf = mutableListOf<Int>

if (f[0] != n) {
	return
}

for (i in n - 1 downTo 0) {
	while (nf.size < f[i]) {
		nf.add(i + 1)
	}
}
```