#aor 
### Event Loop
>[!note]
>#### 이벤트 루프
>
>>이벤트 리스너를 지원하는 공간
>
>>[자바스크립트 엔진](../About%20JavaScript/자바스크립트%20엔진.md)의 Call Stack을 대기 중인 메세지와 동기화하는 역할을 수행한다.

- EventLoop는 실시간으로 [자바스크립트 엔진](../About%20JavaScript/자바스크립트%20엔진.md)의 Call Stack에 대기 중인 작업이 있는지 확인한다.
	- ==Call Stack이 비어있고 Message Queue에 작업이 있을 경우==, EventLoop가 Message Queue에 있는 대기 중인 작업 항목(콜백 함수 ([Callback Function](../Advanced%20Function/Callback%20Function.md))을 Call Stack에 집어넣을 수 있도록 한다.
- 자바스크립트의 비동기 코드를 사용하는 콜백 함수의 처리를 도와준다.
- EventLoop는 브라우저가 직접 관리한다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기