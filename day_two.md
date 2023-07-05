# day two of learining js 
## Expressions: 
The snippets that use values and operations are expressions. 

Keywords: 
`let`, `const`, and `var` are keywords (reserved words) used to create new variables in JavaScript. 

Assignment Operator: 
The `=` symbol is the assignment operator in JavaScript, used to assign a value to a variable. 

Semicolon: 
The semicolon (`;`) indicates the end of a line of code or statement in JavaScript. 

Declaring Value: 
To declare a variable, you can use the `let` keyword. For example: `let example;`. 

Undefined Variables: 
When a variable is declared without assigning a value, it is initially considered `undefined`. 

Assigning Value: 
To assign a value to a variable, use the assignment operator (`=`). For example: `example = 'firas';`. 

Table for Data:

| Variable | Value              |
|----------|--------------------|
| thing    | 'value'            |
| varr     | 'you are good man' |

Variable Naming Styles: 
There are two styles for naming variables in JavaScript: camelCase and snake_case. 
- camelCase: Words are concatenated, with each word (except the first) starting with a capital letter. Example: `myVariableName`.
- snake_case: Words are written in lowercase, separated by underscores. Example: `my_variable_name`.

Evaluating Code: 
You can put expressions in variables and refresh the value of a variable. For example: 
````javascript
let res = ((2 * 3) + 5) * 7;
let val = 'value';
let resolvedValue = val;
val = 'new value';
````
|           | Statements                                 | Expressions                                 |
|-----------|--------------------------------------------|---------------------------------------------|
| Purpose   | Perform actions or control flow            | Produce a value                             |
| Result    | Does not always produce a value            | Always produces a value                      |
| Examples  | `if` statement, `for` loop, function declaration   | Arithmetic operations, function calls, variable assignments |
| Usage     | Used to execute code                       | Used to compute values                       |
| Side Effects | Statements can have side effects        | Expressions are generally side effect-free   |
| Order     | Can be grouped into blocks or sequences    | Can be nested or combined within statements |
| Composition | Statements cannot be nested within expressions  | Expressions can be nested within statements |
