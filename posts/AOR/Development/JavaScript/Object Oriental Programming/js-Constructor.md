#aor 
### Constructor
>[!note]
>#### 생성자 함수
>
>>클래스의 새 인스턴스(복제품)를 만들면, 가장 먼저 실행되는 함수
#### 특징
- `Constructor()`함수 내의 `this` 키워드를 통해 이 복제품에 대한 속성(클래스 필드)을 지정할 수 있다.
- `new`키워드[js-new](js-new.md)를 통해 인스턴스(복제품)를 만들면, 이 인스턴스는 JavaScript에게 객체형태를 제공한다.
- 인스턴스(복제품)에게 인수를 넣으면, 생성자 함수가 전달 받는다.
- 상속받은 클래스의 경우에는 생성자 함수가 없으며, 부모 클래스의 생성자 함수가 자동으로 호출된다.

>Constructor is a special method on JS Class. When i call this JS class later using the new keyword, constructor will create one new black JS object and assign it properties and values based on the blueprint inside
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기