## Question
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:
```
Given nums = [2, 7, 11, 15], target = 9,
Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```
参照：https://leetcode.com/problems/two-sum/


## MyAnswer
```
def two_sum(nums, target)
    i = 0
    while i < nums.length do
         j = i + 1
         while j < nums.length do
             if nums[j] == target - nums[i]
                 return i, j
             end
             j += 1
         end
         i += 1
     end
 end
 
 two_sum([2, 7, 11, 15], 9)
```