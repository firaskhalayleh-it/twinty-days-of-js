# day four :
## Advanced Scope:

In JavaScript, `const` and `let` are both used for variable declarations but have some differences in their behavior.

### `const`:

- Variables declared with `const` are constants, meaning their value cannot be reassigned once it is initialized.
- It is block-scoped, meaning it only exists within the block where it is defined (block scope refers to code within curly braces `{}`).
- When you declare a `const` variable and assign an object or array to it, you can't reassign the variable itself to a new object or array, but you can modify the properties or elements of the object or array.

**Example:**

```javascript
const pi = 3.14159;
pi = 3.14; // Error: You can't reassign a constant variable

const myArray = [1, 2, 3];
myArray[0] = 10; // Valid: You can modify the elements of the array

const myObject = { name: 'John', age: 30 };
myObject.age = 31; // Valid: You can modify the properties of the object
```

### `let`:

- Variables declared with `let` are mutable and can be reassigned.
- It is also block-scoped, like `const`.

**Example:**

```javascript
let count = 5;
count = 10; // Valid: You can reassign a variable declared with let
```

## Hoisting:

Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. However, it's important to note that only the declarations are hoisted, not the initializations or assignments. This can sometimes lead to unexpected behavior if not properly understood.

### Variable Hoisting:

In JavaScript, when a variable is declared using the `var` keyword, its declaration is hoisted to the top of the current function or global scope. However, the assignment (initialization) of the variable remains in its original position. If you try to access the variable before its declaration, it will exist but have the value `undefined`.

**Example:**

```javascript
console.log(name); // Output: undefined
var name = 'John';
console.log(name); // Output: John
```

### Function Hoisting:

Similarly, function declarations are also hoisted to the top of their scope. This means you can call a function before its actual declaration in the code.

**Example:**

```javascript
greet(); // Output: Hello there!
function greet() {
  console.log('Hello there!');
}
```

### Hoisting of `let` and `const`:

One crucial difference between `var`, `let`, and `const` in terms of hoisting is that while `var` is hoisted with the initial value `undefined`, `let` and `const` are also hoisted but not initialized.

**Example:**

```javascript
console.log(x); // Output: ReferenceError: Cannot access 'x' before initialization
let x = 10;
```

### Function Expressions and Arrow Functions:

Function expressions and arrow functions behave differently concerning hoisting. Unlike function declarations, they are not hoisted, and you cannot call them before their actual declaration.

**Example:**

```javascript
greet(); // Output: TypeError: greet is not a function
var greet = function() {
  console.log('Hello there!');
};
```

### Best Practices:

To avoid confusion and potential bugs due to hoisting, it's recommended to follow these best practices:

- Always declare variables at the top of their scope.
- Avoid using `var` whenever possible; use `let` and `const` for block-scoping instead.
- Declare functions before calling them, especially when using function expressions or arrow functions.

Understanding hoisting is essential for writing clean, predictable, and maintainable JavaScript code. By being aware of how hoisting works, you can avoid potential issues and write more robust programs.

## Closures:

In programming, a closure is a concept that refers to the ability of a function to "remember" and maintain access to its lexical scope, even when the function is executed outside of that scope. In simpler terms, a closure allows a function to capture and preserve the variables and their values in the scope where the function was created. These captured variables become part of the function's "closure," and they remain accessible even after the outer function has finished executing.

### How Closures Work:

When a function is defined within another function, the inner function retains access to the outer function's variables and parameters, creating a closure. This behavior is a result of JavaScript's scoping rules, which allow inner functions to access variables in their containing outer function.

**Example:**

```javascript
function outerFunction() {
  const outerVariable = 'I am from the outer function';
  
  function innerFunction() {
    console.log(outerVariable); // The inner function has access to outerVariable
  }

  return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // Output: I am from the outer function
```

In the example above, the `innerFunction` is defined within the `outerFunction`. When `outerFunction` is called, it returns `innerFunction`, creating a closure. As a result, `innerFunction` still has access to the `outerVariable`, even though `outerFunction` has already finished executing.

