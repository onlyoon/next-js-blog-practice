#aor 
### FormData
>[!note]
>#### FormData 생성자 함수
>
>>키-값 쌍을 추가할 수 있는 구조화된 객체이며, JSON 객체와 다른 방식으로 전송되는 데이터 구조
#### 코드 예시
- `append()`메서드 사용으로 데이터 구조에 파일을 추가하는 것이 쉽다.
- 특정 HTML요소를 인자로 넣을 시, 자동으로 해당 form에서 모든 데이터를 수집한다.
```js
const form = document.querySelector('#new-post form');

function sendHttpRequest(method, url, fd) { ... };

async function createPost(userId) {
	fd.append('userId', userId); // <- append() 메서드 사용
	const fd = new FormData(form); // <- 특정 HTML 요소를 인자로 넣는 경우
	sendHttpRequest(method, url, fd);
}
```

>[!warning]
>>`<input>`태그에는 꼭 `name`프로퍼티가 있어야 한다.
>>FormData가 입력값을 제대로 식별하기 위해 필요하다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기