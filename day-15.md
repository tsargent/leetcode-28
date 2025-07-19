# Day 15: Binary Trees

## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree

Given the root of a binary tree, invert the tree, and return its root.

```ts
// Definition for a binary tree node.
class TreeNode {
  val: number;
  left: TreeNode | null;
  right: TreeNode | null;
  constructor(val?: number, left?: TreeNode | null, right?: TreeNode | null) {
    this.val = val === undefined ? 0 : val;
    this.left = left === undefined ? null : left;
    this.right = right === undefined ? null : right;
  }
}

function invertTree(root: TreeNode | null): TreeNode | null {
  // TODO: Implement solution
}
```

## Maximum Depth of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree

Given the root of a binary tree, return its maximum depth.

A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

```ts
function maxDepth(root: TreeNode | null): number {
  // TODO: Implement solution
}
```
