# Connectivity Algorithm in Undirected Graphs

The Connectivity Algorithm in Undirected Graphs is an algorithm used to identify connected components in an undirected graph. It explores the graph using depth-first search (DFS) to identify and output blocks of vertices that form connected subgraphs.

## Algorithm Steps

The algorithm follows these steps:

1. Initialize a counter `i` to 1.
2. Initialize an array `num` to store the numbering of each vertex, initially set to 0 for all vertices.
3. Start a loop that continues until there is a vertex `v` such that `num(v) == 0`.
4. Inside the loop, call the function `blockDFS(v)` to perform a depth-first search starting from vertex `v`.
5. In the `blockDFS(v)` function:
   - Set `pred(v)` and `num(v)` to the current value of `i` and increment `i`.
   - Iterate over all vertices `u` adjacent to `v`:
     - If the edge `(v,u)` has not been processed, push it onto a stack.
     - If `num(u)` is 0, recursively call `blockDFS(u)` to explore the connected component.
     - If `pred(u) ≥ num(v)`, it means there is no edge from `u` to a vertex above `v`. Pop edges from the stack until reaching the edge `(v,u)` and output those edges as a block.
     - Update `pred(v)` to be the minimum of its current value and `pred(u)` if `u` is not the parent of `v`.
     - Update `pred(v)` to be the minimum of its current value and `num(u)` when a back edge `(u,v)` is found.
6. After the loop in step 3, the algorithm has identified and outputted all connected components or blocks in the graph.

## Use Cases

The Connectivity Algorithm in Undirected Graphs has various applications, including:

- Network Analysis: It can be used to identify connected components in a network, helping to understand the overall structure and connectivity of the network.
- Image Processing: The algorithm can be applied to analyze the connected regions or components in an image, aiding in tasks such as object recognition and segmentation.
- Social Network Analysis: By applying the algorithm to a social network graph, it becomes possible to identify distinct communities or clusters of individuals based on their connections.

## History

The concept of connectivity in graphs has been studied extensively in graph theory and computer science. The connectivity algorithm for undirected graphs is based on depth-first search and was first described in the literature as a means to identify and output connected components or blocks within a graph.

The algorithm's time complexity is dependent on the size of the graph and the number of connected components present. By efficiently exploring the graph using depth-first search and maintaining necessary information such as numbering and predecessors, the algorithm provides an effective solution for identifying connected components.

The connectivity algorithm has been utilized in various fields, including network analysis, image processing, and social network analysis, to extract meaningful information from connected data structures.

## References

- [Connected Component (Graph Theory)](https://en.wikipedia.org/wiki/Connected_component_(graph_theory)) - Wikipedia
- [Depth-First Search (DFS) in Graphs](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/) - GeeksforGeeks
- [Graph Connectivity](https://www.cs.cmu.edu/~avrim/451f09/lectures/lect0915.pdf) - Carnegie Mellon University
