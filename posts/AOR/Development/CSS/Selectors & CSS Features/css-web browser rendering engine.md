### Web Rendering Engine
>[!note]
>#### 웹 렌더링 엔진
>
>>브라우저의 핵심 구성 요소중 하나
>
>>요청받은 내용을 브라우저 화면에 표시하는 일을 한다.

- 렌더링 동작 과정
	1. HTML 파일 파싱
	2. 파싱된 태그 DOM 노드로 전환
	3. CSS 파일 파싱
	4. 파싱된 HTML & CSS 파일을 가지고 렌더 트리 생성
	5. 렌더 트리를 기반으로 배치 및 그리기
	6. 완료된 화면 표시
---
### webkit 동작 과정
![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930174238.png)
#### HTML 파일 파싱 및 DOM 트리 생성
- HTML 문서 파싱 후 Parsing Tree 생성
- Parsing Tree 기반 DOM Tree 생성

![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930182111.png)
![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930181850.png)
#### CSS 파일 파싱 및 CSSOM(CSS Object Model) 생성
- CSS 파일 파싱 후 Parsing Tree 생성
- Parsing Tree 기반 CSSOM ([[css-CSSOM]]) 생성

![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930181931.png)
#### 렌더 트리 생성
![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930181945.png)

---
- gecko 동작 과정

![](../../../../Stuff/Image/AOR/CSS/Pasted%20image%2020230930175533.png)

---
- 종류
	- webkit ([[css-webkit]])
		- 애플에서 개발한 KHTML 엔진에서 파생된 오픈소스 엔진
	- blink
		- webkit을 기반으로 제작한 엔진
		- 구글 크롬, 마이크로 소프트 엣지, 네이버 웨일 등 대부분의 브라우저가 블링크를 사용
	- gecko
		- 모질라 재단의 오픈소스 엔진
	- servo
		- 모질라 재단의 차세대 엔진
	- presto
		- 휴대용 기기, 및 게임용 콘솔 전용 엔진
		- 현재 블링크 사용
---
### [CSS](../../../Dev-Index/CSS.md) Index로 돌아가기