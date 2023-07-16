# day three :

## Asynchronous Programming in JavaScript

In this session, Will Sentance introduces the concept of asynchronous programming in JavaScript. He starts by discussing promises as an addition to the traditional ES5 callback model. Promises provide a way to handle asynchronous operations in a more readable and organized manner.

Will explains that JavaScript's asynchronicity is what enables dynamic web applications and simultaneous operations in a single-threaded language. He mentions the event loop, which determines the order of code execution, and the micro task queue, an important aspect of web browser features.

The session then dives into the execution of regular code, where data is stored in global memory. Constants and functions are defined, and function results are stored in variables. New execution contexts are created for function calls, and the code inside functions is executed. Once the function code is completed, the execution context is closed, and the program moves to the next line of code.

Finally, the session covers the declaration and assignment of values to new variables.

Overall, this session provides an overview of the key concepts and mechanisms involved in asynchronous programming in JavaScript.


## Asynchronous JavaScript and Web Browser Features

In this session, Will Sentance discusses the challenges posed by JavaScript's single-threaded and synchronous nature. He highlights the problem of blocking code execution when waiting for slow tasks, such as network requests or rendering.

To address this issue, JavaScript leverages web browser features through facade functions. These features include timers, the HTML DOM, network request capabilities, console, and more. These functions provide an interface for JavaScript to interact with the browser and access its functionalities.

Will explains that JavaScript alone cannot perform tasks like delaying function execution or making network requests. Instead, it relies on these web browser features to accomplish such tasks.

The session emphasizes the distinction between JavaScript, which runs in the browser's JavaScript engine, and the web browser itself, which contains additional features beyond JavaScript.

The session concludes with an exercise for participants to analyze code that utilizes the set timeout function and encourages them to consider the order of execution based on their understanding of web browser features and JavaScript's synchronous nature.

Web browsers provide several features that enhance the capabilities of JavaScript within the browser environment :

| Browser Features                           | JavaScript Equivalent  | Command                |
|--------------------------------------------|------------------------|------------------------|
| Rendering and DOM Manipulation              | Document Object Model  | N/A                    |
| Network Communication                       | XMLHttpRequest (XHR)   | fetch, AJAX, XHR       |
| Timers and Asynchronous Execution           | setTimeout, setInterval| setTimeout, setInterval|
| User Interaction and Events                 | Event listeners        | addEventListener      |
| Web APIs and Browser Features               | Various JavaScript APIs| N/A                    |
| Developer Tools                             | Console object         | console.log, console.error, etc. |



## Execution Model and Web Browser Features in JavaScript




1. Single-threaded execution in JavaScript requires each line of code to finish before moving on.
2. Communication tasks with servers, like retrieving tweets, can cause delays in code execution.
3. JavaScript lacks the ability to wait for task completion before proceeding to other code.
4. Web browser features are introduced to overcome this limitation, including timers and network requests.
5. Examples illustrate using setTimeout to delay function execution and making network requests for data retrieval.
6. The text explains the order of execution and interaction between JavaScript and web browser features.
7. Strict rules are necessary to govern JavaScript's behavior when interacting with web browser features.
8. The concept of blocking code execution using tasks like for loops is introduced.





In this code explanation, the focus is on understanding how JavaScript interacts with the web browser features. The code example uses the `setTimeout` function, which is a web browser feature labeled in JavaScript. It sets up a timer that will trigger the execution of a function after a specified delay.

Here's a summary of the code execution:

```javascript
// Define the printHello function
function printHello() {
  console.log("Hello");
}

// Set up a timer using setTimeout
setTimeout(printHello, 1000);

// Log "Me first" to the console
console.log("Me first");
```

The execution flows as follows:

1. The `printHello` function is defined in JavaScript.
2. The `setTimeout` function is called, which sets up a timer in the web browser for 1000 milliseconds (1 second).
3. The timer starts running in the background while JavaScript continues executing.
4. The JavaScript code moves on to the next line, which logs "Me first" to the console.
5. Time continues to pass in the web browser.
6. After 1000 milliseconds, the timer in the web browser is complete.
7. The `printHello` function is executed and the message "Hello" is logged to the console.

It's important to note that the `setTimeout` function and other web browser features are not part of JavaScript itself but are accessible through JavaScript as facade functions. Understanding this interaction between JavaScript and the web browser features helps explain the behavior of asynchronous operations in JavaScript.


