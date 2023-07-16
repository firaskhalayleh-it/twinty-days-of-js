# day_four
## Accessing Methods on Prototype Objects

This section covers the process of accessing methods on prototype objects. When a method is not found on the current object, JavaScript searches for it in the linked prototype object. This enables objects to access and utilize shared methods stored in the prototype chain.

## Pros and Cons of Implicit Parameters and Prototypal Inheritance

Here, the text discusses the advantages and drawbacks of using implicit parameters and prototypal inheritance in JavaScript. While implicit parameters simplify method invocation and provide code reusability, they can also lead to potential side effects. Understanding and managing these aspects is crucial for building efficient and maintainable code.

## Distinguishing `__proto__` from `prototype`

This part clarifies the distinction between the `__proto__` property and the `prototype` property in JavaScript. While `__proto__` is a hidden property on objects used to create the prototype chain, `prototype` is a property specifically associated with constructor functions used for prototypal inheritance.

## The Role of `this` in Different Execution Contexts

The text explores how the `this` keyword behaves in various execution contexts. It explains how the value of `this` is determined based on the object to the left of the dot when invoking a method, as well as how it may behave differently in functions called without an object context.

## Hidden Properties and Their Visibility

Finally, this section touches on the concept of hidden properties and their visibility. While some hidden properties, like `__proto__`, can be accessed and used in certain ways, others may remain entirely hidden from view. Understanding these hidden properties is essential for effective debugging and code analysis.

---

