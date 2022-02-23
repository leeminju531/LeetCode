### 알고리즘 

내풀이     
![1](https://user-images.githubusercontent.com/70446214/155277813-beb55866-e2cc-455f-87d6-5c843351c68b.png)

-> O(nlogn) runtime , O(1) Space 풀이 
-> 다른 이도 유사한 풀이
<br></br>

### python 

-> 파이썬으로 풀려다 sort 사용법을 몰랐음

### 1. 기본 정렬 방법 (sort , sorted)    

a ) sorted( 리스트 )     
-> 정렬된 리스트를 반환      
-> 리스트를 포함한 iterable 한 객체를 받을 수 있다.     

b ) list.sort()     
-> 리스트를 in-place 정렬     

### 2. sort와 sorted 에는 특정 정렬 기준을 정하기 위한 key 매개변수가 존재한다.    
key는 정렬 기준의 함수를 넣어주어야 한다. 보통 해당 부분을 python의 람다 함수로 채워줄 수 있다.    
![3](https://user-images.githubusercontent.com/70446214/155319679-7c3677b0-0d9d-4b2b-a360-8aee94d1ce15.png)   

### 3. 둘 다 reversed 매개변수를 가지고 있다.     
-> reverse = False(오름차순) 이다.    

<br></br>

### c++ 

-> lamda에 대해서 궁금사항 -> [] [=] [&] understand ok
