# What I've learned in the course?

Reference: https://www.linkedin.com/learning/javascript-essential-training-3?trk=learning-topics_learning_search-card&upsellOrderOrigin=default_guest_learning

## How JS loads?
NOTE: The below, both are only for external JS script
* __Asynchronous__: it specifies that the script will be executed **asynchronously** as soon as it is available.
* __Deferred__ : it makes the browser **wait(parse)** until the document is loaded before running the JavaScript
```
<script src="" async></script>
<script src="" defer></script>
```

## Variable Scope in Js
* __Global Scope__:
* __Local Scope__:

## 6 Primitive Data Types
* Numeric
* String
* Boolean
* Null
* Undefined
* Symbol

## Given var a = 5, var b = "4". What is the result of (a + b)?
* Answer: The sum is 54 (NOT 9). Since the variable b is string data type, JS uses __string operator__ to add two values.
```
var a = 5;
var b = "4";
var sum = a + b;

console.log(sum); // 54
```

## What is difference between == and ===?
* ==: it __ignores__ the comparison of two data types.
* ===: it compares not only values but also data types. Absolute String Equality.
```
//Example
var a = 5;
var b = "5";
var compareTwo;

if(a == b) {
  compareTwo = true;
} else {
  compareTwo = false;
}

console.log(compareTwo) // returns true

// if we change if(a==b) to if(a===b), then it returns false since a and b are different data types (a is integer, b is string).
```
## Anonymous Function
* A function that does not have a name. It is stored in variables.
```
// Example
var a = 5, b = 7;

var findBiggerNum = function() {
  var result;
  a>b ? result = ["a", a] : result = ["b", b];
  console.log(result);
}

findBiggerNum();  // returns ["b", 7]
```

## What if not using var prefix?
* Answer: the variable will be a global scope even if it is defined inside of the block like a loop

## Difference between var, let, and const?
* var: The variable can be re-defined. Also, it can re-assign the value.
* const: The variable can __NOT__ be re-defined. Also, it can __NOT__ re-assign the value.
* let: It is the __block scope__ keyword. It can be applied in the __smaller scope__ than var.
```
function example() {
  var number = 5;
  
  if(number) {
    var number = 10;
    console.log("number: ", number);  // returns number: 10
  }
  
  console.log("number: ", number);  // returns number: 10
}

// If changing var number = 10 to let number = 10, then the first console returns 10 and the second returns 5 (NOT 10).
```

## Create an object having 'view' property, and increase the view by 1.
* Answer:
```
var obj = {
  view: 0,
  updateView: function() {
    return ++obj.view;
  }
}
console.log("view: ", obj.view);  // returns view: 0
obj.updateView();
console.log("view: ", obj.view);  // returns view: 1
}
```

## What is this keyword?
* It refers to the object it belongs to.

## Create an object constructor, which is Course(title, instructor, view)
* Answer:
```
function Course(title, instructor, view){
  this.title = title;
  this.instructor = instructor;
  this.view = view;
  this.updateView = function() {
    return ++this.view;
  }
}

var course01 = new Course("JavaScript Fundamental", "Jason Choi", 0);

console.log(course01);  // returns the object, Course{title: "JavaScript Fundamental", instructor: "Jason Choi", view: 0}
console.log(course01.updateView()); // returns 1
}
```

## Name two object property notations
* DOT notation
* Bracket notation
* If the object property involves special characters, recommend using __Bracket__ notation else recommend using __DOT__ notation as it is easier to read.

## What is Function Closure?
* A function having access to the parent scope, __even after the parent function has closed__.
```
// Example
function giveMeEms(px) {
  var baseValue = 16;
  
  function doMath() {
    return px / baseValue;
  }
  
  return doMath;
}

var smallSize = giveMeEms(12);
var largeSize = giveMeEms(24);

console.log("Small size: ", smallSize)  // returns Small size: 0.75
console.log("Large size: ", largeSize)  // returns Large size: 1.5
```

## DOM and BOM
* DOM: It defines a standard for accessing documents. The model looks a tree-structure of the nodes.
* BOM: It allows JavaScript to "talk to" the browser.

## DOM Methods
* .querySelector(): returns the first element that matches a specified CSS selector(s) in the document.
* .querySelectorAll(): returns all elements in the document that matches a specified CSS selector(s).

## How to create new DOM elements?
1. Create the element - Use .createElement()
2. Create the text node that goes inside the element  - Use .createTextNode()
3. Add the text node to the element - Use .appendChild()
4. Add the element to the DOM tree
```
/******** Example ********/
/******** HTML Before applying JS ********/
<figure class="featured-image">
  <img src="images/testimonials/bluepebble.jpg" alt="Earthrise: A photograph of the Earth and parts of the Moon's surface taken by astronaut William Anders in 1968, during the Apollo 8 mission.">
</figure>
```
```
/******** JS ********/
const FEAGURE = document.querySelector(".featured-image");
const THEIMAGE = FEAGURE.querySelector("img");
var altText = THEIMAGE.getAttribute("alt");

// Create the element - Use .createElement()
var captionElement = document.createElement("figcaption");

// Create the text node that goes inside the element - Use .createTextNode()
var captionText = document.createTextNode(altText);

// Add the text node to the element - Use .appendChild()
captionElement.appendChild(captionText);
// console.log(captionElement);

// Add the element to the DOM tree
FEAGURE.appendChild(captionElement);

THEIMAGE.setAttribute("alt", "");
```
```
/******** HTML After applying JS ********/
<figure class="featured-image">
  <img src="images/testimonials/bluepebble.jpg" alt>
  <figcaption>
    Earthrise: A photograph of the Earth and parts of the Moon's surface taken by astronaut William Anders in 1968, during the Apollo 8 mission.
  </figcaption>
</figure>
```

## What is the difference between querySelector() and getElementsByClassName()?
* You can use querySelector() when you look for **elements with a combination of properties**
* You can use getElementsByClassName() if you expect **faster performance**.
* For example, it is possbile like querySelector('input[name="login"]'); but getElementsByClassName() cannot.

## What are objects in JavaScript?
* __A reference data type__.
* Defined as an unordered collection of related data, of primitive or reference types, in the form of __“key: value” pairs__.
* Example:
```
let school = {
    name : "Vivekananda School",
    location : "Delhi",
    established : "1971"
}
```
