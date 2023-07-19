# day one :

## Introduction 
In this introduction, *Kyle Simpson* expresses his gratitude to **Mark**, who helped him start his journey in teaching JavaScript. He discusses his transition from being a conference speaker to becoming a full-time teacher. Kyle has a strong online presence under the name **GETIFY** and has authored several books, including the *"You Don't Know JS"* series.

The course will delve deeply into JavaScript, contrary to the prevailing trend of focusing on various frameworks and languages. Kyle emphasizes the importance of understanding JavaScript, even though many developers now use TypeScript or other languages. He highlights the need to abandon assumptions about the language and suggests consulting the JavaScript specification as the source of authority for understanding its behavior.

Kyle presents a simple example of using the `++` operator and how it behaves differently when applied to a non-number string. He encourages developers to question their mental models and learn from the JavaScript specification rather than blaming the language for surprises or bugs.

**Code Example:**

```javascript
let x = 5;
console.log(x++); // Output: 5
console.log(x);   // Output: 6

let y = "5";
console.log(y++); // Output: 5
console.log(y);   // Output: 6 (Note: y is coerced to a number before incrementing)
```

In summary, this introduction sets the tone for the course, emphasizing the significance of understanding JavaScript thoroughly and referring to the official [JavaScript specification](https://tc39.es/ecma262/) as a guide to uncover the language's behavior accurately. Understanding the behavior of JavaScript operators and expressions is crucial for writing bug-free code and avoiding assumptions about the language.
Sure! Here's the merged text covering the three major topics - "Types," "Scope," and "Objects (Oriented)" - from the course overview:




## Course Overview

In this course, Kyle Simpson presents three fundamental pillars of JavaScript that are crucial for all JavaScript developers, regardless of the frameworks they use. Understanding these pillars will help developers write more robust and bug-free code.

## Types:

1. **Primitive Types:** Explore the different primitive data types in JavaScript, such as numbers, strings, booleans, null, undefined, and symbols. Understand their characteristics and how they are stored in memory.

2. **Abstract Operations:** Learn about abstract operations, which define various algorithms for type conversion and comparison. These operations play a crucial role in JavaScript's behavior.

3. **Coercion:** Delve into type coercion, where JavaScript automatically converts data between different types. Understand how coercion affects expressions and comparisons and how to handle it correctly.

4. **Equality:** Examine the nuances of equality in JavaScript. Understand the difference between loose (==) and strict (===) equality and how they compare values of different types.

5. **TypeScript, Flow, etc.:** Get an overview of type systems in TypeScript, Flow, and other tools that add static typing to JavaScript. Understand their benefits and how they complement JavaScript's dynamic typing.

## Scope:

1. **Nested Scope:** Understand how JavaScript defines scopes within other scopes, allowing access to variables declared in outer functions from inner functions.

2. **Hoisting:** Learn about hoisting, where JavaScript moves variable and function declarations to the top of their respective scopes during the compilation phase.

3. **Closure:** Delve into closures, which are functions that "remember" their lexical environment even after the outer function has finished executing. Learn how closures enable powerful programming patterns.

4. **Modules:** Explore the modular pattern in JavaScript, where code is organized into separate modules to promote code reusability and maintainability. Understand how closures are used to create private variables and functions within modules.

## Objects (Oriented):

1. **class {}:** Learn about the `class` syntax, which is a newer addition to JavaScript and provides a more familiar syntax for object-oriented programming. Understand how classes are used to create constructor functions and define methods.

2. **Prototypes:** Explore JavaScript's prototype-based inheritance model, where objects inherit properties and methods from their prototypes. Understand how the prototype chain works and how it relates to inheritance.

3. **this Operator:** Understand the behavior of the `this` keyword, which refers to the context of the current execution. Learn how to use `this` correctly in various scenarios to access object properties and methods.

4. **OO vs. OLOO:** Compare Object-Oriented (OO) and Objects Linked to Other Objects (OLOO) approaches in JavaScript. Understand the benefits and limitations of each pattern and when to use them in your code.

These key points provide a concise overview of the major topics covered in the course, laying the groundwork for a more comprehensive understanding of JavaScript's core pillars.

**Primitive Types:**

JavaScript has six primitive types: 

1. **Number**: This includes all numeric values, both integers and floating-point numbers.

```javascript
let num = 42;
let pi = 3.14;
```

2. **String**: Represents a sequence of characters enclosed in single or double quotes.

```javascript
let name = "John";
let message = 'Hello, world!';
```

3. **Boolean**: Represents a true or false value.

```javascript
let isTrue = true;
let isFalse = false;
```

4. **Undefined**: A variable that has been declared but not assigned any value automatically gets the value `undefined`.

```javascript
let x;
console.log(x); // Output: undefined
```

5. **Null**: Represents an intentional absence of any value.

```javascript
let myVariable = null;
```

6. **Symbol**: A unique and immutable data type used to create anonymous unique identifiers.

```javascript
const sym = Symbol("description");
```

Primitive values are not objects and have a fixed size, making them more memory-efficient. However, they can be used as objects because JavaScript creates wrapper objects for primitives using the concept of fundamental objects.

**Typeof:**

The `typeof` operator in JavaScript is used to determine the type of a given value. However, it has some limitations.

```javascript
console.log(typeof 42); // Output: "number"
console.log(typeof "Hello"); // Output: "string"
console.log(typeof true); // Output: "boolean"
console.log(typeof undefined); // Output: "undefined"
console.log(typeof null); // Output: "object" (historical mistake)
console.log(typeof NaN); // Output: "number" (technically invalid number)
```

To work around the limitations of `typeof` when checking for `null` and `NaN`, you can use `Object.prototype.toString`.

```javascript
console.log(Object.prototype.toString.call(null)); // Output: "[object Null]"
console.log(Object.prototype.toString.call(NaN)); // Output: "[object Number]"
```

**BigInt:**

BigInt is a new feature introduced in ES2020 to represent integers of arbitrary precision.

```javascript
const largeNumber = BigInt(9007199254740991);
console.log(largeNumber); // Output: 9007199254740991n
```

BigInts are immutable, and regular numbers cannot be mixed with BigInts in mathematical operations.

```javascript
const bigIntValue = 100n;
const regularNumber = 42;

console.log(bigIntValue + regularNumber); // Error: Cannot mix BigInt and other types
```

**Kinds of Emptiness:**

In JavaScript, there are three types of emptiness: `undefined`, `undeclared`, and `uninitialized`.

```javascript
let declaredVar; // This variable is declared but not initialized, so it is undefined.
console.log(declaredVar); // Output: undefined

// console.log(undeclaredVar); // Error: undeclaredVar is not defined (not declared).

// Uninitialized variables do not exist in JavaScript.

function myFunction() {
  let localVar; // This variable is declared but not initialized, so it is undefined.
  console.log(localVar); // Output: undefined
}
```

To avoid creating global variables accidentally, you can use strict mode.

```javascript
"use strict";

undeclaredVar = 10; // Error: undeclaredVar is not defined
```

**NaN-isNaN:**

NaN stands for "Not a Number" and is a special value in JavaScript that represents an invalid or unrepresentable number.

```javascript
console.log(0 / 0); // Output: NaN
console.log(parseInt("Hello")); // Output: NaN
```

The `isNaN()` function can be used to check if a value is NaN.

```javascript
console.log(isNaN(NaN)); // Output: true
console.log(isNaN(42)); // Output: false
console.log(isNaN("Hello")); // Output: true
```

To check for a valid number, you can use `Number.isNaN()`.

```javascript
console.log(Number.isNaN(NaN)); // Output: true
console.log(Number.isNaN(42)); // Output: false
console.log(Number.isNaN("Hello")); // Output: false
```

**Negative Zero:**

JavaScript has both positive zero and negative zero, and they behave differently in certain scenarios.

```javascript
let positiveZero = 0;
let negativeZero = -0;
```

To check for the existence of negative zero, you can use `Object.is()`.

```javascript
console.log(Object.is(positiveZero, 0)); // Output: true
console.log(Object.is(negativeZero, 0)); // Output: false
console.log(positiveZero === negativeZero); // Output: true
```

Negative zero can be useful in specific situations, like distinguishing between different directions or temperature values.

```javascript
function getDirection(angle) {
  return angle === 0 ? "North" : angle === -0 ? "South" : "Unknown";
}

console.log(getDirection(0)); // Output: "North"
console.log(getDirection(-0)); // Output: "South"
```

Overall, understanding these concepts and their implications can help developers write more robust and reliable JavaScript code.

# homeworks :
## number one:
``` javascript
function convertStringToNumber(input) {
    if (typeof(input)==='string'){
        if (Number.isNaN(+input)){
            return `${typeof(input)} , ${input} : invalid number`
        }
        else{
            return +input
        }
       
    }
    else {
        return `${typeof(input)} , ${input}`
    }
  }
```

## number two: 
``` javascript
const checkNaN = (value) => {
  return Number.isNaN(value)
}
```
## number three :
``` javascript
function isEmptyValue(value) {
  if (
    typeof value === "undefined" ||
    typeof(value) === 'string' &&value.length === 0 ||
    typeof value === "object" && value === null
  ) {
    return true;
  } else {
    return false;
  }
}
```

## number four :
``` javascript
function compareObjects(input1, input2) {
        if (typeof(input1)==='object' && typeof(input2)==='object'){
            return Object.is(input1,input2)
        }
        else {
            return  [input1,input2]
}}


```
## number five : 
``` javascript
const complexCoercion = (input) => {
  if (typeof input !== "object" ) {
    if (typeof input === "number") {
      input.toString();
      return Boolean(input);
    } else if (typeof input === "string") {
      return Boolean(input);
    }
    else if ((typeof input === 'undefined')){
        return false;
    }
  }
  else if (input === null ){
      return false
  }
  else {
    return input;
  }
};
```
