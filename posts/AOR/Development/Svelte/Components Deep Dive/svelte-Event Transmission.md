#aor
### Event Transmission
>[!note]
>#### 이벤트 전달
>
>> Svelte는 부모 컴포넌트가 prop으로 이벤트를 하위 컴포넌트에게 전달이 가능하다.
>
>> 전달은 하나의 컴포넌트 수준에서만 가능하며 동작이 가능하다.

사용법 :

```html
<!-- App.svelte -->
<script>
  import Product from './Product.svelte';
</script>
  
<Product productTitle="A Book" on:click={() => alert('Clicked!')}/> <- 위와 같이 on:click을 하위 컴포넌트에 전달하면
```

```html
<!-- Product.svelte -->
<script>
    export let productTitle;
</script>
  
<article>
    <h1>{productTitle}</h1>
    <button on:click>Add to Cart</button> <- 하위 컴포넌트가 받아서 사용하는 것이 가능하다.
    <button>Delete</button>
</article>
```

>[!warning]
>>하위 컴포넌트의 요소에 해당 이벤트가 들어있지 않았을 경우, 이벤트 전달이 되지 않는다.

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기