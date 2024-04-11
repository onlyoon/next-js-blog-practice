#aor 
### async & await
>[!note]
>#### async & await
>
>>비동기 함수를 위해 사용되는 키워드이다.
#### `async`
- 비동기 함수를 선언하기 위한 키워드이다.
- 함수 내부의 모든 것들을 [Promise](Promise.md)객체로 감싼다.
	- 추가되는 `then()`메서드는 자바스크립트에 의해 내부적으로 수행된다.
- 항상 Promise 객체를 반환한다.

-  비동기 함수 선언 예시
```js
const asyncFunction1 = async (asyncData) => {};
async function asyncFunction2(asyncData) {};
```
#### `await`
- 프로미스를 반환하는 함수 앞에 `await` 키워드로 비동기 작업 선언하는 키워드이다.
- `await`로 선언된 코드는 앞의 Promise가 수행되기 전까지 대기한 후 `then()`메서드를 추가한다.
#### 예시
- `async` && `await`, 사용하지 않는 일반 함수 예시
```js
function trackUserHandler() {
  let positionData;
  getPosition()
    .then(posData => {
      positionData = posData;
      return setTimer(2000);
    })
    .catch(err => { // <- catch문 사용
	  console.log(err);
    })
    .then(data => {
      console.log(`data: `, data, `positionData: `, positionData);
    });
  setTimer(1000).then(() => {
    console.log('Timer Done!');
  })
}
```
- 비동기 함수 예시
```js
async function trackUserHandler() {
  const posData = await getPosition(); 
  const timerData = await setTimer(2000); // getPosition으로 제대로 된 데이터를 받지 못했을 경우, setTimer(2000)는 실행되지 않는다.
  console.log(timeData, posData);
}
```
#### 오류 처리
- `try-catch` 문을 사용한다.
```js
async function trackUserHandler() {
  let posData;
  let timerData;
  try {
    const posData = await getPosition(); 
    const timerData = await setTimer(2000); // getPosition으로 제대로 된 데이터를 받지 못했을 경우, setTimer(2000)는 실행되지 않는다.
  } catch (error) {
	console.log(error);
  }
  console.log(timeData, posData);
}
```

>[!warning]
>>함수에서만 작성이 가능하다.
>
>>`async` 그리고 `await` 키워드는 `then()`메서드를 사용하는 것을 가시적으로 이해하기 쉽도록 변환 시킨 것이다. 
>
>>`try-catch` 문은 새로운 환경 블록을 제공하기 때문에, `try-catch`문 밖에서 필요할 경우, 다른 변수를 엮어야 한다.
>
>>`async`함수는 하나의 함수 내에서 동시에 작업을 실행할 수 없다.
#### 추가 정보
- [async & await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기