## Question

Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Note that an empty string is also considered valid.

Example1:
```
Input: "()"
Output: true
```

Example2:
```
Input: "()[]{}"
Output: true
```

Example3:
```
Input: "(]"
Output: false
```

Example4:
```
Input: "([)]"
Output: false
```

Example5:
```
Input: "{[]}"
Output: true
```

参照：https://leetcode.com/problems/valid-parentheses/


## MyAnswer
```
class solution:
   def isvalid(self, str):
        x, y = [], {"(": ")", "{": "}", "[": "]"}
        for parenthese in str:
            if parenthese in y:
                x.append(parenthese)
            elif len(x) == 0 or y[x.pop()] != parenthese:
                return False
        return len(x) == 0
```