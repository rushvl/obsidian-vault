A tree is basically a graph with **no cycles**.
- Nodes = n
- Edges = n-1

### Terminologies
Root: Start of the tree.
Subtrees: A branch of the tree(left subtree, right subtree etc).
Leaf Node: Nodes with no child.
Depth of a node: Distance of node from root.
Height: Distance of furthest leaf(child) from node.
Lowest Common Ancestor(LCA): The first common parent of two nodes going up.
Diameter: Longest path between any two nodes in a tree.
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
4. [[DFS for a grid]]
5. [[Diameter of a tree]]
6. [[SSSP DFS]]
7. [[Size of subtree]]
8. [[SSSP BFS]]




