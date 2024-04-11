#aor 
### Label Statement
>[!note]
>#### 레이블 구문
>
>>식별자가 붙은 구문
>
>>프로그램 실행 순서를 제어하기 위해 사용한다.
>>`break`, `continue` 구문을 사용해 반복문 실행 설정이 가능하다.
>
>>주로 이중 반복문 사용시, 내부 반복문은 유지하되 외부 반복문만 중단시키고 싶을 때 사용

- 기본 사용법 :
```javascript
label: statement

// apple 이라는 레이블 식별자가 붙은 레이블 문
// ex.)
apple: console.log("apple");
```

- 이중 반복문 활용 예시 : 반복문에 이름을 붙여 중단 시킨다.
- `outerWhile` 네이밍의 반복문: `do-while`문 활용
- `innerFor` 네이밍의 반복문: `for`문 활용
	- `innerFor`이라는 내부 반복문은 돌아가지만, `break outerWhile;`구문을 통해 `outerWhile` 반복문을 미리 중단시켰다.
```javascript
let j = 0;
outerWhile: do {
	console.log('Outer', j);
	innerFor: for ( let k = 0; k < 5; k++) {
		if (k === 3) {
			break outerWhile;
		}
		console.log('Inner', k);
	}
	j++;
} while (j < 3);
```

>[!warning]
>>만일 외부반복문에 계속(`continue`)를 사용할 경우 상위 반복문이 없어진 채로 반복되어 무한 반복문이 생성될 수 있다.
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기