# Two Pointers Technique

The **Two Pointers Technique** is a common algorithmic pattern used to solve problems involving arrays or linked lists, especially when dealing with pairs, sorted data, or subarray/subsequence relationships. It helps reduce time complexity from O(N^2) to O(N) in many cases.

---

## Concept

* The idea is to use two indices (pointers) that move through the data structure to find a desired condition or relationship.
* These pointers can move **towards each other**, **in the same direction**, or **independently**, depending on the problem.

There are three common forms:

1. **Opposite direction pointers**

   * One pointer starts at the beginning, the other at the end.
   * Commonly used for pair-sum or palindrome problems.
   * Example idea: If `arr[left] + arr[right] > target`, move `right` leftward; else, move `left` rightward.

2. **Same direction pointers**

   * Both pointers start at the beginning but move at different speeds or under different conditions.
   * Used in problems like removing duplicates, merging intervals, or detecting cycles in linked lists.

3. **Independent pointers**

   * Used when comparing two arrays, lists, or strings, such as merging sorted arrays or finding intersections.

---

## Key Observations

* Efficient for **sorted data** or **ordered traversal problems**.
* Each element is processed at most once, giving **O(N)** time complexity.
* Space complexity is usually **O(1)** since only two pointers are maintained.
* Works well for problems involving comparisons, distances, or merging.

---

## LeetCode Problems Using Two Pointers

### Opposite direction

* Two Sum II - Input Array Is Sorted (#167) ✅
* 3Sum (#15) ✅
* Container With Most Water(#11) ✅
* Valid Palindrome (#125)

### Same direction

* Remove Duplicates from Sorted Array (#26)
* Linked List Cycle (#141)
* Move Zeroes (#283)

### Independent pointers

* Merge Two Sorted Lists (#21)
* Intersection of Two Linked Lists (#160)
* Merge Sorted Array (#88)

---

The **Two Pointers Technique** is one of the most versatile patterns for array and string problems, providing linear-time solutions for many tasks that might otherwise require nested loops.
