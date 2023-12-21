
## Variations

### Same difference
#cp
You are given an array a of n integers. Count the number of pairs of indices $(i , j)$ such that $i < j$ and $a_j − a_i = j − i$.

$$a_j - j = a_i - i$$

```kotlin
// a is array
val map = mutableMapOf<Long, Long>
var ans = 0

for (i in a.indices) {
	val x = a[i] - i

	if (map.containsKey(x)) {
		ans += map[x]!!
	}
	
	map[x] = map.getOrDefault(x, 0) + 1
}
```

Store count of all previous $a_i - i$ in map if same values comes then add count to ans, then increment count in map.