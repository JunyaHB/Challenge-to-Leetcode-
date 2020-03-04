## Question
Given a 32-bit signed integer, reverse digits of an integer.

Example 1:
```
Input: 123
Output: 321
```

Example 1:
```
Input: -123
Output: -321
```

Example 1:
```
Input: 120
Output: 21
```
参照：https://leetcode.com/problems/reverse-integer/


## MyAnswer
```
class Solution:
    def reverseInt(self, x):
        str_x = str(x)
        reverse_int = ""
        i = len(str_x) - 1
        while i >= 0:
            if str_x[i] == "-":
                reverse_int = str_x[i] + reverse_int
                i -= 1
            else:
                reverse_int += str_x[i]
                i -= 1
        if reverse_int[0] == "0":
            return reverse_int[1:]
        else:
            return reverse_int
    
print(Solution().reverseInt(123))
print(Solution().reverseInt(-123))
print(Solution().reverseInt(120))
```

## Better Answer
```
class Solution(object):
   def reverse(self, x):
       if int(str(abs(x))[::-1])> 2**31 :
           return(0)
       elif x < 0 : 
           return(-int(str(-x)[::-1]))
       else:
           return(int(str(x)[::-1]))
```
引用：https://note.com/tokitky/n/n0ab0e00d0848