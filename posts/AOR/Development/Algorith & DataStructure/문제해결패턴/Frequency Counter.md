#aor
### 빈도 카운터 (Frequency Counter)  

- 자바스크립트 객체를 사용해서 다양한 값과 빈도를 수집하는 패턴  
- 중첩된 루프 & O(N^2) 피하기 위해 사용  
- 객체를 사용하여 프로파일 구성시, 배열이나 문자열의 내용을 분석하는 방법으로 주로 배열이나, 문자열과 같은 선형 구조를 구성해 다른 객체의 형태와 신속하게 비교 가능  
- 두 개의 배열을 객체로 세분화해서 각 배열의 요소를 분류한 다음 각 배열 비교 가능  
  
- O(N^2) 접근법 예시 (순진한 접근법)  
```js  
function same(arr1, arr2){  
// 배열의 크기 같은지 확인  
	if(arr1.length !== arr2.length){  
		return false;  
	}  
// indexOf를 사용하여 이중중첩문 사용, 4  
	for(let i = 0; i < arr1.length; i++){  
		let correctIndex = arr2.indexOf(arr1[i] ** 2)  
		if(correctIndex === -1) {  
			return false;  
		}  
		console.log(arr2);  
		arr2.splice(correctIndex,1)  
	}  
	return true;  
}  
  
same([1,2,3,2], [9,1,4,4]);
```  
  
- 리펙토링 예시 O(2N)  
```js  
function same(arr1, arr2){  
	if(arr1.length !== arr2.length){  
		return false;  
	}  
	let frequencyCounter1 = {}  
	let frequencyCounter2 = {}  
	for(let val of arr1){  
		frequencyCounter1[val] = (frequencyCounter1[val] || 0) + 1  
	}  
	for(let val of arr2){  
		frequencyCounter2[val] = (frequencyCounter2[val] || 0) + 1  
	}  
	console.log(frequencyCounter1);  
	console.log(frequencyCounter2);  
	for(let key in frequencyCounter1){  
		if(!(key ** 2 in frequencyCounter2)){  
			return false  
		}  
		if(frequencyCounter2[key ** 2] !== frequencyCounter1[key]){  
			return false  
		}  
	}  
	return true
}  
  
same([1,2,3,2,5], [9,1,4,4,11])
```  

### [Algorithm & DataStructure](../../../Dev-Index/Algorithm%20&%20DataStructure.md) index로 돌아가기