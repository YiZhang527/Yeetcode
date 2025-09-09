# LeetCode 1456 - Maximum Number of Vowels in a Substring of Given Length

## Approach: Sliding Window

To find the substring of size `k` with the maximum number of vowels, we can:

- Start by counting the vowels in the first `k` characters.  
- Then slide the window: at each step, check the new character entering the window and the old character leaving the window.  
- Keep track of the maximum vowel count encountered.

## Code

```python
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        vowels = "aeiou"
        count = sum(c in vowels for c in s[:k])
        maxCount = count
        for i in range(k, len(s)):
            if s[i] in vowels:
                count += 1
            if s[i - k] in vowels:
                count -= 1
            if count > maxCount:
                maxCount = count
        return maxCount
```