Please note that the diagram is not included in the Markdown format, but you can refer to the original response for the diagram explanation.


```
                                        JavaScript Execution
+------------------------------------------------------------------------------------------+
|                                                                                          |
|                       +-----------------+                      +-----------------+       |
|                       |                 |                      |                 |       |
|                       |   setTimeout    |                      |   printHello    |       |
|                       |   (Web Browser) |                      |    Function     |       |
|                       |                 |                      |                 |       |
|                       +-----------------+                      +-----------------+       |
|                              |                                         |                 |
|                              |                                         |                 |
|                              |                                         |                 |
|                              v                                         v                 |
|                                                                                          |
|                       +-----------------+       Log "Me first" to console                |
|                       |                 |                                                |
|                       |    Console      |                                                |
|                       |   (Web Browser) |                                                |
|                       |                 |                                                |
|                       +-----------------+                                                |
|                                                                                          |
|                              |                                                           |
|                              |                                                           |
|                              |                                                           |
|                              v                                                           |
|                                                                                          |
|                       +-----------------+                                                |
|                       |                 |       Execute printHello function              |
|                       |   Call Stack   |                                                 |
|                       |                 |                                                |
|                       +-----------------+                                                |
|                                                                                          |
|                              |                                                           |
|                              |                                                           |
|                              |                                                           |
|                              v                                                           |
|                                                                                          |
|                       +-----------------+       Log "Hello" to console                   |
|                       |                 |                                                |
|                       |    Console      |                                                |
|                       |   (Web Browser) |                                                |
|                       |                 |                                                |
|                       +-----------------+                                                |
|                                                                                          |
+------------------------------------------------------------------------------------------+
```


This diagram illustrates the flow of execution in the code example. The `setTimeout` function is called, which sets up a timer in the web browser. Meanwhile, the JavaScript code continues executing and logs "Me first" to the console. After the specified delay, the timer in the web browser triggers the execution of the `printHello` function, which logs "Hello" to the console.



To summarize the text and add titles for each subject, let's break it down:

### Introduction to ES2015 (ES6) and Promises

In this section, Will Sentance introduces the concept of Promises in JavaScript and how it changed with the introduction of ES2015 (ES6). He mentions the limitations of using `setTimeout` for background tasks and the need for a way to track and maintain consistency between JavaScript memory and background processes.

### Two-Pronged Facade Functions

Will explains the concept of "two-pronged facade functions" that were introduced in ES6. These functions not only trigger background processes in the web browser (like network requests) but also return a special object called a Promise in JavaScript. The Promise acts as a placeholder that keeps track of the background work and allows developers to know when the task is completed.

### Fetching Data with Fetch API

The Fetch API is introduced as a modern way to make network requests in JavaScript. It replaces the older XMLHttpRequest (XHR) and simplifies the process of sending and receiving data over the internet. Will demonstrates how to use `fetch` to send a request to Twitter for data.

### Promise Object and Its Properties

Will explains the structure of a Promise object, which has two properties: `value` and `onFulfilled`. The `value` property is initially undefined and is used to store the data returned from the background task (in this case, the data fetched from Twitter). The `onFulfilled` property is an array that stores functions to be triggered when the data is available.

### Handling the Returned Data

When the network request is completed and the data is received from Twitter, it is stored in the `value` property of the Promise object. At this point, any functions stored in the `onFulfilled` array are automatically triggered with the data as their input. This allows developers to handle the returned data and perform actions on it, like displaying it on the webpage.

### Using `.then()` for Asynchronous Callbacks

Will discusses the `.then()` method, which is a built-in method of Promises. It allows developers to add functions to the `onFulfilled` array and handle the data when it becomes available. Since the `onFulfilled` property is hidden, developers can't directly push functions to it, but they can use `.then()` to achieve the same result.

### Conclusion and Wrap-Up

will concludes by highlighting the power of Promises in managing asynchronous tasks and maintaining consistency between JavaScript memory and background processes. It emphasizes the importance of using `.then()` to handle data when it is available.

Please note that the above summary is based on the provided text and may not cover all aspects in detail. The code examples and diagrams are not available in the text provided, so I cannot include them in this summary. If you have specific code examples or diagrams you would like to include, please provide them, and I'll be happy to help incorporate them into the summary.

