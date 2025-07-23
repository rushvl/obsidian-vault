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

## Grid

Example of a grid:

| 1   | 0   | 0   |
| --- | --- | --- |
| 0   | 1   | 1   |
| 1   | 1   | 1   |


```cpp
const int N = 1e5+10;
int vis[N][N];

int dx[] = {-1,0,1,0};
int dy[] = {0,1,0,-1};

void dfs(int x, int y, vector<vector<int>> &grid) {
	int n = grid.size(); // number of rows = columns ka size
	int m = grid[0].size(); // number of columns = row ka size
	if(x<0 || y<0) return;
	if(x>=n || y>=m) return;
	if(vis[x][y]) return;
	
	vis[x][y] = 1;
	
	for(int i=0;i<4;i++)
		dfs(x+dx[i],y+dy[i],grid);
}
```
