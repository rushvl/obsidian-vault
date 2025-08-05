
## Kosaraj's Algorithm

Used with directed [[Graph]]. 

**Condensation Graph**: A graph made with SCC of the original graph. This graph does not have any cycle.

A DAG has atleast one node with in-degree 0. The node with highest out time has in degree 0.

We find the node with highest out time(in degree 0) and run dfs on it in the transpose graph(out degree 0). This ensures that the dfs doesnt go out of that connected component(because out degree 0).

```cpp
vi ar[1001];
vi tr[1001];

vi order;
vi SCC;

int vis[N];

vector<int> order;
void dfs(int node) {
	vis[node] = 1;
	for(int child: ar[node]) {
		if(vis[child]==0) 
		dfs(child);
	}
	order.pb(node)
}

void dfs1(int node) {
	vis[node] = 1;
	for(int child : tr[node])
	if(vis[child]==0) dfs1(child);

	SCC.pb(node);
}

void solve() {
	int n,a,b,m;
	cin>>n>>m;
	for(int i=0;i<n;i++)
	ar[i].clear(), tr[i].clear(), vis[i]=0;
	
	order.clear();
	
	for(int i=0;i<m;i++) {
		cin>>a>>b;
		ar[a].pb(b);
		tr[b].pb(a);
	}
	
	for(int i=0;i<n;i++) 
	if(vis[i]==0) dfs(i);
	
	for(int i=0;i<n;i++) vis[i]=0;
	
	for(int i=0;i<n;i++) {
		if(vis[order[n-i]]==0) {
			SCC.clear();
			dfs1(order[n-i]);
		}
		for(int node: SCC)
			cout<<node<<" ";
		cout<<endl;
	}
}
```

## Tarjan's Algorithm

**Low link value**: For each node u, low-link value is defined as lowest id of node reachable from node u.
