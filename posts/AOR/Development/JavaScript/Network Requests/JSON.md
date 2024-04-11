#aor 
### JSON
>[!note]
>#### JavaScript Object Notation
>
>>JavaScript 객체 표기법으로 구조화된 데이터를 표현하기 위한 문자 기반 표준 포맷

- JSON 객체를 받아오기 위해서 [XMLHttpRequest](XMLHttpRequest.md)객체를 사용한다.
>[!warning]
>>JSON 데이터는 객체, 배열, 문자열, 숫자, `Boolean` 타입을 지원합니다.
>>
>>모든 객체의 키(Property)는 큰 따옴표(`" "`)안에 있어야 합니다. 작은 따옴표의 경우 허용되지 않습니다.
>>
>>데이터만 저장 가능하여, 클라이언트나 서버에 함수를 보내는 것이 불가능합니다.

---
#### 자바스크립트 내장 클래스, `JSON`
- 자바스크립트 -> `JSON` 객체 || `JSON` 객체 -> 자바스크립트, 변환을 위해 사용하는 자바스크립트 내장 클래스
- 내장 메서드
	- `parse()`메서드: JSON 객체 -> Javascript 코드
	- `stringify()` : JavaScript 코드 -> JSON 데이터

- 자바스크립트는 JSON 객체를 JavaScript 배열 및 객체 등으로 변환하기 위한 클래스가 있다.
- 이 클래스에는 `parse()` 그리고 `stringify()`메서드가 있다.
	- `stringify()`메서드: JavaScript 코드나 객체, 배열을 JSON 데이터로 변환해준다.
	- `parse()`메서드: JSON 데이터를 Javascript로 변환해 준다.
		- `xhr.responseType`과 동일하게 사용된다.
---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기