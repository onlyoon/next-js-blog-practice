#aor 
### Callback Function
>[!note]
>#### 콜백 함수
>
>>A function came back cuz it called for you by something else.
>
>>함수 호출이 언제 발생될 지 모르니 브라우저에게 함수나 포인터를 실행하도록 ==권한이 넘겨진 함수== <= 이 함수를 다른 함수의 인자값으로 취급
#### 콜백함수 예시
- sumUp의 함수에서 showResult함수를 인자로 받아와 함수 내부에서 다른 함수가 호출되었다
```js
const sumUp = (resultHandler, ...numbers) => {
	let sum = 0;
	for(const num of numbers) {
		sum += (num);
	}
	resultHandler(sum);
}
const showResult = (result) => {
	alert('The result after adding all numbers is ' + result);
};
sumUp(showResult, 1, 5, -3, 6, 10);
```
#### 콜백 지옥
- `getCurrentPosition`의 콜백 함수 안에 `setTimeout`의 콜백 함수 안에 `doMoreAsyncStuff`의 콜백 함수가 있다.
- 읽기가 어려우며, 이해하기도 어렵다.
- 콜백 지옥을 위한 대안으로 [Promise](../Promise%20&%20Callback/Promise.md) 객체를  사용한다.
```js
getCurrentPosition(() => {
	setTimeout(() => {
		doMoreAsyncStuff(() => {
			...
		})
	}, 1000);
}, ...);
```

>[!warning]
>>콜백함수를 중첩시킬 수록 코드가 더 읽기 힘들어지고 유지되기 어려워진다.
>
>>중첩된 콜백 함수는 [Closure](../Function%20Deep%20Dive/Closure.md)때문에 함수 내부의 환경과 외부의 환경의 접근이 가능하다. 그러나 외부의 함수는, 내부의 환경에 접근이 불가능하다.
>
>>브라우저가 콜백 함수를 실행하려면, 항상 Message Queue와 EventLoop에 대한 경로를 가져야 한다.
### [JavaScript](AOR/Dev-Index/JavaScript.md) Index로 돌아가기