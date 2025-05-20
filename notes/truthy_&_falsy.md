# JavaScript: Truthy and Falsy Values

## Truthy Values 💡✅

In JavaScript, a value is *truthy* if it evaluates to `true` when used in a Boolean context (such as an `if` condition). 

### Examples of Truthy Values:

* Non-empty strings: `'hello'`, `'false'`
* Non-zero numbers: `1`, `-1`, `3.14`
* Objects: `{}`, `{ key: 'value' }`
* Arrays: `[]`, `[1, 2, 3]`
* Functions: `function() {}`
* The Boolean `true`
* Any value that is not falsy

```javascript
if ('JavaScript') {
  console.log('This is truthy'); // This will be logged
}
```

## Falsy Values 🚫❌

A value is *falsy* if it evaluates to `false` when used in a Boolean context. There are only **seven** falsy values in JavaScript: 

### List of Falsy Values:

1. `false` — Boolean false
2. `0` — Number zero
3. `-0` — Negative zero
4. `0n` — BigInt zero
5. `""` — Empty string
6. `null`
7. `undefined`
8. `NaN` — Not a Number

```javascript
if (0) {
  console.log('This will not run');
} else {
  console.log('0 is falsy'); // This will be logged
}
```

---



# Advanced Questions 🧠💻❓

## Q1: What is the result of comparing an empty array with `false` and why? 🧮🔍🤔

```javascript
console.log([] == false);  // true
console.log([] === false); // false
```

### Explanation:

* `[] == false` → JS coerces both operands:

  * `[]` becomes `''` → then `0`
  * `false` becomes `0`
  * Result: `0 == 0` → `true`
* `[] === false` → Strict comparison: different types → `false`

## Q2: What will be the result of the following expression and why? 🧪🔎🧩

```javascript
console.log([] + []);          // ""
console.log([] + {});          // "[object Object]"
console.log({} + []);          // 0 (in certain contexts)
```

### Explanation:

* `[] + []` → both are coerced to empty strings → result is `""`
* `[] + {}` → `[]` becomes `""`, `{}` becomes `"[object Object]"` → result: `"[object Object]"`
* `{}` + `[]` → if interpreted as block + expression, it becomes `+[]` which is `0`

## Q3: Does `false == null` return `true` or `false`? ❓👀📘

```javascript
console.log(false == null); // false
```

### Explanation:

* `null` only loosely equals `undefined`
* `false` is not loosely equal to `null`
* Result is `false`
