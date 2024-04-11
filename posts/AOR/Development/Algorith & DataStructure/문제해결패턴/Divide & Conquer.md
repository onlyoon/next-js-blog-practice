#aor
### 분할과 정복 접근법  
  
- 배열이나 문자열같은 큰규모의 데이터셋을 처리하는 알고리즘  
- 큰 데이터 덩어리를 작은 조각으로 나누는 것  
  
- 분할과 정복 접근법을 사용하지 않았을 경우  
```js  
function search(arr, val) {  
	for(let i = 0; i < arr.length; i++) {  
		if(arr[i] === val) {  
			return i;  
		}  
	}  
	return -1;  
}  
```  
- 시간 복잡도: O(N)  
  
- 분할과 정복 접근법을 사용했을 경우  
```js  
function search(array, val) {  
	let min = 0;  
	let max = array.length - 1;  
	while (min <= max) {  
		let middle = Math.floor((min + max) / 2);  
		let currentElement = array[middle];  
  
		if(array[middle] < val) {  
			min = middle + 1;  
		}  
		else if (array[middle] > val) {  
			max = middle - 1;  
		}  
		else {  
			return middle;  
		}  
	}  
return -1;  
}  
```
- 시간 복잡도: Log(N)
### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) index로 돌아가기