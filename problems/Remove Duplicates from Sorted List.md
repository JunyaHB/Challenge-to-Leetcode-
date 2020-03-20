## Question
Given a sorted linked list, delete all duplicates such that each element appear only once.

Example1:
```
Input: 1->1->2
Output: 1->2
```

Example2:
```
Input: 1->1->2->3->3
Output: 1->2->3
```

参照：https://leetcode.com/problems/remove-duplicates-from-sorted-list/


## My Wrong Answer
```
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:        
        pointer = head
        while pointer and pointer.next:
            if pointer.val == pointer.next.val:
                pointer.next = pointer.next.next
            else:
                pointer = pointer.next
        return head
        
```
