# Leetcode-1979.-Find-Greatest-Common-Divisor-of-Array
A comprehensive Java solution for LeetCode 1979 - Find Greatest Common Divisor of Array, including an optimized Euclidean Algorithm implementation, detailed explanation, dry run, complexity analysis, and clean, interview-ready code.
# 1979. Find Greatest Common Divisor of Array

![LeetCode](https://img.shields.io/badge/LeetCode-1979-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)
![Language](https://img.shields.io/badge/Language-Java-blue)
![Status](https://img.shields.io/badge/Status-Solved-success)

## Problem Statement

Given an integer array `nums`, return the **greatest common divisor (GCD)** of the smallest number and largest number in `nums`.

The **greatest common divisor** of two numbers is the largest positive integer that evenly divides both numbers.

---

## Examples

### Example 1

**Input**

```text
nums = [2,5,6,9,10]
```

**Output**

```text
2
```

**Explanation**

- Smallest number = 2
- Largest number = 10
- GCD(2,10) = 2

---

### Example 2

**Input**

```text
nums = [7,5,6,8,3]
```

**Output**

```text
1
```

---

### Example 3

**Input**

```text
nums = [3,3]
```

**Output**

```text
3
```

---

## Constraints

- `2 <= nums.length <= 1000`
- `1 <= nums[i] <= 1000`

---

# Approach

Since the GCD of the entire array is **not required**, we only need:

1. Find the smallest element.
2. Find the largest element.
3. Compute their GCD using the Euclidean Algorithm.

The Euclidean Algorithm repeatedly replaces:

gcd(a, b) = gcd(b, a % b)

until `b == 0`.

---

# Algorithm

1. Find the minimum element.
2. Find the maximum element.
3. Apply Euclidean Algorithm.
4. Return the GCD.

---

# Java Solution

```java
import java.util.Arrays;

class Solution {
    public int findGCD(int[] nums) {
        int mn = Arrays.stream(nums).min().getAsInt();
        int mx = Arrays.stream(nums).max().getAsInt();
        return gcd(mn, mx);
    }

    private int gcd(int a, int b) {
        return b == 0 ? a : gcd(b, a % b);
    }
}
```

---

# Dry Run

### Input

```text
nums = [2,5,6,9,10]
```

### Step 1

Minimum = 2

Maximum = 10

### Step 2

```
gcd(2,10)

10 % 2 = 0

gcd(2,0)

Answer = 2
```

---

# Complexity Analysis

### Time Complexity

- Finding minimum: **O(n)**
- Finding maximum: **O(n)**
- GCD computation: **O(log(max(nums)))**

Overall:

```text
O(n)
```

---

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

# Key Concepts

- Arrays
- Math
- Euclidean Algorithm
- Greatest Common Divisor (GCD)
- Recursion

---

# Tags

`Array` `Math` `Number Theory` `GCD` `Easy`

---

## LeetCode Link

https://leetcode.com/problems/find-greatest-common-divisor-of-array/

---

## Author

**Ammar Ahmad**

If you found this repository helpful, consider giving it a ⭐ on GitHub!
