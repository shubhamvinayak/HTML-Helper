
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
