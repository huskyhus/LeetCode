# Step 1

(infinity)

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if (head == nullptr) {
            return head;
        }

        ListNode dummy(-999, head);
        ListNode* prev = &dummy;
        ListNode* current = head;

        while (current != nullptr) {
            if (current->next != nullptr && current->val == current->next->val) {
                while (current->next != nullptr && current->val == current->next->val) {
                    current = current->next;
                }
                prev->next = current->next;
            } else {
                prev->next = current;
                prev = current;
            }
            current = current->next;
        }

        return dummy.next;
    }
};
```

# Step 2

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode dummy(0, head);
        ListNode* prev = &dummy;
        ListNode* current = head;

        while (current != nullptr) {
            if (current->next != nullptr && current->val == current->next->val) {
                while (current->next != nullptr && current->val == current->next->val) {
                    current = current->next;
                }
                prev->next = current->next;
            } else {
                prev = current;
            }
            current = current->next;
        }

        return dummy.next;
    }
};
```

# Step 3

(5:00)

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode dummy(0, head);
        ListNode *prev = &dummy;
        ListNode *current = head;

        while (current != nullptr) {
            if (current->next != nullptr && current->val == current->next->val) {
                while (current->next != nullptr && current->val == current->next->val) {
                    current = current->next;
                }
                prev->next = current->next;
            }
            else {
                prev = current;
            }
            current = current->next;
        }

        return dummy.next;
    }
};
```
