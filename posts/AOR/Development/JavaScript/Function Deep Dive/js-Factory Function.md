#aor 
### Factory Function
>[!info]
>#### 팩토리 함수
>
>>함수안에 함수를 가지는 함수
>
>>내부 함수는 외부 함수의 모든 상태에 접근이 가능하다.
>
>>재사용이 가능하다.

- 팩토리 함수 미적용 예시
```js
function calculateTax(amount, tax) {
	return amount * tax;
}
const vatAmount = calculateTax(100, 0.19);
const incomeTax = calculateTax(100, 0.25);
```
- 팩토리 함수 적용 예시
```js
function createTaxCalculator(tax) {
	function calculateTax(amount, tax) {
		return amount * tax;
	}
	return calculateTax;
}

const calculateVatAmount = createTaxCalculator(0.19);
const incomeTaxAmount = createTaxCalculator(0.25);

console.log(calculateVatAmount(100));
console.log(calculateIncomeTaxAmount(100));
```
---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기