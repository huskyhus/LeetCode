# Step 3

```python
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0, head)
        prev = dummy
        current = head

        while current is not None:
            if current.next is not None and current.val == current.next.val:
                while current.next is not None and current.val == current.next.val:
                    current = current.next
                prev.next = current.next
            else:
                prev = current
            current = current.next

        return dummy.next
```
