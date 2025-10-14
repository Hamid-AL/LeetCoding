# Understanding Big O Notation (with O(n²) Example)

## 📘 What is Big O Notation?

**Big O notation** is a mathematical way to describe **how the runtime (or memory usage)** of an algorithm grows as the input size increases.  

It focuses on the *rate of growth* — not the exact time — and ignores constants and small details to show how the algorithm *scales*.

### 📘 Big O Formulas (Runtime vs Input Size)
T(n) represent time needed for an input of size n to be processed.

k is a constant.

| Complexity | Name | Example | Formula |
|-------------|------|----------|----------|
| O(1) | Constant | Accessing a specific array element | T(n) = k |
| O(log n) | Logarithmic | Binary search | T(n) = k · log(n) |
| O(n) | Linear | Looping through a list once | T(n) = k · n |
| O(n²) | Quadratic | Nested loops | T(n) = k · n² |
| O(2ⁿ) | Exponential | Solving the traveling salesman problem | T(n) = k · 2ⁿ |

image of time complexity here

---

## 💡 Example: O(n²) — Quadratic Time

A typical example of **O(n²)** complexity is a nested loop, such as comparing each pair of elements in a list.

```python
def compare_pairs(arr):
    for i in range(len(arr)):
        for j in range(len(arr)):
            pass  # Imagine we compare arr[i] and arr[j]
```

- The **outer loop** runs `n` times.  
- The **inner loop** also runs `n` times.  
- So total operations ≈ `n × n = n²`.

---

## ⏱️ How Execution Time Scales

Let’s assume:
- For **n = 10 elements**, the algorithm takes **1 second**.

We can express runtime as:
```math
T(n) = k \cdot n^2
```
where `k` is a constant.

From the given case:
```math
1 = k \cdot 10^2 \Rightarrow k = 0.01
```
Now we can predict runtimes for larger inputs.

| Input Size (n) | Formula | Predicted Time | Human Readable |
|-----------------|----------|----------------|----------------|
| 10 | 0.01 × 10² | 1 second | — |
| 1,000 | 0.01 × 1,000² | 10,000 seconds | ≈ 2.78 hours |
| 10,000 | 0.01 × 10,000² | 1,000,000 seconds | ≈ 11.6 days |

---

## 📊 Growth Comparison

Quadratic time grows **much faster** than linear or logarithmic time.  
Here’s an intuitive comparison:

| Input (n) | O(log n) | O(n) | O(n²) |
|------------|-----------|------|-------|
| 10 | 3 | 10 | 100 |
| 100 | 7 | 100 | 10,000 |
| 1,000 | 10 | 1,000 | 1,000,000 |

---

## ⚡ Takeaway

- **O(n²)** algorithms are fine for small inputs but become **extremely slow** for large datasets.  
- Always aim for **O(n)** or **O(n log n)** if performance matters.  
- Big O helps you predict how your algorithm will behave as your data grows.

---

## 🧠 Quick Recap

- Big O tells how time grows with input size.
- **O(n²)** = double loop = performance drops fast.
- For n = 10 → 1s  
  For n = 1000 → ~2.8h  
  For n = 10000 → ~11.6 days.

---

**Author:** ChatGPT (GPT-5)  
**License:** MIT  
