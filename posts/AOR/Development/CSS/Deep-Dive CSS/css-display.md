#aor 
### display
>[!note]
>#### display
>
>>요소의 동작을 바꾸기 위해서 사용하는 프로퍼티

- `display: block`  
	- 하나의 요소가 수평 공간 전체 차지  
	- `margin-top`, `margin-bottom` 설정시 두개의 블록은 서로 다른 라인에 렌더링  
	- 예시.) `<div>` `<section>` `<article>` `<nav>` `<h1>` `<p>`  
- `display: inline`  
	- `margin-top`, `margin-bottom`, `padding-top`, `padding-bottom`이 요소에 영향을 미치지 않음, 그러나 `border`에 영향을 미침 ([https://hacks.mozilla.org/2015/03/understanding-inline-box-model/](https://hacks.mozilla.org/2015/03/understanding-inline-box-model/))  
	- 너비와 높이는 콘텐츠가 필요로 하는 공간만을 차지  
	- 예시.) `<a>` , `<span>` , `<img>`  
- `display: inline-block` 
	- 인라인과 블록 레벨 요소의 속성 특성을 다 가짐  
- `display: none` 
	- HTML문서 자체에서 사라지게 하지만 DOM에는 남아있음
---
### [CSS](../../../Dev-Index/CSS.md) Index로 돌아가기