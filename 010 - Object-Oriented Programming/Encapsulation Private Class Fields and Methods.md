## Encapsulation: Private Class Fields and Methods

### Introduction to Encapsulation

In the previous lecture, a new class was implemented, demonstrating the need for encapsulation and data privacy. This lecture addresses the important principle of encapsulation in object-oriented programming.

Encapsulation means keeping certain properties and methods private inside a class so that they are not accessible from outside. Only some methods are exposed as a public interface (API) — the methods other developers are allowed to use from outside the class. This concept, also called data privacy, is essential for any application beyond a simple toy example.

There are two main reasons for encapsulation and data privacy:

- To prevent code outside a class from accidentally manipulating internal data.
- To expose only a small API so internal methods can be changed confidently without breaking external code.

### Implementing Encapsulation in JavaScript

Encapsulation in JavaScript classes is implemented using private fields and private methods. These are part of the class fields feature, introduced in ES2022, several years after classes were first introduced in ES6.

In traditional object-oriented languages, what JavaScript calls properties are usually called fields. With the class fields feature, JavaScript classes now have abilities that were not previously available, such as hiding properties or methods from outside the class. Private class fields enable this, pushing JavaScript further towards a class-based pattern, even though it is fundamentally a prototype-based language.

### Types of Class Fields and Methods

The class fields feature includes:

- Public fields
- Private fields
- Public methods
- Private methods

There are also static versions of these four, but they are less important and not discussed in detail here.

#### Public Fields

A field can be thought of as a property present on all class instances — a public instance field. Fields are not inherited like methods (which are added to the prototype). Instead, fields act like properties added directly in the constructor, but now they can be declared outside the constructor as public or private fields.

For example, a locale field that should be present on all class instances can be declared as a public field. This is done outside the constructor, before the constructor function, using the field name and value:

```javascript
locale = navigator.language;
```

Another example is the name of the bank, which can also be a public field on all instances:

```javascript
bank = 'Bankist';
```

Declaring fields in this way makes the class more self-documenting. These fields are present on every instance but not on the prototype.

#### Private Fields

Private fields are similar to public fields but cannot be accessed from outside the class. This is useful for protecting critical data from interference. For example, the movements array should be protected from external manipulation.

```javascript
#movements = [];
```

The hash symbol (`#`) is used to declare a private field. This field can only be accessed inside the class. Attempting to access or modify it from outside will result in an error or will create a new public property with a similar name while leaving the actual private field protected.

Another example is making the pin private. Since it depends on input data, the private field is declared first, and its value is assigned in the constructor:

```javascript
#pin;
// ...
constructor(owner, currency, pin) {
  // ...
  this.#pin = pin;
}
```

#### Public Methods

Public methods are the methods that have been used so far, such as `deposit` or `withdraw`. These methods are part of the public interface (API) and allow other developers to interact with the class.

A new method, `getMovements`, can be created to allow users to read the movements array through the public API:

```javascript
getMovements() {
  return this.#movements;
}
```

#### Private Methods

Private methods are similar to private fields and are declared with the hash symbol. For example, an `approveLoan` method can be made private, as it is intended for internal use only and should not be exposed through the public API:

```javascript
#approveLoan(val) {
  return true;
}
```

Attempting to call a private method from outside the class will result in an error. Private methods are only accessible within the class, ensuring that internal logic is not exposed.

### Static Fields and Methods

There are also static versions of public and private fields and methods. Static fields and methods are not accessible on instances but only on the class itself. For example, a static `test` method can be declared as follows:

```javascript
static test() {
  return true;
}
```

Static fields and methods are used directly on the class, not on instances created from the class. Making a static method private restricts its use to within the class only.

### Conclusion

This lecture covered public fields, private fields, public methods, and private methods in JavaScript classes. Static versions of these are also available but are less commonly used. With these features, encapsulation and data privacy can be effectively implemented in JavaScript classes.

### Key Takeaways

- Encapsulation in JavaScript is achieved through private class fields and methods, ensuring data privacy.
- Public and private fields and methods are part of the class fields feature introduced in ES2022.
- Private fields and methods are inaccessible from outside the class, protecting sensitive data.
- Static versions of fields and methods exist but are less commonly used and only accessible on the class itself.