# day one of learinig course javascript hard parts v2

## Introduction

This course will teach you the fundamentals of JavaScript, including:

* JavaScript principles
* Callbacks & Higher Order Functions
* Closure
* Classes/Prototypes & Asynchronicity

The course also focuses on analytical problem solving, technical communication, and non-technical communication.

## Objectives

By the end of this course, you will be able to:

* Understand the fundamentals of JavaScript
* Write JavaScript code that is clear, concise, and efficient
* Solve complex JavaScript problems
* Communicate technical information to both technical and non-technical audiences

## Prerequisites

No prior knowledge of JavaScript is required. However, some familiarity with programming concepts would be helpful.

## Structure of the course

The course is divided into four modules:

* Module 1: JavaScript Principles
* Module 2: Callbacks & Higher Order Functions
* Module 3: Closure
* Module 4: Classes/Prototypes & Asynchronicity

Each module includes a series of video lectures, readings, and exercises.




## javascript principles
there are main concepts that the course taking it like thread of execution ,memory and call stack. with these principles we will having more informaiton and practice with how the porgram works .
#### thread of execution :
js is line by line language that mean it reads one line of code and run in one moment of time .
#### memeory
it can store functions and data(strings, numbers,boolean etc)
#### call stack
it is a traditional stack that stores the functions that must be run in the execution context.
## functions & callbacks:
- Enables powerful pro-level functions like map, filter, reduce (a core aspect of functional programming)
- Makes our code more declarative and readable
- generalizing the function makes the function reusable as much as possible by provice perimeters/
## functions:
every function has when execute two main things :
1. memory.
2. thread of execution.



## execution context :
created to run the code of function they have 2 parts :
1. thread of execution
2. memory
- foreach function we creat a mini execution context on the main one.
- the main file has execution context named main execution context (global)
- the number of execution that runs in one time is one.

## generalizing functions

The `copyArrayAndMultiplyBy2` function creates a new array called `output`. It then loops through the `myArray` array, multiplying each element by 2 and pushing the doubled element into the `output` array. Finally, the `copyArrayAndMultiplyBy2` function returns the `output` array.

After walking through the code, Will Sentance points out that the function could be simplified by using the `map()` function. The `map()` function takes a function and an array as arguments, and it returns a new array with the results of applying the function to each element of the original array.

Will Sentance then rewrites the `copyArrayAndMultiplyBy2` function using the `map()` function. The new function is called `copyArrayAndMultiplyBy2UsingMap`.

The `copyArrayAndMultiplyBy2UsingMap` function takes an array as an argument and returns a new array with each element doubled. The function works by using the `map()` function to apply the function `x * 2` to each element of the original array.

Will Sentance then compares the two functions and shows that the `copyArrayAndMultiplyBy2UsingMap` function is more concise and easier to read.

The video ends with Will Sentance discussing the benefits of using the `map()` function. He points out that the `map()` function is a powerful tool that can be used to simplify code and make it easier to read.

Here are some of the key points from the video:

* The `copyArrayAndMultiplyBy2` function takes in an array and returns a new array with each element doubled.
* The `map()` function takes a function and an array as arguments, and it returns a new array with the results of applying the function to each element of the original array.
* The `copyArrayAndMultiplyBy2UsingMap` function is a more concise and easier-to-read version of the `copyArrayAndMultiplyBy2` function.
* The `map()` function is a powerful tool that can be used to simplify code and make it easier to read.

## repeating functions:
``` javascript
function tensquared (){
return 10*10;
}
```

this function is not good ,why? couse it break DRY principle (dont repeat yourself).
so we use parameters and callback functions to having more generalized function

## higher-order functions

```javascript
const copyArrayAndManipulate = (array, instructions) => {
  let output = [];
  for (let i = 0; i < array.length; i++) {
    output.push(instructions(array[i]));
  }
  return output;
};

const multiplyByTwo = (number) => {
  return number * 2;
};

const result = copyArrayAndManipulate([1, 2, 3], multiplyByTwo);
console.log(result); // [2, 4, 6]
```

This code defines a higher-order function called `copyArrayAndManipulate`. This function takes two arguments: an array and a function. The function argument is a callback function that is passed each element of the array. The callback function is responsible for manipulating the element in some way. In this case, the callback function is `multiplyByTwo`, which simply multiplies the element by 2.

The `copyArrayAndManipulate` function iterates through the array and calls the callback function for each element. The result of the callback function is then pushed onto the output array. The output array is then returned.

In this example, the callback function is `multiplyByTwo`. However, any function can be used as the callback function. This makes `copyArrayAndManipulate` a very versatile function. It can be used to manipulate arrays in any way that you want.

