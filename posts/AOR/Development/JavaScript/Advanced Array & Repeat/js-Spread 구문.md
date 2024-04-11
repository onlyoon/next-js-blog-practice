#aor
### Spread 구문
>[!note]
>Spread Syntax
>
>> 여러 개의 값을 하나로 압축하며, 이 압축되어 있는 값을 단일 값으로 지정되게 하여, 압축된 단일 값을 한 곳에 지정되게 넣어, 그 곳에서 값이 Spread 되게 도와주는 것이다.
>
>> 배열의 모든 요소를 꺼내 개별 요소의 리스트로 변환하는 구문

- 원본과 복사본은 서로 영향을 미치지 않는다.❌
	- 보통은 객체가 참조값이기 때문에 서로 영향을 미친다.
	- 전개 구문은 주소만을 복사하여 새로운 배열을 만들기 때문에 원본의 객체만을 편집할  경우 새로운 배열에도 영향을 미친다.

- 사용법 :
- 문자열, 숫자 예시
```js
const nameFragments = ['Max', 'Schwarz'];
const copiedNameFragments = [...nameFragments];
nameFragments.push('Mr');
console.log(nameFragments, copiedNameFragments);
const prices = [10.99, 5.99, 3.99, 6.59];
console.log(Math.min(...prices));
```

- 객체 예시
```js
const persons = [
  { name: 'Max', age: 30 },
  { name: 'Manuel', age: 31 },
];
const copiedPersons = [...persons]; // 주소만을 복사하여 새로운 배열을 만듦
persons.push({ name: 'Anna', age: 29 });
persons[0].age = 31; // 메모리 주소 공간을 복사하여 객체를 해당 메모리 공간에 추가
console.log(persons, copiedPersons);
// persons
// 0 : {name: 'Max', age: 31}   persons[0].age = 31
// 1 : {name: 'Manuel', age: 31}
// 2 : {name: 'Anna', age: 29}   .push({ name : 'Anna', age : 29 })

// copiedPersons
// 0: {name: 'Max', age: 31}   persons[0].age = 31
// 1: {name: 'Manuel', age: 31}
// => 객체만을 편집할 경우 새로 복사된 배열에도 영향을 미침
```

- `map()` 예시
```js
// map 함수 활용 예시
// 소괄호 - 중괄호 방식의 반환식일 경우 객체를 반환
// 새로운 객체가 있는 새로운 배열을 반환
const copiedPerson2 = persons.map((person) => ({
    name: person.name,
    age: person.age,
  }));
```

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기