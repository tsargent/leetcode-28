# Day 18: Graph Basics

## Clone Graph

https://leetcode.com/problems/clone-graph

Given a reference of a node in a connected undirected graph.

Return a deep copy (clone) of the graph.

Each node in the graph contains a value (int) and a list (List[Node]) of its neighbors.

```ts
// Definition for a Node.
class GraphNode {
  val: number;
  neighbors: GraphNode[];
  constructor(val?: number, neighbors?: GraphNode[]) {
    this.val = val === undefined ? 0 : val;
    this.neighbors = neighbors === undefined ? [] : neighbors;
  }
}

function cloneGraph(node: GraphNode | null): GraphNode | null {
  // TODO: Implement solution
}
```

## Number of Connected Components in an Undirected Graph

Find the number of connected components in an undirected graph.

```ts
function countComponents(n: number, edges: number[][]): number {
  // TODO: Implement solution using Union-Find or DFS/BFS
}
```
