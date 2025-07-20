# Day 02: Two Pointers

## Valid Palindrome

https://leetcode.com/problems/valid-palindrome

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward.

Given a string s, return true if it is a palindrome, or false otherwise.

```ts
function isPalindrome(s: string): boolean {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

```ts
function isPalindrome(s: string): boolean {
  // Convert to lowercase and keep only alphanumeric characters
  const cleaned = s.toLowerCase().replace(/[^a-z0-9]/g, "");

  let left = 0;
  let right = cleaned.length - 1;

  while (left < right) {
    if (cleaned[left] !== cleaned[right]) {
      return false;
    }
    left++;
    right--;
  }

  return true;
}
```

</details>

## Merge Sorted Array

https://leetcode.com/problems/merge-sorted-array

You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

```ts
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

```ts
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
  let i = m - 1;
  let j = n - 1;
  let k = m + n - 1;

  // Merge from the end to avoid overwriting elements
  while (i >= 0 && j >= 0) {
    if (nums1[i] > nums2[j]) {
      nums1[k] = nums1[i];
      i--;
    } else {
      nums1[k] = nums2[j];
      j--;
    }
    k--;
  }

  // Copy remaining elements from nums2
  while (j >= 0) {
    nums1[k] = nums2[j];
    j--;
    k--;
  }
}
```

</details>
