### 내 접근
너무 어려웠던 문제,,    
Brute Force -> O(n^2) runtime , O(1) space 풀이 가능    
개선된 풀이 생각하기 너무 어렵,,   
    
why ?     
1. 한번의 순회 안에서 논리적인 Sequence로 문제를 해결 (=O(n) runtime). 이 Sequence안에서 해결하는 방법 생각하기 넘 어렵  
2. Observation에서 계속 다양한 Edge Case가 보임 >> 아래 설명은 모두 양수인경우 부터 순차적으로 시퀀스를 생각해냄.    

### good explanation      
https://leetcode.com/problems/maximum-product-subarray/discuss/203013/C%2B%2B-O(N)-time-O(1)-space-solution-with-explanation
    
### Point     
1. Squence 안에서 Multiply를 하는 변수와 ***독립적으로 최대값을 반환하는 변수***를 사용 =>     
why? : running product가 최대값 이였던 적은 있어도 항상 최대값을 유지할 수 없었기 때문.    

2. 순차적으로 순회하면서, 개념적으로 Contiguous Sub array를 처리하기 위한 ***Windows Approach를 하나의 변수를 조건에 따라 reset***시키면서 쳐냈음.
