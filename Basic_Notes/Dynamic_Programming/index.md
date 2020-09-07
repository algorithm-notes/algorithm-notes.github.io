# Dynamic Programming (DP)
[home](/)
## Introduction
Dynamic Programming is just a fancy name for "using previous computed results to compute more stuff". It trades memory for time.

## Minimal example (Fibonacci)
It's up to you to decide the performance difference!
### Without DP
```cpp
int fib(int n) {
    if(n == 0) return 1;
    return fib(n - 1) + fib(n - 2);
}
```
### With DP
```cpp
#define MAX 1000000 /* your choice, in your call fib(n), n < MAX */
int cache[MAX];
// in c/c++, global arrays are initialized with all 0s
int fib(int n) {
    if(n == 0) return 1;
    if(cache[n] != 0) return cache[n];
    return cache[n] = fib(n - 1) + fib(n - 2);
}
```

[this problem on orac](http://orac.amt.edu.au/cgi-bin/train/problem.pl?set=aio19&problemid=1081) can be solved using DP and basic graph theory

## Pages under DP
- [Knapsack](/Basic_Notes/Dynamic_Programming/Knapsack)
