#aor 
### ts(2451)
>[!note]
>#### Cannot redeclare block-scoped variable
>
>>특정 변수나 타입이 전역 스코프 또는 해당 라이브러리의 타입 정의와 충돌했기에 발생하는 현상

-  TypeScript의 경우 전역 실행 환경을 위해 DOM 입력을 사용하여, `name`이라는 변수명을 사용할 경우, `window`객체의 특정 속성과 충돌하게 된다.
1. 빈 export를 추가해서 `window`객체의 `name` 속성과의 충돌 해결
```ts
export {}; // 빈 export 추가
const name = 'john';
```
2. `es6`를 lib 속성에 추가함으로서 `es6` 문법에 관련된 ts(2451) 오류 제거
```ts
// tsconfig.json
{
	"compilerOptions": {
		"lib": ["es6"]
	}
}
```

### [TypeScript](../../Dev-Index/TypeScript.md) Index로 돌아가기