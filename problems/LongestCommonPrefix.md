## Question
Write a function to find the longest common prefix string amongst an array of strings.
If there is no common prefix, return an empty string "".

Example 1:
```
Input: ["flower","flow","flight"]
Output: "fl"
```

Example 2:
```
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

参照：https://leetcode.com/problems/longest-common-prefix/


## MyAnswer
```
class Solution:
    def longestCommonPrefix(self, strs):
        x = strs[0]
        y = strs[1]
        z = strs[2]

        i, j, k = 0, 0, 0

        commonPrefix = ""

        while i < len(x):
            j, k = 0, 0
            while j < len(y):
                k = 0
                while k < len(strs[2]):
                    if x[i] == y[j] == z[k]:
                        commonPrefix += z[k]
                    k += 1
                j += 1
            i += 1
        return commonPrefix
```

## Other Answer
```
class Solution:
    def longestCommonPrefix(self, strs):
        longest_pre = ""
        if not strs: return longest_pre
        shortest_str = min(strs, key=len)
        for i in range(len(shortest_str)):
            if all([x.startswith(shortest_str[:i+1]) for x in strs]):
                longest_pre = shortest_str[:i+1]
            else:
                break
        return longest_pre
```
引用：https://medium.com/@d_dchris/10-methods-to-solve-the-longest-common-prefix-problem-using-python-leetcode-14-a87bb3eb0f3a