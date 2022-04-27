### 내풀이
```cpp
class Solution {
public:
    ListNode* sortList(ListNode* head) {
        if(!head)   return nullptr;
        typedef pair<ListNode* , int> ptrVal; // pointer - value
        vector<ptrVal> v;
        ListNode* dummy = new ListNode(-1); dummy->next = head;
        while( (dummy = dummy->next) != nullptr )
            v.emplace_back(ptrVal(dummy,dummy->val));
        sort(v.begin(),v.end(),[](const ptrVal& lhs,const ptrVal& rhs){
            return lhs.second<rhs.second;
        });
        for(int i=0;i<v.size()-1;i++)
            (v[i].first)->next = v[i+1].first;
        (v.back().first)->next = nullptr;
        return v[0].first;
    }
};
```

10분 컷 ! good !      
-> Time : O(nlogn) , Space : O(n)     

### Most Voted 
```cpp
class Solution {
public:
    ListNode* sortList(ListNode* head) {
        //If List Contain a Single or 0 Node
        if(head == NULL || head ->next == NULL)
            return head;
        
        
        ListNode *temp = NULL;
        ListNode *slow = head;
        ListNode *fast = head;
        
        // 2 pointer appraoach / turtle-hare Algorithm (Finding the middle element)
        while(fast !=  NULL && fast -> next != NULL)
        {
            temp = slow;
            slow = slow->next;          //slow increment by 1
            fast = fast ->next ->next;  //fast incremented by 2
            
        }   
        temp -> next = NULL;            //end of first left half
        
        ListNode* l1 = sortList(head);    //left half recursive call
        ListNode* l2 = sortList(slow);    //right half recursive call
        
        return mergelist(l1, l2);         //mergelist Function call
            
    }
    
    //MergeSort Function O(n*logn)
    ListNode* mergelist(ListNode *l1, ListNode *l2)
    {
        ListNode *ptr = new ListNode(0);
        ListNode *curr = ptr;
        
        while(l1 != NULL && l2 != NULL)
        {
            if(l1->val <= l2->val)
            {
                curr -> next = l1;
                l1 = l1 -> next;
            }
            else
            {
                curr -> next = l2;
                l2 = l2 -> next;
            }
        
        curr = curr ->next;
        
        }
        
        //for unqual length linked list
        
        if(l1 != NULL)
        {
            curr -> next = l1;
            l1 = l1->next;
        }
        
        if(l2 != NULL)
        {
            curr -> next = l2;
            l2 = l2 ->next;
        }
        
        return ptr->next;
    }
};
```
이는 O(1) Space로 설명하지만,     
-> 재귀 구조로 Stack Frame 고려하면 O(n)으로도 볼 수 있을듯 !    
-> 실제로 메모리는 내풀이보다 더나옴     
  
배운점   
1. turtle-hare Algorithm이 Middle Point를 찾기 위해 사용할 수도 있음       
2. 같은문제를 재귀 구조로 풀이 >> 생각해내기 쉽지는 않아보여,,귯       
