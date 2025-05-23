# Closures and Lexical Scope in JavaScript

## 1. Lexical Scope ✏️📚

**Definition:** Lexical scope (also known as static scope) refers to the fact that the accessibility of variables is determined by the physical placement of the code (i.e., where variables and blocks of code are written). ✍️

In JavaScript, the scope is defined at the time of writing the code, not at the time of execution. Functions are lexically scoped, meaning they remember the scope in which they were defined. 🧾

### Example:

```js
function outer() {
  const outerVar = "I am from outer";

  function inner() {
    console.log(outerVar); // Has access to outerVar due to lexical scoping
  }

  inner();
}

outer(); // Output: I am from outer
```

In this example, `inner()` can access `outerVar` because it is defined inside the `outer()` function, and JavaScript uses lexical scoping to determine that relationship. 🧠🪄📘

---

## 2. Closures 🧰🔐

**Definition:** A closure is a function that remembers its lexical scope even when the function is executed outside that lexical scope.

In simpler terms, a closure allows a function to access variables from an enclosing scope even after that outer function has finished executing.

### Example 1: Basic Closure

```js
function makeCounter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}

const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

Here, the anonymous function returned by `makeCounter` is a closure. It retains access to the `count` variable, even though `makeCounter` has finished execution.

### Example 2: Closure with Parameters

```js
function greet(name) {
  return function (message) {
    return `${message}, ${name}`;
  };
}

const greetJohn = greet("John");
console.log(greetJohn("Hello")); // Hello, John
console.log(greetJohn("Welcome")); // Welcome, John
```

### Example 3: Common Pitfall with `var`

```js
function createFunctions() {
  let funcs = [];

  for (var i = 0; i < 3; i++) {
    funcs.push(function () {
      console.log(i);
    });
  }

  return funcs;
}

const functions = createFunctions();
functions[0](); // 3
functions[1](); // 3
functions[2](); // 3
```

**Explanation:**

- `var` has function scope, not block scope.
- All functions in the array share the same `i`, which ends up being 3 after the loop.

**Solution using `let`:**

```js
function createFunctions() {
  let funcs = [];

  for (let i = 0; i < 3; i++) {
    funcs.push(function () {
      console.log(i);
    });
  }

  return funcs;
}

const functions = createFunctions();
functions[0](); // 0
functions[1](); // 1
functions[2](); // 2
```

---

## 3. Uses of Closures

- **Data encapsulation:** Keep variables private.
- **Function factories:** Create specialized versions of functions.
- **Memoization:** Cache results of function calls.
- **Event handlers and callbacks:** Maintain state across invocations.

### Example: Data Encapsulation

```js
function createPerson(name) {
  let age = 0;

  return {
    getName: () => name,
    getAge: () => age,
    incrementAge: () => age++,
  };
}

const person = createPerson("Alice");
console.log(person.getName()); // Alice
console.log(person.getAge()); // 0
person.incrementAge();
console.log(person.getAge()); // 1
```

Here, `age` is private to `createPerson` and is only accessible through the closure methods.

---

## 4. Visualizing Lexical Scope and Closure 🧭🔍

```
Global Scope
└── outer()
    └── inner()
        └── Has access to outer's scope via closure
```

JavaScript functions "remember" where they were created, not where they were called.

---

## 5. Summary 📝

- **Lexical Scope** is about where variables are accessible based on where code is written.
- **Closure** is a function bundled with its lexical environment.
- Closures are fundamental to many JavaScript patterns, including callbacks, factories, and private state.

---

## 6. Additional Resources 🌐📖

- [MDN Web Docs - Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
- [JavaScript.info - Closures](https://javascript.info/closure)
- [You Don't Know JS (Book)](https://github.com/getify/You-Dont-Know-JS)
