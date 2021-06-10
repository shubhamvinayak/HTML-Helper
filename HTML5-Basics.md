
### Input types

* The color input type allows the user to select a color from a color picker and returns the color value in hexadecimal format (#rrggbb). If you don't specify a value, the default is #000000, which is black.`<input type="color" value="#00ff00" id="mycolor">`
* The date input type allows the user to select a date from a drop-down calendar.`<input type="date" value="2019-04-15" id="mydate">`
* The datetime-local input type allows the user to select both local date and time, including the year, month, and day as well as the time in hours and minutes.`<input type="datetime-local" id="mydatetime">`
* The email input type allows the user to enter e-mail address. It is very similar to a standard text input type, but if it is used in combination with the required attribute, the browser may look for the patterns to ensure a properly-formatted e-mail address should be entered.`<input type="email" id="myemail" required>`.
 You can style the email input field for different validation states, when an value is entered using the :valid, :invalid or :required pseudo-classes.
* The month input type allows the user to select a month and year from a drop-down calendar.`<input type="month" id="mymonth">`
* The number input type can be used for entering a numerical value. You can also restrict the user to enter only acceptable values using the additional attributes min, max, and step.`<input type="number" min="1" max="10" step="0.5" id="mynumber">`
* The range input type can be used for entering a numerical value within a specified range. It works very similar to number input, but it offers a simpler control for entering a number.`<input type="range" min="1" max="10" step="0.5" id="mynumber">`
* A search field typically behaves like a regular text field, but in some browsers like Chrome and Safari as soon as you start typing in the search box a small cross appears on the right side of the field that lets you quickly clear the search field. Let's try out an example to see how it works:`<input type="search" id="mysearch">`
* The tel input type can be used for entering a telephone number.Browsers don't support tel input validation natively. However, you can use the placeholder attribute to help users in entering the correct format for a phone number, or specify a regular expression to validate the user input using the pattern attribute. Let's check out an example:`<input type="tel" id="myphone" placeholder="xx-xxxx-xxxx" required>`
* The time input type can be used for entering a time (hours and minutes).Browser may use 12- or 24-hour format for inputting times, based on local system's time setting.`<input type="time" id="mytime">`
* The url input type can be used for entering URL's or web addresses.You can use the multiple attribute to enter more than one URL. Also, if required attribute is specified browser will automatically carry out validation to ensure that only text that matches the standard format for URLs is entered into the input box. Let's see how this works:`<input type="url" id="myurl" required>`
* The week input type allows the user to select a week and year from a drop-down calendar.Let's try out the following example to understand how this works:`<input type="week" id="myweek">`

---------------------------------------------------------------------------------------------------------------------------------------------------------------

### Canvas
* The HTML5 canvas element can be used to draw graphics on the webpage via JavaScript. By default the <canvas> element has 300px of width and 150px of height without any border and content. However, custom width and height can be defined using the CSS height and width property whereas the border can be applied using the CSS border property.
* Drawing Path and Shapes on Canvas
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Drawing on Canvas</title>
<script>
    window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        // draw stuff here
    };
</script>
</head>
<body>
    <canvas id="myCanvas" width="300" height="200"></canvas>
</body>
</html>
 ```
 
* Drawing a Line
```html
<script>
    window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.moveTo(50, 150);
        context.lineTo(250, 50);
        context.stroke();
    };
</script>
```
 
* Drawing a Arc: `context.arc(centerX, centerY, radius, startingAngle, endingAngle, counterclockwise);`
```html
<script>
    window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.arc(150, 150, 80, 1.2 * Math.PI, 1.8 * Math.PI, false);
        context.stroke();
    };
</script>
```
* Drawing a Rectangle
You can create rectangle and square shapes using the rect() method. This method requires four parameters x, y position of the rectangle and its width and height.
The basic syntax of the rect() method can be given with: `context.rect(x, y, width, height);`
```html
<script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.rect(50, 50, 200, 100); 
        context.stroke();
    };
