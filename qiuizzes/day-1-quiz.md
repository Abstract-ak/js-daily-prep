# 🧠 JavaScript Quiz – Day 1

Welcome to Day 1 of your JavaScript prep journey!  
Today's quiz focuses on **variables, data types, and type coercion**.

---

## ✅ Quiz Questions

### 1. What will be the output of the following code?

```js
let a;
console.log(typeof a);
```

<details> <summary>💡 Answer</summary> Output: `"undefined"` Reason: A declared but uninitialized variable is `undefined`. </details>

### 2. What is the output of the following?

```js
let x = "5" + 3;
console.log(x);
```

<details> <summary>💡 Answer</summary> Output: `"53"` Reason: `+` with a string causes string concatenation. </details>

### 3. What will the following log?

```js
let x = "5" - 3;
console.log(x);
```

<details> <summary>💡 Answer</summary> Output: `2` Reason: `-` converts strings to numbers when possible. </details>

### 4. Is Javascript statically or dynamically typed?

<details> <summary>💡 Answer</summary> JavaScript is **dynamically typed** — variable types are determined at runtime. </details>

### 5. What does the following return?

```js
console.log(typeof null);
```

<details> <summary>💡 Answer</summary> Output: `"object"` Reason: This is a well-known quirk in JavaScript due to legacy design. </details>

### 6. Which of the following are primitive data types in JavaScript?

- [ ] Object
- [x] String
- [x] Number
- [ ] Array
- [x] Boolean
- [x] Null
- [x] Undefined

### 7. What error will this prouce?

```js
const a = 5;
a = 10;
```

<details> <summary>💡 Answer</summary> ❌ TypeError: Assignment to constant variable. `const` values can't be reassigned. </details>
