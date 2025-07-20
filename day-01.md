# Day 01: Arrays and Hashing

## Two Sum

https://leetcode.com/problems/two-sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

```ts
function twoSum(nums: number[], target: number): number[] {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

```ts
function twoSum(nums: number[], target: number): number[] {
  const map = new Map<number, number>();
  for (let i = 0; i < nums.length; i++) {
    const complement = target - nums[i];
    if (map.has(complement)) {
      return [map.get(complement)!, i];
    }
    map.set(nums[i], i);
  }
  return [];
}
```

</details>

## Contains Duplicate

https://leetcode.com/problems/contains-duplicate

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

```ts
function containsDuplicate(nums: number[]): boolean {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

```ts
function containsDuplicate(nums: number[]): boolean {
  const set = new Set<number>();
  for (const num of nums) {
    if (set.has(num)) {
      return true;
    }
    set.add(num);
  }
  return false;
}
```

</details>
