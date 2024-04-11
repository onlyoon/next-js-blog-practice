#aor 
### Selector
>[!note]
>#### 선택자
>
>>DOM의 어떤 요소에 선언할 건지 CSS에게 알려주는 역할

- 구성요소
	- 💡 프로퍼티 (Property)
	- 💡 값 (Value)
- 선택자에 대한 선언 예시 :
```CSS
section {
	...
}
```
- 선택자 종류
	- 💡 ==Elements== - `h1{ ... }`
	- 💡 ==Classes== - `.blog-post{ ... }`
		- 같은 클래스로 묶인 요소들에 적용
		- 케밥 표기법(kebab case) 사용
	- 💡 ==Universal== - `*{ ... }`
	- 💡 ==Id== - `#main-title{ ... }`
		- 하나의 요소에만 적용
	- 💡 ==요소의 속성 선택자== - `[disabled]{ ... }`
		- 해당하는 속성을 가진 여러 요소 일괄 적용
### [CSS](../../../Dev-Index/CSS.md) Index로 돌아가기