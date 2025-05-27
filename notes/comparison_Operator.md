# JavaScript: Comparison Operators

## 1. Equality Operators 🆚🎯

### `==` (Loose Equality)

- Compares two values for equality, **after type coercion**.
- Coerces types before comparing.

```javascript
console.log(5 == "5"); // true
console.log(null == undefined); // true
```

### `===` (Strict Equality)

- Compares both value and type. **No type coercion.**

```javascript
console.log(5 === "5"); // false
console.log(5 === 5); // true
```

### `!=` and `!==`

- `!=` is the loose inequality (with coercion).
- `!==` is the strict inequality (no coercion).

```javascript
console.log(5 != "5"); // false
console.log(5 !== "5"); // true
```

## 2. Relational Operators 📈📉🧮

### `>`, `<`, `>=`, `<=`

- Work for numbers and strings
- Strings are compared lexicographically

```javascript
console.log(10 > 5); // true
console.log("b" > "a"); // true
console.log("abc" < "b"); // true
```

## 3. Object and Reference Comparison 🧱🔗🧭

- Objects are compared by reference, **not by value**.

```javascript
let obj1 = { name: "Akash" };
let obj2 = { name: "Akash" };
console.log(obj1 === obj2); // false
let obj3 = obj1;
console.log(obj1 === obj3); // true
```

## 4. Special Cases 🎭⚙️🧐

### Comparing `null` and `undefined`

```javascript
console.log(null == undefined); // true
console.log(null === undefined); // false
```

### Comparing `NaN`

```javascript
console.log(NaN === NaN); // false
console.log(Number.isNaN(NaN)); // true
```

### Boolean Conversion in Comparisons

```javascript
console.log(false == 0); // true
console.log("" == 0); // true
console.log(false === 0); // false
```

Sure! Here's a concise markdown note about the nullish coalescing operator (`??`).

---

### 📝 Nullish Coalescing Operator (`??`)

The **nullish coalescing operator** (`??`) is a logical operator that returns the right-hand side operand only if the left-hand side operand is `null` or `undefined`.

```js
const result = left ?? right;
```

- If `left` is **not** `null` or `undefined`, `result` is `left`.
- If `left` is `null` or `undefined`, `result` is `right`.

---

#### ✅ Example:

```js
const name = null ?? "Anonymous"; // 'Anonymous'
const username = undefined ?? "Guest"; // 'Guest'
const age = 0 ?? 18; // 0 (because 0 is not null/undefined)
const emptyString = "" ?? "Default"; // '' (because '' is not null/undefined)
```

---

#### 🔎 Difference from `||` (Logical OR):

- `||` returns the right-hand side operand if the left-hand side is **falsy** (0, '', false, NaN, null, undefined).
- `??` only checks for `null` or `undefined`.

```js
const a = 0 || 5; // 5 (0 is falsy)
const b = 0 ?? 5; // 0 (0 is not null/undefined)
```

---

#### 📌 Use Cases:

- Setting default values only when the variable is `null` or `undefined`.
- Avoiding defaulting when the value could be 0, false, or an empty string.

---

## Summary Table 📊

| Expression          | ==    | ===   |
| ------------------- | ----- | ----- |
| `5 == '5'`          | true  | false |
| `0 == false`        | true  | false |
| `null == undefined` | true  | false |
| `{}` == `{}`        | false | false |
| `[] == false`       | true  | false |

Always prefer `===` and `!==` to avoid unexpected type coercion unless you explicitly want coercion.

---
