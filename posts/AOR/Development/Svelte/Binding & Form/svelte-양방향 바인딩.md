#aor 
### Two-Way Binding
>[!note]
>#### 양방향 바인딩
>
>>부모 컴포넌트와 자식 컴포넌트가 데이터를 가지고 상호작용하여 서로 동기화하는 작업

- 사용법 : 
```html
// Parent.svelte
<script>
	import Child './Child.svelte';
	let val = '';
	$: console.log(val);
</script>

<Child bind:val={val} />
```

```html
Child.svelte
<script>
	export let val;
</script>

<input type="text" bind:value={val} />
```

>[!warning]
>>Svelte에서는 `<input>`태그의 `type`속성 값에는 양방향 바인딩을 집어넣을 수 없게 되어있다. 
>>ERROR: `'type' attribute cannot be dynamic if input uses two-way binding`
>
>>모든 컴포넌트 프로퍼티에 바인딩을 하는 경우, 버그가 발생되기가 쉽고 로직이 헷갈려서 애플리케이션 분석 및 이해가 어려워진다.
>
>>일반적 HTML태그의 속성 뿐만 아니라 커스텀 요소의 커스텀 속성에도 바인딩 설정이 가능하다.
### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기