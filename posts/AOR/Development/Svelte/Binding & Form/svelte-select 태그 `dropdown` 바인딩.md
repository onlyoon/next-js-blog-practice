#aor 
### `dropdown` 바인딩
>[!warning]
>#### `<select>` 태그 `dropdown` 바인딩
>
>>`<select>`태그 `dropdown`에 바인딩을 하고싶을 경우 `<select>`태그의 `value` 프로퍼티에 바인딩을 하면 된다.
>>d
>>`<select>`태그 내부의 `<option>` 값 선택시 동적 값으로 설정 가능

- `<select>`태그의 `dropdown` 예시
```html
<select bind:value={singleFavColor}>
	<option value="green">Green</option>
	<option value="red">Red</option>
	<option value="blue">Blue</option>
</select>
```
---
### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기