#aor
### 변수

변수 설정시 props에 설정 후 `.svelte`파일에서 `export`해서 사용

- 예시
```javascript
// JavaScript 예시
import App from './App.svelte';
  
const app = new App({
    target: document.body,
    props: {
        name: 'world'
    }
});

export default app;
```

- 예시
```html
// Svelte 예시
<script>
    export let name;
</script>
  
<style>
    h1 {
        color: purple;
    }
</style>
<h1>Hello {name}!</h1>
```
### [[Svelte]]로 돌아가기