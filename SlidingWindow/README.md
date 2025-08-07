# Sliding Window

Sliding Window reduces time complexity from O(n²) to O(n) for many subarray/substring problems.


## Two Common Types of Sliding Window

### 1. Fixed-size Sliding Window

- **Use case**: When the window size is known in advance, such as "maximum average", "sum of at most K elements", etc.
- **Technique**: First, record the initial window of the first k elements, then slide the window starting from i = k, maintaining the window state as you go.
