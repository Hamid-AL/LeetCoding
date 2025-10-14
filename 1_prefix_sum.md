# Prefix Sum Technique

Let's say we have a one-indexed integer array `arr` of size N and we want to compute the value of

$$
\texttt{arr}[a] + \texttt{arr}[a+1] + \cdots + \texttt{arr}[b]
$$

for Q different pairs (a,b) satisfying $1 \le a \le b \le N$. We'll use the following example with N = 6:

| Index i | 1 | 2 | 3 | 4 | 5 | 6 |
|---------|---|---|---|---|---|---|
| arr[i]  | 1 | 6 | 4 | 2 | 5 | 3 |

Naively, for every query, we can iterate through all entries from index a to index b to add them up. Since we have Q queries and each query requires a maximum of $O(N)$ operations, our total time complexity is $O(NQ)$. For N, Q <= 10^5, NQ ~ 10^10, which is too large and will exceed the time limit.

## Prefix Sum Approach

We can use **prefix sums** to process these queries efficiently. We define a prefix sum array `prefix` as follows:

- Set `prefix[0] = 0` (because we're 1-indexing).
- For each k such that $1 \le k \le N$:
$$
\texttt{prefix}[k] = \sum_{i=1}^{k} \texttt{arr}[i]
$$
or equivalently:
$$
\texttt{prefix}[k] = \texttt{prefix}[k-1] + \texttt{arr}[k]
$$

For the example array, the prefix sum array is:

| Index i    | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|------------|---|---|---|---|---|---|---|
| prefix[i]  | 0 | 1 | 7 | 11 | 13 | 18 | 21 |

## Querying with Prefix Sums

To find the sum of elements between indices L and R (inclusive), we use:

```math
\sum_{i=L}^{R} \texttt{arr}[i] = \sum_{i=1}^{R} \texttt{arr}[i] - \sum_{i=1}^{L-1} \texttt{arr}[i]
```

Using the prefix sum array:

```math
\sum_{i=L}^{R} \texttt{arr}[i] = \texttt{prefix}[R] - \texttt{prefix}[L-1]
```

- Preprocessing the prefix sum array takes $O(N)$.
- Each query takes $O(1)$.
- Total time complexity for Q queries: $O(N + Q)$.

## Example Query

Find the sum from `a = 2` to `b = 5`:

From the original array:

$$
\sum_{i=2}^{5} \texttt{arr}[i] = 6 + 4 + 2 + 5 = 17
$$

Using prefix sums:

$$
\texttt{prefix}[5] - \texttt{prefix}[1] = 18 - 1 = 17
$$

| Index i    | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|------------|---|---|---|---|---|---|---|
| prefix[i]  | 0 | 1 | 7 | 11 | 13 | 18 | 21 |
