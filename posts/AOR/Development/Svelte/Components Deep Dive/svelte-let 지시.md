#aor
### `let:`
>[!note]
>let 구문
>
>> 슬롯을 가진 컴포넌트에서 슬롯을 사용하는 컴포넌트로 데이터를 다시 전달하기 위해 사용하는 구문

사용법:
- `Modal.svelte` 파일에서 사용되고 있는 `agreed`변수를 담아서, `didagree`라는 프로퍼티에 담아주며, `App.svelte` 파일에서 `let:`구문을 활용해서 `App.svelte`파일에 담겨진 `closeable`이라는 변수에 `binding`할 수 있도록 한다.

```html
  <!-- App.svelte -->
  
  <script>
  import {} from 'svelte';
  import Modal from "./Modal.svelte";
  
  let showModal = false;
  let closeable = false;
  
  function addToCart(event) {
    console.log(event);
  }
  
  function deleteProduct(event) {
    console.log(event.detail);
  }
</script>
<Modal
  on:cancel={() => (showModal = false)}
  on:close={() => (showModal = false)}
  let:didAgree={closeable}>
  <button slot="footer" on:click={() => (showModal = false)} disabled={!closeable}>Confirm</button>
</Modal>
```

```html
<!-- Modal.svelte -->
<script>
  import { createEventDispatcher } from "svelte";
  
  const dispatch = createEventDispatcher();
  
  let agreed = false;
</script>
  
<style>
  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.75);
    z-index: 10;
  }
  
  .modal {
    padding: 1rem;
    position: fixed;
    top: 10vh;
    left: 10%;
    width: 80%;
    max-height: 80vh;
    background: white;
    border-radius: 5px;
    z-index: 100;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    overflow: scroll;
  }
  
  header {
    border-bottom: 1px solid #ccc;
  }
 </style>


<div class="backdrop" on:click={() => dispatch('cancel')} />
<div class="modal">
    <slot name="footer" didAgree={agreed}>
      <button on:click={() => dispatch('close')} disabled={!agreed}>
        Close
      </button>
    </slot>
</div>
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기