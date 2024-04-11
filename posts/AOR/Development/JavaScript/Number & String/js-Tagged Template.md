#aor 
### Tagged Template
>[!info]
>#### 태그드 템플릿
>
>>템플릿 리터럴과 함께 사용하는 함수
>>함수 이름 뒤에 괄호가 아닌 백틱을 추가하는 함수이다.
>
>>기존의 문자열을 가지고 출력값을 생성하고자 할 때 삼항연산자 보다 유용한 함수이다.

- 예시
```js
function productDescription(string, productName, productPrice) {
	console.log(string);
	console.log(productName);
	console.log(productPrice);
	let priceCategory = 'cheap';
	if (productPrice > 20) {
		priceCategory = 'fair';
	}
	return `${string[0]}${productName}${string[1]}${priceCategory}${string[2]}`;
}
const prodName = 'JavaScript Course'
const prodPrice = 29.99;
const productOutput = productDescription`This product (${prodName}) is ${prodPrice}`;

console.log(productOutput);
// ["This product (", ") is", "."] <- 첫번째 파라미터는 템플릿 리터럴로 분리된 문자열을 배열 형태로 가져온다.
// JavaScript Course <- 두번째 파라미터는 템플릿 리터럴이 된다.
// 29.99
// This product (JavaScript Course) is fair.
```
#### 추가 정보
- [Tagged Template(MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_templates)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기