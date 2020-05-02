#Depth First Search (DFS)

[home](/)

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
