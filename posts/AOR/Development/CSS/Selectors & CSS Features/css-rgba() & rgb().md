#aor 
### rgba() & rgb()
>[!note]
>#### rgba() & rgb()
>
>>rgb() 혹은 rgba() 함수는 적색, 녹색, 청색 파라미터 값에 따라서 색상을 표현하며, `_alpha`값을 통해 색상의 투명도를 나타낸다.

- `rgba()` 예시
```CSS
- 형식
rgba(_R _G _B[ / _A]);
rgba(_R, _G, _B, _A);
div {
	background-color: rgba(255, 0, 0, 0.5);
}
```

- `rgb()` 예시
```css
- 형식
rgb(_R _G _B[ / _A]);
rgb(_R, _G, _B, _A);

div {
  background-color: rgb(255, 0, 0, 0.5);
}
```

>[!warning]
>2023년 현재 `rgba()`함수는 레거시 구문이다.
### [CSS](../../../Dev-Index/CSS.md) Index로 돌아가기