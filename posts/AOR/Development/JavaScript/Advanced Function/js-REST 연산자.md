#aor
### REST 연산자
>[!note]
>REST 연산자
>
>>여러 개의 인수가 무수하게 많을 때 사용하는 연산자


>[!warning]
>>항상 매개변수 항목들 중에서 마지막 인수로서 들어가야 한다.
>
>>자동으로 모든 인수를 합치기 때문이다.

사용하지 않았을 경우 : (인수가 무수하게 많은 상황일 때, 배열타입 인수 사용)
- 사용자가 배열을 보내도록 하는 것
- 함수 표현식에서 for-반복문을 사용해 배열의 모든 인수를 찾아내 작동
```js
const sumUp = (numbers) => {
	let sum = 0;
	for ( const num of numbers) {
	sum += num;
	}
	return sum;
};
sumUp([1, 5, 10, -3, 6, 10]);
sumUp([1, 5, 10, -3, 6, 10, 25, 88]);
```

사용했을 경우 : (인수가 무수하게 많은 상황일 때, REST 인수 사용)
- 배열의 요소를 가져오는 대신 이 함수가 가지는 모든 인수를 가져와 배열에 합치는 것( 함수 안에서 배열을 설계 )
- 인수 타입을 배열처리를 하지 않아도 된다
```js
const sumUp = (...numbers) => {
	let sum = 0;
	for ( const num of numbers) {
	sum += num;
	}
	return sum;
};
sumUp(1, 5, 10, -3, 6, 10);
sumUp(1, 5, 10, -3, 6, 10, 25, 88);
```

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기