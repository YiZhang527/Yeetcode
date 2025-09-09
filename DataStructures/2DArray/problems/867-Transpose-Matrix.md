# LeetCode 867 - Transpose Matrix

### Approach: Row-Column Index Swap

To transpose a matrix, we can:

- Get the number of rows `m` and columns `n` of the original matrix.
- Create a new matrix of size `n x m`.
- For each element at position `(i, j)` in the original matrix, put it at position `(j, i)` in the new matrix.

---

### Code

```python
class Solution:
    def transpose(self, matrix: List[List[int]]) -> List[List[int]]:
        m, n = len(matrix), len(matrix[0])
        res = [[0] * m for _ in range(n)]

        for i in range(m):
            for j in range(n):
                res[j][i] = matrix[i][j]
        return res
```

---

### Complexity Analysis

- Time Complexity: O(m × n) — We iterate through all elements once
- Space Complexity: O(m × n) — Space needed for the output matrix



