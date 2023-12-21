#string

```java
String merge(String a, String b) {
	if (b.contains(a)) {
		return b;
	}

	for (int i = 0; i < a.length(); i++) {
		String s1 = a.substring(i);

		if (b.length() < s1.length()) {
			continue;
		}

		String s2 = b.substring(0, s1.length());

		if (s1.equals(s2)) {
			return a + b.substring(s1.length());
		}
	}

	return a + b;
}
```

This should be ran two times `merge(a, b)` and `merge(b, a)`