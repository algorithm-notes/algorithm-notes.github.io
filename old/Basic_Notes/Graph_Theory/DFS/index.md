# Depth First Search (DFS)

[home](/)

![](/diagram1.gif)

## Minimal example
```cpp
void dfs(int i) {
    seen[i] = true;
    for (int j : adj[i]) {
        if(!seen[j]) {
            dfs(j);
        }
    }
}
```

This DFS idea is really *really* **really** common in graph theory. As often it is the basis of more complex algorithms.
