# Sliding Window

Sliding Window can often reduces time complexity from O(n²) to O(n) for many subarray/substring problems.


## Two Common Types of Sliding Window

### 1. Fixed-size Sliding Window

- **Use case**: When the window size is given as k, and you need to find the maximum, minimum, or other value within every contiguous subarray of length K.
- **Technique**: First, initialize the window with the first k elements, then slide the window starting from i = k, updating the window state at each step.
- **General Template**:
```python
# Initialize the window state
window_state = process(nums[:k])
result = window_state  # Initial result (could be sum, max, count, etc.)

# Slide the window from index k to the end of the array
for i in range(k, len(nums)):
    # Add the new element on the right to the window state
    window_state += nums[i]

    # Remove the element that slides out from the left
    window_state -= nums[i - k]

    # Update the result based on the current window state
    result = update(result, window_state)
```

## Easy Problems
- <a href="https://leetcode.com/problems/maximum-average-subarray-i/" target="_blank">643. Maximum Average Subarray I</a> → <a href="./problems/643-maximum-average-subarray.md" target="_blank">Solution Notes</a>
- <a href="https://leetcode.com/problems/minimum-recolors-to-get-k-consecutive-black-blocks/" target="_blank">2379. Minimum Recolors to Get K Consecutive Black Blocks</a> → <a href="./problems/2379-minimum-recolors-to-get-k-consecutive-black-blocks.md" target="_blank">Solution Notes</a>

## Medium Problems
- <a href="https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/" target="_blank">1456. Maximum Number of Vowels in a Substring of Given Length</a> → <a href="./problems/1456-maximum-number-of-vowels-in-a-substring-of-given-length.md" target="_blank">Solution Notes</a>
