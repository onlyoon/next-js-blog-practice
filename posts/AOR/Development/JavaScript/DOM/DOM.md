#aor 
### DOM
>[!note]
>#### Document Object Model
>
>>브라우저가 Web API를 노출하는 모델
>>이 모델을 통해 자바스크립트는 브라우저와 상호작용을 할 수 있다.

- `document`
	- 📖 Root DOM Node
		- 📖 랜더링된 HTML에 접근하기 위한 최상위 객체
	- HTML 요소 query 메서드로 접근
	- DOM 콘텐츠 상호작용
	- 로드된 HTML 코드와 상호작용을 위한 다양한 메서드 및 기능 제공
	- 📖 `window`객체의 일부
- `window`
	- 📖 JavaScript의 브라우저에서 사용 가능한 최상위 전역 객체
	- 활성화된 브라우저 창 및 탭을 보여줌
	- 📖 전역 엔트리포인트 & 저장소
		- 브라우저에 보여주는 핵심 API에 접근 가능⭕️
	- 실제 `window`에 접근할 수 없고 스크립트가 실행 중인 탭에만 접근 가능⭕️
		- 다른 탭에 로드된 다른 웹페이지와 상호작용이 불가능❌

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기