</script>
 ```
* Drawing a Circle
There is no specific method for creating circle like rectangle's rect() method. However, you can create a fully enclosed arc such as circle using the arc() method.`context.arc(centerX, centerY, radius, 0, 2 * Math.PI, false);`
 ```html
<script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.arc(150, 100, 70, 0, 2 * Math.PI, false);
        context.stroke();
    };
</script>
```
* Applying Styles and Colors on Stroke
 The default color of the stroke is black and its thickness is one pixel. But, you can set the color and width of the stoke using the strokeStyle and lineWidth property respectivley.
```html
<script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.lineWidth = 5;
        context.strokeStyle = "orange";
        context.moveTo(50, 150);
        context.lineTo(250, 50);
        context.stroke();
    };
</script>
 ```
 * You can also set the cap style for the lines using the lineCap property. There are three styles available for the line caps — butt, round, and square. Here's an example:
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.lineWidth = 10;
        context.strokeStyle = "orange";
        context.lineCap = "round";
        context.arc(150, 150, 80, 1.2 * Math.PI, 1.8 * Math.PI, false);
        context.stroke();
    };
</script>
 ```
 * Filling Colors inside Canvas Shapes
 You can also fill color inside the canvas shapes using the fillStyle() method.The following example will show you how to fill a solid color inside a rectangle shape.
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.rect(50, 50, 200, 100); 
        context.fillStyle = "#FB8B89";
        context.fill();
        context.lineWidth = 5;
        context.strokeStyle = "black";
        context.stroke();
    };
</script>
 ```
 Similarly, you can use the fillStyle() method to fill solid color inside a circle too.
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.arc(150, 100, 70, 0, 2 * Math.PI, false);
        context.fillStyle = "#FB8B89";
        context.fill();
        context.lineWidth = 5;
        context.strokeStyle = "black";
        context.stroke();
    };
</script>
 ```
 * Filling Gradient Colors inside Canvas Shapes
 You can also fill gradient color inside the canvas shapes. A gradient is just a smooth visual transition from one color to another. There are two types of gradient available — linear and radial.The basic syntax for creating a linear gradient can be given with:
`var grd = context.createLinearGradient(startX, startY, endX, endY);`
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.rect(50, 50, 200, 100); 
        var grd = context.createLinearGradient(0, 0, canvas.width, canvas.height);
        grd.addColorStop(0, '#8ED6FF');   
        grd.addColorStop(1, '#004CB3');
        context.fillStyle = grd;
        context.fill();
        context.stroke();
    };
</script>
 ```
 Similarly, you can fill canvas shapes with radial gradient using the createRadialGradient() method. The basic syntax for creating a radial gradient can be given with:`var grd = context.createRadialGradient(startX, startY, startRadius, endX, endY, endRadius);`
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.arc(150, 100, 70, 0, 2 * Math.PI, false);
        var grd = context.createRadialGradient(150, 100, 10, 160, 110, 100);
        grd.addColorStop(0, '#8ED6FF');   
        grd.addColorStop(1, '#004CB3');
        context.fillStyle = grd;
        context.fill();
        context.stroke();
    };
</script>
 ```
* Drawing Text on Canvas
You can also draw text onto canvas. These texts can contain any Unicode characters. The following example will draw a simple greeting message "Hello World!" onto a canvas.
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.font = "bold 32px Arial";
        context.fillText("Hello World!", 50, 100);
    };
</script>
 ```
 You can additionally set the color and alignment of the text on the canvas, like this:

```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.font = "bold 32px Arial";
        context.textAlign = "center";
        context.textBaseline = "middle";
        context.fillStyle = "orange";
        context.fillText("Hello World!", 150, 100);
    };
</script>
 ```
 You can also apply stroke on text using the strokeText() method. This method will color the perimeter of the text instead of filling it. However if you want to set both the fill and stroke on canvas text you can use both the fillText() and the strokeText() methods together.
 ```html
 <script>
	window.onload = function() {
        var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");
        context.font = "bold 32px Arial";
        context.textAlign = "center";
        context.textBaseline = "middle";
        context.strokeStyle = "orange";
        context.strokeText("Hello World!", 150, 100);
    };
