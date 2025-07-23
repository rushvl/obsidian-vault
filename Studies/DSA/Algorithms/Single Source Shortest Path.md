
# DFS

Single source shortest path
Gives the shortest distance of every other node from the source node
Algorithm only for [[Tree]]
Uses [[DFS]]
https://www.youtube.com/watch?v=HCSTku0-Eqg

example problem:
```cpp
vector<int> ar[1000];
int vis[1000], dist[1000];

void dfs(int node, int d) {
	vis[node] = 1;
	dist[node] = d;
	for(int child : ar[node]) {
		if(vis[child]==0) dfs(child, dist[node]+1);
	}
}


int main() {
	int n, q, a, b;
	cin>>n;
	//creating the adjacency list
	for(int i=1;i<=n-1; i++) {
		cin >> a >> b;
		ar[a].push_back(b);
		ar[b].push_back(a);
	}
	dfs(1,0) // source is 1 and distance from 1 to 1 is zero

	cin >> q;
	int ans = -1, min_dist = INT_MAX;
	while(q--) {
		int girl_city;
		cin >> girl_city;
		if(dist[girl_city] < min_dist)
			min_dist = dist[girl_city], ans = girl_city;

		else if(dist[girl_city] == min_dist && girl_city<ans) ans = girl_city;
	}

	cout << ans;
}
```


# BFS

Uses a queue, distance array.

```cpp
vector<int> ar[10001];
int vis[10001], dist[10001];


void BFS(int src) {
	queue<int> q;
	q.push(src);
	vis[src] = 1;
	dist[src] = 0;

	while(!q.empty()) {
		int curr = q.front();
		q.pop();

		for(int child : arr[curr]) {
			if(vis[child]==0) {
				q.push(child);
				dist[child] = dist[curr] + 1;
				vis[child] = 1;
			}	
		}
	}
}


int main(){
	int t,n,m,a,b;
	cin >> t;
	while(t--) {
		cin>>n>>m;
		for(int i=1; i<=n; i++) ar[i].clear(), vis[i]=0;

		while(m--) cin>>a>>b , ar[a].push_back(b), ar[b].push_back(a);

		BFS(1);
 	}
}
```