# Dynamic Programming (DP)

Dynamic Programming is a method for solving problems by breaking them down into overlapping subproblems.  
It often reduces time complexity by avoiding redundant computations through **recurrence relations** and **memoization/tabulation**.

## Two Common Types of DP

## 1. **Recurrence/Construction Type (Building/Counting Problems)**
* **Characteristics:** Each element depends on previous (or above) elements for calculation
* **Examples:**
  * Pascal's Triangle (each element = sum of two elements from row above)
  * Fibonacci Sequence (`f(n) = f(n-1) + f(n-2)`)
  * Climbing Stairs (`dp[i] = dp[i-1] + dp[i-2]`)
* 🔑 **Core Concept:** **State transition formula + Initial conditions**

## 2. **Optimization Type (Maximum/Minimum/Optimal Solution)**
* **Characteristics:** Seeking "optimal solution", typically using **min or max operations**
* **Examples:**
  * Knapsack Problem (maximize value)
  * Shortest Path (minimize path cost)
  * Stock Trading Problem (maximize profit)
* 🔑 **Core Concept:** **dp[i] represents the optimal solution under certain constraints**

## Summary
* **Dependency relationships → Recurrence Type DP**
* **Finding optimal values → Optimization Type DP**

These two categories cover approximately 90% of DP problems. The remaining problems involve more advanced techniques like **state compression, interval DP, tree DP**, etc.


## Easy Problems
<a href="https://leetcode.com/problems/pascals-triangle/" target="_blank">118. Pascal's Triangle</a> → <a href="./problems/118-pascals-triangle.md" target="_blank">Solution Notes</a>
