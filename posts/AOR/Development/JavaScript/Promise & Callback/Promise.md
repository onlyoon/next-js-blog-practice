#aor 
### Promise Object
>[!note]
>#### 프로미스 객체
>
>>여러 개의 중첩된 콜백 지옥 대신 사용하는 객체이며, 하나의 중첩 레벨을 사용해 코드를 가독성있게 만들어 주는 비동기 코드를 감싸는 객체이다.
>
>>프로미스 객체의 executor에 들어가는 인자는 `resolve`와 `reject`가 있다.
>>
>>프로미스의 상태: `PENDING` || `RESOLVED` || `REJECTED` || `SETTLED`
#### Promise Status
- `PENDING` = 프로미스가 작동 중이며, `then()`, `catch()`메서드가 실행되지 않습니다.
- `RESOLVED` = 프로미스가 성공적으로 해결되었습니다. `then()`메서드가 실행됩니다.
- `REJECTED` = 프로미스가 거절되었습니다. `catch()`메서드가 실행됩니다.
- `SETTLED` = 모든 프로미스 작업이 끝났습니다. `finally()`메서드가 실행됩니다.

- 예시
```js
const setTimer = (duration) => {
	// 프로미스 객체 생성
	// 함수 인자(executor)는 프로미스 객체가 생성될 때 즉각 호출된다.
	const promise = new Promise((resolve, reject) => {
		setTimeout(() => {
			resolve('DONE!');
		}, duration);
	});
	return promise;
};

setTimer(2000).then(data => {
	console.log(data, posData);
}); // <- setTimer() 함수는 Promise 객체를 반환하며, `then`키워드를 통해, Promise객체의 데이터를 가지고 다음 콜백 함수로 넘어갈 수 있다.
```

- 예시
```js
somePromiseCreatingCode()
	.then(firstResult => {
		return 'done with first promise';
	})
	.catch(err => {
		// would handle any errors thrown before
		// implicitly returns a new promise - just like then()
	})
	.finally(() => {
		 // the promise is settled now - finally() will NOT return a new promise!
		 // you can do final cleanup work here
	 });
```
#### resolve 함수
- Promise 객체의 [Callback Function](../Advanced%20Function/Callback%20Function.md)(executor)에서 사용되는 함수로서 해당 함수가 호출되면, Promise객체가 내부적으로 해결됨(SUCCESS)을 표시하는 함수
- 해결됨을 알리기 위한 인자를 넣는 것이 가능하다.
#### reject 함수
- Promise 객체의 [Callback Function](../Advanced%20Function/Callback%20Function.md)(executor)에서 사용되는 함수로서 해당 함수가 호출되면, Promise객체가 내부적으로 실패함(FAIL)을 표시하는 함수
- 실패함을 알리기 위한 인자를 넣는 것이 가능하다.
#### Promise Chain
- 첫 번째 Promise객체가 들어있는 함수(ex. getPosition)가 끝날 때까지 기다리다가, 반환 시, 꼭 무언가의 값을 반환해야 한다.
- 예시
```js  
const getPosition = (opts) => {
  const promise = new Promise((resolve, reject) => {
    navigator.geolocation.getCurrentPosition(success => {
      resolve(success);
    }, error => {
      reject(error);
    }, opts);
  });
  return promise;
};
  
const setTimer = (duration) => {
  const promise = new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Done!');
    }, duration);
  });
  return promise;
}
  
function trackUserHandler() {
  let positionData;
  getPosition()
    .then(posData => {
      positionData = posData;
      return setTimer(2000);
    })
    .then(data => {
      console.log(`data: `, data, `positionData: `, positionData);
    });
  setTimer(1000).then(() => {
    console.log('Timer Done!');
  })
}

// data:  Done! <- setTimer의 Promise 객체 data
// positionData:  GeolocationPosition {coords: GeolocationCoordinates, timestamp: 1696470186431} <- getPosition의 Promise 객체 데이터
```
#### Promise Error
> 체인을 중도 취소하고 싶지 않을 때, `chatch`메서드를 사용한다.

- `getPosition` 함수에 에러가 발생하게 되면, 반환 값이 들어있는 `catch`메서드가 실행되고, 전체 프로미스 체인을 취소하지 않고, `catch`메서드의 데이터로 프로미스 체인이 실행된다.
- 제대로 된 데이터를 받지 못한 프로미스 체인을 취소하고 싶으면, `catch`메서드가 블록의 끝에 있어야 한다.
- `catch`메서드는 아무 값도 반환하지 않을 경우, `undefined`를 반환한다.
- 예시
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
#### Promise Method
- `race()` 메서드
	- 두 개의 프로미스 반환 함수 중에서 하나의 값만 취할 경우 사용
	- 프로미스 배열을 인자로 받는다.
	- 배열 내의 함수들 중에서 가장 빨리 반환하는 함수의 프로미스를 반환한다.
- 예시
```js
Promise.race([getPosition(), setTimer(1000)]).then(data => {
  console.log(data);
});
```

- `all()` 메서드
	- 두 개의 프로미스 반환 함수 중에서 두 개의 값 모두 취할 경우 사용
	- 하나의 프로미스 반환 함수가 거부될 경우, 다른 프로미스 반환 함수 역시 실행되지 않으며, 오류 값만 알려준다.
	- 프로미스 배열을 인자로 받는다.
	- 배열 내의 함수들의 반환 값들을 배열로 반환한다.
- 예시
```js
Promise.all([getPosition(), setTimer(1000)]).then(data => {
  console.log(data);
});
// [Position, "DONE!"]
```

- `allSettled()` 메서드
	- `all()` 메서드와 다르게 하나의 프로미스 반환 함수가 거부되어도, 다른 프로미스 반환 함수를 실행하고 싶을 경우, 사용
	- 프로미스 배열을 인자로 받는다.
- 예시
```js
Promise.allSettled([getPosition(), setTimer(1000)]).then(data => {
  console.log(data);
});
```

>[!warning]
>>반환 값이 Promise로 자동으로 감싸지기 때문에, 꼭 Promise 객체일 필요는 없으며, 모든 종류의 데이터를 반환할 수 있다.
>
>>`finally()`메서드는 무조건 추가할 필요가 없습니다.
#### 추가 정보
- [Promise](https://developers.google.com/web/fundamentals/primers/promises)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기