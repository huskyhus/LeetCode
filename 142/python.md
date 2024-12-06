# Step 3

```python
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow = head
        fast = head
        third = head
        is_acyclic = True

        while fast is not None and fast.next is not None:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                is_acyclic = False
                break

        if is_acyclic:
            return None

        while third != slow:
            slow = slow.next
            third = third.next

        return third
```
