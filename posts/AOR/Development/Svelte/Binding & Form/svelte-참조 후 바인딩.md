#aor 
### 요소 참조 후 바인딩
>[!note]
>#### Binding After Element Reference
>
>>DOM요소에 대해 참조하고 연결된 포인터의 값을 변수에 저장하기 위해 사용하는 방법이다.
>
>>Svelte를 활용해서 DOM을 변경하는 것이 가능해진다.

- 기존 JS방식
```html
<script>
	function saveData() {
		console.log(document.querySelector("#username").value);	
	}
</script>

<input id="username" />
```

- Svelte 적용 방식
```html
<script>
	function saveData() {
		console.log(usernameInput.value);	
		console.dir(usernameInput);	<!-- 전체 DOM요소를 볼 수 있다. -->
	}
	let usernameInput;
</script>

<input bind:this={userNameInput} />
```

>[!warning]
>>데이터는 항상 Svelte의 일반 구문을 통해서 변경되어야 하니 가급적이면 읽기만 하는 것이 좋다.

---
### 컴포넌트 참조 후 바인딩
>[!note]
>#### Binding After Component Reference
>
>>컴포넌트에 대해 참조하고 연결된 포인터의 값을 변수에 저장한 후에 읽기 위해서 사용하는 방법이다.
>
>>Svelte가 컴포넌트 객체를 바라보는 방식을 알 수 있다.

- Svelte 적용 방식
```html
<!-- App.svelte -->
<script>
	import Product from "./product";
	let customComponent;
	$: console.dir(customComponent); <-- 하위 컴포넌트에 대해서 Svelte가 컴포넌트 객체를 어떻게 바라보는지 알 수 있다.
	let val = 'value';
	function emptyValue() {
		customComponent.empty(); <-- 하위 컴포넌트의 함수를 불러와 사용할 수 있는 특이한 케이스를 적용하는 것이 가능하다.
	}
</script>

<Product val={val} bind:this={customComponent} />
<button on:click={emptyValue}>empty</button>
```

```html
<!-- Product.svelte -->
<script>
	export let val;
	$: let value = val;
	function empty() {
		val = '';
	}
</script>

<p>Product Component with the value: {value}</p>
```

>[!warning]
>>일반적으로는 상태를 관리할 때 프로퍼티와 커스텀 이벤트를 사용해야 하지 함수를 하위 컴포넌트에서 함수를 불러와 사용하는 것은 특이한 경우에 속한다.
>
>>반드시 다른 컴포넌트 내에서 함수를 트리거 해야할 경우에만 사용한다.
### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기