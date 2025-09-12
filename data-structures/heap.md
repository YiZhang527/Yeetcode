# Heap / Priority Queue

## 📝 Introduction

A **Heap** is a complete binary tree that satisfies the heap property. It's commonly used to implement priority queues and efficiently find the min/max element.

## Key Properties
- **Complete Binary Tree**: All levels are filled except possibly the last
- **Heap Property**: 
  - Min Heap: Parent ≤ Children
  - Max Heap: Parent ≥ Children
- **Array Representation**: Can be stored efficiently in an array

## 🎯 Common Operations

| Operation | Time Complexity | Description |
|-----------|----------------|-------------|
| peek() | O(1) | Get min/max element |
| push() | O(log n) | Insert element |
| pop() | O(log n) | Remove min/max element |
| heapify() | O(n) | Build heap from array |

## 🐍 Python Implementation

### Using heapq (Min Heap only)
```python
import heapq

# Create heap
heap = []

# Insert
heapq.heappush(heap, 3)

# Remove min
min_val = heapq.heappop(heap)

# Build heap from list
nums = [3, 1, 4, 1, 5]
heapq.heapify(nums)  # O(n)

# Get k largest/smallest
k_largest = heapq.nlargest(k, nums)
k_smallest = heapq.nsmallest(k, nums)
