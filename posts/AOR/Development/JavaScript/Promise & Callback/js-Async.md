#aor 
### Async
>[!note]
>#### 비동기 
>
>>커피를 주문한 이후에, 줄을 서서 기다리지 않고, 진동벨이 울릴 때, 커피를 가지러 오는 방식
>
>>프로세스(커피)가 완성될 때까지 기다리지 않고, 동시에 다른 작업을 처리하는 방식.
### 비동기의 사용성
- 자바스크립트는 [자바스크립트 엔진](../About%20JavaScript/자바스크립트%20엔진.md)으로 단일 스레드로 모든 작업을 순차적으로 수행한다.
- 특정 연산에서 수행 시간이 오래 걸릴 경우 (ex. setTimeout(), HTTP request)
	- 해당 작업을 브라우저에서 Off-Load시켜 다중 스레드를 사용할 수 있게 한다.
	- Off-Load된 자바스크립트로 쓰여진 작업과 브라우저와 다시 소통해야 할 경우, [Callback Function](../Advanced%20Function/Callback%20Function.md)(진동벨)를 사용한다. 
	- Callback Function 사용 시, 브라우저의 다른 연산이 끝나면 호출된다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기