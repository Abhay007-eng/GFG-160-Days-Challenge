
# 🚀 _Day 2. Add Binary Strings_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/add-binary-strings3805)

## 💡 **Problem Description:**

You are given two binary strings `s1` and `s2` consisting of only `0`s and `1`s. Find the resultant string after adding the two binary strings. The input strings may contain leading zeros, but the output string should not have any leading zeros.

## 🔍 **Example Walkthrough:**

**Input:**  
`s1 = "1101"`, `s2 = "111"`  
**Output:**  
`"10100"`

**Explanation:**

```
 1101
+ 111
—————
10100
```

**Input:**  
`s1 = "00100"`, `s2 = "010"`  
**Output:**  
`"110"`

**Explanation:**

```
 100
+ 10
 ———
 110
```

### Constraints:

- $`1 <= s1.size(), s2.size() <= 10^6`$

## 🎯 **My Approach:**

1. **Binary Addition Logic:**

   - The problem is a standard binary addition problem. We will iterate through the two strings from right to left, adding corresponding bits and considering a carry.
   - If both bits are `1`, we set the sum bit to `0` and carry `1`. If one bit is `1`, the sum bit is `1` with no carry, and if both bits are `0`, the sum bit is `0` with no carry.
   - The process continues until all digits are processed, and the carry is added if necessary.

2. **Steps:**
   - Start from the rightmost bit of both strings, keeping track of any carry from the previous step.
   - Add corresponding bits, including the carry, and append the result to a result string.
   - Continue the process until both strings are exhausted.
   - Reverse the result string (since we process from right to left) and remove any leading zeros.

## 🕒 **Time and Auxiliary Space Complexity**

- **Expected Time Complexity:** O(n), where `n` is the length of the longest string. We only perform a linear scan through the strings to perform the addition.
- **Expected Auxiliary Space Complexity:** O(n), as we store the result in a new string that may be of length up to the size of the input strings.

## 📝 **Solution Code**


## Code (Python)

```python
class Solution:
    def addBinary(self, s1, s2):
        i, j = len(s1) - 1, len(s2) - 1
        carry = 0
        result = []

        while i >= 0 or j >= 0 or carry > 0:
            sum_ = carry
            if i >= 0:
                sum_ += int(s1[i])
                i -= 1
            if j >= 0:
                sum_ += int(s2[j])
                j -= 1
            result.append(str(sum_ % 2))
            carry = sum_ // 2

        result.reverse()
        result_str = ''.join(result)
        first_non_zero = result_str.find('1')
        return result_str[first_non_zero:] if first_non_zero != -1 else "0"
```

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on LinkedIn: [Any Questions](https://www.linkedin.com/in/abhay-valand-4aa92723a/). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐


