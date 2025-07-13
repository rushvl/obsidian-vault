```cpp
const int N = 1e5+10;
vector<int> g[N];
bool vis[N];

bool dfs(int vertex, int par) {
	//Take action on vertex after entering vertex
	vis[vertex] = true;
	bool isLoopExists = false;
	for(int child: g[vertex]) {
		if(vis[child] && child==par) continue;
		if(vis[child]) return true;
		//Take action on child before entering child node
		isLoopExists |= dfs(child,vertex);
		//Take action on child after exiting child node
	}
	//Take action on vertex before exiting vertex
	return isLoopExists;
}	


int main() {
	bool isLoopExists = false;
	for(int i = 1; i<=n; i++) {
		if(vis[i]) continue;
		if(dfs(i, 0)) {
			isLoopExists = true;
			break;
		}
	}
}
```