To run this code, you can save it as a JavaScript file and then open it in a JavaScript debugger. You can also run it in the browser by pasting it into the console.


## higher-order function and callbacks


Higher-order functions and callbacks are a powerful way to make code more reusable and declarative.

A higher-order function is a function that takes in a function as an argument, or returns a function as a value.

A callback function is a function that is passed to another function as an argument, and then called by that function.

The `copyArrayManipulate` function is a higher-order function that takes in a callback function as an argument.

The `multiplyBy2` function is a callback function that multiplies its argument by 2.

The `copyArrayManipulate` function can be used to create a new array with each element multiplied by 2.

Here is an example of how the `copyArrayManipulate` function can be used:




```javascript
const myArray = [1, 2, 3];
const newArray = copyArrayManipulate(myArray, multiplyBy2);

console.log(newArray); // [2, 4, 6]

```
As you can see, the `copyArrayManipulate` function takes the myArray array as an argument, and the `multiplyBy2` callback function as another argument. The `copyArrayManipulate` function then iterates through the myArray array, and calls the `multiplyBy2` function on each element. The `multiplyBy2` function then multiplies each element by 2, and the `copyArrayManipulate` function returns a new array with the multiplied elements.





## arrow function

Arrow functions are a new feature in JavaScript that were introduced in ES6. They are a concise way to write anonymous functions, and they can be used in a variety of ways.

One of the benefits of arrow functions is that they can make your code more concise and readable. For example, the following code:

```javascript
function double(number) {
  return number * 2;
}
```

can be written as an arrow function as follows:

```javascript
const double = (number) => number * 2;
```

As you can see, the arrow function is much shorter and easier to read.

Another benefit of arrow functions is that they have different this binding rules than regular functions. In regular functions, the this keyword refers to the object that called the function. However, in arrow functions, the this keyword refers to the object that defined the arrow function.

This can be useful in some cases, such as when you are using arrow functions as callbacks. For example, the following code:

```javascript
const button = document.querySelector('button');
button.addEventListener('click', () => {
  console.log(this); // window
});
```

will log the window object, because the arrow function is defined in the global scope.

Overall, arrow functions are a powerful new feature in JavaScript. They can make your code more concise, readable, and efficient. If you haven't used them yet, I encourage you to give them a try.

## pair programing:

most active way to grow us as software engineer you must be :
1. searcher
2. stackoverflower

* **Set clear expectations.** Before you start pair programming, it's important to set clear expectations about your roles and responsibilities. Who will be the driver and who will be the navigator? What kind of communication style do you prefer?
* **Be open to feedback.** When you're pair programming, be open to feedback from your partner. They may have different ideas about how to solve a problem, or they may be able to see errors in your code that you've missed.
* **Be patient.** Pair programming can be a slow process at first, as you get used to working together. But it's important to be patient and to communicate openly with your partner.
* **Have fun!** Pair programming can be a lot of fun, if you're willing to experiment and learn from each other. So relax, enjoy the process, and learn as much as you can.

Here are some additional tips:

* **Take turns being the driver and the navigator.** This will help you to learn from each other and to improve your skills.
* **Don't be afraid to ask questions.** If you don't understand something, ask your partner for help.
* **Take breaks.** Pair programming can be mentally demanding, so it's important to take breaks every 20-30 minutes.
* **Get feedback from others.** Once you've finished pair programming, ask someone else to review your code. This can help you to identify any errors or areas for improvement.



# homeworks :

### homework [one](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
``` javascript
const squareList = arr => {
  // Only change code below this line
  const result  = arr.filter(val=>parseInt(val)===val&&val>0).map(val=>val*val)
  return result;
  // Only change code above this line
};

const squaredIntegers = squareList([4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2]);
console.log(squaredIntegers);
```
### homework [two](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
``` javascript
// Only change code below this line
function urlSlug(title) {
const res = title
.toLowerCase()
.split(' ')
.filter(val=>val!=='')
.join('-');
return res;
}
// Only change code above this line
console.log(
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone"))
```
### homework three:
1.
 ``` javascript
   const mapAsync =async(array,callback)=>{
    let newArray  = [];
    for (let element of array){
       newArray.push(await callback(element))
      
    }
    return Promise.resolve(newArray)} 
    
  
```

2.
```javascript
const sumRange =(range,sum) =>{
    
    if (range <= 0){
        return sum;
    }
    
    return sumRange(range-1,sum + range);
}
const result = sumRange(4, 0);
console.log(result);

```

