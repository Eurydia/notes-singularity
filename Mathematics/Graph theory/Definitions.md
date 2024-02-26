# Definitions

## Graph

There are four different mathematical objects which are considered **graph** based on their properties. Namely;
- **undirected simple graph**
- **directed simple graph**
- **undirected multigraph**
- **directed multigraph**

### Undirected simple graph

An **undirected simple graph** is a an ordered pair $(V,E)$ where $V$ is a set of **vertices** and $E$ is a set of **unordered pairs** of vertices.

In a an undirected simple graph, there is at most one edge between two vertices. Either two vertices are connected or they are not.

### Directed simple graph

A **directed simple graph** is a an ordered pair $(V,E)$ where $V$ is a set of **vertices** and $E$ is a set of  **ordered pairs** of vertices.

In a directed simple graph, there is at most two edges between two vertices.

### Undirected multigraph

An **undirected multigraph** is a an ordered triple $(V,E,\phi)$ where $V$ is a set of **vertices**, $E$ is a multiset of **unordered pairs** of vertices, and $\phi:E\to\{\{v_{1},v_{2}\} : v_{1},v_{2}\in V\}$

### Directed simple graph

A **directed multigraph** is a an ordered triple $(V,E,\phi)$ where $V$ is a set of **vertices**, $E$ is a multiset of **ordered pairs** of vertices, and $\phi:E\to V\times V$.

## Endpoint

In a graph $G:=(V,E)$, the vertices $v_{1},v_{2}\in V$ are **endpoints** of the **undirected edge** $\{v_{1},v_{2}\}\in E$.

If $G$ is a **directed graph**, the vertices $v_{1},v_{2}$ are called the **tail** and the **head** of the edge $(v_{1},v_{2})$, respectively.

## Incidence

In a graph $G:=(V,E)$, the edge $e\in E$ is said to be **incident** on its **endpoints**.

## Loop-free graph

A **undirected graph** $G:=(V,E)$ is said to be **loop-free** if it does not contain an edge $e\in E$ which connects a vertex to itself.

## Weighted graph

A **weighted graph** is a graph in which a weight is assigned to each edge. The weights could represent additional context about the graph, for example costs, lengths or capacities, depending on the problem at hand.

## Degree

The **degree** of a vertex in a graph is the number of edges that are incident to the vertex; in a **multigraph**, a loop contributes twice to a vertex's degree.

## Regular graph

A **regular graph** is a graph in which each vertex has the **degree**. A regular graph with vertices of degree $k$ is called a $k$‑regular graph.

## Complete graph

A **complete graph** is an **undirected simple graph** which every vertex is connected to every other vertex, denoted $K_{n}$ where $n$ represents the number of vertices.

## Tournament

A **tournament** is a **complete graph** whose edges has been given a direction. 

## Cycle graph

A **cycle** is an **undirected simple graph** with $n$ vertices that forms an $n$-sided polygon. They are unique, denoted by $C_{n}$.

## Path graph

A **path graph** is a **cycle graph** with one edge removed.

## Bipartite graph

A **bipartite graph** $(V, E)$ is a graph that $V$ can be partitions into two **partitions** $V_{1}, V_{2}$, such that every edge $e\in E$ has **endpoints** in both partitions.

## Complete-bipartite graph

A **complete-bipartite graph** $(V, E)$ is a graph that $V$ can be partitions into two **partitions** $V_{1}, V_{2}$, such that every vertex $v\in V_{1}$ is connected to every vertex in $V_{2}$ by an edge. A **complete-bipartite** graph is denoted by $K_{m,n}$ where $m:=|V_{1}|$ and $n:=|V_{2}|$.

## Graph isomorphism

A graph $G_{1}$ is an isomorph with graph $G_{2}$, denoted by $G_{1}\cong G_{2}$, if there exist a function $\phi :V_{G_{1}}\to V_{G_{2}}$, such that $\{v_{1},v_{2}\}\in V_{G_{1}}$ if and only if $\{\phi(v_{1}),\phi(v_{2})\}\in V_{G_{2}}$.

