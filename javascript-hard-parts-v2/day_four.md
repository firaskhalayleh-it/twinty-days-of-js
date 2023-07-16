
# day_four
## Accessing Methods on Prototype Objects

This section covers the process of accessing methods on prototype objects. When a method is not found on the current object, JavaScript searches for it in the linked prototype object. This enables objects to access and utilize shared methods stored in the prototype chain.

```javascript
// Constructor function for creating User objects
function User(name, score) {
  this.name = name;
  this.score = score;
}

// Adding methods to the prototype of User objects
User.prototype.increment = function () {
  this.score++;
};

User.prototype.login = function () {
  console.log(`${this.name} logged in`);
};

// Creating instances of User objects
const user1 = new User("Will", 3);
const user2 = new User("Tim", 5);

// Accessing methods on User objects
user1.increment();
user2.login(); "Tim logged in"
```

## Pros and Cons of Implicit Parameters and Prototypal Inheritance

they are discusses the advantages and drawbacks of using implicit parameters and prototypal inheritance in JavaScript. While implicit parameters simplify method invocation and provide code reusability, they can also lead to potential side effects. Understanding and managing these aspects is crucial for building efficient and maintainable code.

## Distinguishing `__proto__` from `prototype`

This part clarifies the distinction between the `__proto__` property and the `prototype` property in JavaScript. While `__proto__` is a hidden property on objects used to create the prototype chain, `prototype` is a property specifically associated with constructor functions used for prototypal inheritance.

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound`);
};

function Dog(name, breed) {
  Animal.call(this, name);
  this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

const dog1 = new Dog("Buddy", "Labrador");

dog1.speak(); // Output: "Buddy makes a sound"
```

## The Role of `this` in Different Execution Contexts

The trainer explores how the `this` keyword behaves in various execution contexts. It explains how the value of `this` is determined based on the object to the left of the dot when invoking a method, as well as how it may behave differently in functions called without an object context.

```javascript
const person = {
  name: "John",
  sayHello: function () {
    console.log(`Hello, my name is ${this.name}`);
  },
};

person.sayHello(); // Output: "Hello, my name is John"

const helloFunc = person.sayHello;
helloFunc(); // Output: "Hello, my name is undefined" (if not in strict mode)
```

## Hidden Properties and Their Visibility

Finally, this section touches on the concept of hidden properties and their visibility. While some hidden properties, like `__proto__`, can be accessed and used in certain ways, others may remain entirely hidden from view. Understanding these hidden properties is essential for effective debugging and code analysis.

---
Sure! Here's a summary of the text with explanations and code examples for each subject:

###  Prototypal nature

Prototypal inheritance is a fundamental concept in JavaScript that allows objects to inherit properties and methods from other objects. Each object in JavaScript has a hidden link to another object called its prototype. If a property or method is not found on the current object, JavaScript looks for it in the prototype chain until it reaches the top-level object, which is typically the global object.

**Example:**

```js
// Creating an object literal
const person "Jo30,
  greet() {
    console.log(`Hello, my name is ${this.name}, and I'm ${this.age} years old.`);
  }
};

// Creating a new object using the person object as its prototype
const employee = Object.create(person);
employee.salary = 50000;

// Accessing properties and methods from the prototype
console.log(employee.name); // "John"
employee.greet(); // "Hello, my name is John, and I'm 30 years old."
```

### Manual Object Creation using Object.create()

The `Object.create()` method allows you to create a new object and set its prototype to another object. It is a way of manually establishing the prototypal link between objects.

**Example:**

```js
const userFunctionStore = {
  increment() {
    this.score++;
  }
};

const user1 = Object.create(userFunctionStore);
user1.name = "Alice";
user1.score = 10;

const user2 = Object.create(userFunctionStore);
user2.name = "Bob";
user2.score = 20;

user1.increment();
console.log(user1.score); // 11

user2.increment();
console.log(user2.score); // 21
```

### Using the New Keyword for Automated Object Creation

The `new` keyword automates the object creation process, making it more convenient to create objects with their prototypes linked. When a function is invoked with the `new` keyword, it automatically creates a new object, sets the function's prototype as the prototype of the new object, and returns the new object.

**Example:**

```js
function UserCreator(name, score) {
  const newUser = Object.create(UserCreator.prototype);
  newUser.name = name;
  newUser.score = score;
  return newUser;
}

UserCreator.prototype.increment = function() {
  this.score++;
};

const user1 = new UserCreator("Alice", 10);
const user2 = new UserCreator("Bob", 20);

user1.increment();
console.log(user1.score); // 11

user2.increment();
console.log(user2.score); // 21
```

### Using Arrow Functions for Lexical `this`

Arrow functions in JavaScript have lexical scoping for `this`, meaning that `this` inside an arrow function refers to the value of `this` in the surrounding code block. Arrow functions are useful when you want to define functions inside methods of objects without losing the reference to the object.

**Example:**

```js
function UserCreator(name, score) {
  this.name = name;
  this.score = score;
}

UserCreator.prototype.increment = function() {
  const add1 = () => {
    this.score++;
  };
  add1();
};

const user1 = new UserCreator("Alice", 10);
const user2 = new UserCreator("Bob", 20);

user1.increment();
console.log(user1.score); // 11

user2.increment();
console.log(user2.score); // 21
```

In this example, the `add1` function inside the `increment` method is an arrow function. It retains the reference to `this` from the `increment` method, which allows us to access and modify the object's properties correctly.

