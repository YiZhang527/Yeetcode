# Bit Manipulation

Bit manipulation provides efficient O(1) space solutions for set operations, state tracking, and finding unique elements.

## Core Bit Operations

### 1. Basic Operators
- **AND (`&`)**: Returns 1 when both bits are 1 else 0
- **OR (`|`)**: Returns 0 when both bits are 0 else 1
- **XOR (`^`)**: Returns 0 when bits are same else 1
- **NOT (`~`)**: Flips all bits: ~n = -(n + 1)
- **Left Shift (`<<`)**: Shifts bits left, equivalent to multiplying by 2^n
- **Right Shift (`>>`)**: Shifts bits right, equivalent to dividing by 2^n

### 2. Essential Techniques
- **Check if nth bit is set**: `(num >> n) & 1`
- **Set nth bit to 1**: `num | (1 << n)`
- **Clear nth bit to 0**: `num & ~(1 << n)`
- **Toggle nth bit**: `num ^ (1 << n)`
- **Clear lowest set bit**: `num & (num - 1)`
- **Get lowest set bit**: `num & -num`

## Bit Manipulation: Set / Clear / Toggle

In bit manipulation, each bit can be thought of as a switch:

| Operation | Bit Value | Switch Analogy | Description |
|-----------|-----------|----------------|------------|
| **Set**    | 1         | Turn the switch ON  | Set a specific bit to 1, leaving other bits unchanged |
| **Clear**  | 0         | Turn the switch OFF | Set a specific bit to 0, leaving other bits unchanged |
| **Toggle** | Flip      | Flip the switch state | Flip a specific bit: 0 → 1 or 1 → 0, leaving other bits unchanged |


### ⚠️ Important Note on Operator Precedence
**Bitwise operators have lower precedence than arithmetic operators!** For example:
- `1 << n + 1` means `1 << (n + 1)`, NOT `(1 << n) + 1`
- `x & y - 1` means `x & (y - 1)`, NOT `(x & y) - 1`

Always use parentheses to make your intention clear when mixing bitwise and arithmetic operations.

## Common Bit Manipulation Patterns

### 1. XOR Properties for Finding Unique Elements
- **Use case**: When all elements appear twice except one, or finding missing/duplicate numbers
- **Key insight**: `a ^ a = 0` and `a ^ 0 = a`, XOR is commutative and associative
- **General Template**:
```python
def find_single_element(nums):
   result = 0
   for num in nums:
       result ^= num
   return result
