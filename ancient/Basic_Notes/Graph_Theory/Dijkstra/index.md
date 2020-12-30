# Dijkstra

[home](/)

Basically weighted [BFS](/Basic_Notes/Graph_Theory/BFS)...

Here is a example, which AC's on [orac](http://orac.amt.edu.au/cgi-bin/train/problem.pl?set=fario04&problemid=107)

This Dijkstra idea of weighted BFS and be extended to solve harder problems easily, which is shown here.

The problem without flavored text:
Find the shortest distance from A to B on a graph, given that some edges doesn't have weights which allows you to *half and floor* your current distance travelled.

```c++
// author: Athur Sun

#include <bits/stdc++.h>

using namespace std;

int N, S, F, P, W;

vector<pair<int, int>> edges[234];
vector<int> worms[789];

int dists[987];

int main() {
    ios::sync_with_stdio(false), cin.tie(nullptr);
    cin >> N >> S >> F >> P;
    for (int i = 0; i < P; ++i) {
        int a, b, t;
        cin >> a >> b >> t;
        edges[a].push_back({b, t});
    }
    cin >> W;
    for (int i = 0; i < W; ++i) {
        int a, b;
        cin >> a >> b;
        worms[a].push_back(b);
    }
    priority_queue<pair<int, int>> pq;
    for (int i = 1; i <= N; ++i) {
        dists[i] = INT_MAX / 3;
    }
    pq.push({0, S}), dists[S] = 0;
    while(!pq.empty()) {
        auto p = pq.top();
        pq.pop();
        
        for (auto& e : edges[p.second]) {
            int next = dists[p.second] + e.second;
            if(next < dists[e.first]) {
                dists[e.first] = next;
                pq.push({-next, e.first});
            }
        }
        
        for (int w : worms[p.second]) {
            int next = dists[p.second] / 2;
            if(next < dists[w]) {
                dists[w] = next;
                pq.push({-next, w});
            }
        }
    }
    cout << dists[F];
    return 0;
}
```
