# JavaScript Data Types and Dynamic Typing

## Introduction to Data Types in JavaScript
In the previous lecture, we discussed values and variables.  
In every programming language, values can have different types depending on the kind of data they hold.  

JavaScript values are either:
- **Objects**  
- **Primitives**

---

## Primitive Data Types
There are **seven primitive data types** in JavaScript:

1. **number**
2. **string**
3. **boolean**
4. **undefined**
5. **null**
6. **symbol**
7. **BigInt**

---

### Number Data Type
All numbers in JavaScript are **floating-point numbers** (even if decimals are not visible).

```javascript
let age = 23; // same as 23.0
````

---

### String Data Type

Strings are **sequences of characters** enclosed in quotes (`""` or `''`).

```javascript
let firstName = 'Jonas';
```

---

### Boolean Data Type

Booleans represent logical values: `true` or `false`.

```javascript
let isJavaScriptFun = true;
console.log(isJavaScriptFun);
```

---

### Undefined and Null

* **undefined** → Value of a variable that is declared but not assigned.
* **null** → Represents an empty value (used in specific situations).

```javascript
let year;
console.log(year);        // undefined
console.log(typeof year); // "undefined"

year = 1991;
console.log(typeof year); // "number"
```

---

### Symbol and BigInt

* **symbol** → Introduced in ES2015; represents a **unique** value.
* **BigInt** → Introduced in ES2020; represents integers too large for the number type.

---

## Dynamic Typing in JavaScript

JavaScript uses **dynamic typing**:

* You do not need to define variable types explicitly.
* Types are determined **by the value**, not the variable.
* A variable can hold values of different types at different times.

```javascript
let isJavaScriptFun = true;
console.log(typeof isJavaScriptFun); // boolean

isJavaScriptFun = 'YES!';
console.log(typeof isJavaScriptFun); // string
```

---

## Comments in JavaScript

Used for documentation or deactivating code.

**Single-line:**

```javascript
// This is a single line comment
```

**Multi-line:**

```javascript
/*
This is a multi-line comment.
It can span multiple lines.
*/
```

---

## Examples of Data Types

```javascript
let age = 23;                // number
let firstName = 'Jonas';     // string
let isJavaScriptFun = true;  // boolean

console.log(typeof age);         // "number"
console.log(typeof firstName);   // "string"
console.log(typeof isJavaScriptFun); // "boolean"
```

---

## The typeof Operator

The `typeof` operator checks the type of a value:

```javascript
console.log(typeof true);        // "boolean"
console.log(typeof 23);          // "number"
console.log(typeof 'Jonas');     // "string"
```

⚠️ Bug:

```javascript
console.log(typeof null); // "object" (this is a long-standing bug)
```

---

## Dynamic Typing in Action

Reassigning values of different types to the same variable:

```javascript
let isJavaScriptFun = true;
console.log(typeof isJavaScriptFun); // "boolean"

isJavaScriptFun = 'YES!';
console.log(typeof isJavaScriptFun); // "string"
```

---

## Key Takeaways

* JavaScript has **7 primitive types**: `number`, `string`, `boolean`, `undefined`, `null`, `symbol`, `BigInt`.
* JavaScript uses **dynamic typing**: variable types can change at runtime.
* The `typeof` operator checks the type of a value.
  ⚠️ Known bug: `typeof null` returns `"object"`.
* Use comments (`//` or `/* ... */`) to explain or deactivate code.
