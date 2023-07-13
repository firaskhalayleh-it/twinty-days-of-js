# Closure in JavaScript
- it enable us to not repeat calculations or tasks that take usually long time .

## introduction
- every time function runs it creates a new local memory.after finish running code (return the value/result) it delete the exception context of it.

Closure is a powerful concept in JavaScript that enables the creation of professional-level functions and optimization techniques.
It allows functions to remember data from previous executions and facilitates the implementation of design patterns.
Understanding closure involves grasping local memory,execution context, and functions with memories. In summary, closure empowers developers to build advanced functions, optimize performance, and enhance code structure.


## Returning Functions from Functions

Functions can be returned from other functions in JavaScript. This concept is crucial for understanding closure. When a function is returned from another function, it can be assigned to a variable and invoked later. The returned function retains access to variables and data from its outer function, even after the outer function has finished executing.

### Benefits of Closure

Closure allows for the creation of advanced functions and optimization techniques. By returning functions and capturing their surrounding data, closure enables powerful functionalities such as memoization and state management. It enhances code modularity, reusability, and performance.

### Example


```javascript
function outerFunction() {
  const outerVariable = 'Hello';

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

const myFunction = outerFunction();
myFunction(); // Output: Hello
```

In this example, the `innerFunction` is returned from the `outerFunction`. Even though `outerFunction` has completed execution, `innerFunction` retains access to the `outerVariable` through closure. Invoking `myFunction` logs the value of `outerVariable`, demonstrating the persistence of data via closure.

Closure plays a crucial role in various aspects of JavaScript development, including advanced function creation, design patterns, and performance optimization. Understanding and effectively utilizing closure can greatly enhance your JavaScript programming skills.



```
   +---------------------------+
   |                           |
   |         outerFunction     |
   |    +-----------------+    |
   |    |  outerVariable  |    |
   |    +-----------------+    |
   |                           |
   +-----------+---------------+
               |
               | Closure
               |
   +-----------v---------------+
   |                           |
   |       innerFunction        |
   |    +-----------------+    |
   |    |  Closure (Link) |----+---> outerVariable
   |    +-----------------+    |
   |                           |
   +---------------------------+



```


## Calling Functions in the Same Function Call

In JavaScript, we can call a function within the same function call in which it was defined. This behavior has interesting consequences and is crucial to understanding closure. Let's explore an example that sheds light on this concept.

```javascript
function outer() {
  let counter = 0;

  function incrementCounter() {
    counter++;
    console.log(counter);
  }

  incrementCounter();
}

outer();
```

In this example, we have the `outer` function that defines a `counter` variable and an `incrementCounter` function. Inside `incrementCounter`, we increment the `counter` by one and log its value. Finally, we call `incrementCounter` within the `outer` function.

When we invoke `outer`, it creates a new execution context and stores the `counter` variable in its local memory. Next, it defines the `incrementCounter` function within the `outer` execution context and executes it immediately.

Here comes the interesting part. When `incrementCounter` tries to access the `counter` variable, it first looks for it in its own local memory. Since it doesn't find it there, it then searches in the outer (parent) execution context, which in this case is the `outer` function's execution context.

This ability to access variables from the parent execution context, even when a function is called within the same function call, demonstrates the concept of closure. In this example, `incrementCounter` can access and modify the `counter` variable because it was defined in the same function call as the one in which it is executed.

Understanding this behavior is crucial for grasping the fundamentals of closure and its implications in JavaScript. It sets the foundation for more advanced concepts and techniques involving closure.


```
                             +-------------------+
                             |                   |
                             |   Global Memory   |
                             |                   |
                             +--------+----------+
                                      |
                                      |
                                      |      +-------------------------------+
                                      |      |                               |
                                      |      |      outer Execution Context  |
                                      |      |                               |
                                      +------|-------------------------------+
                                             |       outer Local Memory      |
                                             |                               |
                                             |  counter: 0                   |
                                             |  incrementCounter: <function> |
                                             |                               |
                                             +-------------------------------+
                                                         |
                                                         |
                                              +-----------------------+
                                              |                       |
                                              |  incrementCounter()   |
                                              |  Execution Context    |
                                              |                       |
                                              |  incrementCounter     |
                                              +-----------------------+
```

In this diagram, we have the global memory represented at the top. Within the global memory, we have the `outer` function defined.

When we invoke the `outer` function, it creates a new execution context called the `outer` execution context. Inside the `outer` execution context, the local memory is created to store variables and functions specific to that execution context. In this case, the `counter` variable is initialized with a value of 0, and the `incrementCounter` function is defined.

Now, when the `incrementCounter` function is executed, it creates a new execution context called the `incrementCounter` execution context. This execution context has its own local memory.

When `incrementCounter` tries to access the `counter` variable, it first looks for it in its own local memory. If it doesn't find it there, it moves up the scope chain and searches for it in the parent execution context, which is the `outer` execution context. In this case, it finds the `counter` variable in the `outer` execution context and increments its value.



## Function and Closure

This text discusses the concept of functions and closures in JavaScript. It follows a dialogue between Will Sentance and participants. Here are the key points covered:

- Functions can be stored in variables and have their own local memory when called.
- When a function is returned from another function, it carries with it a backpack of surrounding data attached to its definition.
- The returned function can access and manipulate the surrounding data even when it is called outside of its original context.
- The surrounding data is stored in the function's hidden scope property, allowing it to be accessed when the function is executed.
- The surrounding data is private and can only be accessed by running the function.
- The function definition, along with its attached surrounding data, can be stored and reused.

