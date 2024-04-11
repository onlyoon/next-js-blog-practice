#aor 
### Graph Traversal
>[!note]
>#### 그래프 순회
>
>>그래프 순회를 위해선 처음 시작하는 노드가 있어야 한다.
>
>>순회의 결과에 대한 리스트를 저장하는 배열 필요
>
>>방문한 정점들에 대한 정보를 저장할 객체 필요

#### 재귀적 DFS
- 재귀적 DFS를 위해서 하나의 함수를 준비하고 그 함수 내에서 Helper 함수로 재귀를 시작한다.
- Helper 함수는 입력된 정점을 "방문되었다" 객체에 추가하고 해당 정점을 결과 리스트에 저장하는 과정이 필요하다.

```js
DFS(정점) {
    if (정점이 비었다면?)
        return 이것이 root이다.
    정점을 방문할 때마다, 배열에 저장한다.
    해당 정점을 방문했다고 저장한다.
    for (이웃 정점들) {
        if (이웃 정점이 방문되지 않았다면?) {
            DFS(이웃 정점)
        }
    }
}
```

```js
    DFS(sVertex) { // <- 인자: 시작 정점
        const result = []; // 결과 리스트
        const visited = {}; // 방문되었다는 표시의 객체
        const adjacencyList = this.adjacencyList; // 그래프
        (function dfs(vertex) { // 헬퍼함수 <- IIFE 사용, 첫 인자: sVertex
            if (!vertex) return null; // <- 정점이 비었다면? 
            visited[vertex] = true; // 방문되었다는 표시
            result.push(vertex); // <- 결과 리스트에 정점 삽입
            adjacencyList[vertex].forEach(neighbor => { // <- 그래프에서 vertex와 이웃된 값들을 돈다.
                if (!visited[neighbor]) { // <- 만일 인접한 노드가 방문되지 않았을 경우
                    return dfs(neighbor); // <- 새로운 헬퍼 함수를 호출
                }
            });
        })(sVertex); // <- IIFE의 첫 시작 인자
        return result;
    }
```

#### 활용
- P2P
- Web 크롤링
- 최단거리 검색, 추천 알고리즘, 가까운 친구 검색
### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) Index로 돌아가기