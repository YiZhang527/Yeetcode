# LeetCode 867 - Transpose Matrix

### Approach: Row-Column Index Swap

To transpose a matrix, we can:

- Get the number of rows `m` and columns `n` of the original matrix.
- Create a new matrix of size `n x m`.
- For each element at position `(i, j)` in the original matrix, put it at position `(j, i)` in the new matrix.
    - **Why swapping indices achieves transposition:**
      
      Visual understanding:
      ```
      Original matrix (3×2):    Transposed matrix (2×3):
      [1, 2]                    [1, 3, 5]
      [3, 4]         →          [2, 4, 6]
      [5, 6]                
      
      Observe how element positions change:
      1: (0,0) → (0,0)  # Elements on diagonal stay in place
      2: (0,1) → (1,0)  # Row and column indices swap
      3: (1,0) → (0,1)  # Row and column indices swap
      4: (1,1) → (1,1)  # Elements on diagonal stay in place
      5: (2,0) → (0,2)  # Row and column indices swap
      6: (2,1) → (1,2)  # Row and column indices swap
      ```
      So the core of transposition is: swapping the row and column indices of each element, which transforms each horizontal row into a vertical column.
      
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

