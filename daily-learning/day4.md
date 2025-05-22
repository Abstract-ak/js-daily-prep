# 📅 Day 4 – JavaScript Prep

## ✅ Topics Covered

- JavaScript Objects
- Object Methods
- Optional Chaining (`?.`)
- Destructuring
- The `this` keyword (basics)

---

## 1. JavaScript Objects 🧱📦

### What is an Object?

In JavaScript, an object is a non-primitive data type that allows you to store collections of key-value pairs. 🔑🎠

### Object Syntax:

```js
const person = {
  name: "John",
  age: 30,
  isStudent: false,
};
```

### Key Characteristics:

- Keys are strings (or Symbols)
- Values can be any data type: string, number, boolean, array, function, another object, etc.

### Creating Objects:

- **Object Literals:**

  ```js
  const car = { brand: "Toyota", year: 2020 };
  ```

- **Constructor Function:**

  ```js
  function Person(name, age) {
    this.name = name;
    this.age = age;
  }
  const john = new Person("John", 30);
  ```

- **Object.create():**

  ```js
  const proto = {
    greet() {
      return "Hello!";
    },
  };
  const obj = Object.create(proto);
  ```

### Accessing Properties:

- Dot notation: `person.name`
- Bracket notation: `person["name"]`

### Modifying and Deleting Properties:

```js
person.age = 35;
delete person.isStudent;
```

---

## 2. Object Methods ⚙️

### Defining Methods:

```js
const person = {
  name: "Alice",
  greet() {
    return `Hi, I'm ${this.name}`;
  },
};
```

### `this` Keyword: 📍

- Refers to the object the method belongs to
- Context-aware, can change based on how the function is called

### Other Built-in Methods:

- `Object.keys(obj)` – Returns an array of keys
- `Object.values(obj)` – Returns an array of values
- `Object.entries(obj)` – Returns an array of \[key, value] pairs
- `Object.assign(target, source)` – Copies properties
- `Object.freeze(obj)` – Makes object immutable
- `Object.seal(obj)` – Prevents adding/removing properties but allows modifying existing ones

---

## 3. Optional Chaining (`?.`) 🪜❓

### Purpose:

Prevents runtime errors when trying to access nested properties of an object that might not exist.

### Syntax:

```js
const user = { profile: { name: "John" } };
console.log(user?.profile?.name); // John
console.log(user?.settings?.theme); // undefined
```

### Use Cases:

- Deeply nested object lookups
- API response handling
- Guarding against null or undefined values

---

## 4. Destructuring 🛠️

### Object Destructuring:

```js
const user = { name: "Jane", age: 25 };
const { name, age } = user;
```

### Renaming Variables:

```js
const { name: userName } = user;
```

### Default Values:

```js
const { city = "Unknown" } = user;
```

### Nested Destructuring:

```js
const person = { name: "Tom", address: { city: "NY", zip: 10001 } };
const {
  address: { city },
} = person;
```

---

## 5. The `this` Keyword (Basics)

### What is `this`?

`this` refers to the object from which a function is called. 🧭🔗📣

### In Different Contexts: 🌍🧩

- **Global Scope:**

  ```js
  console.log(this); // Window (browser) or global (Node.js)
  ```

- **Object Method:**

  ```js
  const obj = {
    name: "Alex",
    greet() {
      console.log(this.name); // "Alex"
    },
  };
  ```

- **Arrow Functions:**
  Arrow functions do not have their own `this`. They inherit it from the enclosing scope.

  ```js
  const obj = {
    name: "Sam",
    greet: () => console.log(this.name), // likely undefined
  };
  ```

- **Event Handlers / Callbacks:**
  You may need to bind `this` using `.bind(this)` or use arrow functions.

---
