#aor 
### `type="number"` 바인딩
>[!warning]
>#### `<input>` 태그 `type="number"` 바인딩
>
>>`<input>`태그 `type="number"`의 출력값을 숫자로 변환시킬 경우 바인딩이 용이하다.

- `<input>`태그의 값을 문자열 -> 숫자로 변환하기 위해 활용하는 예시
```html

<!-- 이 경우 문자열 -> 숫자로 변환이 불가능하다. -->
<input type="number" value={price} on:input={event => console.log(event.target.value)} />

<!-- 이 경우 문자열 -> 숫자 변환이 가능하다. -->
<script>
	let price = 0;
	$: console.log(price);
</script>
<input type="number" bind:value={price} />
```
---
### `type="checkbox"` 바인딩
>[!warning]
>#### `<input>` 태그 `type="checkbox"` 바인딩
>
>>input태그 `type="checkbox"`의 값을 바인딩할 경우 값이 `undefined`가 나온다.
>
>>답: 값이 아닌 checked property를 바인딩을 해줘야 제대로 된 값을 받을 수 있다.

- `<input>`태그의 `type="checkbox"`의 값을 받는 예시
```html
<input type="checkbox" bind: checked={agreed} />
```

- `type="checkbox"`의 `<input>`태그가 그룹일 경우
```html
<script>
	let favColor = ["red"];
	$: console.log(favColor);
</script>

<input type="radio" name="color" vallue="red" bind:group={favColor} />
<input type="radio" name="color" vallue="blue" bind:group={favColor} />
<input type="radio" name="color" vallue="green" bind:group={favColor} />
<!-- 단일 혹은 중복 선택시 배열 출력 -->
```
---
### `type="radio"` 바인딩
>[!warning]
>#### `<input>` 태그 `type="radio"` 바인딩
>
>>input태그 `type="radio"`의 값이 그룹화 되어있는 경우 바인딩해 값을 도출할 수가 있다.

- `<input>`태그의 `type="radio"`의 값을 받는 예시
```html
<script>
	let favColor = "red";
	$: console.log(favColor);
</script>

<input type="radio" name="color" vallue="red" bind:group={favColor} />
<input type="radio" name="color" vallue="blue" bind:group={favColor} />
<input type="radio" name="color" vallue="green" bind:group={favColor} />
<!-- 단일 출력 -->
```
---
### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기