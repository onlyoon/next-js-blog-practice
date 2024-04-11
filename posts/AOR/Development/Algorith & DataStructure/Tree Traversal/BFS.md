#aor 
### 너비 우선 탐색
>[!note]
>#### Breadth-first Search
>
>>트리를 ==가로==질러서 탐색하는 것

![](../../../../Stuff/Image/AOR/Algorithm%20&%20DataStructure/img%20(1).gif)

#### 특징
- FIFO형태의 자료구조(큐)를 활용해서 구현할 수 있다.
#### 탐색
상단의 그림에 따른 출력값 : [1, 2, 3, 4, 5, 6, 7, 8, 9]

1. 큐와 배열을 생성한다.
2. 큐 안에 루트 노드가 없으면
	- 큐 에 넣어준다.
1. 큐 안에 아무것도 없을 때까지
	- 큐에 노드가 있다면, 노드를 큐에서 꺼내 배열에 넣어준다.
	- 꺼내진 노드의 왼쪽에 값이 있다면
		- 큐에 넣어준다.
	- 꺼내진 노드의 오른쪽에 값이 있다면,
		- 큐에 넣어준다.
3. 모든 값을 저장한 변수를 출력한다.

#### 코드 예시
```js
  class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
    this.count = 0;
  }
}
class BinarySearchTree {
  constructor() {
    this.root = null;
  }
  // 삽입 메서드
  insert() {
    ...
  }
  // 너비 우선 탐색 메서드
  BFS() {
    let data = [];
    let queue = []; 
    let node = this.root;
    queue.push(node);
    while(queue.length) {
      node = queue.shift();
      data.push(node);
      if (node.left) queue.push(node.left);
      if (node.right) queue.push(node.right);
    }
    return data;
  }
}
```
### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) Index로 돌아가기