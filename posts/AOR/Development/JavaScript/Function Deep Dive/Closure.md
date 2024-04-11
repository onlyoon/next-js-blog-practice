#aor 
### Closure
>[!note]
>#### 클로저
>
>>폐쇄
>
>>자신이 생성될 때의 렉시컬 환경[Lexical Environment](Lexical%20Environment.md)을 기억하는 함수
>
>>“A closure is the combination of a function and the lexical environment within which that function was declared.”  
>>클로저는 함수와 그 함수가 선언됐을 때의 렉시컬 환경(Lexical environment)과의 조합이다. - MDN
>
>>`function` 식별자를 가지고 함수를 선언할 때, 이 식별자를 가지고 새로운 렉시컬 환경을 만들어낸다.

---
#### 자바스크립트의 모든 함수는 클로저이다.
- 렉시컬 환경에 객체로서 정의되어 폐쇄적이며, 이 환경에 따른 프로퍼티들(변수나 함수)을 함수가 기억하기 때문에, 해당하는 함수가 사라지지 않는 한 필요하지 않더라도, 사라지지 않는다.
- 각 함수는 주변 환경을 등록하고 변수는 그 환경 안에서 정의된다.

>[!warning]
>>클로저는 현재 상태를 기억하고 변경된 최신 상태를 유지하는데 사용된다.
>
>>전역변수를 줄이는데 사용된다.
>
>>동일 형태의 코드 재사용률을 높이는 것이 가능하다.

---
#### 추가 정보
- [클로저에 대한 추가 정보](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기