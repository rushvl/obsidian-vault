A bridge is defined as an edge which when removed makes graph disconnected. Or more precisely it increases the number of connected components.

Forward edges are the only candidates for bridges. 

We use something similar to [[In Out time of nodes]]. We use in and low(the intime of lowest ancestor that can be reached directly by the current node).

```cpp
vector<int> ar[100];
int in[101], low[101], vis[101];

void dfs(int node, int par) {
	vis[node] = 1;
	in[node] = low[node] = timer;
	timer++;
	
	for(int child: ar[node]) {
		if(child==par) continue; //already visited, since its the parent, cant update lowtime either
		
		if(vis[child]==1) {
			//edge node-child is a backedge
			low[node] = min(low[node], in[child]);
			
		} 
		else {
			//edge node-child is a forward edge
			dfs(child,node);
			
			//if low time of child is > intime of node that means that the child is connected to the ancestore of node
			if(low[child]>in[node])
				cout<<node<<" - "<<child;
		}
		
		
	}
}


int main() {
	int n,m,x,y;
	cin>>n>>m;
	
	while(m--)
		cin>>x>>y, ar[x].push_back(y), ar[y].push_back(x);
	
	dfs(1,-1)
}
```