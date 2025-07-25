
# DFS Approach

Directed [[Graph]]
Uses stack

```cpp
void dfs(int node, int vis[], stack<int> &st,vector<int> adj[]) {
	vis[node] = 1;
	for (auto it : adj[node]) {
		if (!vis[it]) dfs(it, vis, st, adj);
	}
	st.push(node);
}

vector<int> topoSort(int V, vector<int> adj[])
{
	int vis[V] = {0};
	stack<int> st;
	for (int i = 0; i < V; i++) {
		if (!vis[i]) {
			dfs(i, vis, st, adj);
		}
	}

	vector<int> ans;
	while (!st.empty()) {
		ans.push_back(st.top());
		st.pop();
	}
	return ans;
};
```

# Kahn's Algorithm

Directed [[Graph]]/[[Tree]]
Graph traversal in which node v is visited only after all its dependencies are visited.

```cpp
vector<int> ar[100];
vector<int> res;
int in[100];

void kahn(int n) {
	queue<int> q;
	for(int i=1; i<=n; i++) 
		if(in[i]==0) q.push(i);
		
	while(!q.empty()) {
		int curr = q.front();
		q.pop();
		res.push_back(curr);
		for(int node: ar[curr]) {
			in[node]--;
			if(in[node]==0)
				q.push(node);
		}
	}
	
	cout << "Toposort : ";
	for(int node: res) cout<<node<<" ";
}

int main() {
	int n,m,x,y;
	cin>>n>>m;
	
	for(int i=1;i<=m;i++) {
		cin>>x>>y;
		ar[x].push_back(y);
		in[y]++;
	}
	
	kahn(n);
}
```