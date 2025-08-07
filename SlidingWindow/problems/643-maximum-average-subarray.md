## LeetCode 643 - Maximum Average Subarray I

### Description

Given an integer array `nums` and an integer `k`, return the maximum average value of any contiguous subarray of length `k`.

---

### Approach: Sliding Window

To find the subarray of size `k` with the maximum average, we can:

- Start by calculating the sum of the first `k` elements.  
- Then slide the window: at each step, subtract the element that moves out of the window and add the new element coming into the window.  
- Keep track of the maximum sum encountered.

---

### Code

```python
class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:
        n = len(nums)
        windowSum = sum(nums[:k])
        maxSum = windowSum
        for i in range(k, n):
            windowSum += nums[i]
            windowSum -= nums[i - k]
            if windowSum > maxSum:
                maxSum = windowSum
        return maxSum / k
```

---

### Complexity Analysis

- **Time Complexity**: O(n) — We iterate over the array once.  
- **Space Complexity**: O(1) — Constant extra space is used.
