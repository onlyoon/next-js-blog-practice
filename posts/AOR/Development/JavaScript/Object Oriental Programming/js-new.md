#aor 
### `new` 키워드
>[!note]
>#### `new` 키워드
>
>>객체를 생성하는 방법 중에서, 생성자 함수를 사용해 객체를 만드는 방법을 활용하는 키워드이다.
>
>>생성자 함수가 생성 중인 객체를 참조하기 위해 사용한다.

- 예시 : 
```js
class Product {
	constructor(title) {
		this.title = title; // 클래스 속성
	}
}
const chickenProduct = new Product("Chicken");
```
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기