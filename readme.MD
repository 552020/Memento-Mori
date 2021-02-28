# content

Variation on a code example of Flangan. (Flanagan, JavaScript: The Definitive Guide, Seventh Edition, 2020: 412)

# status

not really happy with the color palette and typography, but also not so much time to spend on it.

check it online [here](https://552020.github.io/Memento-Mori/)

# languages

HTML, CSS, JavaScript

## new stuff (for me)

All the JavaScript code to let the clock run was for me really new and I basically copypasted them.

### new date()

let now = new Date();

The [Date()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date) constructor with the [new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) operator. I cite "Note: The only correct way to instantiate a new Date object is by using the new operator. If you call the Date object directly, such as now = Date(), the returned value is a string rather than a Date object."

### .toLocaleTimeString()

The [.toLocaleTimeString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleTimeString). The method is called on the variable "now", that store the actual date.

.toLocaleTimeString adapts the format of the date/time to the local (i.e. specified) standards.

// Depending on timezone, your results will vary
const event = new Date('August 19, 1975 23:15:30 GMT+00:00');

console.log(event.toLocaleTimeString('en-US'));
// expected output: 1:15:30 AM

console.log(event.toLocaleTimeString('it-IT'));
// expected output: 01:15:30

console.log(event.toLocaleTimeString('ar-EG'));
// expected output: ١٢

### setInterval()

The [.setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) is also atm for me pretty advanced stuff, even if it's fully the function of the method is really clear. It lets update the date every second letting "something"(the Window and the Worker) to call the function displayTime() again and again.

# starting point

The original code of the snippet in Flanagan.

<!DOCTYPE html> <!-- This is an HTML5 file -->
<html> <!-- The root element -->
<head> <!-- Title, scripts & styles can go here -->
<title>Digital Clock</title>
<style> /* A CSS stylesheet for the clock */
#clock { /* Styles apply to element with id="clock" */
font: bold 24px sans-serif; /* Use a big bold font */
background: #ddf; /* on a light bluish-gray background. */
padding: 15px; /* Surround it with some space */
border: solid black 2px; /* and a solid black border */
border-radius: 10px; /* with rounded corners. */
}
</style>
</head>
<body> <!-- The body holds the content of the document. -->
<h1>Digital Clock</h1> <!-- Display a title. -->
<span id="clock"></span> <!-- We will insert the time into this element. -->
<script>
// Define a function to display the current time
function displayTime() {
let clock = document.querySelector("#clock"); // Get element with id="clock"
let now = new Date(); // Get current time
clock.textContent = now.toLocaleTimeString(); // Display time in the clock
}
displayTime() // Display the time right away
setInterval(displayTime, 1000); // And then update it every second.
</script>
</body>
</html>
