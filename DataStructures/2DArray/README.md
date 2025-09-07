# 2D Array / Matrix
A 2D array is a common data structure that represents a table, matrix, or grid, where each element is itself an array.

## Basic Concepts

- **Definition**: A 2D array consists of `m` rows and `n` columns, usually represented as `m x n`.
- **Accessing Elements**: Use `array[i][j]` to access the element at row `i` (0 ≤ i < m) and column `j` (0 ≤ j < n).
- **Storage Order**:
  - **Row-major order**: Elements are stored row by row, with all elements of a row stored contiguously.
  - **Column-major order**: Elements are stored column by column, with all elements of a column stored contiguously.

## Initialization
```python
# m x n zero matrix
m, n = 3, 3
matrix = [[0] * n for _ in range(m)]
```

## Problems
