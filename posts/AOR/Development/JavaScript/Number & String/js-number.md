#aor 
### number
>[!note]
>#### 자바스크립트 숫자
>
>>자바스크립트의 모든 숫자는 64비트로 저장되는 소수점을 가집니다.
>>이를 통해 자바스크립트로 모든 수를 나타내는 것이 불가능합니다.
>
>>자바스크립트의 숫자는 정수형 숫자가 아닙니다.

- 자바스크립트의 한계
	- 해당 숫자를 넘는 수를 표현하는 것이 불가능하며 자바스크립트는 범위를 초과하는 수를 표현해야 할 경우 부정확한 결과를 보여준다.
```js
// 자바스크립트의 Number 객체로 표현할 수 있는 가장 큰 숫자
Number.MAX_SAFE_INTEGER
// 9007199254740991 <- 2 ^ (53 - 1)

// 자바스크립트의 Number 객체로 표현할 수 있는 가장 작은 숫자
Number.MIN_SAFE_INTEGER
// -9007199254740991 
```
#### 추가 정보
- [Number (mozilla)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기