#aor 
### Class
>[!note]
>#### 클래스
>
>>객체를 위한 템플릿
>
>>객체 리터럴 표기법의 단점을 보완하기 위한 대안
#### Class 용어 정리
- `new`키워드를 통해 인스턴스(복제품)이 생성되면 클래스가 객체로 변환되며, `constructor()`함수가 호출되어 클래스 속성이 객체의 속성으로 바뀐다.

```js
class Product {
	category = 'DEFALT'; // 클래스 필드
	constructor(title) {
		this.title = title; // 클래스 속성
	}
	printInfo() { // 클래스 메서드 | 객체 메서드
		console.log(this.title, this.category);
	}
}

const chickenProduct = new Product("Chicken");
chickenProduct.category = "FOOD";
chickenProduct.printInfo();
```



### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기