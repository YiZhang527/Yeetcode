# LeetCode 2379 - Minimum Recolors to Get K Consecutive Black Blocks

## Approach: Sliding Window

To find the minimum number of white blocks to recolor in any substring of length `k`, we can:

- Count the number of `'W'` in the first window of size `k`.  
- Slide the window one character at a time:
  - Add 1 if the new character is `'W'`.  
  - Subtract 1 if the character leaving the window is `'W'`.  
- Keep track of the minimum count of `'W'` encountered during the sliding process.

## Code

```python
class Solution:
    def minimumRecolors(self, blocks: str, k: int) -> int:
        change = blocks[:k].count("W")
        minChange = change
        for i in range(k, len(blocks)):
            if blocks[i] == "W":
                change += 1
            if blocks[i - k] == "W":
                change -= 1
            if change < minChange:
                minChange = change
        return minChange
```

