#aor 
### not
>[!note]
>#### `:not()`
>
>>특정 규칙을 뒤집거나, 특정 선택자를 제외할 수 있게 하는 의사 클래스([[../Deep-Dive CSS/css-Pseudo]])
>
>>복잡하고 이해하기 어려운 규칙이 작성될 수 있다.

- 예시  
```css  
/* a.active빼고 모든 a태그 적용 */
a.active {  
color: #521751;  
}  
a:not(.active){  
color: blue;  
}
```  
### [CSS](../../../Dev-Index/CSS.md) Index로 돌아가기