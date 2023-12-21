#undirected 
#dfs 
#incomplete_reason
There is a cycle in graph if a back edge is present in the graph.
Back edge is an edge that indirectly joins a node to itself.

If we are on node $u$ and let $v$ be an adjacent of $u$.
If $v$ is already visited and it is not the parent of $u$ then graph has cycle.

Parent is from which node we came to $u$, if $v$ is not parent of $u$ then some other node is; but how $v$ is already visited then?
It can be when $v$ is connect to the parent of $u$ some how, it leads to formation of cycle. Which I don't understand how.

```java
public static boolean cycle(HashMap<Integer, ArrayList<Integer>> adjList, int n) {
	boolean[] visited = new boolean[n];

	for (int i = 0; i < n; i++) {
		if (!visited[i]) {
			if (find(adjList, visited, -1, i)) {
				return true;
			}
		}
	}

	return false;
}

private static boolean find(HashMap<Integer, ArrayList<Integer>> adjList, boolean[] visited, int parent, int cur) {
	visited[cur] = true;

	if (!adjList.containsKey(cur)) {
		return false;
	}

	for (int next : adjList.get(cur)) {
		if (!visited[next]) {
			if (find(adjList, visited, cur, next)) {
				return true;
			}
		}
		else if (parent != next) {
			return true;
		}
	}

	return false;
}
```