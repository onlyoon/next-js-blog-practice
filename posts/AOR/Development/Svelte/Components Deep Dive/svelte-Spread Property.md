#aor
### Spread Property
>[!note]
>Spread Property
>
>>Spread 연산자([[../../JavaScript/Advanced Array & Repeat/js-Spread 구문]])를 가지고 컴포넌트의 Property에 넣어준다.

사용법 :
```html
<script>
  import Product from "./Product.svelte";
  
  let products = [
    {
      id: "p1",
      title: "A book",
      price: 9.99
    },
    {
      id: "p1",
      title: "A book",
      price: 9.99
    },
    {
      id: "p1",
      title: "A book",
      price: 9.99
    },
  ];
  
</script>

{#each products as product}
<Product {...product} />
{/each}
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기