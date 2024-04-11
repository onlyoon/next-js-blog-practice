#aor 
### tweened
>[!note]
>#### Title
>
>>값이 변경될 때 적용되는 애니메이션 저장소
>>Tweened는 숫자와 날짜를 값으로 가지는 객체나 배열 관련해서 애니메이션을 만들 수 있다.


#### 작동 예시
```html
<script>
import {tweened} from "svelte/motion";
import {} from "svelte/easing"; // <-- github svelte에서 easing.mjs 파일에서 다양한 메서들과 함수 공식이 있다.   
const progress = tweened(0, {
	delay: 0, // <-- 애니메이션이 시작할 때까지 걸리는 시간
	duration: 700, // <-- 애니메이션이 작동되는 시간, 기본값 400밀리초 | Max값 700밀리초 
	easing: "?", // <-- 
	interpolator: "?",
});

setTimeout(() => {
	progress.set(0.5);
}, 1500);
</script>

<progress value={$progress} />

```

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기