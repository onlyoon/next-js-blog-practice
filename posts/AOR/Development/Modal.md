#aor

@출처
https://brunch.co.kr/@bommade/45
### Modal
>[!note]
>Modal
>
>> 화면을 다른 화면 위로 띄워 표현하는 방식으로, 사용자의 이목을 끌기 위해 사용하는 화면 전환 기법이다.
>
>
>>Modal을 만들기 위해서는 두개의 `<div>`태그가 필요하다.
>>하나는 모달용 `<div>` 다른 하나는 백드롭용 `<div>`
>

>[!note]
>Modal `<div>`
>
>> 컨텐츠를 보여주는 `<div>`이다.

사용법(js) : 
```css
.modal {
  padding: 1rem;
  position: fixed;
  top: 10vh;
  left: 10%;
  width: 80%;
  max-height: 80vh;
  background: white;
  z-index: 100; /* 가장 최상단에 보여주도록 한다. */
}
```

>[!note]
>BackDrop `<div>`
>
>>배경 화면이 어두워지게 하는 `<div>`이며, 전체 웹사이트를 다 감싸야 한다.

사용법(js) : 
```css
.backdrop {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100vh;
	background: rgba(0, 0, 0, 0.75); /* 사용자의 입맛대로 투명도 수정 가능 */
	z-index: 10; /* 숫자를 높게해 가깝게 배치 */
}
```

>[!warning]
>>중요한 User Flow에서는 모달을 사용하지 않는다.
>
>>무언가를 추가하거나 수정, 코멘트 작성 등 특정 구간에 제한된 액션을 하는 곳에서 모달을 사용한다.
>>정보의 흐름에 따르지는 않지만, 꼭 이목을 끌어야 할 때 사용한다.
>
>>화면은 되도록 단순하고, 사용자가 빠르게 처리할 수 있는 내용을 표현해야 하는 것이 좋다.
>
>>모달 사용을 최소화해야 한다.
>>사용자는 빈번한 모달 사용시 서비스에 집중하지 못하고, 피곤함을 느낄 수 있으며, 지속된 광고/스팸 팝업으로 인식이 가능하다.

