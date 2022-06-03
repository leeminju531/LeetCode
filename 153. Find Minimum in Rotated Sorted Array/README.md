### 내풀이     
이분탐색으로 끊어진 부분을 찾음

이전에 못푼 문젠데 오랫만에 푸니까 잘풀림,, 왜지

```cpp
class Solution {
public:
    int findMin(vector<int>& nums) {
        int l = 0,r=nums.size()-1;
        int mid;
        while(r-l > 1){
            mid = (l+r)/2;
            if(nums[l]<nums[mid]){
                l = mid;
            }
            else{ 
                r = mid;
            }
        }
        return nums[r]>nums[l] ? nums[0] : nums[r]; 
        
    }
}; 
```
