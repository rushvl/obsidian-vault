---
id: Knapsack Problem
aliases: []
tags: []
---

# Knapsack Problems

There are 3 types:

- Fractional Knapsack
- O/1 Knapsack
- Unbounded Knapsack

## Solving

Base condition:

- wt array size 0
- weight left in knapsack 0

```cpp
int knapsack(int wt[], int val[], int w, int n) {
  if(n==0 || w==0) return 0;

  if(wt[n-1]<=w) 
  return max(val[n-1]+knapsack(wt,val,w-wt[n-1],n-1), knapsack(wt,val,w,n-1));

  else if (wt[n-1]>>w);
  return knapsack(wt,val,w,n-1);
}
```

### Memoization Optimization

`knapsack(wt[],val[],w,n)` -> w and n are the changing inputs

```cpp
int t[n+1][w+1]; //or set matrix sizes according to constraints 
memset(t,-1,sizeof(t)); // initialize t with -1

int knapsack(int wt[],int val[],int w, int n) {
  if(n==0 || w==0) return 0;
  if(t[n][w]!=-1) return t[n][w];

  if(wt[n-1]<=w) 
  ts[n][w] = return max(val[n-1]+knapsack(wt,val,w-wt[n-1],n-1), knapsack(wt,val,w,n-1));

  else if (wt[n-1]>>w)
  return t[n][w] = knapsack(wt,val,w,n-1);
}
```

### Top Down Approach

Replace (n,w) with (i,j) and map the recursive call to array form.

```cpp
for(int i=1;i<n+1;i++) {
  for(int j=1; j<w+1;j++) {
    if(i===0 || j==0) t[i][j]=0;

    if(wt[i-1]<=j)
    t[i][j] = max(val[i-1]+t[i-1][j-wt[i-1]],t[i-1][j]);

    else 
    t[i][j] = t[i-1][j];
  }
}
```
