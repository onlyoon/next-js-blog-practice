#aor
### 두 컴포넌트간 통신
>[!note]
>#### 컴포넌트 property 전달
>
>> 방식 1. `<ContactCard userName="{name}" />`
>> 방식 2. `<ContactCard {name} />` (Self-Extending Property)

사용법:
```html
// App.svelte
<script>
    import ContactCard from "./ContactCard.svelte";
    export let name;
</script>
  
<ContactCard name="{name}"/> // 방식 1. userName property로 name변수 전달
<ContactCard {name}/> // 방식 2. name property로 name변수 전달
```

```html
<script>
    export let name; // 부모 컴포넌트로부터 userName 받아오기
</script>

<div class="contact-card">
      <h1>{name}</h1>  // 받아온 userName 활용
</div>
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기