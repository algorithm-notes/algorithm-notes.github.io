# Breath First Search (BFS)

[home](/)

![](/diagram1.gif)

## Minimal example
```cpp
void bfs(int i) {
    std::queue<int> q;
    q.push(i);
    seen[i] = true;
    while(!q.empty()) {
        int i = q.front();
        q.pop();
    
        for (int j : adj[i]) {
            if(!seen[j]) {
                seen[j] = true;
                q.push(j);
            }
        }
    }
}
```

BFS can be used to find the shortest path between A and B on an unweighted graph.

In many algorithms, it's also used to find the max flow between A and B.
