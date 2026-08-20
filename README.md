# Leetcode_Day22

# Day 22 — LeetCode 66: Plus One

## Problem

Given an array of digits representing a large integer, increment the integer by one and return the resulting array of digits.

### Example

```text
Input:  [1,2,3]
Output: [1,2,4]
```

```text
Input:  [9,9,9]
Output: [1,0,0,0]
```

## Approach

* Start from the last digit because addition begins from the least significant digit.
* If the current digit is less than `9`, simply increment it and return the array.
* If the digit is `9`, change it to `0` and continue carrying the `1` to the previous digit.
* If every digit is `9`, create a new array with one extra position and put `1` at the beginning.

## Java Solution

```java
class Solution {
    public int[] plusOne(int[] digits) {
        for(int i = digits.length - 1; i >= 0; i--) {
            if(digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            digits[i] = 0;
        }

        int[] res = new int[digits.length + 1];
        res[0] = 1;
        return res;
    }
}
```

## Complexity

* **Time Complexity:** `O(n)` in the worst case
* **Space Complexity:** `O(n)` only when all digits are `9`; otherwise `O(1)` extra space.

## Key Learning

The important idea was handling **carry propagation** efficiently. Instead of converting the entire array into a number, we can process the digits directly from right to left.

**Day 22 complete. 🚀**
