# Step 1 (using std::set)

(6:05)

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        std::set<ListNode*> visited = {};
        ListNode *currentPos = head;

        while (currentPos != nullptr){
            if (visited.contains(currentPos)){
                return currentPos;
            }
            visited.insert(currentPos);
            currentPos = currentPos->next;
        }

        return nullptr;

    }
};
```

# Step 1 (Floyd)

(7:00)

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        if (head == nullptr || head->next == nullptr) {
            return nullptr;
        }

        ListNode *slow = head->next;
        ListNode *fast = head->next->next;
        ListNode *third = head;

        while (slow != fast) {
            if(fast == nullptr || fast->next == nullptr) {
                return nullptr;
            }
            slow = slow->next;
            fast = fast->next->next;
        }

        while (slow != third) {
            slow = slow->next;
            third = third->next;
        }

        return third;
    }

};
```

# Step 2

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode *slow = head;
        ListNode *fast = head;
        ListNode *third = head;

        bool isAcyclic = true;

        // determine whether acylic or not
        while (fast != nullptr && fast->next != nullptr) {
            slow = slow->next;
            fast = fast->next->next;
            if (slow == fast) {
                isAcyclic = false;
                break;
            }
        }

        if (isAcyclic) {
            return nullptr;
        }

        // if cyclic, determine where the cycle begins
        while (third != slow) {
            third = third->next;
            slow = slow->next;
        }

        return third;
    }
};
```

# Step 3

(2:50)

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode *slow = head;
        ListNode *fast = head;
        ListNode *third = head;
        bool isAcyclic = true;

        while (fast != nullptr && fast->next != nullptr) {
            slow = slow->next;
            fast = fast->next->next;
            if (slow == fast) {
                isAcyclic = false;
                break;
            }
        }

        if (isAcyclic) {
            return nullptr;
        }

        while (third != slow) {
            third = third->next;
            slow = slow->next;
        }

        return third;
    }
};
```

# Step 2 (do-while for clarity)

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode *slow = head;
        ListNode *fast = head;
        ListNode *third = head;

        do {
            if(fast == nullptr || fast->next == nullptr) {
                return nullptr;
            }
            slow = slow->next;
            fast = fast->next->next;
        } while (slow != fast);

        while (third != slow) {
            third = third->next;
            slow = slow->next;
        }
        return third;
    }
};
```

# Step 3

(2:00)

```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode *slow = head;
        ListNode *fast = head;
        ListNode *third = head;

        do {
            if (fast == nullptr || fast->next == nullptr) {
                return nullptr;
            }
            slow = slow->next;
            fast = fast->next->next;
        } while (slow != fast);

        while (third != slow) {
            third = third->next;
            slow = slow->next;
        }
        return third;
    }
};
```
