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
        if x < 0 or x != int(str(abs(x))[::-1]):
            return False
        else:
            return True
        
print(Solution().isPalindrome(121))
print(Solution().isPalindrome(-121))
print(Solution().isPalindrome(10))
```
