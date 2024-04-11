

#aor 
### Recursion
>[!note]
>#### 재귀 함수
>
>>자체적으로 함수를 실행하고 반환되는 값을 가지고 내부 함수 호출에 활용하는 함수이다.
>
>>재귀 함수는 코드를 줄여주며, 중첩 레벨을 알 수 없는 데이터를 읽어올 경우에 주로 사용된다.

- 재귀 함수 삼항 연산식 예시
```js

// 일반적인 재귀 함수
function recursion(x , n) {
	if (n === 1) {
		return x;
	}
	return x * recursion(x, n - 1);
}

// 3항연산식을 사용할 경우 코드의 수가 줄음을 볼 수 있다.
function recursion(x, n) {
	return n === 1 ? x : x * recursion(x, n - 1);
}
```

- 중첩 레벨이 얼마나 되는지 알 수 없는 데이터를 읽어올 경우
```js
const myself = {
	name: 'Max',
	friends: [
		{
			name: 'Manuel',
			friends: [
				{
					name: 'chris',
					friends: [
						{
							name: 'hari'
						},
						{
							name: 'amilia'
						}
					]
				}
			]
		},
		{
			name: 'julia'
		}
	]
};

// 중첩 레벨을 알 수 없는 경우에 for문을 사용하는 것 부적절하다.
// function printFriendName(person) {
//	...
// 	for (const friends of person.friends) {
//		...
// 		for (const friendsFriends of friends.friends) {
//	 		...
// 		}
// 	}
// }

// 중첩 레벨을 알 수 없는 경우에 사용하는 재귀 함수이다.
function getFriendNames(person) {
	const collectedName = [];
	if (!person.firneds) {
		return [];
	}
	for (const friend of person.friends) {
		collectedNames.push(friend.name);
		collectedNames.push(getFriendNames(friend));
	}
	return collectedName;
}
// 재귀함수의 truthy 그리고 falsy 값일때의 출력값은 항상 같은 형식을 유지해야 한다.
```
---
#### 추가 정보
- [재귀 (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#Recursion)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기