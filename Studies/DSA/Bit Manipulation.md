### Get number of set bits:

```cpp
int n;
int set_bits = __builtin_popcount(n);
```

### Count bits in a number

```cpp
int n;
int count = (int)log2(n)+1;
```

### Subset Generation

- Let there be an array A = \[a1, a2, a3, ...]
- If we have a binary number 10111 - it denotes that we will take the 0th,1st, 2nd and 4th element in the subset
- In this way, if we take the binary numbers from 0 to 2^(A.size()), we get all possible subsets.

```cpp
vector<vector<int>> subsets(vector<int> &nums) {
	int n = nums.size();
	int subset_ct = (1<<n);
	vector<vector<int>> subsets;
	for(int mask = 0; i<subset_ct; i++) {
		vector<int> subset;
		for(int i = 0; i<n; i++) {
			if((mask & (1<<i))!=0) {//check if bit is set
				subset.push_back(nums[i]);
			}
		}
		subsets.push_back(subset);		
	}
}
```
