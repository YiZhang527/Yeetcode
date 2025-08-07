## LeetCode 2379 - Minimum Recolors to Get K Consecutive Black Blocks

### Description

You are given a string `blocks` consisting of characters `'W'` and `'B'`, and an integer `k`.  
Return the minimum number of white `'W'` blocks that need to be recolored to black `'B'` so that there is at least one substring of length `k` containing only black blocks.

---

### Approach: Sliding Window

To find the minimum number of white blocks to recolor in any substring of length `k`, we can:

- Count the number of `'W'` in the first window of size `k`.  
- Slide the window one character at a time:
  - Add 1 if the new character is `'W'`.  
  - Subtract 1 if the character leaving the window is `'W'`.  
- Keep track of the minimum count of `'W'` encountered during the sliding process.

---

### Code

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

---

### Complexity Analysis

- **Time Complexity**: O(n) — We iterate over the array once.  
- **Space Complexity**: O(1) — Constant extra space is used.

