# Graph Representation

[home](/)

A guide on how to represent graphs for informatics

## Basic Graphs

### Adjacency Matrix
A N x N grid with values referring to the edge between the nodes.

#### Complexity

| Complexity | Operation |
| --- | --- |
| Insert Edge | O(1) |
| Query a node's all neighbours | O(N) |
| Get the edge between node i and j if it exists | O(1) |

### Adjacency List
A list for each node for its neighbours.

#### Complexity

| Complexity | Operation |
| --- | --- |
| Insert Edge | O(1) |
| Query a node's all neighbours | amortized O(E/N) |
| Get the edge between node i and j if it exists | amortized O(E/N) |

## Minimal example:

```c++
int weights[N][N];
weights[2][4]; // this is the weight of the edge from 2 to 4. Yay!

// Adj Matrix from Adj List:
// Assuming 0-based nodes
// a non-existent edge will have weight [marker]
int marker = 69696969;
for (int i = 0; i < N; ++i) {
    for (int j = 0; j < N; ++j) {
      // if this doesn't change, then there's no edge btw i and j
      matrix[i][j] = marker;
    }
    // assuming j.first = node id, j.second = edge weight
    for (std::pair<int, int>& j : adjlist[i]) {
        matrix[i][j.first] = j.second;
    }
}
```

### Adjacency List

Minimal example:

```c++
std::vector<std::pair<int, int>> adjlist[N];
int weights[N][N];

int marker = 69696969;

// ********************* //
// converting adj lists to adj matrices


for (int i = 0; i < N; ++i) {
    for (int j = 0; j < N; ++j) {
      weights[i][j] = marker;
    }
    for (auto& a : adjlist[i]) {
        a.first; // node id
        a.second; // edge weight
        // Yay! we just retrieved all the node ids adjacent to node i *and* their edge weights!
        weights[i][a.first] = a.second;
    }
}
```

[this problem on orac](http://orac.amt.edu.au/cgi-bin/train/problem.pl?set=aio19&problemid=1081) can be solved using DP and basic graph theory

## SPOILER!

Below is the whole solution to the above problem, proudly open sourced at orac by Angus Ritossa

This program features adjacency lists, [BFS](/Basic_Notes/Graph_Theory/BFS), and [DP](/Basic_Notes/Dynamic_Programming)

```c++
#include <bits/stdc++.h>
using namespace std;
int n, m, x, k;
vector<int> adj[100010];
int dis[100010][2], ans;
int main()
{
	freopen("evadingin.txt", "r", stdin);
	freopen("evadingout.txt", "w", stdout);
	scanf("%d%d%d%d", &n, &m, &x, &k);
	for (int i = 0; i < m; i++)
	{
		int a, b;
		scanf("%d%d", &a, &b);
		adj[a].push_back(b);
		adj[b].push_back(a);
	}
	for (int i = 1; i <= n; i++) dis[i][0] = dis[i][1] = 2e9;
	dis[x][0] = 0;
	queue<pair<int, int> > q;
	q.emplace(x, 0);
	while (q.size())
	{
		int a = q.front().first;
		int b = q.front().second;
		int d = dis[a][b];
		q.pop();
		for (auto c : adj[a])
		{
			if (dis[c][!b] == 2e9)
			{
				dis[c][!b] = d+1;
				q.emplace(c, !b);
			}
		}
	}
	for (int i = 1; i <= n; i++) ans += dis[i][k%2] <= k;
	printf("%d\n", ans);
}
```
