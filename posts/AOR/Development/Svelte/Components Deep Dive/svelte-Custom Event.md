#aor
### Custom Event
>[!note]
>Custom Event
>
>>브라우저에서는 Custom된 Event를 생성시킬 수 있다.

사용법:

1. `createEventDispatcher` import
```javascript
import { createEventDispatcher } from 'svelte'
```

2.  `createEventDispatcher()`함수의 return 값으로 `dispatch` 변수 생성
```javascript
const dispatch = createEventDispatcher();
```


3. 이벤트 함수 입력 및 `dispatch` 인수 입력
- 1번째 인수: 이벤트 네이밍
- 2번째 인수: 데이터 전달
```javascript
function addToCart() {
	dispatch("Add-To-Cart", {id: 'Yoon'}); // <- 원하는 네이밍 입력
}
```

4. 이벤트 활용
```html
<button on:click="{addToCart}"></button>

<!-- 혹은 -->

<button on:click={(event) => 
	{
		dispatch('delete', {id: 'Wen'})} // <- console.log(event)의 로그의 detail property를 보면 {id: 'Wen'}인 것을 알 수 있다.
		console.log(event);
	} 
/>
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기