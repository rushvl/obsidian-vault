```cpp
const int N = 1e5+10;
vector<int> g[N];
bool vis[N];

vector<vector<int>> cc;
vector<int> current_cc;

void dfs(int vertex) {
	//Take action on vertex after entering vertex
	vis[vertex] = true;
	current_cc.push_back(vertex); //modification
	for(int child: g[vertex]) {
		if(vis[child]) continue;
		//Take action on child before entering child node
		dfs(child);
		//Take action on child after exiting child node
	}
	//Take action on vertex before exiting vertex
}	

int main() {
	int n, e;
	for(int i = 0; i<e; i++) {
		int x, y;
		cin >> x >> y;
		g[x].push_back(y);
		g[y].push_back(x);
	}
	int ct = 0;
	for(int i = 1; i<=n; i++) {
		if(vis[i]) continue;
		current_cc.clear();
		dfs(i);
		cc.push_back(current_cc);
		ct++;
	}
}
```

## Grid

```cpp
int cnt = 0;
for(int i=1;i<=N;i++) {
	for(int j=1;j<=M;j++) {
		if(ar[i][j]==1 && vis[i][j]==false) {
			cnt++;
			dfs(i,j);
		}
	}

}
```