# Day 03: Sliding Window

## Best Time to Buy and Sell Stock

https://leetcode.com/problems/best-time-to-buy-and-sell-stock

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

```ts
function maxProfit(prices: number[]): number {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

**Approach**: Single Pass (Greedy)  
**Pattern**: Track minimum buy price and maximum profit in one iteration.

**Step-by-step explanation**:

1. Initialize minPrice to the first day's price and maxProfit to 0
2. Iterate through prices starting from day 2
3. For each day, we have two choices:
   - If current price is lower than minPrice, update our minimum buy price
   - If current price is higher, calculate profit (current price - minPrice) and update maxProfit if better
4. Key insight: We only need to track the lowest price seen so far, not when it occurred
5. At each step, we're asking: "What's the best profit if I sell today?"
6. Time: O(n), Space: O(1) - optimal single-pass solution

```ts
function maxProfit(prices: number[]): number {
  let minPrice = prices[0];
  let maxProfit = 0;

  for (let i = 1; i < prices.length; i++) {
    if (prices[i] < minPrice) {
      minPrice = prices[i];
    } else {
      maxProfit = Math.max(maxProfit, prices[i] - minPrice);
    }
  }

  return maxProfit;
}
```

</details>

## Maximum Subarray

https://leetcode.com/problems/maximum-subarray

Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

```ts
function maxSubArray(nums: number[]): number {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

**Approach**: Kadane's Algorithm (Dynamic Programming)  
**Pattern**: At each step, decide whether to extend current subarray or start fresh.

**Step-by-step explanation**:

1. Initialize maxSum and currentSum to the first element
2. For each subsequent element, we face a decision:
   - Extend the current subarray by adding this element: currentSum + nums[i]
   - Start a new subarray from this element: nums[i]
3. Choose whichever gives a larger sum: Math.max(nums[i], currentSum + nums[i])
4. Update our global maximum if the current subarray sum is better
5. Key insight: If currentSum becomes negative, it's better to start fresh
6. This captures the essence of dynamic programming: optimal substructure
7. Time: O(n), Space: O(1) - single pass with constant space

```ts
function maxSubArray(nums: number[]): number {
  let maxSum = nums[0];
  let currentSum = nums[0];

  for (let i = 1; i < nums.length; i++) {
    // Either extend the current subarray or start a new one
    currentSum = Math.max(nums[i], currentSum + nums[i]);
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
}
```

</details>
