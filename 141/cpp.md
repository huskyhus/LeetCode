# Step 3

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode* head) {
        if (head == nullptr) {
            return false;
        }

        ListNode* fastCursor = head->next;
        ListNode* slowCursor = head;

        while (fastCursor != slowCursor) {
            if (fastCursor == nullptr) {
                return false;
            }
            if (fastCursor->next == nullptr) {
                return false;
            }

            fastCursor = fastCursor->next->next;
            slowCursor = slowCursor->next;
        }

        return true;
    }
};
```
