### 내풀이     
-> DP   
-> 처음엔 단순한 Rerursive로 풀려다 print를 통해 cache가 필요함을 확인
![image](https://user-images.githubusercontent.com/70446214/156686608-68bd7c1d-66db-4a53-8004-d968e5768e5e.png)     

파이썬의 cache를 dictionary 대신 set을 이용     
-> 주의할 점은 두 아키텍쳐 모두 key값으로 list를 가질 수 없다.   

-> 코드는 깔끔해 보임. 살짝 아쉬운점은 top-down으로 인한 call stack overflow를 개선할 방향이 있으면 좋을듯.     


### Most Voted Solution   

![image](https://user-images.githubusercontent.com/70446214/156698682-559c915b-aa9b-4b06-92be-f7de8e215243.png)     
내풀이     
![image](https://user-images.githubusercontent.com/70446214/156698715-e0a6a6dd-5c75-47e4-a92a-fbac8927bab8.png)
