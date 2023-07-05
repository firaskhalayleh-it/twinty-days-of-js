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

