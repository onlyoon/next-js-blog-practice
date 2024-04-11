#aor 
### 자바스크립트 데이터 관리
>[!note]
>#### JavaScript Data Management
>
>>자바스크립트 코드 실행을 위한 메모리와 실행 단계에 대한 관리가 이루어지는 곳 
### 구성요소
#### 힙
- 장기적 메모리와 시스템 메모리 데이터를 저장하는데 사용한다.
#### 스택
- 단기적 메모리와 현재 실행되고 있는 함수를 관리(Call Stack)한다.
##### Call Stack 예시
```js
function getName() {
  return propmpt('Your Name : ', '');
}
function greet() {
  const userName = getName();
  console.log('Hello ' + userName);
}
greet();
```
- 과정
	1. Main Script 파일 -> 스택 || 이동 (`anonymous`로 Call Stack에 저장)
	2. `greet()` 함수 -> 스택 || 이동
	3. `getName()` 함수 -> 스택 || 이동
	4. `prompt()` 함수 -> 스택 || 이동
	5. 사용자 입력 중 ...
	6. 스택 -> `prompt()` 함수 || 제거 
	7. 스택 -> `getName()` 함수 || 제거
	8. `console.log()` 함수 -> 스택 || 이동
	9. 스택 ->`console.log()` 함수 스택 || 제거
	10. 스택 -> `greet()` 함수 스택 || 제거
	11. 스택 -> Main Script 파일 || 제거 (`anonymous`)
#### 단일 스레드
- 하나의 스레드는 하나의 작업을 수행한다.
- 자바스크립트는 하나의 작업만 수행한다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기