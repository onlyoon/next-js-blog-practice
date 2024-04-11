#aor
### 슬라이딩 윈도우 접근법  
  
- 배열이나 문자열과 같은 일련의 데이터를 입력하거나 특정 방식으로 연속적인 해당 데이터의 하위 집합을 찾는 경우에 유용  
- 연속적인 하위 집합을 슬라이딩해서 찾아 해당하는 답을 도출하기 위한 접근법  
- 규모가 큰 데이터셋에서 하위 집합을 추적하는 문제에 유용  
  
  
- 슬라이딩 윈도우 접근법을 사용하지 않았을 경우  
```js  
function maxSubarraySum(arr, num) {  
	if ( num > arr.length){  
		return null;  
	}  
	var max = -Infinity;  
	for (let i = 0; i < arr.length - num + 1; i ++){  
		temp = 0;  
		for (let j = 0; j < num; j++){  
			temp += arr[i + j];  
		}  
		if (temp > max) {  
			max = temp;  
		}  
	}  
	return max;  
}  
  
maxSubarraySum([2,6,9,2,1,8,5,6,3],3)  
```  
- 시간 복잡도: O(N^2)  
  
- 슬라이딩 윈도우 접근법을 사용했을 경우  
```js  
function maxSubarraySum(arr, num){  
	let maxSum = 0;  
	let tempSum = 0;  
	if (arr.length < num) return null;  
	// 초깃값 설정  
	for (let i = 0; i < num; i++) {  
		maxSum += arr[i];  
	}  
	tempSum = maxSum;  
	// 초깃값의 다음 부터 수행  
	for (let i = num; i < arr.length; i++) {  
	// 앞 뒤로 한번씩 뺄셈 덧셈을 수행함으로서 중첩 반복 사용 안함  
		tempSum = tempSum - arr[i - num] + arr[i];  
	// 이전 것과 비교  
		maxSum = Math.max(maxSum, tempSum);  
	}  
	return maxSum;  
}  
  
maxSubarraySum([2,6,9,2,1,8,5,6,3],3)  
```  
- 시간 복잡도: O(N)
### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) index로 돌아가기