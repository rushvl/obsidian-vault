
## Terminologies
Undirected Graphs: You can travel either way between nodes.
Directed Graphs: A graph with a direction, at least one edge is unidirectional.
Strongly Connected Graph: You can go to vertex a to vertex for all such vertexes in the graph.

## Code Representation

### Adjacency Matrix
Vertices = N, Edges = M
We create a matrix of V\*V called A
$$
A[i][j]=
\begin{cases}
1 &if \ i \ is \ connected \ to \ j\\
0 &i=j,\ or\ otherwise
\end{cases}
$$

`a[i][j] = wt`, for weighted graph

```cpp
const int N = 1e3+10;
int graph[N][N];

int main() {
	int n,m;
	cin >> n >> m;
	for(int i = 0; i<m; i++) {
		int v1,v2;
		cin >> v1 >> v2;
		graph[v1][v2] = 1;
		graph[v2][v1] = 1;
	}
	// O(N^2) space complexity
	// N<=10^4
}
```

Downsides
- O(N^2) space complexity
Upsides
- Finds whether two nodes are connected in O(1).
### Adjacency List

Space complexity = O(V+E)

```cpp
int N = 1e3; // N<=10^3
vector<pair<int,int>> graph[N];
int main() {
	int n,m;
	cin >> n >> m;
	for(int i = 0; i<m; i++) {
		int v1,v2,wt;
		cin >> v1 >> v2 >> wt;
		graph[v1].push_back({v2,wt});
		graph[v2].push_back({v1,wt});
	}
}
```


## Algorithms

 1. [[DFS]]
 2. [[Connected Components]]
 3. [[Find Cycle in Graph,Tree]]
 4. 