This feature of JavaScript allows for powerful and elegant programming techniques, enabling functions to retain and manipulate data from their original context.


```javascript
function outer() {
  let counter = 0;

  function incrementCounter() {
    counter++;
    console.log(counter);
  }

  return incrementCounter;
}

const myNewFunction = outer();
myNewFunction(); // Output: 1
myNewFunction(); // Output: 2
myNewFunction(); // Output: 3
```

In this example, we have a function called `outer` that defines a local variable `counter` and a nested function `incrementCounter`. The `incrementCounter` function increments the `counter` variable and logs its value to the console.

When we call `outer` and assign its return value to `myNewFunction`, we are actually capturing the `incrementCounter` function along with its surrounding data, which includes the `counter` variable. This is possible because of closure. 

Subsequently, when we invoke `myNewFunction`, it still has access to the `counter` variable even though it is no longer directly within the scope of the `outer` function. Each time we call `myNewFunction`, the `counter` value is incremented and logged to the console.

Certainly! Here are the questions and their corresponding answers in Markdown code:

**Questions from session:**

1. Can you have a backpack of the second level? (referring to nested execution contexts)
2. Can you have a callback function that accesses the surrounding data?
3. Is the data stored in the backpack considered private?
4. How does scope come into play?
5. How does error propagation work in nested operations?
6. How can the contents of the backpack be viewed during debugging?
7. What happens if a variable in `outer` is not referenced by the returned function?

**Answers:**

1. Yes, nested execution contexts can have their own backpacks. It forms a chain where each level has its associated data stored in the backpack.
2. Yes, it is possible to pass a callback function that can access the surrounding data. This is often used in functional programming techniques like function decoration.
3. The term "private" can be subjective and language-dependent. While the data in the backpack is not directly accessible outside the function, it may not be entirely private as it can still be accessed through the function itself.
4. Scope determines the visibility and accessibility of variables. In this context, the function can access variables from its surrounding scope by referring to the data stored in its backpack.
5. Error propagation works through the chain of references in nested operations. If an error occurs in an operation, it can propagate through the chain, making it easier to track and handle errors.
6. The contents of the backpack can be viewed during debugging using tools like the Chrome DevTools. These tools provide the ability to inspect the function's backpack and see its associated data.
7. If a variable in `outer` is not referenced by the returned function, it will not be stored in the backpack. The function only carries the data that it needs, so any unused variables will not be included.


## Closure Functions and Persistent Memories

Closure functions have a persistent store of data attached to them, like a cache, which gives us a new toolkit for writing professional code. They allow us to create helper functions that remember their previous input-output combinations, providing a way to store and reuse data.

## Memorization and Persistent Data

Memorization is the practice of storing previously computed values to avoid redundant calculations. It is useful when dealing with tasks that require significant computation time. By storing the results in a function's backpack (closure), we can retrieve the value instead of recalculating it, improving performance.

## Lexical Scoping and Closure

Lexical scoping, a feature of JavaScript, allows functions to access data from their parent scope. When we create a function inside another function, it carries the entire environment with it, including all the variables in the backpack. This allows the inner function to access and use the data from the outer function.

## The Backpack (Closure)

The backpack, also known as closure, refers to the persistent storage of data attached to a function. It contains the variables and values from the function's parent scope, allowing the function to access and use that data even when executed elsewhere. The backpack is a powerful tool for creating functions with persistent memories.

## Benefits and Use Cases

The backpack (closure) offers several benefits, including the ability to lock down functions to prevent multiple executions and to store and retrieve previously calculated values. It is useful in scenarios such as creating winning functions in games or implementing efficient computations that rely on previously computed data.

## Lexical Scope and Static Scoping



# homeworks:

### Homework 1: Compose Function

```javascript
function compose(...functions) {
  return function(input) {
    let result = input;
    for (let i = 0; i < functions.length - 1; i++) {
      if (typeof functions[i] === 'function') {
        result = functions[i](result);
      }
    }
    return result;
  };
}

// Example usage
function addOne(num) {
  return num + 1;
}

function double(num) {
  return num * 2;
}

function square(num) {
  return num ** 2;
}

const composedFunction = compose(square, double, addOne);
console.log(composedFunction(2));
```


### Homework 2: PowerOf Closure

```javascript
const powerOf = (base) => {
  const exp = () => {
    return Math.pow(base, 2);
  };
  return exp;
};

const result = powerOf(3);
console.log(result());
```


### Homework 3: CalculateAverage Function

```javascript
const calculateAverage = (arr, nums) => {
  let sum = 0;
  const calculation = () => {
    for (let num of arr) {
      sum += num;
    }
    return sum / nums;
  };
  return calculation;
};

const value = calculateAverage([32, 42, 34, 23, 4, 2], 6);
console.log(value());
```

### Homework 4: CalculateAverage Function (Revised)

```javascript
const calculateAverage = (arr, nums) => {
  let sum = 0;
  const calculation = () => {
    for (let num of arr) {
      sum += num;
    }
    return sum / nums;
  };
  return calculation;
};

const value = calculateAverage([32, 42, 34, 23, 4, 2], 6);
console.log(value());
```


