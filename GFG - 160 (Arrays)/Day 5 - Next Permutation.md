---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Arrays
  - permutation
  - constructive algo
---

# 🚀 _Day 5. Next Permutation_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/next-permutation5226)

## 💡 **Problem Description:**

Given an array of integers `arr[]` representing a permutation, implement the next permutation that rearranges the numbers into the lexicographically next greater permutation. If no such permutation exists, rearrange the numbers into the lowest possible order (i.e., sorted in ascending order).

**Note:** A permutation of `n` numbers is any possible arrangement of all the integers in the range `[1, n]`, where each integer occurs exactly once.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr = [2, 4, 1, 7, 5, 0]`  
**Output:**  
`[2, 4, 5, 0, 1, 7]`

**Explanation:**  
The next permutation of the given array is `[2, 4, 5, 0, 1, 7]`.

**Input:**  
`arr = [3, 2, 1]`  
**Output:**  
`[1, 2, 3]`

**Explanation:**  
As `arr[]` is the last permutation, the next permutation is the lowest one.

**Input:**  
`arr = [3, 4, 2, 5, 1]`  
**Output:**  
`[3, 4, 5, 1, 2]`

**Explanation:**  
The next permutation of the given array is `[3, 4, 5, 1, 2]`.

### Constraints:

- `1 ≤ arr.size() ≤ 10^5`
- `1 ≤ arr[i] ≤ 10^5`

## 🎯 **My Approach:**

1. **Identify the Pivot:**

   - Start from the rightmost side of the array and find the first index `i` such that `arr[i] < arr[i+1]`.
   - This index `i` is the pivot where the next permutation needs to be modified.

2. **Swap with Successor:**

   - Find the smallest element on the right of `i` that is greater than `arr[i]` and swap them. This ensures the permutation becomes lexicographically larger.

3. **Reverse the Suffix:**
   - Reverse the elements from `i+1` to the end of the array to get the next smallest permutation.

## 🕒 **Time and Auxiliary Space Complexity**📝

- **Expected Time Complexity:** O(n), as we traverse the array multiple times to find the pivot, the successor, and reverse the suffix.
- **Expected Auxiliary Space Complexity:** O(1), as we only use a constant amount of additional space for temporary variables.

## 📝 **Solution Code**



## Code (Python)

```python
class Solution:
    def nextPermutation(self, arr):
        n = len(arr)
        i = n - 2

        while i >= 0 and arr[i] >= arr[i + 1]:
            i -= 1

        if i >= 0:
            j = n - 1

            while arr[j] <= arr[i]:
                j -= 1

            arr[i], arr[j] = arr[j], arr[i]

        arr[i + 1:] = reversed(arr[i + 1:])
```

# 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on LinkedIn: [Any Questions](https://www.linkedin.com/in/abhay-valand-4aa92723a/). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

