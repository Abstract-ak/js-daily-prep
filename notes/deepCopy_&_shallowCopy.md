# Shallow Copy and Deep Copy in JavaScript

## 📌 What is a Copy?

In JavaScript, when you assign an object or an array to a new variable, it **does not** create a new copy of that object/array. Instead, it **copies the reference**. This means any changes to the new variable will also reflect in the original object.

Example:

```javascript
const original = { name: "John" };
const copy = original;

copy.name = "Doe";
console.log(original.name); // "Doe" (reference copied!)
```

````

To avoid this, we create copies:

- **Shallow Copy**: Copies top-level properties only.
- **Deep Copy**: Recursively copies all nested objects and arrays.

---

## 🟩 Shallow Copy

A **shallow copy** creates a new object, but nested objects/arrays are still **referenced** from the original.

### How to Create a Shallow Copy?

#### 1️⃣ Using `Object.assign()`

```javascript
const original = { name: "John", address: { city: "NY" } };
const shallow = Object.assign({}, original);

shallow.name = "Doe";
shallow.address.city = "LA";

console.log(original.name); // "John" (copied)
console.log(original.address.city); // "LA" (reference)
```

#### 2️⃣ Using Spread Operator (`...`)

```javascript
const original = { name: "John", address: { city: "NY" } };
const shallow = { ...original };

shallow.address.city = "LA";
console.log(original.address.city); // "LA"
```

#### 3️⃣ For Arrays: Using `slice()` or `concat()`

```javascript
const original = [1, 2, [3, 4]];
const shallow = original.slice();

shallow[2][0] = 99;
console.log(original[2][0]); // 99
```

---

## 🟩 Deep Copy

A **deep copy** creates a new object **recursively**, including all nested objects/arrays.

### How to Create a Deep Copy?

#### 1️⃣ Using JSON Methods

```javascript
const original = { name: "John", address: { city: "NY" } };
const deep = JSON.parse(JSON.stringify(original));

deep.address.city = "LA";
console.log(original.address.city); // "NY"
```

⚠️ **Limitations**:

- Cannot copy functions, `undefined`, `Symbol`, or special objects (like `Date`, `Map`, `Set`).
- Circular references will cause errors.

#### 2️⃣ Using StructuredClone (modern JS)

```javascript
const original = { name: "John", address: { city: "NY" } };
const deep = structuredClone(original);

deep.address.city = "LA";
console.log(original.address.city); // "NY"
```

#### 3️⃣ Using Recursion or Libraries (like lodash’s `cloneDeep`)

Example of recursive deep copy:

```javascript
function deepClone(obj) {
  if (obj === null || typeof obj !== "object") return obj;

  if (Array.isArray(obj)) {
    return obj.map(deepClone);
  }

  const clonedObj = {};
  for (let key in obj) {
    clonedObj[key] = deepClone(obj[key]);
  }
  return clonedObj;
}

const original = { name: "John", address: { city: "NY" } };
const deep = deepClone(original);

deep.address.city = "LA";
console.log(original.address.city); // "NY"
```

---

## 🔍 Use Cases

| Copy Type    | Use When                                             |
| ------------ | ---------------------------------------------------- |
| Shallow Copy | Simple structures without nested references          |
| Deep Copy    | Nested objects/arrays, avoid unintended side-effects |

---

## ⚠️ Common Pitfalls

- Using shallow copy on nested objects can lead to bugs due to shared references.
- JSON methods cannot handle circular references and special object types.
- For **robust** deep copies (including `Date`, `Map`, `Set`), use `structuredClone` or third-party libraries.

---

## 💡 Summary

✅ **Shallow Copy**: Top-level only, nested structures shared
✅ **Deep Copy**: Entire structure copied recursively
✅ Use the **right tool** for your structure to avoid bugs!
````
