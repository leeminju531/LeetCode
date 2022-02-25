### 내풀이     
![1](https://user-images.githubusercontent.com/70446214/155697189-6ece88ec-dcfd-42dd-a338-0a2211b651df.png)   

-> 문제를 볼때 recursive에 ***고정관념***을 두었던거 같다.       

-> 이 문제는 dp문제였음. 내 풀이는 정확도는 맞으나 ***runtime complexity가 O(mnk)*** 이다
(k는 대각선의 길이)    

### 다른이 풀이    
![1](https://user-images.githubusercontent.com/70446214/155697343-29917049-9aa1-4ad2-af52-54562da8f50f.png)   

해당 방법은 O(m*n) runtime , O(m*n) Space Complexity를 갖지만 

**O(n) Space Complexity를 갖도록 줄여보았다.**     

![1](https://user-images.githubusercontent.com/70446214/155697520-741833d4-cd56-48c0-8602-1686a138515d.png)   

결과적으로 ***Cache Hit***가 더 빈번하게 발생해 시간도 줄어들 수 있었다.    
