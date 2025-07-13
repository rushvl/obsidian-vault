Used for  problems, where given 2 nodes, find whether one node lies in the subtree of another node or not
https://www.youtube.com/watch?v=4VCqVBnUrDY
[[Tree]] algorithm

```cpp
int timer = 1;
bool dfs(int v) {
	vis[v]=1;
	In[v] timer++;
	for(int child: ar[v]) {
		if(vis[child]==0) {
			dfs(child);
		}
	}
	Out[v] = timer++;
}
```

Intime(node)>intime(root)
outtime(node)<outtime(root)

If these two conditions are fulfilled then the node lies in the subtree of the root.