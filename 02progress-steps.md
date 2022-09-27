##### 这个真的好难写，想不到一个日常生活中遇到的简单操作写起来这么麻烦。
   今天费了好大劲才实现step之间的横线，而且还没完全掌握更离谱的是js的操作直接把我整懵了，这比第一个项目的js操作复杂多了。:joy:
遇到看不懂的，直接[MDN](https://developer.mozilla.org/zh-CN/),或者说直接[Google](https://google.com)
***
总之第二个项目就先这样了

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Progress Steps</title>
     
    <style>
    *{
        box-sizing: border-box;
    }

    
:root {
  --line-border-fill: lightblue;
  --line-border-empty: #383838;

}

    body{
        display: flex;
        height: 100vh;
        align-items: center; /* 上下居中 */
        justify-content: center;   /* 左右居中 */
       
    }

    .container{
        text-align: center;
    }

    .progress-container{
        display: flex;
        justify-content: space-between;
        position: relative;
        margin-bottom: 30px;
        max-width: 100%;
        width: 500px;
        
    }

    .progress-container::before {
  content: '';/*这个很重要 */
  background-color: blue;
  position: absolute; /*这个很重要 */
  top: 50%;

  height: 4px; /*这个很重要 */
  width: 100%; /*width这个很重要 */
  z-index:-1;
}
     .progress {
        background-color: var(--line-border-fill);
        position: absolute;
        
        transition: 0.4s ease;
} 

    
.circle{
    height: 50px;
    width: 50px;
    background-color: lightblue;
    text-align: center;
    padding-top: 12px;
    border-radius: 50%;
    border: 3px solid red;
    
}   
.circle.active {
  border-color: var(--line-border-fill);
} 

.btn{
    height: 40px;
    width: 100px;
    border-radius: 30px;
    border: 3px solid #383838;
    color: black;
}


.btn:disabled {
  
  cursor: not-allowed;
}
    </style>

</head>
<body>
    <div class = "container">
        <div class = "progress-container">
            <div class="progress" id="progress"></div>
            <div class = "circle active">1</div>
            <div class = "circle">2</div>
            <div class = "circle">3</div>
            <div class = "circle">4</div>
              
        </div>

        <button class = "btn" id = "prev" disabled>Pre</button>
        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
        <button class = "btn" id = "next">Next</button>

        <script type = "module">
            const progress = document.getElementById('progress')
const prev = document.getElementById('prev')
const next = document.getElementById('next')
const circles = document.querySelectorAll('.circle')

let currentActive = 1

next.addEventListener('click', () => {
    currentActive++

    if(currentActive > circles.length) {
        currentActive = circles.length
    }

    update()
})

prev.addEventListener('click', () => {
    currentActive--

    if(currentActive < 1) {
        currentActive = 1
    }

    update()
})

function update() {
    circles.forEach((circle, idx) => {
        if(idx < currentActive) {
            circle.classList.add('active')
        } else {
            circle.classList.remove('active')
        }
    })

    const actives = document.querySelectorAll('.active')

    progress.style.width = (actives.length - 1) / (circles.length - 1) * 100 + '%'

    if(currentActive === 1) {
        prev.disabled = true
    } else if(currentActive === circles.length) {
        next.disabled = true
    } else {
        prev.disabled = false
        next.disabled = false
    }
}
        </script>
    </div>
</body>
</html>
```
