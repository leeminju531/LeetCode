### me
-> 문제 해결 방식은 Most Voted Solution 과 다르지 않음     
-> 알고리즘과 실제 구현을 못함. (리턴 타입으로 적당한 메모리 구조 생각 못함 )   

### Most Voted    
![1](https://user-images.githubusercontent.com/70446214/160779943-384392db-0005-4f41-86d9-0136c083e4ec.png)   
    
0. 완전 탐색을 요하며 문제에서 Recursion 요구는 명백함    
-> backtracking 풀이 ( ***backtracking algorithm uses the depth-first search method*** )    

1. 만족하는 palindrome를 path에 추가해 base case 에서 result에 넣어주는 방식 !  << 이 구조를 생각하지 못함.     

2. Time Complexity 계산     
![1](https://user-images.githubusercontent.com/70446214/160781315-97cf6289-cd1e-46b2-abf9-5df3f0928ffa.png)

### python      
![image](https://user-images.githubusercontent.com/70446214/161240776-46dc40ef-ffd7-42a0-954c-68b9669a8a2c.png)           

![image](https://user-images.githubusercontent.com/70446214/161240835-238f10f9-fd10-4e19-a810-a6cc41e9df6a.png)     
mutable 한 객체 (특히 list)는 pass by reference로 받는다.         
주의 !!       
