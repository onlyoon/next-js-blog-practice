#aor
### Slot
>[!note]
>Slot
>
>>컴포넌트의 HTML 코드에서 부모 컴포넌트(외부 컴포넌트)로 커스텀 Mark-up 삽입 가능
>>`@ html`과 다르게 XSS 공격에 대응할 수 있다.

사용법 :
- `slot`에 이름을 지어서 여러 슬롯을 대상으로 지정하는 것이 가능하다.

```html
<!-- App.svelte -->
<Modal>
	<h1 slot="header">Hello!</h1>
	<p>This Work!</p>
</Modal>
```

```html
<!-- Modal.svelte -->
<header>
	<slot name="header"/>
</header>
<div class="content">
	<slot/>
</div>
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기