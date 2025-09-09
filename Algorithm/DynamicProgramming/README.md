# Dynamic Programming (DP)

Dynamic Programming is a method for solving problems by breaking them down into overlapping subproblems.  
It often reduces time complexity by avoiding redundant computations through **recurrence relations** and **memoization/tabulation**.

## Two Common Types of DP

### 1. Recurrence / Construction Type

- **Use case**: When each state depends on previously computed states, often in sequence building or counting problems.
- **Technique**: Define a recurrence relation and build the solution step by step.
- **Examples**: Fibonacci numbers, Pascal’s Triangle, Climbing Stairs.
- **General Template**:
```python
dp = [0] * (n+1)
dp[0], dp[1] = base_case_0, base_case_1

for i in range(2, n+1):
    dp[i] = transition(dp[i-1], dp[i-2])
return dp[n]
```
### 2. Optimization Type (Max/Min)

- **Use case**: When the problem asks for the maximum, minimum, or optimal value under certain constraints.
- **Technique**: Define `dp[i]` as the best solution up to index `i`, then update it by taking `min`/`max` over possible choices.
- **General Template**:
```python
dp = [0] * (n+1)
dp[0] = base_case

for i in range(1, n+1):
    dp[i] = min_or_max(choice_1, choice_2, ...)
return dp[n]
```

## Easy Problems
<a href="https://leetcode.com/problems/pascals-triangle/" target="_blank">118. Pascal's Triangle</a> → <a href="./problems/118-pascals-triangle.md" target="_blank">Solution Notes</a>
