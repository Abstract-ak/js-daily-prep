# JavaScript Data Types: Primitive vs Reference

In JavaScript, data types are divided into two main categories: 📂📝

- **Primitive Data Types**
- **Reference (Non-Primitive) Data Types**

Understanding the difference between these two categories is fundamental to mastering JavaScript behavior, especially in memory management, equality comparison, and mutation.

---

## 1. Primitive Data Types 🧮🔢

Primitive data types are **immutable** and **stored by value**. This means that when you assign or copy a primitive value, a new copy is created.

### Types of Primitive Data Types:

1. **Number**

   - Represents both integer and floating-point numbers.
   - Example:

     ```js
     let age = 25;
     let price = 99.99;
     ```

2. **String**

   - Represents a sequence of characters.
   - Example:

     ```js
     let name = "Akash";
     ```

3. **Boolean**

   - Represents a logical value: `true` or `false`.
   - Example:

     ```js
     let isActive = true;
     ```

4. **Undefined**

   - A variable that has been declared but not assigned a value.
   - Example:

     ```js
     let score;
     console.log(score); // undefined
     ```

5. **Null**

   - Represents the intentional absence of any value.
   - Example:

     ```js
     let user = null;
     ```

6. **Symbol (ES6)**

   - Used to create unique identifiers for object properties.
   - Example:

     ```js
     const id = Symbol("id");
     ```

7. **BigInt (ES2020)**

   - Used to represent integers of arbitrary length.
   - Example:

     ```js
     const bigNumber = 1234567890123456789012345678901234567890n;
     ```

### Characteristics of Primitive Types: ⚙️📌🧩

- Stored directly in the **stack**.
- Compared by **value**.
- Immutable: You cannot change the value directly.

### Example:

```js
let a = 10;
let b = a;
b = 20;
console.log(a); // 10 (remains unchanged)
```

---

## 2. Reference Data Types 🗂️🏷️

Reference types are **mutable** and **stored by reference**. When you assign or copy a reference type, you're copying the reference (address), not the actual value.

### Types of Reference Data Types:

1. **Object**

   - A collection of key-value pairs.
   - Example:

     ```js
     const person = { name: "Akash", age: 25 };
     ```

2. **Array** (a type of object)

   - An ordered list of values.
   - Example:

     ```js
     const fruits = ["apple", "banana", "cherry"];
     ```

3. **Function** (a callable object)

   - Example:

     ```js
     function greet() {
       console.log("Hello");
     }
     ```

### Characteristics of Reference Types: 🔁🔍

- Stored in the **heap**, with a reference (address) on the **stack**.
- Compared by **reference**, not by value.
- Mutable: Changes made to one reference affect all references.

### Example:

```js
const obj1 = { name: "Akash" };
const obj2 = obj1;
obj2.name = "Rahul";
console.log(obj1.name); // "Rahul" (both point to the same object)
```

---

## 3. Key Differences 📝📚

| Feature          | Primitive                     | Reference                    |
| ---------------- | ----------------------------- | ---------------------------- |
| Stored in        | Stack                         | Heap (referenced from stack) |
| Comparison       | By value                      | By reference                 |
| Mutability       | Immutable                     | Mutable                      |
| Examples         | Number, String, Boolean, etc. | Object, Array, Function      |
| Copying behavior | Creates a new copy            | Copies the reference         |

---

## 4. Equality Comparison 🤝🆚

```js
// Primitive
let x = 5;
let y = 5;
console.log(x === y); // true (same value)

// Reference
let objA = { val: 10 };
let objB = { val: 10 };
console.log(objA === objB); // false (different references)

let objC = objA;
console.log(objA === objC); // true (same reference)
```

---

## 5. Copying Techniques ✂️📋

### For Primitive:

```js
let a = 10;
let b = a; // copy
```

### For Reference:

#### Shallow Copy 🧻📄🧷

A shallow copy creates a new object and copies over the values of all top-level properties from the original. However, if those properties are themselves reference types (like nested objects), only the reference is copied.

```js
const original = { name: "Akash", address: { city: "Delhi" } };
const copy = { ...original };
copy.address.city = "Mumbai";
console.log(original.address.city); // "Mumbai" (because address is a shared reference)
```

#### Deep Copy (using JSON) 🌊📦🧬

A deep copy recursively copies all nested objects and arrays, creating entirely new references. This means that changes to the copied object do not affect the original. However, this method only works if the object is JSON-serializable (no functions, `undefined`, or symbols). 🛠️

```js
const original = { name: "Akash", address: { city: "Delhi" } };
const deepCopy = JSON.parse(JSON.stringify(original));
deepCopy.address.city = "Mumbai";
console.log(original.address.city); // "Delhi" (no mutation)
```

> ✅ Use deep copy when you need complete separation between the original and the copied object.
> ⚠️ Be cautious of performance and limitations with JSON-based deep copies.

---

## Conclusion 🧾🔚

- Understanding the difference between primitive and reference types is critical for debugging and writing efficient code.
- Remember: primitives are copied **by value**, reference types are copied **by reference**.
- Always be cautious when copying or comparing reference types.
