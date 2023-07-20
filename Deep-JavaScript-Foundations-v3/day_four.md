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
