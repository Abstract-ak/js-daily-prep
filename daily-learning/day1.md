# 📅 Day 1 - JavaScript Interview Preparation

## ✅ Topics Covered

- JavaScript Variables: `var`, `let`, `const`
- Data Types (Primitive & Reference)
- Type Coercion
- Basic Console Logging

---

## JavaScript Variables: `var`, `let`, and `const`

Variables are containers for storing data values. In JavaScript, we use `var`, `let`, and `const` to declare variables.

### 1. `var`

- **Function scoped** – available within the function where it's declared.

- **Hoisted** – gets hoisted to the top of its scope and initialized as `undefined`.

- Can be **re-declared** and **updated**.

### 📌 Example:

```js
console.log(a); // undefined (due to hoisting)
var a = 10;

function example() {
  var x = 20;
  if (true) {
    var x = 30; // same variable as above
    console.log(x); // 30
  }
  console.log(x); // 30
}
```

## 2. `let`

- **Block scoped** – available only within `{ }` where it's defined.
- **Hoisted** but **not initialized** – accessing it before declaration throws `ReferenceError`.
- Can be **updated** but **not re-declared** in the same scope.

### 📌 Example:

```js
let a = 10;
a = 20; // ✅
let b = 30;
// let b = 40; ❌ SyntaxError

if (true) {
  let a = 50;
  console.log(a); // 50 (block scope)
}
console.log(a); // 20
```

## 3. `const`

- Also **block scoped**.
- Must be **initialized** at the time of declaration.
- Cannot be **re-assigned** or **re-declared**.

### 📌 Example:

```js
const a = 10;
// a = 20; ❌ TypeError

const obj = { name: "John" };
obj.name = "Doe"; // ✅ allowed (mutation allowed)
```

## 🔸 Data Types in JavaScript

JavaScript has **two categories** of data types:

### 1. **Primitive Types** (stored by value)

| Type        | Example         | Description                        |
| ----------- | --------------- | ---------------------------------- |
| `String`    | `"hello"`       | Text data                          |
| `Number`    | `42`, `3.14`    | Integer and floating-point numbers |
| `Boolean`   | `true`, `false` | Logical values                     |
| `Null`      | `null`          | Explicit absence of value          |
| `Undefined` | `undefined`     | Unassigned variable                |
| `Symbol`    | `Symbol("id")`  | Unique identifiers                 |
| `BigInt`    | `123n`          | Large integers                     |

```js
let str = "Hello";
let num = 42;
let isTrue = true;
let empty = null;
let notDefined;
let uniqueId = Symbol("id");
let bigNum = 123456789012345678901234567890n;
```

### 2. **Reference Types** (stored by reference)

| Type     | Example           | Description            |
| -------- | ----------------- | ---------------------- |
| Object   | `{name: "Alice"}` | Key-value pairs        |
| Array    | `[1, 2, 3]`       | List-like object       |
| Function | `function() {}`   | Reusable block of code |
| Date     | `new Date()`      | Date and time object   |
| RegExp   | `/ab+c/`          | Regular expressions    |

```js
let obj = { name: "Bob" };
let arr = [1, 2, 3];
let greet = function () {
  return "Hello";
};
```

---

## 🔸 Type Coercion

**Type coercion** is the process of converting a value from one type to another (e.g., string to number).

### 1. **Implicit Coercion**

Automatically performed by JavaScript.

```js
console.log("5" + 2); // "52"  (number 2 coerced to string)
console.log("5" - 2); // 3     (string '5' coerced to number)
console.log(true + 1); // 2     (true → 1)
console.log(false + "2"); // "false2" (boolean → string)
```

### 2. **Explicit Coercion**

Manually performed using functions.

```js
Number("42"); // 42
String(42); // "42"
Boolean(1); // true

parseInt("100px"); // 100
parseFloat("3.14"); // 3.14
```

### Comparison with Coercion

```js
console.log(0 == false); // true (type coercion)
console.log(0 === false); // false (strict equality)

console.log(null == undefined); // true
console.log(null === undefined); // false
```

---

## 🔸 Console Logging

The `console` object provides access to the browser’s debugging console.

### 1. `console.log()`

- Prints a message to the console.

```js
console.log("Hello World");
```

### 2. `console.error()`

- Outputs an error message.

```js
console.error("Something went wrong!");
```

### 3. `console.warn()`

- Outputs a warning message.

```js
console.warn("This is a warning.");
```

### 4. `console.table()`

- Displays tabular data.

```js
console.table([
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 },
]);
```

### 5. `console.time()` & `console.timeEnd()`

- Measures time taken for a block of code.

```js
console.time("loop");
for (let i = 0; i < 100000; i++) {}
console.timeEnd("loop"); // e.g., loop: 3.5ms
```

### 6. `console.assert()`

- Logs a message only if the assertion fails.

```js
console.assert(2 + 2 === 5, "Math is broken!");
```

### ✅ Summary Table

| Feature        | `var`                  | `let`                 | `const`               |
| -------------- | ---------------------- | --------------------- | --------------------- |
| Scope          | Function               | Block                 | Block                 |
| Hoisting       | Yes (init = undefined) | Yes (not initialized) | Yes (not initialized) |
| Re-declaration | Yes                    | No                    | No                    |
| Re-assignment  | Yes                    | Yes                   | No                    |

| Type    | Category  | Mutable | Stored By |
| ------- | --------- | ------- | --------- |
| String  | Primitive | No      | Value     |
| Object  | Reference | Yes     | Reference |
| Array   | Reference | Yes     | Reference |
| Boolean | Primitive | No      | Value     |

---

Use `let` and `const` in modern JavaScript. Prefer `const` unless reassignment is necessary.
