[home](/)

# Union Find
Union find is really really ***really*** useful. It finds the set a node belongs to on O(log(n)) (?? or O(1) or O(a(n))). It does this by assigning a parent to each set. By doing this, we can do getparent(a) == getparent(b) to see if node a and node b belongs to the same set.

## Optimizations
- Making the distance from each node to their parents log n
- Cord compression, makes it amortized O(1) (?)

## Minimal example using cord compression

```c++
// 0-based arrays

#define MAX_N 100000

int parents[MAX_N];

void intialize() {
	for (int i = 0; i < N; ++i) {
		parents[i] = i;
	}
}

int get(int i) {
	return i == parents[i] ? i : parents[i] = get(parents[i]);
}
```
