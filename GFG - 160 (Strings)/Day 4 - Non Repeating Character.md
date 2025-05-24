
# 🚀 _Day 4. Non-Repeating Character_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/non-repeating-character-1587115620)

## 💡 **Problem Breakdown:**

Given a string `s` consisting of lowercase Latin letters, return the first non-repeating character in `s`. If there is no non-repeating character, return `'$'`.

**Note:** When you return `'$'`, the driver code will output `-1`.

## 🔍 **Example Walkthrough:**

**Input:**  
`s = "geeksforgeeks"`  
**Output:**  
`'f'`

**Explanation:**  
In the given string, `'f'` is the first character in the string which does not repeat.

**Input:**  
`s = "racecar"`  
**Output:**  
`'e'`

**Explanation:**  
In the given string, `'e'` is the only character in the string which does not repeat.

**Input:**  
`s = "aabbccc"`  
**Output:**  
`-1`

**Explanation:**  
All the characters in the given string are repeating.

### Constraints:

- $`1 <= s.size() <= 10^5`$

## 🎯 **My Approach:**

1. **Frequency Array Method**:

   - Since the input consists only of lowercase Latin letters, a frequency array of size `26` is sufficient to count occurrences of each character.
   - Traverse the string once to update the frequency of each character in the array.
   - Traverse the string a second time to identify the first character with a frequency of `1`.

2. **Steps:**
   - Initialize a frequency array `freq[26]` and set all elements to `0`.
   - For each character in the string, increment its corresponding frequency in the array.
   - Iterate through the string again, checking for the first character with a frequency of `1`.
   - If no such character exists, return `'$'`.

## 🕒 **Time Complexity:**

- **Expected Time Complexity:** O(n), where `n` is the size of the string. The algorithm requires two linear passes through the string.
- **Expected Auxiliary Space Complexity:** O(1), as the frequency array uses a fixed amount of additional space (`26` elements).

## 📝 **Solution Code**


## Code (Python)

```python
class Solution:
    def nonRepeatingChar(self, s):
        freq = [0] * 26
        for c in s:
            freq[ord(c) - ord('a')] += 1
        for c in s:
            if freq[ord(c) - ord('a')] == 1:
                return c
        return '$'
```

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on LinkedIn: [Any Questions](https://www.linkedin.com/in/abhay-valand-4aa92723a/). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

