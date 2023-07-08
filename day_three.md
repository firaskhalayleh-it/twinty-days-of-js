# day three of learining js 

## the code of quiz project is in the [file](optionalQuestion.html)


In the provided HTML document, the JavaScript script is responsible for handling the quiz functionality. Here's a description of what is used in the JavaScript script:

1. Variable Declarations:
   - `statement`: Stores the reference to the element with the id `'statement'` that represents the quiz statement.
   - `explanation`: Stores the reference to the element with the id `'explanation'` that displays the explanation after answering the quiz.
   - `optionButtons`: Stores the reference to the element with the id `'options'` that contains the quiz answer buttons.

2. Function Declarations:
   - `disable`: Takes a button element as an argument and sets the `disabled` attribute to disable the button.
   - `enable`: Takes a button element as an argument and removes the `disabled` attribute to enable the button.
   - `isCorrect`: Takes a guess as an argument and compares it with the `answer` property of the `fact` object. Returns `true` if the guess is correct.

3. `fact` Object:
   - Contains properties related to the quiz fact, including `statement`, `answer`, and `explanation`. These properties hold the content for the quiz statement, the correct answer, and the explanation.

4. Setting the Statement:
   - `statement.textContent = fact.statement;` sets the text content of the `statement` element to the value of `fact.statement`, displaying the quiz statement.

5. Event Listeners:
   - A `for` loop iterates over the `optionButtons.children` elements.
   - For each button, an event listener is added using `addEventListener` to listen for a click event.
   - Within the event listener function, the explanation text content is set to `fact.explanation`.
   - Another loop disables all the option buttons using the `disable` function.
   - The value of the clicked button is stored in the `guess` variable.
   - If the guess is correct, the clicked button is assigned the class `'correct'`. Otherwise, it is assigned the class `'incorrect'`.

This script enables the quiz functionality by displaying a statement, allowing the user to select an answer, and providing feedback based on their selection.

# Functions

Functions are used to perform actions or behaviors. They can have parameters that determine the number of values needed to execute the action. When declaring parameters, you cannot directly replace them with values. For example, `const fun = ('value') => {}` would result in an error.

When calling a function, if you provide a value for a parameter that is not declared, it will be ignored.

- `return`: Functions can return values, although some functions may not return any value. The difference between using `return` and `console.log` is that `return` is used to pass a value back to the caller, while `console.log` is used for printing output to the console. It's important to note that code after the `return` statement in the same scope is not reachable.

Arrow functions are a shorthand syntax used to create unnamed functions with less code. They can be assigned to variables,
like `const res = (a, b) => a + b;`, which is equivalent to:

```javascript
function res(a, b) {
  return a + b;
}
```
## Scope

Scope refers to where variables and functions are declared and accessible within a program.

1. Scopes are nested within programming.
2. The widest scope is the global scope, which means variables declared in the global scope can be accessed from anywhere in the program.
3. Each function has its own scope, and variables declared within a function are only accessible within that function's scope.

When it comes to accessing variables, it depends on the scope in which they are declared. In the global scope, you can access all variables. However, in narrower scopes (such as within a function), you can only access variables declared within that scope or variables declared in wider scopes.

### Let vs. Scope:
If a variable is declared using `let` in the global scope, it can be accessed within functions. However, you cannot assign a new value to that variable in the global scope. Here's an example:

```javascript
let num = 5; // Variable declared in global scope

function multiplyByTwo() {
  console.log(num * 2); // Accessing the variable in a function's scope
}

multiplyByTwo(); // Output: 10

num = 10; // Assigning a new value in the global scope
console.log(num); // Output: 10
```
### Let vs. Var:
The main difference between let and var is in their scope behavior. Variables declared with var are function-scoped, meaning they are accessible within the entire function in which they are declared, regardless of block scope. On the other hand, variables declared with let are block-scoped, meaning they are only accessible within the block (such as a loop or conditional statement) in which they are declared. This can help prevent unintended variable hoisting and scoping issues.
Here's the code example explaining the difference between let and var in JavaScript, converted to Markdown format:

```javascript
function example() {
  var x = 10; // Variable declared with var
  let y = 20; // Variable declared with let

  if (true) {
    var x = 30; // Re-declaring x with var inside a block
    let y = 40; // Declaring y with let inside a block
    console.log("Inside Block - var x:", x); // Output: 30
    console.log("Inside Block - let y:", y); // Output: 40
  }

  console.log("Outside Block - var x:", x); // Output: 30
  console.log("Outside Block - let y:", y); // Output: 20
}

example();
```

# homeworks :
### homework [one](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return):
``` javascript
function timesFive (num){
  return num*5;
}
```
### homework [two] (https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)
``` javascript
// Declare the myGlobal variable below this line

let myGlobal =10;
function fun1() {
  // Assign 5 to oopsGlobal here
  oopsGlobal =5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
### homework [three](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
``` javascript 
function myLocalScope() {
  // Only change code below this line
let myVar = 'fdsa'
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```
### homework [four](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)
``` javascript
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
   const  outerWear = 'sweater'
  // Only change code above this line
  return outerWear;
}

myOutfit();
````
### homework [five](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
``` javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
 
  return  arr.shift();;
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

