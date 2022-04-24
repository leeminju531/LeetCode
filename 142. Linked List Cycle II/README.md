### 내풀이
바로 이전에 배운 Floyd's Detection Algorithm 
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
    ListNode *detectCycle(ListNode *head) {
        if(!head)   return nullptr;
        ListNode *fast,*slow;
        fast = slow = head;
        while( fast != nullptr && fast->next != nullptr && slow != nullptr)
        {
            slow = slow->next;
            fast = fast->next->next;
            if(slow == fast)
            {
                slow = head;
                while(slow != fast)
                {
                    slow = slow->next;
                    fast = fast->next;
                }
                return slow;
            }
        }
        return nullptr;
    }
};
```

### 개선 가능 부분 
while문 조건문 의미 -> Cycle이 가능할 때 까지를 의미했음
```cpp
while(fast != nullptr && slow != nullptr)
{
  slow = slow->next;
  fast = fast->next;
  if(fast->next == nullptr) break;
  fast = fast->next;
  /*do something*/
}
```
위와 같은 조건문을 만드는게 가독성이 더 좋
