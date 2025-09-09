# LeetCode 118 - Pascal's Triangle

### Approach: Dynamic Programming (Recurrence Type)

- Build the triangle row by row with 1s.
- For rows from the third onward, fill the middle elements by adding the two numbers directly above from the previous row.
- Store each completed row so it can be used to calculate the next row.

---

### Code

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        dp = []
        for i in range(numRows):
            row = [1] * (i + 1)
            if i >= 2: # Only from the third row onward do we need to calculate the middle elements.
                for j in range(1, i):
                    row[j] = dp[i-1][j-1] + dp[i-1][j]  # The middle elements are obtained by adding adjacent numbers from the previous row.
            dp.append(row)
        return dp
```

---

### Complexity Analysis

- Time Complexity: O(numRows²) — Total number of elements in the triangle
- Space Complexity: O(numRows²) — Space to store the entire triangle



