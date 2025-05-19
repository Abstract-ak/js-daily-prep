# 🧠 JavaScript Quiz – Day 2

Today's quiz focuses on **functions, scope, and hoisting**.

---

## ✅ Quiz Questions

### 1. What is the output?

```js
greet();
function greet() {
  console.log("Hello!");
}
```

<details>
  <summary>💡 Answer</summary>
  Output: `"Hello!"`  
  Reason: Function declarations are hoisted.
</details>

---

### 2. What is the output?

```js
sayHi();
var sayHi = function () {
  console.log("Hi!");
};
```

<details>
  <summary>💡 Answer</summary>
  Output: `TypeError: sayHi is not a function`  
  Reason: `sayHi` is hoisted as `undefined`.
</details>

---

### 3. What type of scope is this?

```js
{
  let name = "Akash";
}
console.log(name);
```

<details>
  <summary>💡 Answer</summary>
  ❌ ReferenceError  
  Reason: `name` is block-scoped.
</details>

---

### 4. What is hoisting?

<details>
  <summary>💡 Answer</summary>
  Hoisting is JavaScript's behavior of moving **declarations** to the top of their scope **before code execution**.
</details>

---

### 5. What happens here?

```js
console.log(a);
let a = 10;
```

<details>
  <summary>💡 Answer</summary>
  ❌ ReferenceError: Cannot access 'a' before initialization  
  Reason: `let` is hoisted but remains in the temporal dead zone.
</details>

---

### 6. Which one is **function-scoped**?

- [x] `var`
- [ ] `let`
- [ ] `const`

---

### 7. What will be logged?

```js
function test() {
  var x = 5;
}
console.log(x);
```

<details>
  <summary>💡 Answer</summary>
  ❌ ReferenceError: `x` is not defined  
  Reason: `x` is scoped inside the function.
</details>

---

### 8. True or False: Function expressions are hoisted.

<details>
  <summary>💡 Answer</summary>
  ❌ False  
  Only function declarations are hoisted, not expressions.
</details>

---

## 🧠 Notes & Review

- Always declare variables at the top of their scope.
- Prefer `let`/`const` to avoid hoisting bugs.
- Understand difference between **declaration hoisting** and **assignment execution**.

---
