---
title: 'Save & Store - Canvas API'
date: '2020-01-01'
---

### Save & Store - Canvas API
>#### Save & Store
>
>>context의 stroke style을 **save**하고 **restore**시 **save**했던 상태로 되돌아가는 메서드

#### 코드 예시
```html
<html>
    <head>
        <style>
            canvas { border: 1px solid black; }
       </style>
        <script>
            window.onload = function(e) {
                var _cvs = document.querySelector("#myCanvas"),                        
                    _ctx = _cvs.getContext("2d");
                
                _ctx.fillStyle = "red";
                _ctx.fillRect(10, 50, 100, 100); // <-- 빨강
                
                _ctx.save();
                
                _ctx.fillStyle = "blue";
                _ctx.fillRect(120, 50, 100, 100); // <-- 파랑
                
                _ctx.save();
                
                _ctx.fillStyle = "orange";
                _ctx.fillRect(230, 50, 100, 100); // <-- 주황
                
                _ctx.restore();
                
                _ctx.fillRect(340, 50, 100, 100); // <-- 파랑
                
                _ctx.restore();
                
                _ctx.fillRect(450, 50, 100, 100); // <-- 빨강
            }
       </script>
    </head>
    
    <body>
        <canvas id="myCanvas" width="560" height="240"></canvas>
    </body>
</html>
```
