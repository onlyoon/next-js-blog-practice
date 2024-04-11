#aor 
### Pure Function
>[!note]
>#### 순수 함수 
>
>>입력값이(인자) 주어지면 늘 같은 출력값을 내놓는 함수
>
>>프로그램에서 그 어떤 부수 효과[js-Side Effect](js-Side%20Effect.md)를 야기하지 않는다.
>>함수 실행시, 함수의 내부에서만 동작하지 함수의 외부에선 작동되는 것이 없다.

- 순수 함수
```js
function add(num1, num2) {
	return num1 + num2;
}
console.log(add(1, 2)); // 3
```

>[!note]
>#### 비순수 함수 
>
>>입력값이(인자) 주어지면 다른 출력값을 내놓는 함수
>
>>출력값에 대한 예측이 불가능하다.

- Case 1: 
```js
function addRandom(num1) {
	return num1 + Math.random();
}
console.log(addRandom(2)); // ???? 
```
- Case 2: <- 함수 외부의 변수를 바꾸는 경우
```js
function addMoreNumbers(num1, num2) {
	const sum = num1 + num2;
	previousResult = sum; // <- 함수의 밖에서 정의된 변수를 바꿔서 부수효과를 일으켰다.
	return sum;
}
```
- Case 3: <- 함수 외부의 객체나 배열의 원본이 바뀌는 경우
```js
const hobbies = ["Sports", "Cooking"];

function printHobbies(h) {
	h.push('NEW HOBBY');
	console.log(h);
}

printHobbies(hobbies);
```

>[!warning]
>>최대한 함수를 순수하게 논리적으로 작성해, 부수 효과를 피하는 방향으로 가야 한다.

---

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기