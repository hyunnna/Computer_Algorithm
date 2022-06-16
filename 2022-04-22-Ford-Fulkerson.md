# <span style="color: #87CEEB">**Ford-Fulkerson-Algorithm** </span>  

**유량 네트워크** : 최대 유량 문제이다. 유량을 최대화 하는 알고리즘이므로 간선의 가중치는 비용이 아니라 **용량(capacity)** 이다.  

- 유량 네트워크(flow network) : 간선에 용량이라는 속성이 있는 그래프
- 소스 (source) : 유량이 시작하는 정점, 유일하게 유량이 발생
- 싱크 (sink) : 유량이 도착해야 하는 정점.
- 용량(capacity) : 각 간선에 대해서 흐를 수 있는 최대 유량 c(u,v)
- 유량(flow) : 각 간선에 대해서 다음 constraints를 만족하는 값 f(u,v)   

* 용량의 제한(capacity constraint) : 유량은 그 간선의 용량을 초과할 수 없다.
* 유량의 보존(conservation of flows) : 소스의 싱크를 제외한 정점에는 들어오는 유량과 나가는 유량은 같다.
* 유량의 대칭성(skew symmetry) : u-> v로 f만큼 유량이 흐르면 v->u로 -f만큼 유량이 흐른다고 생각  

***
### 1) 동작방식 
1) 깊이 우선 탐색으로 source-sink 까지 경로를 찾음
1) 최소 capacity 값을 flow 값으로 지정해서 가장 작은 값을 흘려보냄
1) 이때 반대 유량 (-flow)를 빼준다
1) 다른 경로가 없을 때 까지 capacity를 채운다
1) 다 찾은 후 총 flow 값을 return

### 2) 역방향 간선 ( 반대 유량 값 더하기 )   

<img src ="https://user-images.githubusercontent.com/62924325/165848499-32da7167-b9c3-4966-9bc1-74939da4ab57.png" width="300" height="300">
위와 같은 구조에서 최대 유량을 구하면  

<img src ="https://user-images.githubusercontent.com/62924325/165848518-8c3e503c-06e8-476e-a394-73b3d4a3e226.png" width="300" height="300">

#### ① C-A-B-D  <1>  

<img src ="https://user-images.githubusercontent.com/62924325/165848536-7a8dab0e-e817-4718-9a9a-6977ab39f31b.png" width="300" height="300">

#### ② C-B-D <1>  

<img src ="https://user-images.githubusercontent.com/62924325/165848545-33c9dc26-33e4-4ea9-8a3b-2cc258052f1f.png" width="300" height="300">

#### ③ 여기서 A-B 의 flow 1을 반대방향으로 흘려준다

<img src ="https://user-images.githubusercontent.com/62924325/165848553-dfa5de2b-b97e-40b3-9688-21ece12fb941.png" width="300" height="300">

#### ④ 이렇게 모든 순환이 끝났다. 역방향 간선이 없었다면 다른 경로를 찾지 못한다. 이 구조는 네트워크 구조이므로 더 넓은 capacity로 이동하는 것이 더 효율적이기 때문에 역방향 간선은 포드 풀커슨 알고리즘의 장점이다.

### 3) 최소 유량값 구하기

![image](https://user-images.githubusercontent.com/62924325/165846359-e625fad3-87c5-4551-b578-538eff58e212.png)

#### ① 깊이 우선 탐색으로 A(Source)에서 F(Sink)까지 경로를 무작위로 선정 : **A-B-C-F** 

< 흐를수 있는 flow 값 >  
A - B <12>  
B - C <6>  
C - F <8>  

가장 작은 capasity 값이 flow 값이 므로 총 흐를 수 있는 값은 **<6>**

![image](https://user-images.githubusercontent.com/62924325/165846390-d5bc4dea-fa39-4c62-aa8e-6588a5865d26.png)
#### ② 같은 방법으로 **A-D-E-F <4>**   

![image](https://user-images.githubusercontent.com/62924325/165846412-e6d78e88-23d9-4d39-a3e5-e1345143ba5e.png)

#### ③ **A-B-F <6>**  

![image](https://user-images.githubusercontent.com/62924325/165846428-fa569b6d-97eb-4ae1-9611-0ffbd2242ed3.png)

#### ④ **A-D-E-C-F <2>**  

#### 따라서 총 흐를 수 있는 유량 값은 **6+4+6+2 = 18**



### 4) 코드 실행  

```java

public class Main {

    public class Path(int i)

    {
        int node = 8;
        int load[][];
        load = new int [-1][-1];
        int[] d = new int[node + 1];

        for (int j = 1; j <= node; j++) {
            d[i] = 1;
            if (load[i][j] == 1 && d[j] == 0) {
                return load;
            }

        }
    }

```
