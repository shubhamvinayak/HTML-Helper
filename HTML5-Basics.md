
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

