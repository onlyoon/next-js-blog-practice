#aor 
### Higher Order Function
>[!note]
>#### 고차함수
>
>>함수 안에서만 동작하는 함수를 말한다.
#### 예시
- `sumUp`함수 내에서 검증하는 함수를 넣어, 추가적 기능이 있는 함수
```js
function sumUp(...numbers) {
	const validateNumber = (number) => { // <- higher order function
      if (typeof number === `number`) {
        return number;
      } else {
        console.log(`it's not a number! it's a ${typeof number}`);
        return 0;
      }
	};
	let sum = 0;
	for ( const num of numbers) {
		sum += validateNumber(num);
	}
	return sum;
};
console.log(sumUp(1, 5, `r`, -3, 6, `10`));
sumUp(1, 5, `l`, -3, 6, `we`, 25, `10`);
```

>[!warning]
>>고차함수의 경우 하나의 함수에 다양한 기능이 들어가니 사용하는 것은 자제하는 것이 좋다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기