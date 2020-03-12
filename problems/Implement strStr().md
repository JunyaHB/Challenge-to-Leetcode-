## Question

Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Example1:
```
Input: haystack = "hello", needle = "ll"
Output: 2
```

Example2:
```
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

Clarification:
What should we return when needle is an empty string? This is a great question to ask during an interview.
For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

参照：https://leetcode.com/problems/implement-strstr/


## MyAnswer 1
```
class Solution:
    def strStr(self, haystack, needle):
        if haystack.find(needle):
            return haystack.find(needle)
        return -1
```

## MyAnswer 2
```
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        for i in range(len(haystack) - len(needle)+1):
            if haystack[i:i+len(needle)] == needle:
                return i
        return -1
```