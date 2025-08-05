
Create a tree out of the graph with the sum of weights minimum by removing edges.

## Kruskal's Algorithm

Greedy based algorithm.
Uses [[Disjoint Set Union]]
Sort in ascending order by edge weights and then greedily connect.

```cpp
struct edge {
	int a;
	int b;
	int w;
};

edge ar[10000];
int par[10000];

bool comp(edge a, edge b) {
	if(a.w<b.w) return true;
	return false;
}

//dsu find function with path compression
int find(int a) {
	if(par[a]==-1) return a;
	return par[a] = find(par[a]);
}

void merge(int a, int b) {
	par[a] = b;
}

int main() {
	int n,m,a,b,w;
	cin>>n>>m;
	
	for(int i=1;i<=n;i++) par[i]=-1;
	
	for(int i=0li<m;i++) {
		cin>>ar[i].a>>ar[i].b>>ar[i].w;
	}
	
	sort(ar, ar+m, comp);
	
	for(int i=0;i<m;i++) {
		a = find(ar[i].a);
		b = find(ar[i].b);
		
		if(a!=b) { // if aprents are not the same, i.e different set
			sum += ar[i].w;
			merge(a , b);
		}
	}
}
```