#aor
### Event.preventDefault()
>[!note]
>`event.preventDefault()`
>
>>브라우저의 기본 동작을 실행하지 않도록 하는 메소드

>[!example]
>1. `<checkbox>` 클릭시 체크가 되는 경우
>2. `<a>` 클릭시 `href` 속성에 적힌 `url`로 이동하는 경우 
>3. `<form>` 내부의 `submit` 타입의 버튼 클릭시 action 속성 값으로 params를 전달하면서 페이지를 이동 및 새로고침 하는 경우

사용법:
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <script>
	const form = document.querySelector('form');
	 
	form.addEventListener('submit',event=> {
	    event.preventDefault(); <-- 위와 같이 설정할 경우, submit 후에 새로 고침이 실행되지 않아 event 로그를 볼 수 있다.
	    console.log(event);
	});
</script>
</head>
<body>
  <form>
    <lable for="title">Title</lable>
    <input type ="text" id="title">
    <button type="submit">Submit</button>
  </form>
</body>
</html>
```

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기