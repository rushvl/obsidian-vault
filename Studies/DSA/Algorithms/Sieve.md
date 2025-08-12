---
id: Sieve
aliases: []
tags: []
---

- [ ] ## Algorithm

```cpp
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

## Variations

### Highest Prime

```cpp
vector<int> hp(N);
vector<bool> isPrime(N,1);
isPrime[0] = isPrime[1] = false;
for(int i = 2; i<N; i++) {
 if(isPrime[i]==true) {
  for(int j = 2*i; j<n; j+=i) {
   isPrime[j] = false;
   hp[j] = i;
  }
 }
}
```

### Lowest Prime

```cpp
vector<int> lp(N);
vector<bool> isPrime(N,1);
isPrime[0] = isPrime[1] = false;
for(int i = 2; i<N; i++) {
 if(isPrime[i]==true) {
  for(int j = 2*i; j<n; j+=i) {
   isPrime[j] = false;
   if(lp[j]==0) lp[j] = i;
  }
 }
}
```

### Prime Factorization

```cpp
int num;
cin >> num;
map<int,int> prime_factors;

while(num>1) {
 int prime_factor = hp[num];
 while(num%prime_factor==0) {
  num/=prime_factor;
  primefactors[prime_factor]++;
 }
}
```
