# Learning JavaScript from scratch to a professional level in just 20 days

## day number one :
<details>
  <summary>Table of Contents</summary>

  - [JavaScript Introduction](#day_one/#javascript-introduction)
  - [DOM (Document Object Model)](#day-2-dom-document-object-model)
  - [Values and Data Types](#day-3-values-and-data-types)
  - [Operators]([day(https://github.com/firaskhalayleh-it/twinty-days-of-js/blob/main/day_one.md#operators))
</details>

# JavaScript Introduction

The purpose of this course is to provide an introduction to JavaScript, covering its core principles and focusing on practical projects. 

## Course Objectives
1. Taking my first steps into an infinite journey.
2. Hands-on projects.
3. Just-in-time vs. just-in-case learning.

## What is JavaScript (JS)?
JavaScript is a programming language that enables websites to perform interactive tasks and facilitates communication between different web elements. It allows for modifying websites and making them interactive. JavaScript supports a wide range of programming styles, making it a popular choice for learning. It was created in just 10 days of implementation back in 1995.

## Usage and Platforms
JavaScript is primarily used for web development and can run on various platforms, including:

- Browsers
- Servers (via Node.js)
- Embedded systems

## Transpiling to JavaScript
There are languages like TypeScript that can be translated to JavaScript when the code needs to run in a browser.

## Writing JavaScript Code
JavaScript code can be written in the following environments:

1. Integrated Development Environments (IDEs) like VS Code.
2. Browsers directly support executing JavaScript code.
3. Online compilers, such as CodePen (background).


# DOM (Document Object Model)

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It provides a structured representation of the web page,
allowing JavaScript to interact with and manipulate the elements, attributes, and content within the document.

## How the DOM Works
When a web page is loaded in a browser, the browser creates a DOM tree based on the HTML or XML structure of the document. This tree consists of various nodes representing elements, attributes, and text within the document. Each element becomes an object, which can be accessed and manipulated using JavaScript.

## Accessing and Manipulating DOM Elements
JavaScript provides several methods and properties to interact with the DOM elements. Here are some commonly used commands:

- `document.title`: Retrieves or sets the title of the HTML document.
- `document.querySelector()`: Returns the first element that matches a specified CSS selector.
- `document.getElementById()`: Retrieves an element by its unique ID.
- `document.getElementsByTagName()`: Retrieves a collection of elements with the specified tag name.

These commands allow you to retrieve specific elements or collections of elements from the DOM, enabling you to modify their attributes, content, or styles.

## MDN (Mozilla Developer Network)

The Mozilla Developer Network (MDN) is a comprehensive resource for web developers. It provides detailed documentation, guides, tutorials, and examples for various web technologies, 
including JavaScript and the DOM. It is an excellent reference for understanding the usage and functionality of different DOM methods and properties, for sure we cant remember all commands in js so this site help us tor remember the command and understand it You can access MDN at [developer.mozilla.org](https://developer.mozilla.org/).

# Values and Data Types

Values are chunks of data that we work with in programming. They can represent various types of information, such as text, numbers, or objects. In JavaScript, there are two main categories of data types: primitive types and objects.

## Primitive Types
Primitive types are the most basic types of data in JavaScript. They include:

- Strings: Used to represent text. Strings can work with Unicode characters, including emojis.
- Numbers: Used to represent numerical values.
- Null: Represents the intentional absence of any object value.
- Undefined: Represents the absence of a defined value.
- Boolean: Represents a logical value of either true or false.

## String Manipulation
Strings in JavaScript can be accessed and manipulated using various methods. Here are some commonly used methods:

- `[]` Operator: Used to access individual characters in a string by specifying the index.
- `indexOf()`: Finds the index of a specific substring within a string.
- `includes()`: Checks if a target substring exists within a string.
- `startsWith()`: Checks if a string starts with a specific substring.
- `toLowerCase()` and `toUpperCase()`: Convert the text to lowercase or uppercase.

These methods allow you to work with and manipulate strings effectively.


# Operators

Operators are special symbols used to perform operations on operands, which can be values or variables. In JavaScript, there are three main types of operators:

## 1. Arithmetic Operators
Arithmetic operators are used to perform mathematical operations. Some common arithmetic operators include:

| Operator | Description     |
|----------|-----------------|
| `+`      | Addition        |
| `-`      | Subtraction     |
| `*`      | Multiplication  |
| `/`      | Division        |
| `%`      | Modulus (Remainder) |

These operators allow you to perform basic mathematical calculations in JavaScript.

## 2. Comparison Operators
Comparison operators are used to compare values and determine the relationship between them. Common comparison operators include:

| Operator | Description            |
|----------|------------------------|
| `<`      | Less than              |
| `>`      | Greater than           |
| `<=`     | Less than or equal to  |
| `>=`     | Greater than or equal to|

These operators return a boolean value (`true` or `false`) based on the comparison result.

## 3. Equality Operators
Equality operators are used to compare values for equality. There are two types of equality operators:

| Operator | Description                                     |
|----------|-------------------------------------------------|
| `==`     | Equality (equal without considering data types, performs type coercion if necessary) |
| `===`    | Strict Equality (equal with consideration of both values and data types)           |
| `!=`     | Inequality (not equal without considering data types)                               |
| `!==`    | Strict Inequality (not equal with consideration of both values and data types)      |

These operators allow you to compare values for equality or inequality, with or without considering their data types.

By using these operators, you can perform various operations and comparisons in JavaScript.
