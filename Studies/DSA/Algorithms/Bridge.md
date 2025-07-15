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

### Lowtime meaning:

Imagine a building with rooms connected by hallways:

- Each **room** is a node in the graph.
- You enter rooms in a certain order during your exploration (DFS). The order you enter a room is its **discovery time (`tin`)**.
- Initially, when you enter a room vv, the earliest room you can reach from vv is just vv itself (you’re inside it).
- This is why **`low[v] = tin[v]`** at the start: you only know about the current room.
- As you explore hallways (edges) to other rooms:
    - If you find a **shortcut (back edge)** to an earlier room (an ancestor), you update your earliest reachable room to that earlier room.
    - If your friends in the rooms you visit can reach an earlier room, you update your earliest reachable room accordingly.

You look at the intime of the earliest node the current node can visit, via a different path than the one that connects it with its parent.