Make - new node
Find - parent of group
union - a,b

```cpp

int parent[n];

void make(int v) {
	parent[v] = v;
}

void find(int v) {
	if(v==parent[v]) return v;
	return parent[v] = find(parent[v]);
}

void Union(int a, int b) { // union is a keyword so we use Union
	a = find(a);
	b = find(b);
	if(a!=b) {
		//union by size
		if(size[a]<size[b]) //join smaller tree to larger tree always
			swap(a,b);
		parent[b] = a;
	}
}

int main() {
	return 0;
}
```