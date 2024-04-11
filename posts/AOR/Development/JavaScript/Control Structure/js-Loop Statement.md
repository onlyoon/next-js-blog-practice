#aor 
### 반복문 제어구조
>[!note]
>#### 반복문 제어구조
>
>>반복문 제어구조엔 총 4가지 방식이 있다.
>>1. for Loop
>>2. for-of Loop
>>3. for-in Loop
>>4. while Loop
#### 1. for loop

```javascript
for (let i = 0; i < 3; i++) {
  console.log(i);
}
```
----
#### 2. for-of loop

- 배열의 모든 요소에 대해 코드 실행
```javascript
for (const el of array) {
  console.log(el);
}
```
----
#### 3. for-in loop

- 객체의 모든 키에 대해 코드를 실행
```javascript
for (const key in obj) {
  console.log(key);
  console.log(obj[key]);
}
```
----
#### 4. while loop

- 조건이 충족되는 동안에만 코드를 실행

```javascript
while (isLoggedIn === true) {
  ...
}
```
---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기