#aor
### Component Life Cycle
>[!note]
>컴포넌트 생명주기
>
>> Svelte의 컴포넌트 생명 주기는 총 2개의 파트로 나뉜다.
>
>> 1. Svelte가 컴포넌트의 생명 주기를 생성하는 파트
>> 2. Svelte가 컴포넌트에 의해 생성된 실제 DOM을 업데이트하는 파트

#### Svelte가 컴포넌트의 생명 주기를 생성하는 파트
 - `<script>` 태그 실행
	 - 컴포넌트가 DOM 어딘가에 렌더링될 경우 하향식으로 실행된다.
	 - 기초적인 초기화 단계가 이루어지게 된다.
 - `onMount()`
	 - Svelte가 제공하는 함수
	 - 복잡한 초기화 단계가 이루어지게 된다. { ex.) DataFetching }
		 - 서버에서 데이터를 가져올 경우 onMount() 함수 실행
- `onDestroy()`
	- Svelte가 제공하는 함수
	- 컴포넌트가 DOM에서 분리될 경우 실행되는 함수
		- DOM에서 엘리먼트 제거, 이벤트 리스너 제거 등 여러 정리 작업의 업무를 맡고 있는 함수

예시 :
```html
<script>
  import { createEventDispatcher, onMount, onDestroy } from "svelte";

  const dispatch = createEventDispatcher();  
  onMount(() => {
    console.log('onMount');
  });
  
  onDestroy(() => {
    console.log('onDestroy');
  });
  console.log("Script executed!");
</script>
```

- 컴포넌트가 생성되었을 때
```javascript
// when component created
Script executed!
onMount
```

- 컴포넌트가 없어졌을 때
```javascript
// when DOM element deleted
onDestroy
```
#### 1. Svelte가 컴포넌트에 의해 생성된 실제 DOM을 업데이트하는 파트
- `beforeUpdate()`
	- 업데이트가 실제 DOM에 반영되기 전에 실행되는 함수
	- Markup에서 무언가가 변경될 경우, 실제 DOM에 연결하기 직전의 추가 코드를 위한 함수
	- 주로 Svelte가 업데이트 되기 전 DOM 상태를 저장하기 위해서 사용
- `afterUpdate()`
	- 업데이트가 실제 DOM에 반영된 직후에 실행되는 함수
	- DOM이나 View단을 수동으로 업데이트 하는데 용이한 함수
	- ex.) 스크롤 위치
- `tick()`
	- `node.js`의 이벤트 루프가 완료된 작업들 끼리 연결이 가능해 다음 작업간의 연결이 가능하다.
	- `Promise` 객체를 반환하며, `Promise`객체가 해결되는 것은 다음 업데이트 완료 이후이다.
	- 특정 함수에 의해 DOM이 수정되면, 코드가 실행이 되더라도, `afterUpdate`가 반영이 되지 않는 결과를 볼 수 있다. 이것을 해결하기 위해 `tick()`을 사용한다.

>[!warning]
>>`beforeUpdate`, `afterUpdate`, `onMount`, `onDestroy`는 항상 `<script>`태그 내부에 있는 함수 핸들러 외부에서 호출해야 한다.
>
>>함수 내부에서 호출은 불가능하다.

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기