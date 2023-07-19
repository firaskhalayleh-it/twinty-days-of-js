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
