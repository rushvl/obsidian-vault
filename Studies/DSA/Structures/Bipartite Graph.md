A [[Graph]] is **bipartite** if the nodes can be partitioned into two independent sets `A` and `B` such that **every** edge in the graph connects a node in set `A` and a node in set `B`.

Test for Bipartite Graph:

```cpp
bool dfs(int v, int c) {
	vis[v] = 1; // visited array
	col[v] = c; // color array, c can be 1 or 0
	for(int child: ar[v]) {
		if(vis[child] == 0) {
			if(dfs(child, c ^ 1) == false) return false; // c^1 = inversion with XOR
			else if(col[v]==col[child]) return false;
		}
	}
	return true;
}
```