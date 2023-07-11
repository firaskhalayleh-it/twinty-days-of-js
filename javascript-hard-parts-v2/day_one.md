# day one of learinig course javascript hard parts v2
## introduction
# Introduction

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


## functions & callbacks 



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
