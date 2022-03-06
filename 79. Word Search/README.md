### 내풀이   
-> 처음에 bfs로 풀려고함.     
-> 디버깅 끝에 풀이 자체가 옳지 않았음.    
-> 이 문제는 dfs + BackTracking !     
![image](https://user-images.githubusercontent.com/70446214/156928601-96557396-ea5f-44f4-819d-bc0494c56130.png)   

다른이의 풀이에서 배운 것    

### 0.구조    
-> 첫번째로 main문에서 dfs의 function과 같은 structure를 가지고 있어 맘에 들진 않았는데    
-> 이는 해결할 방법이 보이진 않음. most voted solution도 같은 구조를 갖음.   
    
### 1. Row , Col Array를 정의한건 정말 좋았음 (다른 풀이에서 배움)    
-> 이것이 없었으면 코드의 길이는 훨씬 길어졌을 것 !   

### 2. 내가 풀이한 space complexity는 o(m*n)    
-> **이는 board를 그대로 활용해 O(1) space 로 풀이할 수 있다.***   
![image](https://user-images.githubusercontent.com/70446214/156928822-988b8cc5-3a05-4e38-9d99-dde0ac11203d.png)     
  
![image](https://user-images.githubusercontent.com/70446214/156929353-f6bc7d63-6e40-40cc-b497-059df48cb121.png)     
-> check[][] (가야 할 장소) 가 false이면 이라는 논리 연산이 아닌, 구조 자체가 달라진다.      
