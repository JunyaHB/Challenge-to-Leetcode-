## Question
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Example:
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
参照：https://leetcode.com/problems/roman-to-integer/


## MyAnswer
```
class Solution:
    def romanToInt(self, s):
        roman_val = {"I": 1, "V": 5, "X":10, "L": 50, "C": 100, "D": 500, "M": 1000} 
        total_val = 0
        for i in range(len(s)):
            if i > 0 and roman_val[s[i]] > roman_val[s[i-1]]:
                total_val += roman_val[s[i]] - 2 * roman_val[s[i-1]]
            else:
                total_val += roman_val[s[i]]
        return total_val
    
print(Solution().romanToInt("MMMCMLXXXVI"))
print(Solution().romanToInt("MMMM"))
print(Solution().romanToInt("C"))
```