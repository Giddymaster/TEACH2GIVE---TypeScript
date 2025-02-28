# Introduction to TypeScript

TypeScript is a statically typed language developed and maintained by Microsoft. It is a superset of JavaScript, meaning it includes all JavaScript features while adding extra functionalities. One key benefit of TypeScript is its ability to catch errors at compile time. The typical workflow involves writing TypeScript code, compiling it into JavaScript, and detecting type errors during compilation.

## Dynamic vs. Static Typing

Programming languages can be either dynamically or statically typed.TypeScript enforces static typing, reducing runtime errors and improving code reliability.

- **Dynamically typed languages** determine variable types at runtime, allowing type changes without explicit declarations. Examples include JavaScript, PHP, and Python.

  ```js
  let x = 5; // x is a number
  x = "Hello"; // x is now a string (no error)
  console.log(x); // Output: Hello

- **Statically  typed languages**  require variable types to be declared explicitly or inferred, with type checks occurring at compile time. Examples include TypeScript, Java, and C++.

```ts
let x: number = 5; // x is explicitly declared as a number
x = "Hello"; // Error: Type 'string' is not assignable to type 'number'
```

## JavaScript vs. TypeScript

Here are some key differences between JavaScript and TypeScript:

- **Typing:**  

  JavaScript is dynamically typed, whereas TypeScript is statically typed with optional dynamic typing.

- **Error Detection:**  
  JavaScript detects errors at runtime, while TypeScript detects errors at compile time, reducing potential bugs in production.

- **Tooling:**  
  JavaScript has basic support for code completion and debugging, while TypeScript offers enhanced IDE support with autocompletion, type-checking, and better refactoring tools.

- **Compilation:**  
  JavaScript runs directly in the browser without requiring compilation, whereas TypeScript must be compiled into JavaScript before execution.
