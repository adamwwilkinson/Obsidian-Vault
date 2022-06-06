# Graphs
Definition: A *graph* $G$ consist of a set $V(G)$ called *vertices* together with a collection $E(G)$ of pairs of vertices. Each pair $\{x, y\} \in E(G)$ is called an *edge* of $G$.

They are used to model commonly occurring situations, enabling questions about problems to be reduced to well studied "standard" graph theory question.

### Terminology
Adjacency: if $\{x, y\} \in E(G)$, we say $x, y$ are adjacent
Paths: A *path of length* $n$ in a graph is a sequence of vertices all adjacent to each other
Cycles: A path which loops
Distance: The length of the shortest path between two vertices
Connected: if there exist a path between any two vertices
Forests: A graph with no cycles
Trees: Only one connected component
Directed: The edge (arcs) has an ordered pair of vertices, and hence a direction
Weighted: Each edge is assigned a weight

### Subgraphs
If $G$ is a graph, then subgraph $H$ is a graph such that
$$V(H) \subseteq V(G)$$
$$E(H) \subseteq E(G)$$

A *spanning* subgraph of $H$ has been obtained from $G$ by only removing the edges.

An *induced* subgraph of $H$ has been obtained from $G$ by removing vertices and their adjoining edges


### Representing Graphs
2 Ways to represent a graph, adjacency list or an adjacency matrix.