
# Inheritance Between "Classes": Constructor Functions

## Introduction to Inheritance Between "Classes"

Over the last couple of lectures, we explored how prototypal inheritance works in JavaScript. We did that using a couple of different techniques: constructor functions, ES6 classes, and Object.create. All of these techniques allow objects to inherit methods from their prototype and delegate their behavior to their prototype.

## Real Inheritance Between Classes

Now, it is time to turn our attention to more real inheritance, as learned in the very first lecture of the section. This refers to real inheritance between classes, not just prototypal inheritance between instances and a prototype property. The use of class terminology here is simply for easier understanding, even though real classes do not exist in JavaScript.

## Creating Student and Person Classes

We will create a new Student class and make it inherit from the Person class that we have been using so far. Person will be the parent class and Student will be the child class, as Student is a subtype of Person. This setup allows us to have specific methods for Student, while Student can also use generic Person methods, such as the `calcAge` method.

## Implementing Inheritance Using Constructor Functions

We will start by implementing inheritance between classes using constructor functions. This approach will help you understand how to set up the prototype chain to allow inheritance between the prototype properties of two different constructor functions.

### Person Constructor Function

```js
// Person constructor function
function Person(firstName, birthYear) {
  this.firstName = firstName;
  this.birthYear = birthYear;
}

// Adding calcAge method to Person's prototype
Person.prototype.calcAge = function() {
  console.log(2037 - this.birthYear);
};
```

## Building the Student Constructor Function

Usually, we want a child class to have the same functionality as the parent class, but with some additional functionality. Therefore, we pass in the same arguments as the parent, plus some additional ones. For Student, we will use firstName, birthYear, and an additional course property.

### Student Constructor Function

```js
// Student constructor function
function Student(firstName, birthYear, course) {
  // Call the Person constructor function
  Person.call(this, firstName, birthYear);
  this.course = course;
}
```

## Creating a Student Instance

Let us create a new Student instance named Mike, born in 2020 and studying Computer Science.

```js
const mike = new Student('Mike', 2020, 'Computer Science');
console.log(mike);
```

## Adding Methods to Student's Prototype

We can add methods to the Student's prototype property. For example, let us add an `introduce` method for the Student to introduce themselves.

```js
Student.prototype.introduce = function() {
  console.log(`My name is ${this.firstName} and I study ${this.course}`);
};

mike.introduce();
```

## Avoiding Duplicate Code and Using `call`

Currently, part of the Student constructor function is a simple copy of the Person constructor function. Having duplicate code is not ideal as it violates the "Don't Repeat Yourself" principle and can lead to inconsistencies if the parent implementation changes. Instead, we call the Person function using `call` to set the `this` keyword correctly.

## Linking Prototypes for Inheritance

To allow Student instances to access methods from Person's prototype, we need to link the prototypes. We want `Person.prototype` to be the prototype of `Student.prototype`. This is done using `Object.create`.

```js
Student.prototype = Object.create(Person.prototype);
```

### Order of Linking Prototypes and Adding Methods

It is important to link the prototypes before adding any new methods to the Student's prototype. This is because `Object.create` returns an empty object, so methods should be added after this step to avoid overwriting them.

### Why Not Assign Prototypes Directly?

Assigning `Student.prototype = Person.prototype` would make both prototypes the exact same object, which is not desired. We want Student to inherit from Person, not to share the same prototype object.

## Inheriting Methods Through the Prototype Chain

With the prototype chain set up, we can now call methods like `calcAge` on the Student instance, and JavaScript will look up the prototype chain to find the method in Person's prototype.

```js
mike.calcAge(); // Outputs: 17
```

## Inspecting the Prototype Chain

When accessing a method not found on the object or its immediate prototype, JavaScript continues searching up the prototype chain. For example, `calcAge` is found in `Person.prototype`, which is linked to `Student.prototype`.

## Completing the Prototype Chain

`Object.prototype` sits at the top of the prototype chain. Methods like `hasOwnProperty` can still be called on Student instances, regardless of how far away they are in the prototype chain.

## Fixing the Constructor Property

After linking the prototypes, the `constructor` property of `Student.prototype` points to `Person`. To fix this, we manually set it back to `Student`.

```js
Student.prototype.constructor = Student;
```

## Using the `instanceof` Operator

We can use the `instanceof` operator to check if an object is an instance of a particular constructor. After setting up the prototype chain, `mike instanceof Student` and `mike instanceof Person` both return true.

```js
console.log(mike instanceof Student); // true
console.log(mike instanceof Person); // true
console.log(mike instanceof Object); // true
```

---

## Conclusion

This concludes the demonstration of how inheritance between classes works with function constructors in JavaScript. Internally, ES6 classes work the same way, with only the syntax differing. The prototype chain allows child classes to inherit methods from parent classes, and understanding how to manipulate the prototype chain manually consolidates your knowledge about prototypes in JavaScript.

## Key Takeaways

- **Prototypal inheritance** in JavaScript can be implemented using constructor functions, ES6 classes, and Object.create.
- **Inheritance between classes** allows child classes to access methods from parent classes via the prototype chain.
- The **prototype chain** must be set up correctly using Object.create to ensure proper inheritance and avoid duplicate code.
- The **constructor property** should be manually reset after linking prototypes to maintain accurate type information.