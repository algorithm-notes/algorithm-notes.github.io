# Breath First Search (BFS)

Breath first search explores the nodes in the shortest path possible.

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