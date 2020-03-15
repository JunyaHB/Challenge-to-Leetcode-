## Question
Given an array of non-negative integers, you are initially positioned at the first index of the array.
Each element in the array represents your maximum jump length at that position.
Determine if you are able to reach the last index.

Example1:
```
Input: [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
```

Example2:
```
Input: [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum
             jump length is 0, which makes it impossible to reach the last index.
```

参照：https://leetcode.com/problems/jump-game/


## My Wrong Answer
```
class Solution:
    def canJump(self, nums):
        if 0 in nums:
            zero_position = nums.index(0)
            if zero_position == 0:
                return False
            i = zero_position - 1
            decision_list = []
            while i >= 0:
                if nums[i] <= zero_position - i:
                    decision_list += "False"
                else:
                    decision_list += "True"
                i -= 1
            if "True" in decision_list:
                return True
            else:
                return False
        else:
            return True
```

## Better Answer
```
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        n = len(nums)-1
        for i in range(n-1,-1,-1):
            if nums[i] + i>=n:
                n = i
        return n == 0
```