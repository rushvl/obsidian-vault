## Algorithm
```
int lo = 0, hi = n-1;
int mid;
while(hi-lo>1) {
	int mid = (hi+lo)/2;
	if(v[mid]<to_find) {
		lo = mid+1;
	}
	else {
		hi = mid;
	}
}
```

## Description

**Complexity**: log(n)

It needs a **monotonic** series.
Search space - range in which we want to conduct binary search
condition in while loop: `while(high-low > 1)`

## Interesting Problems
