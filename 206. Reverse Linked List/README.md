### 내풀이

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        
        ListNode* p0 = nullptr;
        ListNode* p1;
        
        while(head != nullptr ){
            p1 = head->next;
            head ->next = p0;
            p0 = head;
            head = p1;
        }
        return p0;
        
    }
};
```
space : O(1)      
time : O(n)

good ! 

