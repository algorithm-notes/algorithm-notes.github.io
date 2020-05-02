# Graph Representation

[home](/)

A guide on how to represet graphs for informatics

## Basic Graphs
### Adjacency Matrix
A n*n grid with values refering to the edge between the nodes.

Minimal example:

```c++
int weights[N][N];
weights[2][4] // this is the weight of the edge from 2 to 4. Yay!

// Adj Matrix from Adj List:
// Assuming 0-based nodes
// a non-existent edge will have weight [marker]
int marker = 69696969;
for (int i = 0; i < N; ++i) {
    for (int i = 0; i < N; ++i) {
      // if this doesn't change, then there's no edge btw i and j
      matrix[i][j] = marker;
    }
    for (std::pair<int, int>& j : adjlist[i]) {
        matrix[i][j.first] = j.second;
    }
}
```

### Adjacency List

## Trees
