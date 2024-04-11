#aor 
### BigInt
>[!note]
>#### BigInt
>
>>숫자의 길이의 제약이 없이 정수를 다룰 수 있게 해주는 숫자형
>
>>숫자에 n을 붙이면 BigInt가 된다.

- 예시 (n을 숫자 옆에 붙이면 된다)
```js
// Number
90071992547409919
// BigInt
90071992547409919n
BigInt(90071992547409919);
// BigInt floating point error
90071992547409919.55n
```

>[!warning]
>>BigInt로 소수를 표현할 경우 에러가 나타난다. <- 정수형만 가능하다.
>
>>5n / 2n일 경우 2.5n이 아닌 2n이 나타난다. 소수를 표현하는 것이 불가능하기 때문이다.
>
>>BigInt 숫자를 다른 타입의 숫자와 계산하는 것이 불가능하다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기