### 내풀이
-> 설계 핵심 자료구조 뿐 아니라 구현에도 어려움을 느낌


### 핵심 사항 

    가장 덜 사용한 key를 찾기위한 적합한 자료구조
    
=> O(1)의 삽입과 삭제 Complexity에서 Hash의 사용은 자명했는데    
-> 위 문제 조건을 만족시키는 아키텍쳐에 어려움을 느낌   
    
=> 해답은 ***링크드 리스트.***   
-> 링크드 리스트를 잘 설계하면,     
-> 어떤 위치에 존재하는 노드를 꺼내와 다른 곳에 삽입해도   
-> O(1) 시간복잡도를 갖는다.   

```cpp
class LRUCache {
public:
    LRUCache(int capacity):capacity_(capacity) {
        
    }
    
    int get(int key) {
        if(!kv.count(key))  return -1;
        updateLRU(key);
        return kv[key]; 
    }
    
    void put(int key, int value) {
        if(kv.size() == capacity_ && kv.count(key) == 0)
            evict();
        kv[key] = value;
        updateLRU(key);
    }
    void updateLRU(int key)
    {
        if(mp.count(key))
            lru.erase(mp[key]);
        lru.push_front(key);
        mp[key] = lru.begin();
    }
    void evict()
    {
        mp.erase(lru.back());
        kv.erase(lru.back());
        lru.pop_back();
    }
private:
    int capacity_;
    list<int> lru; // least recently used cache - front : lastest
    unordered_map<int,list<int>::iterator> mp; // key - iterator
    unordered_map<int,int> kv; // key - value
};


```

1. **링크드 리스트를 위해 cpp에서는 list라는 자료구조를 제공**   
2. Iterator는 Pointer를 구조화한 객체로 생각하는 게 쉽다.   
3. 함수형으로 분리해 독립적으로 생각해내는 것 -> 이것도 부족해서 구현이 어려웠음.    
