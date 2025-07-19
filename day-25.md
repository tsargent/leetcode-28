# Day 25: Heaps

## Top K Frequent Elements

https://leetcode.com/problems/top-k-frequent-elements

Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

```ts
function topKFrequent(nums: number[], k: number): number[] {
  // TODO: Implement solution
}
```

## Kth Largest Element in an Array

https://leetcode.com/problems/kth-largest-element-in-an-array

Given an integer array nums and an integer k, return the kth largest element in the array.

Note that it is the kth largest element in the sorted order, not the kth distinct element.

```ts
function findKthLargest(nums: number[], k: number): number {
  // TODO: Implement solution
}
```

## Min Heap Implementation

Implement a basic min heap for practice:

```ts
class MinHeap {
  private heap: number[] = [];

  constructor() {
    // TODO: Initialize heap
  }

  insert(val: number): void {
    // TODO: Implement insert
  }

  extractMin(): number | null {
    // TODO: Implement extract min
  }

  peek(): number | null {
    // TODO: Implement peek
  }

  private heapifyUp(index: number): void {
    // TODO: Implement heapify up
  }

  private heapifyDown(index: number): void {
    // TODO: Implement heapify down
  }
}
```
