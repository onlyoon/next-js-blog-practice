#aor 
### Query Method
>[!note]
>#### 쿼리 메서드
>
>>자바스크립트에서 HTML요소를 쿼리 및 선택시, 사용되는 메서드

##### `document.querySelector(<CSS selector>); ` :  
- 반환 값 (요소 | null)  
##### `document.getElementById(<ID>);` :  
- 반환 값 (요소 | null)  
##### `document.querySelectorAll(<CSS selector>);` :  
- 유연성, 다양한 쿼리 지원
- 반환 값 (NodeList 객체 | 빈 NodeList 객체) 
	- Non-Live List, DOM의 스냅샷 반환
##### `document.getElementsByClassName(<CSS CLASS>);` :  
- 반환 값 (HTMLCollection 객체 | 빈 HTMLCollection 객체)
##### `document.getElementsByTagName(<HTML TAG>);` :  
- 반환 값 (HTMLCollection 객체 | 빈 HTMLCollection 객체)
	- Live-List, 최신 DOM 반영
----
- 첫 자식 노드 & 마지막 자식 노드  
	- `태그 이름.firstElementChild`  
	- `태그 이름.firstChild`  
	- `태그 이름.lastElementChild`  
	- `태그 이름.lastChild`  
- 부모 노드  
	- `태그 이름.parentNode`  
	- `태그 이름.parentElement`  
	- `태그 이름.closest`  
	- 요소 트리에 있는 아무 조상을 선택할 때 용이  
- 형제 노드  
	- `태그 이름.previousElementSibling`  
	- 📖 가장 가까운 이전 형제 요소 노드 반환  
	- `태그 이름.nextSibling  
	- 📖 가장 가까운 이후 형제 요소 노드 반  
---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기