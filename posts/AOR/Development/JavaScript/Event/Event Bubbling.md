#aor
### Event Bubbling
>[!note]
>Event Bubbling
>
>>이벤트가 연속하여 발생하는 버블 현상
>
>>한 요소에 이벤트가 발생하면 해당 요소에 할당된 이벤트 핸들러가 동작되고 이어서 부모 요소의 핸들러가 동작되고 지속적으로 최상단의 부모 요소를 만날 때까지 반복되어 핸들러가 동작되는 현상

예시:
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <script>
	const divs = document.querySelectorAll("div");
	
	const clickEvent = (e) => {
	  console.log(e.currentTarget.className);
	};
	
	divs.forEach((div) => {
	  div.addEventListener("click", clickEvent);
	});
</script>
</head>
 <body>
    <div class="DIV1">
      DIV1
      <div class="DIV2">
        DIV2
        <div class="DIV3">DIV3</div>
      </div>
    </div>
  </body>
</html>

```

![](../../../../Stuff/Image/AOR/JavaScript/Pasted%20image%2020230914122414.png)

- DIV3 버튼을 클릭하면 => DIV3, DIV2, DIV1 이벤트 전파

![](../../../../Stuff/Image/AOR/JavaScript/Pasted%20image%2020230914122630.png)

### [JavaScript](../../../Dev-Index/JavaScript.md) Index로 돌아가기