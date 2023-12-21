#undirected
#dfs
#incomplete_reason 
Like in [[Cycle in undirected graphs|in undirected graph]] we can't pass parent of next node because *I don't understand why* we can't move in both directions; so if we can move  from $u$ to $v$ then it is not certain we can do reverse of that.

We have to keep a separate list of visited list of the path and check will going to adjacent nodes that if they are already in the path list.

```java
public static boolean cycle(HashMap<Integer, List<Integer>> adjList, int n) {
	boolean[] visited = new boolean[n];
	boolean[] path = new boolean[n];

	for (int i = 0; i < n; i++) {
		if (!visited[i]) {
			if (find(adjList, visited, path, i)) {
				return true;
			}
		}
	}

	return false;
}

public static boolean find(HashMap<Integer, List<Integer>> adjList, boolean[] visited, boolean[] path, int cur) {
	visited[cur] = true;

	if (!adjList.containsKey(cur)) {
		return false;
	}

	path[cur] = true;

	for (int next : adjList.get(cur)) {
		if (!visited[next]) {
			if (find(adjList, visited, path, next)) {
				return true;
			}
		}
		else if (path[next]) {
			return true;
		}
	}

	path[cur] = false;

	return false;
}
```