

# 🚀 _Day 6. Longest Consecutive Subsequence_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/hashing-gfg-160/problem/longest-consecutive-subsequence2449)

## 💡 **Problem Description:**

Given an array `arr[]` of non-negative integers, find the length of the longest subsequence such that the elements in the subsequence are consecutive integers. The consecutive numbers can be in any order.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [2, 6, 1, 9, 4, 5, 3]`  
**Output:**  
`6`  
**Explanation:**  
The consecutive numbers are `[1, 2, 3, 4, 5, 6]`. These 6 numbers form the longest consecutive subsequence.

**Input:**  
`arr[] = [1, 9, 3, 10, 4, 20, 2]`  
**Output:**  
`4`  
**Explanation:**  
The consecutive numbers are `[1, 2, 3, 4]`. These 4 numbers form the longest consecutive subsequence.

**Input:**  
`arr[] = [15, 13, 12, 14, 11, 10, 9]`  
**Output:**  
`7`  
**Explanation:**  
The consecutive numbers are `[9, 10, 11, 12, 13, 14, 15]`. These 7 numbers form the longest consecutive subsequence.

### Constraints:

- $`1 <= arr.size() <= 10^5`$
- $`0 <= arr[i] <= 10^5`$

## 🎯 **My Approach:**

1. **Set-based Consecutive Detection**:  
   The core idea is to leverage a hash set for fast lookups.

   - Insert all elements of the array into a set.
   - For each number in the set, check if it is the starting number of a sequence (i.e., `num - 1` is not in the set).
   - If it is a starting number, count how many consecutive numbers exist in the sequence.
   - Keep track of the maximum sequence length.

2. **Steps**:
   - Add all elements of the array to a hash set.
   - Traverse each number in the set.
   - If a number is the start of a sequence, calculate the length of the sequence.
   - Update the maximum sequence length as required.

## 🕒 **Time and Auxiliary Space Complexity**

- **Expected Time Complexity:** O(n), as we traverse the array and perform O(1) operations for each element using a hash set.
- **Expected Auxiliary Space Complexity:** O(n), as the hash set requires additional space to store all elements of the array.

## 📝 **Solution Code**

## Code (Python)

```python
class Solution:
    def longestConsecutive(self, arr):
        num_set = set(arr)
        longest = 0

        for num in num_set:
            if num - 1 not in num_set:
                current, count = num, 1
                while current + 1 in num_set:
                    current += 1
                    count += 1
                longest = max(longest, count)

        return longest
```

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on LinkedIn: [Any Questions](https://www.linkedin.com/in/abhay-valand-4aa92723a/). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