</script>
 ```
 ------------------------------------------------------------------------------------------------------------------------------------------------------

### SVG
The Scalable Vector Graphics (SVG) is an XML-based image format that is used to define two-dimensional vector based graphics for the web. Unlike raster image (e.g. .jpg, .gif, .png, etc.), a vector image can be scaled up or down to any extent without losing the image quality.
* Embedding SVG into HTML Pages
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Embedding SVG in HTML</title>
</head>
<body>
    <svg width="300" height="200">
        <text x="10" y="20" style="font-size:14px;">
            Your browser support SVG.
        </text>
        Sorry, your browser does not support SVG.
    </svg>
</body>
</html>
```
* Drawing a Line : The attributes x1, x2, y1 and y2 of the <line> element draw a line from (x1,y1) to (x2,y2).
```html
<svg width="300" height="200">
    <line x1="50" y1="50" x2="250" y2="150" style="stroke:red; stroke-width:3;" />
</svg>
```
* Drawing a Rectangle
The attributes x and y of <rect> element defines the co-ordinates of the top-left corner of the rectangle. The attributes width and height specifies the width and height of the shape.
```html
<svg width="300" height="200">
    <rect x="50" y="50" width="200" height="100" style="fill:orange; stroke:black; stroke-width:3;" />
</svg>
```
* Drawing a Circle: The attributes cx and cy of the <circle> element defines the co-ordinates of the center of the circle and the attribute r specifies the radius of the circle. However, if the attributes cx and cy are omitted or not specified, the center of the circle is set to (0,0)
```html
<svg width="300" height="200">
    <circle cx="150" cy="100" r="70" style="fill:lime; stroke:black; stroke-width:3;" />
</svg>
```
* Drawing Text with SVG
You can also draw text on the web pages with SVG. The text in SVG is rendered as a graphic so you can apply all the graphic transformation to it but it is still acts like text — that means it can be selected and copied as text by the user. Let's try an example to see how this works:The attributes x and y of the <text> element defines the location of the top-left corner in absolute terms whereas the attributes dx and dy specifies the relative location.
```html
<svg width="300" height="200">
    <text x="20" y="30" style="fill:purple; font-size:22px;">
        Welcome to Our Website!
    </text>
    <text x="20" y="30" dx="0" dy="20" style="fill:navy; font-size:14px;">
        Here you will find lots of useful information.
    </text>
</svg>
```
You can even use the <tspan> element to reformat or reposition the span of text contained within a <text> element. Text contained in separate tspans, but inside the same text element can all be selected at once — when you click and drag to select the text. However, the text in separate text elements cannot be selected at the same time. Let's check out an example:
```html
<svg width="300" height="200">
    <text x="30" y="15" style="fill:purple; font-size:22px; transform:rotate(30deg);">
        <tspan style="fill:purple; font-size:22px;">
            Welcome to Our Website!
        </tspan>
        <tspan dx="-230" dy="20" style="fill:navy; font-size:14px;">
            Here you will find lots of useful information.
        </tspan>
    </text>
</svg>
```

SVG: 1) Vector based (composed of shapes). 2)Multiple graphical elements, which become the part of the page's DOM tree. 3) Modified through script and CSS. 4) Good text rendering capabilities. 5)Give better performance with smaller number of objects or larger surface, or both. 6) Better scalability. Can be printed with high quality at any resolution. Pixelation does not occur

CAnvas: 1)Raster based (composed of pixel). 2)Single element similar to <img> in behavior. Canvas diagram can be saved to PNG or JPG format. 3) Modified through script only. 4) Poor text rendering capabilities. 5) Give better performance with larger number of objects or smaller surface, or both. 6) Poor scalability. Not suitable for printing on higher resolution. Pixelation may occur
	
-------------------------------------------------------------------------------------------------------------------------------------------------------
