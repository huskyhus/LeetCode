# Step 1

(6:34)

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* first = head;
        ListNode* second = head;

        while (second != nullptr){
            if (first->val == second->val) {
                second = second->next;
                first->next = second;
            }
            else {
                first = second;
                second = second->next;
            }
        }

        return head;
    }
};
```

# Step 2

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode *current = head;

        while (current != nullptr && current->next != nullptr) {
            if (current->val == current->next->val) {
                current->next = current->next->next;
            }
            else {
                current = current->next;
            }
        }

        return head;
    }
};
```

# Step 3

(1:50)

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* current = head;

        while (current != nullptr && current->next != nullptr) {
            if (current->val == current->next->val) {
                current->next = current->next->next;
            }
            else {
                current = current->next;
            }
        }

        return head;
    }
};
```
