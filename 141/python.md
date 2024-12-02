# Step 3

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        if head is None:
            return False

        fastCursor = head.next
        slowCursor = head

        while fastCursor != slowCursor:
            if fastCursor is None:
                return False
            if fastCursor.next is None:
                return False

            fastCursor = fastCursor.next.next
            slowCursor = slowCursor.next

        return True

```