### Practical Uses of Closures:

Closures are powerful and have various practical applications in JavaScript. Some common use cases include:

1. **Encapsulation:** Closures allow you to create private variables and functions within an outer function. This concept is often used in the module pattern to create encapsulated components.

2. **Partial Functions:** Closures can be used to create partial functions, where you pre-fill some arguments of a function and return a new function that takes the remaining arguments.

3. **Callbacks and Event Handling:** Closures are widely used in asynchronous programming, where they help maintain the context and state of the surrounding code.

## Module Patterns and ES6 Modules:

In JavaScript, module patterns are used to encapsulate and organize code into reusable, self-contained units. They help avoid global namespace pollution, promote code reusability, and improve maintainability.

### CommonJS (Node.js) Module Pattern:

In Node.js, the CommonJS module pattern is used to organize code into modules. Each module is encapsulated, and its functionality is exposed through the `module.exports` object. Other modules can then require this module using the `require()` function.

**Example:**

**greet.js** (module file):
```javascript
function sayHello(name) {
  return `Hello, ${name}!`;
}

module.exports = {
  sayHello,
};
```

**app.js** (main application file):
```javascript
const greetings = require('./greet');
console.log(greetings.sayHello('John')); // Output: Hello, John!
```

### ES6 Modules (ESM):

ES6 introduced native support for modules in JavaScript. Instead of using the CommonJS pattern, ES6 modules use the `import` and `export` statements for exporting and importing functionality.

**Example:**

**greet.js** (module file):
```javascript
export function sayHello(name) {
  return `Hello, ${name}!`;
}
```

**app.js** (main application file):
```javascript
import { sayHello } from './greet';
console.log(sayHello('John')); // Output: Hello, John!
```

### Differences between CommonJS and ES6 Modules:

1. **Syntax:** CommonJS uses `require()` and `module.exports` for imports and exports, respectively, while ES6 modules use `import` and `export`.

2. **Dynamic vs. Static:** CommonJS modules are evaluated and loaded at runtime, which makes it more flexible for dynamic loading. On the other hand, ES6 modules are statically analyzed during parsing, enabling better optimization by JavaScript engines.

3. **Browser Support:** CommonJS modules are primarily used in server-side environments like Node.js, while ES6 modules are designed for both server-side and client-side (browsers) applications.

4. **Top-level Scope:** In CommonJS, each module has its own scope, and all code within a module is executed immediately. In ES6 modules, the top-level scope is not executed immediately, and you can choose which variables and functions to export.

In modern JavaScript development, ES6 modules are becoming the standard, as they offer better performance, static analysis, and a more natural syntax compared to the CommonJS pattern used in Node.js.

# homeworks : 
## homework one :
``` javascript
for (var i = 0; i < 5; i++) {
  (function (index) {
    setTimeout(function() {
      console.log("value of [i] is: ", index);
    }, 100);
  })(i);
}
```
## homework two : 
``` javascript
let array = [];
for (let i = 0; i < 5; i++) {
   
   array.push(i);
   console.log("Current array is: ", array)
}
```
## homework three : 
``` javascript
let functions = [];

for (var i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
functions.forEach((func) => func());
}
```
## homework four : 
``` javascript
const privateCounter = (() => {
  let count = 0;

  const increment = () => {
    count++;
  };

  const getCount = () => {
    return count;
  };

  return {
    increment,
    getCount
  };
})();

// Example usage:
privateCounter.increment();
privateCounter.increment();
console.log(privateCounter.getCount()); // Output: 2
```
## homework five : 
``` javascript
const generateFibonacci = (count) => {

  const fibonacci = (currentCount) => {
    if (currentCount === 0) {
      return 0;
    } else if (currentCount === 1) {
      return 1;
    } else {
      return fibonacci(currentCount - 1) + fibonacci(currentCount - 2);
    }
  };

  return fibonacci;
};


const fib = generateFibonacci(10);
for (let i = 0; i < 10; i++) {
  console.log(fib(i));
}
```

