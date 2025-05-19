# 📅 Day 1 - JavaScript Interview Preparation

## ✅ Topics Covered

- JavaScript Variables: `var`, `let`, `const`
- Data Types (Primitive & Reference)
- Type Coercion
- Basic Console Logging

---

<!-- ## 🧠 Key Learnings -->

## JavaScript Variables: `var`, `let`, and `const`

JavaScript provides three ways to declare variables: `var`, `let`, and `const`. Each has different **scoping**, **hoisting**, and **mutability** characteristics.

---

- `var` is function-scoped and can be hoisted.
- `let` and `const` are block-scoped.
- `const` variables can't be reassigned.

```js
var a = 5;
let b = 10;
const c = 15;

a = 6; // ✅
b = 20; // ✅
c = 25; // ❌ Error
```

## 1. `var`

### ✅ Characteristics:

- **Function-scoped**
- **Hoisted** to the top of its function scope and initialized with `undefined`
- Can be **re-declared** and **updated**

### 📌 Example:

```javascript
function example() {
  console.log(x); // undefined (due to hoisting)
  var x = 10;
  console.log(x); // 10
}
example();
```

### ⚠️ Caveats:

- Not block-scoped (can lead to bugs)
- Should generally be avoided in modern code

---

## 2. `let`

### ✅ Characteristics:

- **Block-scoped**
- **Hoisted**, but **not initialized**
- Cannot be **re-declared** in the same scope, but **can be updated**

### 📌 Example:

```javascript
function example() {
  // console.log(y); // ReferenceError: Cannot access 'y' before initialization
  let y = 20;
  y = 25; // valid
  console.log(y); // 25
}
example();
```

### ✅ Good for:

- Loops
- Re-assignable variables scoped to a block

---

## 3. `const`

### ✅ Characteristics:

- **Block-scoped**
- **Hoisted**, but **not initialized**
- Cannot be **re-declared** or **updated**

### 📌 Example:

```javascript
const z = 30;
// z = 40; // TypeError: Assignment to constant variable
console.log(z); // 30
```

### 🔍 Note:

- You **can mutate** objects/arrays declared with `const`:

```javascript
const obj = { name: "Akash" };
obj.name = "Changed"; // Allowed
console.log(obj.name); // "Changed"
```

---

## 🔁 Summary Table

| Feature       | `var`       | `let`             | `const`   |
| ------------- | ----------- | ----------------- | --------- |
| Scope         | Function    | Block             | Block     |
| Hoisting      | Yes         | Yes (TDZ)         | Yes (TDZ) |
| Re-declarable | Yes         | No                | No        |
| Re-assignable | Yes         | Yes               | No        |
| Best Use      | Legacy code | Reassignable vars | Constants |

---

Use `let` and `const` in modern JavaScript. Prefer `const` unless reassignment is necessary.
