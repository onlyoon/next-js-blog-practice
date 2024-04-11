#aor 
### requestAnimationFrame() - Canvas API
>[!note]
>#### rAF
>
>>브라우저에게 애니메이션을 알려 다음 렌더링이 갱신되기 전에 브라우저가 애니메이션을 위해 지정된 함수를 호출하도록 요청하는 메서드
>
>>Repaint가 되기 전에 사용하는 메서드

- 애니메이션의 부드러운 렌더링을 보여주기 위해서 사용한다.
	- 브라우저에서 사용자에게 부드러운 애니메이션을 구현하려면 16.6ms마다 코드를 호출하는 식으로 구현해야 한다. ( 1000ms / 60fps )
	- 16.6ms 마다 코드를 지속적으로 호출하는 함수는 `setInterval()`과 `setTimeout()`이 있다.

#### `setInterval()` & `setTimeout()` vs. `rAF`
- `setInterval()` & `setTimeout()` 이 두가지 함수는 타이머 함수이며, 이 타이머 함수는 주어진 시간 내에 동작하지만, 프레임을 신경쓰지 않고 동작한다.
- `rAF`는 타이머에 따라 동작하는 것과 달리 실제 화면이 갱신되어 표시되는 주기에 따라서 함수를 호출해, 자바스크립트가 프레임 시작 시 실행되도록 보장해준다.

>[!info]
>>16.6ms마다 코드를 호출하는 식으로 표현해야 하는 이유는 인간의 눈은 1초에 60번 장면이 넘어가야 부드럽다고 느끼기 때문이다. ( 1000ms / 60fps )
>
>>자바스크립트에서 스타일 속성 변경시, 특히 모바일에서 성능이 좋지 않기 때문에, 최적화를 하기 위해서 사용한다.
>
>>`requestAnimationFrame()`은 요청 ID를 반환하며, 이 ID와 cancelAnimationFrame을 사용해 애니메이션을 중지시킬 수 있다.

- https://inpa.tistory.com/entry/%F0%9F%8C%90-requestAnimationFrame-%EA%B0%80%EC%9D%B4%EB%93%9C
- https://www.jeong-min.com/36-RAF/
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기