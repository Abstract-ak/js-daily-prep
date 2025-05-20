# JavaScript: Comparison Operators 

## 1. Equality Operators 🆚🎯

### `==` (Loose Equality)

* Compares two values for equality, **after type coercion**.
* Coerces types before comparing. 

```javascript
console.log(5 == '5'); // true
console.log(null == undefined); // true
```

### `===` (Strict Equality)

* Compares both value and type. **No type coercion.** 

```javascript
console.log(5 === '5'); // false
console.log(5 === 5);   // true
```

### `!=` and `!==`

* `!=` is the loose inequality (with coercion).
* `!==` is the strict inequality (no coercion). 

```javascript
console.log(5 != '5');   // false
console.log(5 !== '5');  // true
```

## 2. Relational Operators 📈📉🧮

### `>`, `<`, `>=`, `<=`

* Work for numbers and strings
* Strings are compared lexicographically 

```javascript
console.log(10 > 5);      // true
console.log('b' > 'a');   // true
console.log('abc' < 'b'); // true
```

## 3. Object and Reference Comparison 🧱🔗🧭

* Objects are compared by reference, **not by value**. 

```javascript
let obj1 = { name: 'Akash' };
let obj2 = { name: 'Akash' };
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
console.log('' == 0);    // true
console.log(false === 0); // false
```

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