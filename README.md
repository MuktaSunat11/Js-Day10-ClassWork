# Day10-Class Assignment
This is a simple HTML, CSS, and JavaScript project that creates a circle that can change color and shape.

# HTML

The HTML code creates a container div with a circle div inside it. The circle div has a shape div inside it. The shape div is initially a circle, but can be changed to a triangle by clicking the "change shape" button.

```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change Shape and Color</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div class="container">
        <div id="circle">
            <div class="inner-part"></div>
        </div>
            <div id="change-color">
                <button>Change Color</button>
            </div>

            <div id="change-shape">
                <button>Change Shape</button>
            </div>
        </div>
        <script src="./script.js"></script>
</body>
</html>
```

# CSS

The CSS code styles the container div, the circle div, and the shape div. The CSS code styles the container div, the circle div, and the shape div. The shape div is positioned absolutely inside the circle div.

```
*{
    margin:0;
    padding:0;
}
.container{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    flex-wrap: wrap;
    height: 100vh;
}
#circle{
    height: 150px;
    width: 150px;
    box-sizing: border-box;
    border-radius: 50%;
    background-color: green;
}
.inner-part{
    background-color: white;
    position: relative;
    width: 75px;
    height: 75px;
    left: 38px;
    top: 40px;
}

#container div {
    padding: 3px;
    text-align: center;
    margin-top: 20px;
}
.triangle-bottom-left{
    background-color: transparent;
    position: relative;
    left: 38px;
    top: 40px;
    width: 0;
    height: 0;
    border-bottom: 75px solid red;
    border-right: 75px solid transparent;
}
```

# Javascript

The JavaScript code adds event listeners to the "change color" and "change shape" buttons.The "change color" button changes the background color of the circle div to a random color. The "change shape" button changes the shape of the shape div from a circle to a triangle.

```
var color = [
    "red",
    "black",
    "cyan",
    "voilet",
    "blue",
    "yellow",
    "purple",
    "orange",
    "lemon",
    "green"
  ];
  var index = 0;
  var isTriangle = false;
  
  var cShape = document.getElementById("change-shape");
  var cColor = document.getElementById("change-color");
  
  cShape.addEventListener("click", changeShape);
  cColor.addEventListener("click", changeColor);
  
  function changeColor() {
    if (index === color.length) {
      index = 0;
    }
    document.getElementById("circle").style.backgroundColor = color[index];
    index++;
  }
  
  function changeShape() {
    if (!isTriangle) {
      var i = document.getElementsByClassName("inner-part")[0];
      i.className = "triangle-bottom-left";
      isTriangle = true;
    }else{
      var i = document.getElementsByClassName("triangle-bottom-left")[0];
      i.className = "inner-part";
      isTriangle = false;
    }
  }
```
