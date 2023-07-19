# day two :

## Inferencing

Type inferencing is the ability of TypeScript and Flow to automatically deduce the types of variables, function return values, and expressions based on the values assigned or used in the code. It allows developers to write code without explicitly annotating the types, while the static type checkers analyze the code and automatically assign appropriate types to variables and expressions.

```typescript
const name = "John"; // Type inference: string
const age = 30; // Type inference: number
const isValid = true; // Type inference: boolean
const total = age + 5; // Type inference: number
const greeting = `Hello, ${name}!`; // Type inference: string
```

## Custom Types

Custom types allow developers to define their own data structures that represent specific shapes of data in the application. By creating custom types, developers can provide meaningful names to complex data structures, improving code readability and maintainability. Custom types can include properties with specified data types, enabling TypeScript and Flow to enforce type checking for those properties.

```typescript
type Person = {
  name: string;
  age: number;
  email?: string; // Optional property with type string
};

const john: Person = {
  name: "John Doe",
  age: 30,
  email: "john@example.com",
};

function greet(person: Person): string {
  return `Hello, ${person.name}! You are ${person.age} years old.`;
}

const greeting = greet(john);
console.log(greeting); // Output: "Hello, John Doe! You are 30 years old."
```

## Validating Operand Types

TypeScript and Flow can detect invalid operations that involve incompatible operand types. For example, if you try to perform operations like addition, subtraction, or comparison between values of different data types, the static type checkers will raise type errors during compilation.

```typescript
function add(a: number, b: number): number {
  return a + b;
}

const result1 = add(5, 10); // Valid operation: 5 + 10 = 15

// Uncommenting the line below will raise a type error
// const result2 = add(5, "10"); // Error: Invalid operation, trying to add a number and a string
```

## Static Typing Pros

Static typing has several advantages, including making code more self-documenting by explicitly declaring data types, catching type-related errors during development, and enhancing tooling support, such as IDE auto-completions and type hints. Static typing improves code reliability, helps developers catch potential issues early, and makes the codebase easier to understand, especially for teams working collaboratively.

```typescript
function calculateArea(width: number, height: number): number {
  return width * height;
}

const rectangleWidth: number = 10;
const rectangleHeight: number = 5;

const area: number = calculateArea(rectangleWidth, rectangleHeight);
console.log(`The area of the rectangle is: ${area}`); // Output: "The area of the rectangle is: 50"
```

## Static Typing Cons

While static typing offers several benefits, it also has some drawbacks. It requires an additional build process to transpile TypeScript/Flow code to regular JavaScript, adding a step to the development workflow. Additionally, the syntax for advanced type features can be more complex, potentially increasing the learning curve for some developers. Furthermore, strict static typing may not always align with the dynamic nature of JavaScript, leading to situations where developers need to add type annotations or deal with type-related challenges.

```typescript
// Uncommenting the line below will raise a syntax error in TypeScript
// const favoriteColor?: string = "blue"; // Error: '?' cannot be used with 'const' declaration

// Another example of syntax complexity in TypeScript
function concatStrings(str1: string, str2: string): string {
  return str1 + str2;
}
```

## Understanding Your Types

Understanding the types used in your code is essential for writing quality JavaScript applications, whether you choose to use static typing or not. By having a clear understanding of the data types in your code, you can structure your codebase more effectively, leading to improved code organization and maintainability. Thinking about types also promotes better code design, making your code more robust, and reducing the chances of type-related bugs.

```typescript
function calculateArea(width: number, height: number): number {
  return width * height;
}

const rectangleWidth: number = 10;
const rectangleHeight: number = 5;

const area: number = calculateArea(rectangleWidth, rectangleHeight);
console.log(`The area of the rectangle is: ${area}`); // Output: "The area of the rectangle is: 50"
```

---

## Understanding Lexical Scope in JavaScript

Lexical scope is the mechanism by which JavaScript deals with scope and is one of the three core pillars of JavaScript. Scopes act as containers for variables, and the way JavaScript handles scope is critical to writing efficient and effective code.

## How JavaScript Processes Code

JavaScript is a compiled language, which means there are several stages of processing that occur before the code is executed. These stages include lexing and tokenization, parsing, abstract syntax tree creation, and code generation.

## Marble Sorting and Scopes

In this metaphor, colored marbles represent identifiers in the program, and buckets represent scopes. Different types of scopes in JavaScript, such as global scope, function scope, and block scope, relate to the colored buckets in the metaphor.

## Closures in JavaScript

Closures are functions that retain access to their surrounding lexical environment even when executed outside of that environment. They allow developers to create private variables and functions in JavaScript.

```javascript
function outerFunction() {
  let outerVariable = 'I am from the outer function';
  
  function innerFunction() {
    console.log(outerVariable); // Inner function has access to outerVariable due to closure
  }
  
  return innerFunction;
}

const innerFunc = outerFunction();
innerFunc(); // Output: "I am from the outer function"
```

