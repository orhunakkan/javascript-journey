# Values and Variables

## Introduction to Values and Variables
In this section, we begin to learn the JavaScript language, starting with **values** and **variables**.  
We will use persons as examples, such as a person's name, age, or job.

---

## Understanding Values
A **value** is a piece of data — the most fundamental unit of information in programming.  

Examples:  
- `"Jonas"` (text value)  
- `23` (number value)  
- Mathematical operations create new values:  
```

40 + 8 + 23 - 10 = 61

````

### Code Samples
```javascript
console.log("Jonas");
console.log(23);
console.log(40 + 8 + 23 - 10);
````

---

## Storing Values in Variables

We can **store values in variables** to reuse them.

```javascript
let firstName = "Jonas";
```

This is called **declaring a variable**.
It creates a memory location in the computer and stores the value.

Example:

```javascript
let JS = "amazing";
```

Variables are like boxes:

* The **box** is the variable
* The **label** is the variable name
* The **content** is the value stored

```javascript
console.log(firstName);

firstName = "Matilda"; // Value changed
```

---

## Variable Naming Conventions and Rules

### Camel Case

The standard naming style in JavaScript is **camelCase**:

```javascript
let firstNamePerson;
```

Other style (less common in JavaScript):

```javascript
let first_name;
```

---

### Rules for Variable Names

* Cannot start with a number:

```javascript
let 3years = 3; // ❌ Error
```

* Can only contain **letters, numbers, underscores (\_), or \$**:

```javascript
let jonas_and_matilda = "JM";
```

* Cannot use reserved keywords:

```javascript
let new = 27;       // ❌ Error
let function = 1;   // ❌ Error
```

✅ Fix → Start with `_` or `$`:

```javascript
let _function = 1;
let $function = 1;
```

* `name` is technically allowed but not recommended:

```javascript
let name = "Jonas";
```

---

### More Naming Conventions

* Do not start with uppercase (reserved for specific use cases):

```javascript
let Person = "Jonas"; // Not recommended
```

* Use **UPPERCASE** for constants that never change:

```javascript
const PI = 3.1415;
```

---

## Descriptive Variable Names

Descriptive names improve readability:

```javascript
let myFirstJob = "programmer";
let myCurrentJob = "teacher";
```

❌ Poor practice:

```javascript
let job1 = "programmer";
let job2 = "teacher";
```

---

## Recap: What is a Variable?

A **variable** is like a box where you store a value.
Use the **variable name** to retrieve or change the value later.

```javascript
console.log(myFirstJob);

myFirstJob = "coder"; // Updates value everywhere
```

Output: `"coder"`

---

## Key Takeaways

* **Values** → The smallest units of information in programming.
* **Variables** → Boxes that store values for reuse.
* Follow **camelCase** naming convention and avoid reserved keywords.
* Use **descriptive variable names** for clarity and maintainability.

```
```
