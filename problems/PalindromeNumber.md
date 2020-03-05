## Question
Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

Example 1:
```
Input: 121
Output: true
```

Example 2:
```
Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

Example 3:
```
Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

参照：https://leetcode.com/problems/palindrome-number/


## MyAnswer
```
class Solution:
    def isPalindrome(self, x):
        str_x = str(x)
        reverse_x = ""
        i = len(str_x) - 1
        while i >= 0:
            reverse_x += str_x[i]
            i -= 1
        if str_x == reverse_x:
            return True
        else:
            return False
        
print(Solution().isPalindrome(121))
print(Solution().isPalindrome(-121))
print(Solution().isPalindrome(10))
```