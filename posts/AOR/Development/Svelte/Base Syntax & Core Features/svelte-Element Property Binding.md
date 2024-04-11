#aor
### Element Property Binding

>[!note]
>#### Svelte의 DataFlow
>
>> 기본적인 Svelte의 DataFlow는 단방향이라 Html Element의 Attribute의 변경 사항에 따라 변수를 바꾸지 않는다.
>
>> 그래서 양방향 DataFlow를 위해 `listener`를 추가해야 한다.
>
>> ex.) 방식 1. `on:input="{}"` 방식 2.  `bind:value="{}"`
>
>> Custom 요소에서도 양방향 바인딩을 사용하는 것이 가능하다.

방식 1: `on:input="{}"`
```javascript
<script>
	export let name;
	export let age;
	$: uppercaseName = name.toUpperCase();
	$: if (name === 'Wen') {
		age = 31;
	}
	function countIncrement() {
        return age += 1;

    }
	function nameInput(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<input type="text" value="{name}" on:input="{nameInput}" />
```

방식 2: `bind:value="{}"`
```javascript
<script>
let name = 'Yoon';
let age = '27'
$: uppercaseName = name.toUpperCase();
$: if (name === 'Wen') {
	age = 31;
}
</script>

<input type="text" bind:value="{name}" />
```

>[!warning]
>> 모든 컴포넌트의 `prop`에 양방향 바인딩을 하는건 버그가 발생하기가 쉽다. 

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기
