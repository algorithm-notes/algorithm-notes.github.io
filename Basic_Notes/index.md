# Basic Graph Theory
Graphs are non-linear data structures that are often used in informatics.

Basic definitions and terms are listed on this page. More may be found in advanced sections of these notes.

## Definitions
| Word | Definition |
| --- | --- |
| Vertices | A point on the Graph, also called Nodes |
| Edges | Connections between these points. Can be weighted (have a value) or unweighted. Can be directed or undirected |
| Degree | Amount of edges leading from a node |
| Weighted Graph | A Graph with weighted edges |
| Multigraphs | Graphs with parallel edges (Multiple Edges between same Vertices) |
| Path | Sequence of Connected Edges without loops |
| Walk | Sequence of Connected Edges, may have loops |
| Cycle | Path starting and ending at the same point |
| Acyclic Graph | Graph without cycles |
| Tree | Connected Acyclic Graph, has n-1 edges |
| Forest | Set of Trees |
| Vortex Graph | Connected Graph with n edges, has a cycle with trees connected to it |
| DAG | Directed Acyclic Graph |
| Hamiltonian Cycle | A cycle where each node is visited once |

### Rooted Tree Definitions

| Word | Definition |
| --- | --- |
| Root | A Special Node Singled out |
| Parent of a node | The Adjacent node one closer to the root, only the root doesn't have a parent |
| Child of a node | Adjacent nodes one further from the root, nodes without roots are leaves |
| Siblings of a node | The Parent's other children |
| Ancestors of a node | Nodes on a node's path to root |
| Grandparent of a node | The Parent's Parent |
| Depth | A node's distance from root |
| Height | A node's shortest distance from leaves (Not used too often, means depth in some cases) |
| Subtree | The part of a tree that is below a node that is not root |
| Binary tree | Tree with a maximum degree of 3, root has a degree of maximum 2 |
| Complete Binary Tree | Tree where the all rows except for the last is completely filled |
| Perfect Binary Tree | All rows are completely filled |

## Pages under Basic Graph Theory:
- [Graph Representation](Graph_Representation)
- [BFS](BFS)
- [DFS](DFS)
- [Dijkstra](Dijkstra)
- [Bottleneck Algorithm](Bottleneck)
- [Graph colouring](Graph_colouring)
- [Union find](Union_Find)
- [Minimum Spanning Tree](Minimum_Spanning_Tree)
