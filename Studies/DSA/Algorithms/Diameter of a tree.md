https://www.youtube.com/watch?v=9goVqAvYEbI&list=PL5DyztRVgtRVLwNWS7Rpp4qzVVHJalt22&index=15
Longest path that exists in a tree
Using [[Single Source Shortest Path]]

```cpp
vi ar[10001];
int vis[10001];
int maxD, maxNode;


void dfs(int node, int d) {
	vis[node] = 1;
	if(d>maxD) maxD = d, maxNode = node;
	if(vis[child]==0) dfs(child, d+1);
}


int main() {
	//adjacecncy list input
	
	//end
	maxD = -1;
	dfs(1,0); //goes to one extrema of diameter

	for(int i = 0; i<n; i++) vis[i] = 0;
	maxD = -1;
	dfs(maxNode,0); //one extrema to other
}
```