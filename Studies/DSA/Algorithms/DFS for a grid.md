
Example of a grid:

| 1   | 0   | 0   |
| --- | --- | --- |
| 0   | 1   | 1   |
| 1   | 1   | 1   |


```cpp
const int N = 1e5+10

void dfs(int i, int j, vector<vector<int>> &grid) {
	int n = image.size(); // number of rows = columns ka size
	int m = image[0].size(); // number of columns = row ka size
	if(i<0 || j<0) return;
	if(i>=n || j>=m) return;
	
	dfs(i-1,j);
	dfs(i+1,j);
	dfs(i,j-1);
	dfs(i,j+1);
}
```
