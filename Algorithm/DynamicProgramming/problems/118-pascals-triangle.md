# LeetCode 118 - Pascal's Triangle

## Approach: Dynamic Programming (Recurrence Type)

- Build the triangle row by row.
- Initialize each row with 1s.
- For rows from the third onward, fill the middle elements by adding the two numbers directly above from the previous row.
- Store each completed row so it can be used to calculate the next row.

## Code1

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        dp = [[] for _ in range(numRows)]
        if numRows >= 1:
            dp[0] = [1]
        if numRows >= 2:
            dp[1] = [1,1]
        for i in range(2,numRows):
            array = []
            prev = dp[i-1]
            for j in range(len(prev) - 1):
                array.append(prev[j] + prev[j+1])
            dp[i] = [1] + array + [1]
        return dp
```

## Code2

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




