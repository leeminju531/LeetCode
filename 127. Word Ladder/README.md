### 내풀이     
![1](https://user-images.githubusercontent.com/70446214/159688436-1b2e4e29-d1cc-4da2-9574-8d1d0fda3267.png)         
-> 알고리즘 틀린 풀이     

"hit" -> "hot" -> "dot" -> "dog" -> cog"    

내가 생각한 풀이는 beginWord에서 endWord 까지 도달하기 위한 절차에는    
꼭 하나의 문자는 endWord에 대응하는 문자로 치환해야 한다고 생각함.   

hot->dot->dog 와 같이 위 절차를 지키지 않는 순서가 필요할 수도 있음...    


### 문제풀이 Key Point    
1. ***처음 푸는데 있어, 룰이 없는 ,즉 내가 생각했던 절차를 지키지 않는 예외사항이 알고리즘 생성에 혼란을 주었다.    
-> 이는 그저 '주어진 word가 lowerCase라는 제한사항 그 자체를 이용해 Optimal 모든 case를 순회하며 찾는 방식으로    
'무식하지만' 확실한 접근방법이 존재했다.***      

문제풀이는 shortest path의 전형적인 bfs를 제안했다. 나는 dfs접근 풀이가 가능할 것 같아서 ***dfs로 접근***해봤다.(이젠 재귀가 익숙한듯ㅋ)     

![1](https://user-images.githubusercontent.com/70446214/159713408-06f5ff15-ea74-4552-a673-a8f4fb8140c0.png)     

-> Time Limited exceed !      
-> we need **shortest path algorithm like Breadth-First-Search.**     

## Most Voted      
![1](https://user-images.githubusercontent.com/70446214/159729105-186b6595-18cb-4c95-a57c-c58f8ae7fc91.png)     
-> set을 이용해서 general하게 사용되는 visited을 대체했다는 것.     
-> 또한 이 문제는 처음 직관으로 봤을때 visit에 사용되는 영역이 구분되어야 한다고 여겨졌음 (그렇기에 재귀를 사용)    
-> 위의 불필요한 중복계산으로 인해 Time limited가 난 것.     

### C++   

1. set을 구성할떄 Iterator을 이용해 처음부터 한번에 선언할 수 있다.   
2. key가 없어도 erase사용해도 괜찮      
 ![1](https://user-images.githubusercontent.com/70446214/159732016-8881d076-1bc2-48e5-a7a6-82bf287cbb9d.png)



