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
* Answer: The sum is still 9 (NOT 54). Even though variable b is string data type, JS is aware of the operator + and it assumes the user is trying to add two numbers.
```
var a = 5;
var b = "4";
var sum = a + b;

console.log(sum); // 9
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
