# Sliding Window Technique

The **Sliding Window Technique** is an efficient approach for solving problems related to contiguous subarrays or substrings. It reduces the need for nested loops and often brings the time complexity down from O(N^2) to O(N).

---

## Concept

* A **window** represents a contiguous subset of elements in an array or string.
* Instead of recomputing values for each subarray from scratch, slide the window across the array while updating the value incrementally.

There are two main types of sliding windows:

1. **Fixed-size window**:

   * The window size is constant.
   * Useful for problems like finding sums, averages, maximums, or minimums over subarrays of length `k`.

2. **Variable-size window (Two Pointers)**:

   * The window size changes dynamically.
   * Expand the window until a condition is violated, then shrink it from the left to restore the condition.
   * Commonly used for problems like longest/shortest subarray or substring satisfying a condition.

---

## Key Observations

* Each element is visited at most twice (once when entering and once when leaving the window), giving **O(N)** time complexity.
* Space complexity is **O(1)** for sums or O(k) if frequency maps are required.
* Sliding window is particularly effective for "maximum/minimum", "sum/average", or "length of substring/subarray" problems.

---


## Sample Problem:
Find the maximum sum of a subarray of size k.

Example:

Input: nums = [2, 1, 5, 1, 3, 2], k = 3

Output: 9

Explanation:
- Start with the sum of the first k elements.

- Slide the window one element at a time, subtracting the element that goes out of the window and adding the new element.

- Keep track of the maximum sum encountered.

## LeetCode Problems:
* Longest Substring Without Repeating Characters (#3) ✅
* Maximum Average Subarray I (#643) ✅
* Minimum Window Substring (#76)
* Sliding Window Maximum (#239)