#aor 
### Axios
>[!note]
>#### Axios 라이브러리
>
>>데이터를 fetch를 하는 것을 개선하는데 초점을 맞춘 라이브러리이다.

- 오류 상태 코드를 반환하는 응답도, 에러 처리를 한다.
- 응답을 받을시, `.json()`메서드를 사용할 필요가 없다.
- 반환값이 [Promise](../Promise%20&%20Callback/Promise.md)객체이다.
- Header `Content-Type`를 입력할 필요가 없다.

```js
async function postRequest() {
	const response = await axois.post(URL, data);
	console.log(response.data);
}

async function deleteRequest() {
	const response = await axois.post(`URL$/{QUERYDATA}`);
	console.log(response.data);
}
```
### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기