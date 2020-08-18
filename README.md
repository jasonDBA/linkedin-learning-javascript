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
