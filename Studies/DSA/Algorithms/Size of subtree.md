
```cpp
int dfs(int node) {
	vis[node] = 1;
	int curr_size = 1; //minimum size of a subtree is one(the node itself)

	for(int child: ar[node])
		if(vis[child] == 0) {
			curr_size += dfs(child);
		}

	subSize[node] = curr_size;
	return curr_size;
}
```