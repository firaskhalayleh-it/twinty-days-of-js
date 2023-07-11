# day two of learining js 
## Expressions: 
The snippets that use values and operations are expressions. 

### Keywords: 
`let`, `const`, and `var` are keywords (reserved words) used to create new variables in JavaScript. 

### Assignment Operator: 
The `=` symbol is the assignment operator in JavaScript, used to assign a value to a variable. 

### Semicolon: 
The semicolon (`;`) indicates the end of a line of code or statement in JavaScript. 

### Declaring Value: 
To declare a variable, you can use the `let` keyword. For example: `let example;`. 

### Undefined Variables: 
When a variable is declared without assigning a value, it is initially considered `undefined`. 

### Assigning Value: 
To assign a value to a variable, use the assignment operator (`=`). For example: `example = 'firas';`. 

### Table for Data:

| Variable | Value              |
|----------|--------------------|
| thing    | 'value'            |
| varr     | 'you are good man' |

### Variable Naming Styles: 
There are two styles for naming variables in JavaScript: camelCase and snake_case. 
- camelCase: Words are concatenated, with each word (except the first) starting with a capital letter. Example: `myVariableName`.
- snake_case: Words are written in lowercase, separated by underscores. Example: `my_variable_name`.

### Evaluating Code: 
You can put expressions in variables and refresh the value of a variable. For example: 
````javascript
let res = ((2 * 3) + 5) * 7;
let val = 'value';
let resolvedValue = val;
val = 'new value';
````
## Statements Vs.Expressions
|           | Statements                                 | Expressions                                 |
|-----------|--------------------------------------------|---------------------------------------------|
| Purpose   | Perform actions or control flow            | Produce a value                             |
| Result    | Does not always produce a value            | Always produces a value                      |
| Examples  | `if` statement, `for` loop, function declaration   | Arithmetic operations, function calls, variable assignments |
| Usage     | Used to execute code                       | Used to compute values                       |
| Side Effects | Statements can have side effects        | Expressions are generally side effect-free   |
| Order     | Can be grouped into blocks or sequences    | Can be nested or combined within statements |
| Composition | Statements cannot be nested within expressions  | Expressions can be nested within statements |


## Arrays:
Arrays allow us to store multiple values together. For example, string arrays have properties like length, square brackets `[]` for accessing elements by index, and methods like `indexOf` and `includes`.

### Some methods for arrays:
1. `pop()`: Removes and returns the last element of the array.
2. `push()`: Adds elements to the end of the array. You can push objects or nested arrays.
3. `sort()`: Sorts the elements of the array in ascending order.
4. `join()`: Joins the elements of the array into a single string.
5. `concat()`: Combines multiple arrays into a new array.

Arrays can hold multiple types of data or be empty or have a single value. Unlike strings, arrays are mutable and can be modified.

Here's a table summarizing the differences between `push()` and `concat()`:

| Method | Purpose                                           | Modifies Original Array | Returns                |
|--------|---------------------------------------------------|-------------------------|------------------------|
| `push` | Adds elements to the end of the array              | Yes                     | Returns the new length |
| `concat` | Combines arrays and returns a new concatenated array | No                    | Returns a new array    |

When declaring an array, a new variable is created with values assigned to its indexes. The indexes point to the actual values stored in the array.

Using `const` with arrays:
With `const`, you can't reassign the array itself, but you can modify its contents.

Declaring variables that point to the array:
```javascript
let arr1 = [0, 1, 2];
let arr2 = arr1;
arr1[1] = 3;
```
In the above example, arr1 and arr2 both change because they point to the same values.
## Objects

Objects are a data type that describes complex data. We can use variables to point to different values in our code. In JavaScript, we can access properties of an object using dot notation. Commas are used to separate properties within an object. We can assign properties to objects.

### Object methods:
1. `join()`: Joins the elements of an object.
2. `freeze()`: Makes the properties of an object immutable.
3. Spread (`...`): Used for dividing the values of an array.
4. `this`: A method that allows us to reference other properties within an object. Example: `this.propertyName`.
   
We can also define functions as object properties, and we can include arrays as object properties. Objects can be nested, creating nested objects within objects.

### Built-in objects:
1. Array: An array can contain objects or other data types.
2. Document: An object representing the current web page.
3. Console: An object with properties like `log()`, `warn()`, and `error()`.
4. Math: An object with methods like `random()` and `PI`.
5. Strings: Although strings are primitive values, JavaScript automatically wraps them as objects. Strings have methods such as `length`, `toUpperCase()`, `toLowerCase()`, etc.


# homeworks 
### homework [one](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)
``` javascript
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line
  for (let i = 0; i < contacts.length; i++) {
    if (name === contacts[i].firstName) {
      if (contacts[i].hasOwnProperty(prop)) {
        return contacts[i][prop];
      } else {
        return "No such property";
      }
    }
  }
  return "No such contact";
  // Only change code above this line
}

console.log(lookUpProfile("Akira", "likes"));
```

### homework [two](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice):
``` javascript
function forecast(arr) {
  // Only change code below this line
arr =arr.slice(2,4);
  return arr;
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));

```

### homework [three](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator):
```javascirpt
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence = ['learning',...fragment, 'is', 'fun']; // Change this line
  return sentence;
}

console.log(spreadOut());
```

