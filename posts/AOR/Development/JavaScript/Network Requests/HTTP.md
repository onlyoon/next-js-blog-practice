#aor 
### HTTP
>[!note]
>#### HTTP (HyperText Transfer Protocol)
>
>>텍스트 기반 통신 규약으로, 인터넷에서 데이터를 주고 받을 수 있는 프로토콜
#### HTTP Headers
- HTTP 헤더를 사용하면 클라이언트와 서버가 HTTP 요청 또는 응답을 통해 추가 정보(meta data)를 전달할 수 있습니다.
- `Content-Type` 프로퍼티
	- `application/json`: 요청에 JSON 데이터가 있다고 알려주는 값이다.
#### HTTP 메세지
- 서버-클라이언트 간 데이터가 교환되는 방식
#### HTTP Request Methods
- `GET`
- `POST`
- `PUT`
- `DELETE`
- `PATCH`
- `HEAD`
- `TRACE`
- `OPTIONS`
- `CONNECT`
#### HTTP response status codes
- HTTP 응답 상태 코드는 특정 [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) 요청이 성공적으로 완료되었는지 여부를 나타냅니다.
1. [Informational responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses) (`100` – `199`)
2. [Successful responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#successful_responses) (`200` – `299`)
3. [Redirection messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#redirection_messages) (`300` – `399`)
4. [Client error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses) (`400` – `499`)
5. [Server error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#server_error_responses) (`500` – `599`)

>[!warning]
>DevTools의 Network탭에서 PayLoad를 보면, 어떤 데이터가 전송되었는지 알 수 있다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기