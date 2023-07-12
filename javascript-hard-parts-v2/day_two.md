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

Here's an example that demonstrates closure in JavaScript:

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





