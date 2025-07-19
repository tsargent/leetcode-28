# Day 17: BFS (Breadth-First Search)

## Binary Tree Level Order Traversal

https://leetcode.com/problems/binary-tree-level-order-traversal

Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

```ts
function levelOrder(root: TreeNode | null): number[][] {
  // TODO: Implement solution
}
```

## Populating Next Right Pointers in Each Node

https://leetcode.com/problems/populating-next-right-pointers-in-each-node

You are given a perfect binary tree where all leaves are on the same level, and every parent has two children.

Populate each next pointer to point to its next right node. If there is no next right node, the next pointer should be set to NULL.

```ts
// Definition for a Node.
class Node {
  val: number;
  left: Node | null;
  right: Node | null;
  next: Node | null;
  constructor(val?: number, left?: Node, right?: Node, next?: Node) {
    this.val = val === undefined ? 0 : val;
    this.left = left === undefined ? null : left;
    this.right = right === undefined ? null : right;
    this.next = next === undefined ? null : next;
  }
}

function connect(root: Node | null): Node | null {
  // TODO: Implement solution
}
```
