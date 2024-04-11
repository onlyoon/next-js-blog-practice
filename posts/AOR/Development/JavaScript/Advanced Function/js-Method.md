#aor 
### Method
>[!note]
>#### 메서드
>
>>객체에 저장된 함수를 말한다.
#### 메서드 예시
- 일반적인 객체
```js
const person = {
	name: 'Max', // property
	greet: function greet() { // <- greet Method
		console.log('Hello there!');
	}
}
person.greet(); // "Hello there!" 
```
- DOM
```js
const startGameBtn = document.getElementById('start-game-btn'); // <- getElementById Method
```
- EventListener
```js
function chicken() {
  console.log('Chicken');
}
startGameBtn.addEventListener('click', chicken); // <- addEventListener Method
```
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기