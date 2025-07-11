

# 🚀 _Day 3. Find All Triplets with Zero Sum_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/hashing-gfg-160/problem/find-all-triplets-with-zero-sum)

## 💡 **Problem Description:**

Given an array `arr[]` of size `n`, the task is to find all possible triplets `i`, `j`, `k` such that `arr[i] + arr[j] + arr[k] = 0`, and the triplets should be returned in a sorted form, i.e., `i < j < k`.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [0, -1, 2, -3, 1]`  
**Output:**  
`[[0, 1, 4], [2, 3, 4]]`  
Explanation:  
The triplets with a sum of zero are:

- `arr[0] + arr[1] + arr[4] = 0 + (-1) + 1 = 0`
- `arr[2] + arr[3] + arr[4] = 2 + (-3) + 1 = 0`

**Input:**  
`arr[] = [1, -2, 1, 0, 5]`  
**Output:**  
`[[0, 1, 2]]`  
Explanation:  
Only one triplet satisfies the condition: `arr[0] + arr[1] + arr[2] = 1 + (-2) + 1 = 0`

**Input:**  
`arr[] = [2, 3, 1, 0, 5]`  
**Output:**  
`[]`  
Explanation:  
No triplet with sum 0.

### Constraints:

- $`3 <= arr.size() <= 10^3`$
- $`-10^4 <= arr[i] <= 10^4`$

## 🎯 **My Approach:**

1. **Optimized Approach using Hash Map**:

   - We use a hash map to store the sum of pairs of elements in the array.
   - For each element `arr[i]`, check if the negative of that element exists as a sum of some pair `(arr[j] + arr[k])`. If so, it's a valid triplet.
   - Ensure that no index is repeated by sorting and using a set to store the triplets in a sorted manner.

2. **Steps:**
   - Traverse the array and for each element `arr[i]`, calculate the pair sum `target = -arr[i]`.
   - Use a hash map to find if a pair `(arr[j] + arr[k])` exists where `j != i` and `k != i`.
   - Add the triplet `(i, j, k)` into the result after ensuring it's sorted.

## 🕒 **Time and Auxiliary Space Complexity**

- **Expected Time Complexity:** $O(n^2)$, where `n` is the size of the array. This is because for each element, we check pairs of the remaining elements.
- **Expected Auxiliary Space Complexity:** $O(n^2)$, where `n` is the size of the array. We use additional space to store the hash map and results.

## 📝 **Solution Code**
`

## Code (Python)

```python
class Solution:
    def findTriplets(self, arr):
        n = len(arr)
        result = set()
        pair_sum_map = {}

        for i in range(n):
            for j in range(i + 1, n):
                pair_sum = arr[i] + arr[j]
                if pair_sum not in pair_sum_map:
                    pair_sum_map[pair_sum] = []
                pair_sum_map[pair_sum].append((i, j))

        for i in range(n):
            target = -arr[i]
            if target in pair_sum_map:
                for pair in pair_sum_map[target]:
                    if i not in pair:
                        triplet = tuple(sorted([i, pair[0], pair[1]]))
                        result.add(triplet)

        return sorted([list(triplet) for triplet in result])
```

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, please visit my LinkedIn: [Any Questions](https://www.linkedin.com/in/abhay-valand-4aa92723a/). Thank you for your input; together, we strive to create a space where learning is a collaborative endeavor.

⭐ Star this repository if you find it helpful or intriguing! ⭐

---
