# 📅 Day 2 - JavaScript Interview Preparation

## ✅ Topics Covered

- Functions in JavaScript
- Function Expressions vs Declarations
- Scope (Global, Local, Block)
- Hoisting

---

## Functions in JavaScript

A **function** is a reusable block of code designed to perform a particular task. In JavaScript, functions are first-class objects — they can be stored in variables, passed as arguments, and returned from other functions.

### Function Syntax

```js
function greet(name) {
  return `Hello, ${name}!`;
}
```

### Key Properties

- **Name** (optional in expressions)
- **Parameters**: Inputs passed into a function
- **Return value**: Value sent back using `return`
- **Scope**: Functions create their own scope

---

## Function Declarations vs Function Expressions

### Function Declaration

```js
function add(a, b) {
  return a + b;
}
```

- Hoisted to the top of the scope.
- Can be invoked before they appear in the code.

### Function Expression

```js
const add = function (a, b) {
  return a + b;
};
```

- Not hoisted (only the variable is hoisted, not the function body).
- Must be defined before use.

### Named vs Anonymous

```js
// Anonymous
const greet = function (name) {
  return `Hi, ${name}`;
};

// Named
const greet = function greetFunction(name) {
  return `Hi, ${name}`;
};
```

### Arrow Functions (ES6+)

```js
const square = (x) => x * x;
```

- No `this`, `arguments`, `super`, or `new.target`
- Best suited for non-method functions

---

## Scope in JavaScript

Scope determines the visibility and lifetime of variables.

### 1. Global Scope

Declared outside any function or block.

```js
var globalVar = "I am global";
```

Accessible anywhere in the code.

### 2. Local/Function Scope

Declared within a function.

```js
function test() {
  var localVar = "I am local";
}
```

Accessible only inside the function.

### 3. Block Scope (let and const)

Introduced with ES6 (`let`, `const`). Blocks (`{}`) define the scope.

```js
if (true) {
  let blockScoped = "Only here";
  const alsoBlockScoped = "Still here";
}
```

`var` does not respect block scope — it is function-scoped.

### Lexical Scope

Inner functions have access to variables of outer functions.

```js
function outer() {
  let x = 10;
  function inner() {
    console.log(x); // Accessible
  }
  inner();
}
```

---

## Hoisting in JavaScript

**Hoisting** is JavaScript's default behavior of moving declarations to the top of the current scope.

### Variable Hoisting

```js
console.log(a); // undefined
var a = 5;
```

- `var` declarations are hoisted with `undefined`.
- `let` and `const` are hoisted but **not initialized**. Accessing them before declaration causes a **ReferenceError**.

### Function Hoisting

- Function declarations are hoisted fully:

```js
greet(); // Works
function greet() {
  console.log("Hello");
}
```

- Function expressions are not hoisted:

```js
greet(); // TypeError: greet is not a function
var greet = function () {
  console.log("Hi");
};
```

### Temporal Dead Zone (TDZ)

The phase between entering scope and variable declaration where `let`/`const` exist but are not accessible.

```js
console.log(x); // ReferenceError
let x = 10;
```

---

## Summary Table

| Concept                | `var`           | `let` / `const` | Function Declarations | Function Expressions   |
| ---------------------- | --------------- | --------------- | --------------------- | ---------------------- |
| Hoisting               | Yes (undefined) | Yes (in TDZ)    | Yes                   | Variable only          |
| Scope                  | Function        | Block           | Function              | Depends (block/global) |
| Redeclaration          | Allowed         | Not allowed     | N/A                   | Allowed                |
| Before Declaration Use | `undefined`     | ReferenceError  | Allowed               | TypeError              |

---

## Best Practices

- Use `let` and `const` over `var` to avoid hoisting pitfalls.
- Prefer function declarations for reusable named functions.
- Use arrow functions for short, non-method callbacks.
- Understand lexical scope for closures and callbacks.
- Avoid relying on hoisting; always declare variables and functions at the top of their scope.
