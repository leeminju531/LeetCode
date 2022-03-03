### 내 풀이    

-> 문제조건에선 o(m+n)의 알고리즘을 요구.   
-> o(n)으로 어떤 알고리즘으로 처리할 수 있을지 모르겠음    
-> hash set과 brute force iteration을 이용해     
-> O(mn^2) runtime , O(2m) space complexity 알고리즘은 구상    
-> 일단구현   
-> 정확도는 맞으나 Time limited Exceed !     
      
![1](https://user-images.githubusercontent.com/70446214/156504980-3b69ae73-051d-4805-b19a-07ecfdeeac5f.png)   
  
## python 
### 1. collections.Counter     
구현에서 dictionary에서 "char : count" 형태로 저장했는데,    
***collections 모듈의 Counter를 이용하면 이를 한줄로 깔끔하게 처리***할 수 있다.    
또한 결과 타입은 collections.Counter 이지만, 딕셔너리처림 사용할 수 있는것으로 보인다.    
![1](https://user-images.githubusercontent.com/70446214/156505908-e4a80b7e-b914-416f-8c28-fac2e5f61a2d.png)   

***Counter를 이용한 결과물은 해쉬***라고 봐도 무방하다.


dictionary와 차이점   
~~~
# case of dictionary
dict = {'a':1,'b':2}       
dict['c'] 
# occured error !     
~~~

~~~
# case of collections.Counter
counter = {'a':1,'b':2} # dict 아님 ! 편의를 위함
counter['c'] += 1
# result = {'a':1,'b':2,'c':1}
~~~
사소하지만 c++의 hash와 같은 느낌 !

### 2. enumerate -> iterater한 객체의 별개 값과 인덱스를 같이 반환 (이는 range(len)을 이용한 것보다 파이썬에서 추천하는 방식임)
![1](https://user-images.githubusercontent.com/70446214/156513643-973ef788-5fef-4b1e-bc05-35391f007748.png)

![1](https://user-images.githubusercontent.com/70446214/156513882-eeb71238-7d2e-4534-92ec-e90451da8eab.png)     
***start라는 매개변수도 있음 ! (시작 인덱스를 0이 아닌 다른값으로 '인덱스 네이밍'을 변경할 수 있음)***


### Most Voted Solution   
1.
![1](https://user-images.githubusercontent.com/70446214/156511526-b861ed3a-dbd5-456c-bd6d-9733a79f56a1.png)   

-> hash를 이용한 것은 같음 ! 하지만 내가 이용한 brute force한 iteration이 아닌 1회전의 iteration으로 구현되었다.    
-> 핵심은 한번의 iteration안에서 ***Missing변수와 ,정답을 찾은 이후 hash를 조작***하여 1회전의 iteration을 살려낸 것으로 보인다.  

2. Top Discussion : Here is a 10-line template that can solve most 'substring' problems     

https://leetcode.com/problems/minimum-window-substring/discuss/26808/Here-is-a-10-line-template-that-can-solve-most-'substring'-problems
