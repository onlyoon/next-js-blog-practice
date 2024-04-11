#aor 
### fetch API
>[!note]
>#### fetch API
>
>>서버와 프로토콜로 상호작용하기 위해, 사용하는 API
>
>>[XMLHttpRequest](XMLHttpRequest.md)를 보완한 자바스크립트의 최신형 API, 구세대 브라우저에서 지원하지 않는다.
>
>>[Promise](../Promise%20&%20Callback/Promise.md)를 기반으로 한 함수이자, 함수 자체적으로 지원해 [Promise](../Promise%20&%20Callback/Promise.md) 객체를 반환하는 API이다.
>
>>fetch API는 파싱된 응답이 아닌, 스트리밍된 응답을 반환한다.
>
>>Promise객체를 적극적으로 사용하지만, 오류 처리 작업이 번거롭다.
#### 코드 예시
- fetch API는 `xhr.response`가 주는 파싱된 응답이 아닌, 스트리밍된 응답을 반환한다.
	- 이 응답을 가지고 `response` 객체에 대해 `json()`메서드를 호출하면, fetch API가 response 본문을 스냅샷을 찍은 후, 파싱해 JSON객체를 자바스크립트 코드로 변환하는 작업을 한다.
- fetch API의 두번째 인자에 `method`, `body` 프로퍼티가 들어가야 하며, 추가적으로 `header` 프로퍼티를 넣을 수 있다.
```js
const sendHttpRequest = (url, method, data) => {
    return fetch(url, {
	    method: method,
	    body: JSON.stringify(data),
	    header: {
		    'Content-Type': 'application/json'
	    }
    }).then(response => {
        return response.json();
    });
};
```
#### 오류 처리
```js
const sendHttpRequest = (url, method, data) => {
    return fetch(url, {
        method: method,
        body: JSON.stringify(data)
    }).then(response => {
        if (response.status >= 200 && response.status < 300) {
            return response.json();
        } else {
	        // 오류 데이터에 엑세스하기 위해 && 응답 본문에 엑세스하기 위해 사용하는 방법
            return response.json().then(errData => {
                console.log(errData);
                throw new Error('Something went wrong - server-side.');
            })
        }
    });
};
```

>[!warning]
>>fetch API의 추가 메서드를 통해 JSON객체의 데이터 뿐만 아니라, 스냅샷으로 반환해야 하는, 스트리밍 데이터를 얻을 수 있다.
>
>>스트리밍 데이터이기 때문에, 상태 코드를 필요로 하는 시점과 Content에 접근할 수 있는 시점이 다르다.
#### 추가 정보
- [Fetch_API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기