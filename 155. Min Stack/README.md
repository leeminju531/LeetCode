### 내풀이     
-> 유명한 문제,  ***두개 스택 사용*** 
```cpp
class MinStack {
public:
    MinStack() {
        
    }
    
    void push(int val) {
        st.push_back(val);
        if(min_st.empty())  min_st.push_back(val);
        else
        {
            if(min_st.back() < val)
                min_st.push_back(min_st.back());
            else
                min_st.push_back(val);
        }
    }
    
    void pop() {
        min_st.pop_back();
        st.pop_back();
    }
    
    int top() {
        return st.back();
    }
    
    int getMin() {
        return min_st.back();
    }
    vector<int> st;
    vector<int> min_st;
};
```
