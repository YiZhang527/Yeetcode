## LeetCode 566 - Reshape the Matrix

### Approach: Linear Index Mapping

To find the subarray of size `k` with the maximum average, we can:

- First check if reshaping is possible: m * n must equal r * c
- If not possible, return the original matrix
- Take out the elements of the original matrix in order, fill them into the new matrix one by one, and move to the next row when one row is filled

---

### Code1

```python
class Solution:
    def matrixReshape(self, mat: List[List[int]], r: int, c: int) -> List[List[int]]:
        m, n = len(mat), len(mat[0])
        if m * n != r * c:
            return mat
        
        res = [[0]*c for _ in range(r)]
        newi, newj = 0, 0
        for i in range(m):
            for j in range(n):
                res[newi][newj] = mat[i][j]
                newj += 1
                if newj == c:
                    newj = 0
                    newi += 1
        return res
```

### Code2

```python
class Solution:
    def matrixReshape(self, mat: List[List[int]], r: int, c: int) -> List[List[int]]:
        m, n = len(mat), len(mat[0])
        if m * n != r * c:
            return mat
        
        res = [[0]*c for _ in range(r)]
        k = 0
        for i in range(m):
            for j in range(n):
                res[k // c][k % c] = mat[i][j]
                k += 1
        return res
```

---

### Complexity Analysis

- Time Complexity: O(m × n) — We iterate through all elements once 
- Space Complexity: O(m × n) — Space needed for the output matrix

