#aor 
### XMLHttpRequest
>[!note]
>#### XMLHttpRequest 객체
>
>>서버와 프로토콜로 상호작용하기 위해서 사용하는 통신 객체
#### 코드 예시
```js
const xhr = new XMLHttpRequest();

// HTTP Header에 프로퍼티-값을 추가하는 메서드 <- 한번 추가시 삭제가 불가능하다.
xhr.setRequestHeader('Content-Type', 'application/json');

// XMLHttpRequest를 초기화하는 메서드
xhr.open('GET', 'https://jsonplaceholder.typicode.com/posts');

// JSON 객체로 받은 응답을 구문분석해주는 메서드
xhr.responseType = 'json';

// 요청을 보낸 이후의 load event를 기다리기 위한 event listener 생성 메서드
xhr.onload = function() {
	...
}
// HttpRequest 전송 후, 응답을 받지 못하는 오류 발생 시 발동되는 event listener 생성 메서드
xhr.onError = function() {}
// XMLHttpRequest를 서버에 전달하는 메서드
xhr.send();

```

- HTTP 요청 전송을 다양화(재사용)하기 위해 [Promise](../Promise%20&%20Callback/Promise.md)객체를 활용할 수 있다.
```js
const sendHttpRequest = (method, url) => {
    const promise = new Promise((resolve, reject) => {
        const xhr = new XMLHttpRequest();
        xhr.open(method, url);
        xhr.responseType = 'json';
        xhr.onload = function () {
            resolve(xhr.response);
        };
        xhr.onError = function() {
	        console.log(xhr.response);
	        console.log(xhr.status);
        }
        xhr.send();
    });
    return promise;
};

async function fetchSomething() {
	const responseData = await sendHttpRequest('GET', 'url');
	...
}
fetchSomething();
```
#### load event
- 데이터가 로딩된 이후(요청이 완료되면) 자동으로 실행되는 이벤트이다.

>[!warning]
>>서버 실패에 대한 상태 코드가 반환시, `onerror`메서드가 아닌 `onload`메서드에만 해당 오류가 기록된다.
>
>>요청이 실패했을 경우, `onerror` 메서드에 해당 오류가 기록된다. 
#### 추가 정보
- [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기