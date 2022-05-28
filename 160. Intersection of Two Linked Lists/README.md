### 내풀이
```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        unordered_set<ListNode*> hashSet;
        ListNode* dummyA = new ListNode;
        dummyA->next = headA;
        while( (dummyA=dummyA->next) ){
            hashSet.insert(dummyA);
        }
        ListNode* dummyB = new ListNode;
        dummyB->next = headB;
        while( (dummyB = dummyB->next) ){
            if(hashSet.find(dummyB) != hashSet.end())
                return dummyB;
        }
        return nullptr;
        
    }
};
```
space complexity : O(n)
time complexity : O(n)

### Top Voted Solution
space complexity : O(1)
time complexity : O(n)

1. Concatenate list A and list B, ***if there's an intersection, there's a loop***    
=> Floyd Cycle 알고리즘 이용 가능     
=> 아이디어 대박    
```python
class Solution(object):
    def getIntersectionNode(self, A, B):
        if not A or not B: return None

        # Concatenate A and B
        last = A
        while last.next: last = last.next
        last.next = B

        # Find the start of the loop
        fast = slow = A
        while fast and fast.next:
            slow, fast = slow.next, fast.next.next
            if slow == fast:
                fast = A
                while fast != slow:
                    slow, fast = slow.next, fast.next
                last.next = None
                return slow

        # No loop found
        last.next = None
        return None
```
2. 
1) 각각의 길이를 잰다.
2) Intersection의 똑같이 떨어진 위치로 옮긴다.
3) 각각 다음노드를 순회하면서 Intersection Point를 찾는다.
```java
public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
    int lenA = length(headA), lenB = length(headB);
    // move headA and headB to the same start point
    while (lenA > lenB) {
        headA = headA.next;
        lenA--;
    }
    while (lenA < lenB) {
        headB = headB.next;
        lenB--;
    }
    // find the intersection until end
    while (headA != headB) {
        headA = headA.next;
        headB = headB.next;
    }
    return headA;
}

private int length(ListNode node) {
    int length = 0;
    while (node != null) {
        node = node.next;
        length++;
    }
    return length;
}

```
