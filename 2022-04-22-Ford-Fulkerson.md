Ford-Fulkerson-Algorithm

유량 네트워크 : 최대 유량 문제이다. 유량을 최대화 하는 알고리즘이므로 간선의 가중치는 비용이 아니라 용량(capacity)이다.  

유량 네트워크(flow network) : 간선에 용량이라는 속성이 있는 그래프
소스 (source) : 유량이 시작하는 정점, 유일하게 유량이 발생
싱크 (sink) : 유량이 도착해야 하는 정점.
용량(capacity) : 각 간선에 대해서 흐를 수 있는 최대 유량 c(u,v)
유량(flow) : 각 간선에 대해서 다음 constraints를 만족하는 값 f(u,v)


용량의 제한(capacity constraint) : 유량은 그 간선의 용량을 초과할 수 없다.
유량의 보존(conservation of flows) : 소스의 싱크를 제외한 정점에는 들어오는 유량과 나가는 유량은 같다.

유량의 대칭성(skew symmetry) : u-> v로 f만큼 유량이 흐르면 v->u로 -f만큼 유량이 흐른다고 생각




1) 동작방식 
- 깊이 우선 탐색으로 start-end 까지 경로를 찾음
- 최소 capacity 값을 flow 값으로 지정해서 가장 작은 값을 흘려보냄
- 이때 반대 유량 (-flow)를 빼준다
- 다른 경로가 없을 때 까지 capacity를 채운다
- 다 찾은 후 총 flow 값을 return

코드실행

성능분석

