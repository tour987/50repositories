```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <style> .penal{
    height: 80vh;
    width: 15vw;
    border-radius: 50px;
    background-position: center;
    cursor: pointer;
    flex: 0.5;

    position: relative;
    transition: 100ms;
    margin:10px;
}

.container{
    display: flex;
    width: 90vw;
    margin-left: 4vw;
    margin-top: 4vw;
}

.div1{
     background-image: url('https://images.unsplash.com/photo-1558979158-65a1eaa08691?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80');
     background-size: cover;
}
.div2{
    background-image: url('https://images.unsplash.com/photo-1572276596237-5db2c3e16c5d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80');
        background-size: cover;
  
}
.div3{
    background-image: url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1353&q=80');
    background-size: cover;
}
.div4{
    background-image: url('https://images.unsplash.com/photo-1551009175-8a68da93d5f9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1351&q=80');
    background-size: cover;
}

.div5{
    background-image: url('https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80');
    background-size: cover;
}



.penal h3{
    position: absolute;
    color:  blue;
    padding-left:  50px;
    opacity: 0;
    padding-top: 500px;
    font-size: 42px;
}


.penal.active {
    flex: 5;
}

.penal.active h3{
    opacity: 1;
}
  
</style>
    <title>expanding cards</title>
</head>
<body>
    <div class = "container">
        <div class = "active div1 penal"><h3> Explore The World</h3></div>
        <div class = " div2 penal"><h3>Eild Forest</h3></div>
        <div class = " div3 penal"><h3>Sunny Beach</h3></div>
        <div class = " div4 penal"><h3>City On Winter</h3></div>
        <div class = " div5 penal"><h3>Handsome Guy</h3></div>

    </div>

    <script type = "module">
       const penals = document.querySelectorAll('.penal');

penals.forEach(penal =>{
    penal.addEventListener('click',() =>{
        removeActiveClass();
        penal.classList.add('active');
    })
})

function removeActiveClass(){
    penals.forEach(penal => {
        penal.classList.remove('active');
    });
}

export {
    removeActiveClass
}
    </script>
</body>
</html>
```
