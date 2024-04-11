#aor 
### 이진 탐색 트리
>[!note]
>#### Binary Search Tree (BTS)
>
>>데이터가 순서에 맞게 정렬되어 있으며, [Binary Trees](Binary%20Trees.md)데이터 구조를 지닌 데이터 구조

![](../../../../Stuff/Image/AOR/Algorithm%20&%20DataStructure/Binary_search_tree_example.gif)

#### 특징
- 부모 노드의 왼쪽에 있는 모든 노드들은 항상 부모 노드보다 작다.
$ParentNode[key] >= LeftChildNode[key]$
- 부모 노드의 오른쪽에 있는 노드들은 항상 부모 노드보다 크다
$ParentNode[key] <= RightChildNode[key]$
#### 삽입
>일반적인 경우의 시간복잡도 O(log n)
>트리가 한 쪽으로  치우치는 경우 O(n)

- 새로운 노드 삽입 시
	- 루트 노드가 없을 경우
		- 첫 번째 노드를 생성한다.
	- 루트 노드가 있을 경우
		- 새로운 노드의 값을 루트 노드와 비교
			- 값이 루트 노드보다 클 경우
				- 오른쪽으로 새로운 노드 이동
				- 이동한 곳에 값이 있을 경우
					- 비교 재-반복
				- 이동한 곳에 값이 없을 경우
					- ==삽입==
			- 값이 루트 노드보다 작을 경우
				- 왼쪽으로 새로운 노드 이동
				- 이동한 곳에 값이 있을 경우
					- 비교 재-반복
				- 이동한 곳에 값이 없을 경우
					- ==삽입==
#### 탐색
>시간복잡도 O(log n)

- 값 탐색시
	- 루트 노드가 없을 경우
		- `return false`
	- 루트 노드가 있을 경우
		- 값이 루트 노드의 값과 맞는지 비교
			- 값이 루트 노드보다 클 경우
				- 오른쪽으로 새로운 노드 이동
				- 이동한 곳에 값이 있을 경우
					- `return value`
				- 이동한 곳에 값이 없을 경우
					- `return null`
				- 이동한 곳에 다른 값이 있을 경우
					- 다른 값과 비교 재-반복
			- 값이 루트 노드보다 작을 경우
				- 왼쪽으로 새로운 노드 이동
				- 이동한 곳에 값이 있을 경우
					- `return value`
				- 이동한 곳에 값이 없을 경우
					- `return null`
				- 이동한 곳에 다른 값이 있을 경우
					- 다른 값과 비교 재-반복
#### 코드 예시
```js
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }
  // 삽입 메서드
  insert(value) {
    let newNode = new Node(value);
    if (this.root === null) {
      this.root = newNode;
      return this;
    } else {
      let current = this.root;
      while (true) {
        if (value === current.value) return undefined;
        if (value < current.value) {
          if (current.left === null) {
            current.left = newNode;
            return this;
          } else {
            current = current.left;
          }
        } else {
          if (current.right === null) {
            current.right = newNode;
            return this;
          } else {
            current = current.right;
          }
        }
      }
    }
  }
  // 탐색 메서드
  find(value) {
    if (this.root === null) {
      return false;
    } else {
      let current = this.root;
      while (true) {
        if (value === current.value) {
          return current.value;
        }
        if (value < current.value) {
          if (current.left === null) {
            return false;
          } else if (current.left.value !== value) {
            current = current.left;
          } else {
            return true;
          }
        } else {
          if (current.right === null) {
            return false;
          } else if (current.right.value !== value) {
            current = current.right;
          } else {
            return true;
          }
        }
      }
    }
  }
}

//      10
//   5     12
// 2  6  11   16
var tree = new BinarySearchTree();
tree.insert(10);
tree.insert(5);
tree.insert(12);
tree.insert(16);
tree.insert(11);
tree.insert(2);
tree.insert(6);
tree.find(1); // false
tree.find(16); // true

```

>[!note]
>>삽입 및 탐색에 대한 메서드 로직이 동일하니, 재사용이 가능할 것 같다.

#### 백준
- [5639번](https://www.acmicpc.net/problem/5639)
- [1268번](https://www.acmicpc.net/problem/1269)
- [1620번](https://www.acmicpc.net/problem/1620)
- [1351번](https://www.acmicpc.net/problem/1351)
- [2287번](https://www.acmicpc.net/problem/2287)
- [2957번](https://www.acmicpc.net/problem/2957) - RED BLACK TREE
### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) Index로 돌아가기