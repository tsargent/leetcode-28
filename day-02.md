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

**Approach**: Two Pointers  
**Pattern**: Preprocess input, then compare from both ends moving inward.

**Step-by-step explanation**:

1. First, preprocess the string: convert to lowercase and remove all non-alphanumeric characters
2. Set up two pointers: left at the beginning, right at the end of the cleaned string
3. Compare characters at both pointers
4. If they don't match, it's not a palindrome - return false
5. If they match, move both pointers toward the center (left++, right--)
6. Continue until pointers meet or cross
7. If we successfully compare all pairs, it's a palindrome - return true
8. Time: O(n), Space: O(n) for the cleaned string

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

**Approach**: Three Pointers (Reverse Merge)  
**Pattern**: Merge from end to avoid overwriting, leveraging extra space in nums1.

**Step-by-step explanation**:

1. Key insight: nums1 has extra space at the end, so we merge backwards to avoid overwriting
2. Set up three pointers: i (last element of nums1), j (last element of nums2), k (last position in nums1)
3. Compare nums1[i] and nums2[j], place the larger one at nums1[k]
4. Move the pointer of the array we took from, and move k backwards
5. Continue until we've processed all elements from both arrays
6. Handle remaining elements: if nums2 has leftover elements, copy them over
7. If nums1 has leftover elements, they're already in the right place
8. Time: O(m+n), Space: O(1) - true in-place merge

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