## The Module Pattern in JavaScript

The module pattern is based on closures and allows developers to create reusable and modular code. It enables the creation of private variables and functions that are not accessible from outside the module.

```javascript
const myModule = (function() {
  let privateVariable = 'I am private';

  function privateFunction() {
    console.log(privateVariable);
  }

  return {
    publicFunction: function() {
      privateFunction();
    }
  };
})();

myModule.publicFunction(); // Output: "I am private"
```

## Block Scoping in JavaScript

Block scoping, introduced in ES6, allows developers to create variables that are only accessible within a specific block of code, such as a loop or an if statement.

```javascript
function printNumbers() {
  for (let i = 0; i < 5; i++) {
    console.log(i); // Each 'i' is scoped to the block of the loop
  }
}

printNumbers(); // Output: 0, 1, 2, 3, 4
```

## The Scope Chain in JavaScript

The scope chain is created when JavaScript code is executed and allows functions to access variables from their surrounding lexical environment.

```javascript
const outerFunction = () => {
  const outerVariable = 'I am from the outer function';

  const innerFunction = () => {
    console.log(outerVariable); // Inner function has access to outerVariable via the scope chain
  };

  innerFunction();
};

outerFunction(); // Output: "I am from the outer function"
```

## Dynamic Scope vs Lexical Scope in JavaScript

Dynamic scope allows functions to access variables from their calling context, while lexical scope allows functions to access variables from their surrounding lexical environment.

Dynamic Scope Example:
```javascript
function outerFunction() {
  console.log(myVariable); // Looks for 'myVariable' in the calling context, not lexical scope
}

function innerFunction() {
  const myVariable = 'I am from inner function';
  outerFunction();
}

innerFunction(); // Output: Error - myVariable is not defined
```

## Common Scoping Patterns in JavaScript

Revealing Module Pattern Example:
```javascript
const myModule = (function() {
  let privateVariable = 'I am private';

  function privateFunction() {
    console.log(privateVariable);
  }

  return {
    publicFunction: privateFunction
  };
})();

myModule.publicFunction(); // Output: "I am private"
```

## Best Practices for Working with Scopes in JavaScript

Avoid global variables, use block scoping to avoid bugs, create modules to encapsulate functionality, understand the scope chain, and use closures to create private variables and functions. Apply these concepts in your JavaScript code to improve its readability, maintainability, and efficiency.
---
# homework 
## number one :
``` typescript
interface HelloWorldResponse {
  message: string;
}

interface CheckBooleanResponse {
  result: boolean;
}

interface ReturnObjResponse {
  x: string;
  y: number;
}

type PromiseResponse = HelloWorldResponse | CheckBooleanResponse | ReturnObjResponse;

const sayHelloWorld = new Promise<HelloWorldResponse>((resolve, reject) => {
  resolve({ message: "Hello world!" });
});

const checkBoolean = (boolean: boolean) => new Promise<CheckBooleanResponse>((resolve, reject) => {
  if (boolean) {
    resolve({ result: boolean });
  } else {
    reject(`Input is false :(`)
  }
});

const returnObj = new Promise<ReturnObjResponse>((resolve, reject) => {
  resolve({
    x: "meow",
    y: 45,
  });
});

const promisesArray: Promise<PromiseResponse>[] = [sayHelloWorld, checkBoolean(true), returnObj];

const convertToObj = async (array: Promise<PromiseResponse>[]): Promise<{ [key: string]: PromiseResponse }> => {
  const obj: { [key: string]: PromiseResponse } = {};
  
  for (let i = 0; i < array.length; i++) {
    try {
      const result = await array[i];
      obj[`promise${i + 1}`] = result;
    } catch (error) {
      obj[`promise${i + 1}`] = { error: error.message };
    }
  }
  
  return obj;
}

convertToObj(promisesArray).then((result) => {
  console.log(result);
});

```

---
## number two :
Sure, here are the answers without code examples:

**Answer to Question #1:**

Choice: D) 1, ReferenceError

Explanation: `var a` is hoisted and accessible throughout the function. `let b` and `const c` have block scope, so they are only accessible within the if block. Trying to access `b` and `c` outside the block will result in a ReferenceError.

**Answer to Question #2:**

Choice: A) undefined, ReferenceError

Explanation: Variables `a`, `b`, and `c` are declared inside the if block, so they are not hoisted and cannot be accessed before their declarations, resulting in ReferenceError.

**Answer to Question #3:**

Choice: C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1, 100, 45 ]

Explanation: Variables `a`, `b`, and `c` are declared inside and outside the if block. Inside the block, new variables are created, which have a separate scope from the outer ones. After the if block, the outer variables retain their original values, while the inner variables are discarded.
