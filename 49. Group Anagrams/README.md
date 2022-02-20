### 내 풀이  
-> 최적 풀이를 잘 모르겠음 ...   
-> O(n^2) runtime , O(n) Space Complexity 방안은 떠올림   
![1](https://user-images.githubusercontent.com/70446214/154856986-07947c9e-f2e5-49b3-a6e6-9f68c47a5873.png)

-> 개 더러움 , 구현 실수 디버깅 못찾기 딱좋음....  


<br></br>
### 알고리즘 풀이   
![1](https://user-images.githubusercontent.com/70446214/154859136-2d250642-babd-49f3-b65f-358aacc2cf12.png)
-> ㅈㄴ깔끔해    
-> 위 풀이는 문자의 길이가 평균 m이라고 할때   
-> ***O(n*mlogm) runtime , O(n) space Complexity***   
![2](https://user-images.githubusercontent.com/70446214/154859139-d403fc0d-479f-427c-a7b9-a876528e25bd.png)
    
-> 이는 ***Counting Sort 정렬법을 이용하면 O(n*m) runtime***이 가능하다.   
<br></br>
### C++   
unordered_map<string, vector<string>> mp;   
  
1. ***해쉬에는 value를 vector로 갖도록 정의할 수 있다*** !! (이 구조를 몰랐음 !! )    
  
2. mp 작명 좋은데?     
  for(auto p : mp)로 순회할때도 이름 적당 ! 
  
3. for(auto p : mp) 위 방법으로 해쉬도 손쉽게 순회 가능함 !     
