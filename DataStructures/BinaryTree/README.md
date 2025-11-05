# Core Understanding of Binary Search

## Core Principle

**Most binary searches will eventually converge where left and right meet.**

The essence of binary search is continuously narrowing the search interval:
- The interval `[left, right]` is halved each time
- Eventually converges to a single point
- At that point `left == right`

## Two Major Types of Binary Search

### Type 1: Finding Specific Value (May Terminate Early)
```python
# Return when found, -1 if not found
while left <= right:  # Note: using <=
    mid = (left + right) // 2
    if nums[mid] == target:
        return mid  # ✅ Early termination
    elif nums[mid] < target:
        left = mid + 1
    else:
        right = mid - 1
return -1
```

### Type 2: Finding Position/Boundary (Will Always Converge)
```python
# Must converge to left == right
while left < right:  # Note: using 
    mid = (left + right) // 2
    if (condition):
        left = mid + 1
    else:
        right = mid
return left  # left == right
```

## Common Problem Classification

| Problem Type | Will Converge? | Reason |
|-------------|----------------|---------|
| **Finding Specific Value** | | |
| Find target | Not necessarily | Can return early when found |
| Check existence | Not necessarily | Can return early when found |
| **Finding Boundary** | | |
| First element >= target | ✅ Always | Need to find leftmost boundary |
| Last element <= target | ✅ Always | Need to find rightmost boundary |
| Insertion position | ✅ Always | Need exact position |
| **Finding Optimal Solution** | | |
| Peak element | ✅ Usually | Converges to peak position |
| Minimum in rotated array | ✅ Always | Converges to minimum |
| Leftmost 1 | ✅ Always | Need to find boundary |
| Finding split point | ✅ Always | Need exact position |

## Why "Finding Boundary" Must Converge?

Because you're looking for the **leftmost** or **rightmost** position that satisfies the condition:
```python
# Find first position >= 5
[1, 2, 3, 5, 5, 5, 7, 8]
           ↑
        Need this one

# Even if mid finds a 5, can't be sure it's the first one
# Must continue searching left until left == right
```

## Rules of Thumb

1. **If problem has a unique answer position** → Will converge
2. **If only checking existence** → May return early
3. **If finding "first", "last", "minimum", "maximum"** → Will definitely converge

## Special Case: Peak Element Problem

Peak element problem can use either approach:
- **Method 1**: Converge to `left == right` (more elegant)
- **Method 2**: Return when peak found (more intuitive)

Most prefer Method 1 because:
- Cleaner code
- No complex boundary checks needed
- Follows the general binary search pattern

## Summary

Except for "return when specific value found" cases, almost all binary searches will have left and right converge!
