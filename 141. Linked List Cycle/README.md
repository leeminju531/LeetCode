### 내 풀이
![image](https://user-images.githubusercontent.com/70446214/164779601-3c3352e5-a482-4377-81fd-f38eac6891ed.png)

-> O(n) , O(n) Runtime , Space Complexity

### Most Voted Solution 
-> used ***Floyd's Cycle Finding Algorithm*** (turtle and hare alogirhm)
```cpp
class Solution {
public:
    bool hasCycle(ListNode *head) {
	
		// if head is NULL then return false;
        if(head == NULL)
            return false;
        
		// making two pointers fast and slow and assignning them to head
        ListNode *fast = head;
        ListNode *slow = head;
        
		// till fast and fast-> next not reaches NULL
		// we will increment fast by 2 step and slow by 1 step
        while(fast != NULL && fast ->next != NULL)
        {
            fast = fast->next->next;
            slow = slow->next;
            
			
			// At the point if fast and slow are at same address
			// this means linked list has a cycle in it.
            if(fast == slow)
                return true;
        }
        
		// if traversal reaches to NULL this means no cycle.
        return false;
    }
};
```

-> O(n) , O(1) Runtime , Space

### Floyd's Cycle algorithm

1. List의 ***순환 여부***를 찾을 수 있다.
2. List의 ***순환이 시작되는 노드***를 찾을 수 있다.

2의 가장 간단한 증명 이해 https://namho46.tistory.com/14
