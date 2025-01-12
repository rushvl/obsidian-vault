## Algorithm

```
vector<bool> isPrime(N,1);
isPrime[0] = isPrime[1] = false;
for(int i = 2; i<N; i++) {
	if(isPrime[i]==true) {
		for(int j = 2*i; j<n; j+=i) {
			isPrime[j] = false;
		}
	}
}
```

**Complexity**: n\*log(log(n))
Gets all the primes from 1 to N and stores them in the vector. Most optimal way to get primes.