If these points are removed from a [[Graph]] the number of [[Connected Components]] increase.

### Some Characteristics
- End points of a [[Bridge]] will be an articulation point if that node has degree of at least 2.
- It is not necessary for an articulation point to be an end point of a [[Bridge]].
- Finding bridges algorithm cannot be used to find articulation point.

For root we count the number of children(subtrees). For other nodes its the same lowtime\<intime check.

If we are counting the number of articulation points, use a set and push the articulation nodes into the set because the same node can be found as articulation points by different subtrees.

$visited[to] = false$  - the edge is part of DFS tree;
$visited[to] = true$  &&  - $to \neq parent$  - the edge is back edge to one of the ancestors;
$to = parent$  - the edge leads back to parent in DFS tree.

```cpp
int n; // number of nodes
vector<vector<int>> adj; // adjacency list of graph

vector<bool> visited;
vector<int> tin, low;
int timer;

//p=-1 means that the node is the root
void dfs(int v, int p = -1) {
    visited[v] = true;
    tin[v] = low[v] = timer++;
    int children=0;
    for (int to : adj[v]) {
        if (to == p) continue;
        if (visited[to]) {
            low[v] = min(low[v], tin[to]);
        } else {
            dfs(to, v);
            low[v] = min(low[v], low[to]);
            if (low[to] >= tin[v] && p!=-1)
                IS_CUTPOINT(v);
            ++children;
        }
    }
    if(p == -1 && children > 1)
        IS_CUTPOINT(v);
}

void find_cutpoints() {
    timer = 0;
    visited.assign(n, false);
    tin.assign(n, -1);
    low.assign(n, -1);
    for (int i = 0; i < n; ++i) {
        if (!visited[i])
            dfs (i);
    }
}
```