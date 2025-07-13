Algorithm for [[Tree]],[[Graph]]
Start with the root -> go to any child -> go full depth of that child
We keep a **visited** array, which stores the visited nodes. This can be avoided for [[Tree]], needed for [[Graph]].
[[Graph#Adjacency List]]


```cpp
const int N = 1e5+10;
vector<int> g[N];
bool vis[N];

void dfs(int vertex) {
	//Take action on vertex after entering vertex
	vis[vertex] = true;
	for(int child: g[vertex]) {
		if(vis[child]) continue;
		//Take action on child before entering child node
		dfs(child);
		//Take action on child after exiting child node
	}
	//Take action on vertex before exiting vertex
}	
```


Time complexity: O(V+E)