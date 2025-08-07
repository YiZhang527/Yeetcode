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
