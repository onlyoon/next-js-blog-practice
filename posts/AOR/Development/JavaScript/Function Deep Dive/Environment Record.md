#aor 
https://roseline.oopy.io/dev/javascript-back-to-the-basic/environment-record
https://velog.io/@sehyunny/what-is-realm-in-js
https://hihiha2.tistory.com/20
https://kwangsunny.tistory.com/37
https://h-owo-ld.tistory.com/m/149
### Environment Record
>[!note]
>#### 환경 레코드
>
>>코드의 중첩 구조를 기반으로 식별자들을 특정 변수 또는 함수에 연결(binding)하기 위해 사용
>
>>환경 레코드는 선언적 환경 레코드, 객체 환경 레코드, 그리고 함수 환경 레코드로 구성된다.

---
### Declarative Environment Record
>[!note]
>#### 선언적 환경 레코드
>
>>스코프(범위) 내에서 선언된 식별자들(`var`, `const`, `let`, `class`, `module`, `import`, `function`)의 바인딩을 관리하는 것이다.
>
>>선언적 환경 레코드는 함수 환경 레코드 그리고 모듈 환경 레코드로 구성된다.
#### Function Environment Record
>[!note]
>#### 함수 환경 레코드
>
>>함수의 최상단 스코프(범위)를 나타내는데 사용되는 선언적 환경 레코드 중 하나이다.
>
>>화살표 함수가 아니라면 `this`바인딩을 제공한다.
>>`super`을 참조하는 경우, 메서드를 실행하게끔 도와준다.
#### Module Environment Record
>[!note]
>#### 모듈 환경 레코드
>
>>Module의 외부 스코프를 나타낼 때 사용하는 선언적 환경 레코드 중 하나이다.
>
>>변경이 가능한 그리고 불가능한 바인딩과 변경이 불가능한 import 바인딩(immutable import binding)을 제공한다.

- immutable import binding은 참조하는 외부 레코드의 바인딩에 대해서 간접 접근으로 변경하지 못하게 한다.
---
### Object Environment Record
>[!note]
>#### 객체 환경 레코드
>
>>`Binding Object` 객체와 연결되는 환경 레코드

---
### Global Environment Record
>[!note]
>#### 전역 환경 레코드
>
>>최상단의 스코프를 나타내는데 사용하는 환경 레코드
>
>>`Built-In` 전역 객체[js-Built-in](js-Built-in.md), 전역 객체의 프로퍼티 및 스크립트 내의 모든 최상위 선언에 대한 바인딩 제공
>
>>전역 환경 레코드는 전역 환경의 객체 환경 레코드와 전역 환경의 선언 환경 레코드로 구성된다.

---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기