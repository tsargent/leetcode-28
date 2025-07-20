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

**Approach**: Hash Map  
**Pattern**: Store complements in a map for O(1) lookup, avoiding nested loops.

**Step-by-step explanation**:

1. Create a hash map to store numbers we've seen and their indices
2. For each number, calculate what its complement would need to be (target - current number)
3. Check if we've already seen this complement in our map
4. If yes, we found our pair - return the stored index and current index
5. If no, store the current number and its index for future lookups
6. This avoids the O(n²) brute force approach by trading space for time

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

**Approach**: Hash Set  
**Pattern**: Early termination - return immediately when duplicate found.

**Step-by-step explanation**:

1. Create a hash set to track numbers we've already encountered
2. Iterate through the array once
3. For each number, check if it's already in our set
4. If yes, we found a duplicate - return true immediately
5. If no, add the number to our set and continue
6. If we finish the loop without finding duplicates, return false
7. This gives us O(n) time complexity with early termination optimization

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
