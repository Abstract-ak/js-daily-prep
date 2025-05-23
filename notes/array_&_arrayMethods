      # Arrays and Array Methods in JavaScript

## Arrays Overview

Arrays in JavaScript are ordered collections of values. Each value (called an element) has a numeric position (index) starting from 0.

```javascript
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // "apple"
```

---

## Basic Array Methods

### `push()`

Adds one or more elements to the end of an array and returns the new length.

```javascript
let arr = [1, 2];
arr.push(3); // [1, 2, 3]
```

### `pop()`

Removes the last element from an array and returns it.

```javascript
let arr = [1, 2, 3];
arr.pop(); // returns 3, array becomes [1, 2]
```

### `shift()`

Removes the first element and shifts all other elements to a lower index.

```javascript
let arr = [1, 2, 3];
arr.shift(); // returns 1, array becomes [2, 3]
```

### `unshift()`

Adds one or more elements to the beginning of an array.

```javascript
let arr = [2, 3];
arr.unshift(1); // returns new length (3), array becomes [1, 2, 3]
```

---

## Higher-Order Array Methods

### `map()`

Returns a new array with the results of calling a function on every element.

```javascript
let nums = [1, 2, 3];
let doubled = nums.map((x) => x * 2); // [2, 4, 6]
```

### `filter()`

Returns a new array with elements that pass a condition.

```javascript
let nums = [1, 2, 3, 4];
let evens = nums.filter((x) => x % 2 === 0); // [2, 4]
```

### `reduce()`

Reduces the array to a single value.

```javascript
let nums = [1, 2, 3, 4];
let sum = nums.reduce((acc, val) => acc + val, 0); // 10
```

### `find()`

Returns the first element that satisfies the condition.

```javascript
let nums = [1, 2, 3, 4];
let firstEven = nums.find((x) => x % 2 === 0); // 2
```

### `forEach()`

Executes a function for each element. Does not return a new array.

```javascript
let nums = [1, 2, 3];
nums.forEach((x) => console.log(x));
```

### `some()`

Returns `true` if at least one element satisfies the condition.

```javascript
let nums = [1, 2, 3];
let hasEven = nums.some((x) => x % 2 === 0); // true
```

### `every()`

Returns `true` if all elements satisfy the condition.

```javascript
let nums = [2, 4, 6];
let allEven = nums.every((x) => x % 2 === 0); // true
```

### `includes()`

Checks if an array contains a certain value.

```javascript
let fruits = ["apple", "banana"];
fruits.includes("banana"); // true
```

### `indexOf()`

Returns the first index of the value, or -1 if not found.

```javascript
let colors = ["red", "blue", "green"];
colors.indexOf("blue"); // 1
```

### `lastIndexOf()`

Returns the last index of the value, or -1 if not found.

```javascript
let nums = [1, 2, 3, 2];
nums.lastIndexOf(2); // 3
```

### `sort()`

Sorts the array in place. Can take a compare function.

```javascript
let nums = [3, 1, 4, 2];
nums.sort((a, b) => a - b); // [1, 2, 3, 4]
```

### `reverse()`

Reverses the array in place.

```javascript
let nums = [1, 2, 3];
nums.reverse(); // [3, 2, 1]
```

### `slice()`

Returns a shallow copy of a portion of an array.

```javascript
let arr = [1, 2, 3, 4];
arr.slice(1, 3); // [2, 3]
```

### `splice()`

Adds/removes items to/from an array at a specific index.

```javascript
let arr = [1, 2, 3];
arr.splice(1, 1, 9); // removes 1 item at index 1, inserts 9 => [1, 9, 3]
```

---

## Spread Operator & Destructuring

### Spread Operator (`...`)

Used to copy or merge arrays.

```javascript
let arr1 = [1, 2];
let arr2 = [...arr1, 3]; // [1, 2, 3]
```

### Array Destructuring

Extracts values from arrays into distinct variables.

```javascript
let [a, b] = [1, 2];
console.log(a); // 1
```

---

## Looping Through Arrays

### Using `for` loop

```javascript
let arr = ["a", "b", "c"];
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
```

### Using `for...of`

```javascript
for (let item of arr) {
  console.log(item);
}
```

### Using `forEach()`

```javascript
arr.forEach((item) => console.log(item));
```

### Using `map()` for side effects (not recommended)

```javascript
arr.map((item) => console.log(item)); // returns new array of undefined
```

---

## Summary

- Use `push`, `pop`, `shift`, `unshift` for basic array manipulations.
- Use `map`, `filter`, `reduce` for transformation and computation.
- Use `find`, `some`, `every`, `includes` for searching and condition checks.
- Use `indexOf`, `lastIndexOf`, `slice`, `splice` for index-based operations.
- Use `sort`, `reverse` for reordering arrays.
- Spread operator (`...`) is great for copying or merging arrays.
- Destructuring simplifies extraction of elements.
- Prefer `for...of` or `forEach` for clean iteration.
