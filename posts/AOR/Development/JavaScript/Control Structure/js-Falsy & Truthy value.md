#aor 
### Falsy & Truthy value
>[!note]
>#### Falsy & Truthy value
>
>>Boolean 문맥에서 사용되는 모든 true값: truthy, 모든 false값: falsy
>
>>자바스크립트는 해당하는 조건문 값을 Boolean 값으로 강제로 변환한다. (실제로 변환되지는 않는다)
### Truthy
- 조건문 값이 문자열일 경우 `true`
- 조건문 값이 배열, 객체일 경우 `true`
```javascript
// truthy 값이 되는 것들
if (true)
if ({})
if ([])
if (42)
if ("0")
if ("false")
if (new Date())
if (-42)
if (12n)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
```
### Falsy
```javascript
// falsy 값이 되는 것들
if (false)
if (null)
if (undefined)
if (0)
if (-0)
if (0n)
if (NaN)
if ("")
```

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기