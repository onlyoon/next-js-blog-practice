#aor 
@출처
https://velog.io/@doondoony/javascript-iife
### Immediately Invoked Function Expression
>[!note]
>#### 즉시 실행되는 함수 표현식
>
>>즉시 실행되어 값으로 바로 평가되는 함수
>
>>전역 스코프를 오염시키지 않기 위해 사용

- IIFE 사용전:
```js
const iife() {
	console.log("Immediately Invoked Function Expression!");
}
life(); // "Immediately Invoked Function Expression!"
```

- IIFE 사용후:
```js
(function() {
	console.log("Immediately Invoked Function Expression!");
})(); // "Immediately Invoked Function Expression!"
```
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기