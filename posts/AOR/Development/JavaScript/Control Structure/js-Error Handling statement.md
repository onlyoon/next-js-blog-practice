#aor 
### Error Handling Control Structure
>[!note]
>#### 에러 핸들링 제어구조
>
>>오류가 발생되었다는 것을 알려주기 위해 사용한다.
>
>>직접 오류를 발생시키는 기능을 만들기 위해선
>>1. 함수를 직접 생성
>>2. try-catch문을 활용

#### 용도
- 입력의 오류 Catch
- 네트워크의 오류 Catch
- `...` 기타 등등
---
#### 형식
```jsx
try { ... } catch(error) { ... }
```
---
#### 예시
```jsx
try {
  chosenMaxLife = getMaxLifeValues();
} catch (error) {
  console.log(error);
  chosenMaxLife = 100;
  alert('입력값이 잘못되었으니 초기값 100으로 되었습니다.');
  throw error; // 자체 분석 서버로 해당하는 오류를 보내 앱에 생긴 오류의 알림을 받는 것이 가능, 자체 분석 서버에 오류를 기록
} finally { // 오류가 있든 없든 항상 실행
  // clean up 작업을 수행
}
```
---
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기