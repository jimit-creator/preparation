
# ES6 Interview Question

#### =============

**What is ES6? and Explain some key features.**

ES6 (ECMAScript 2015) is the 6th version of the ECMAScript language specification, officially released in June 2015. It brought major improvements to JavaScript, making it more powerful, readable, and developer-friendly. It's often referred to as "Modern JavaScript."

**Key Concepts Introduced in ES6:**
- ```let``` and ```const```
- Arrow Functions
- Template Literals
- Destructuring
- Default Parameters
- Rest and Spread Operators ```(...)```
- Modules (```import/export```)
- Classes
- Promises
- Map and Set

#### =============

**What are let, const, and var? How do they differ?**

- var is function-scoped, while let and const are block-scoped.

- let can be reassigned; const cannot.

- var allows hoisting (initialized as undefined), but let and const do not.

#### =============

**What is destructuring in ES6?**

Destructuring allows unpacking values from arrays or properties from objects into variables.

#### =============

**What are template literals?**

Template literals allow embedded expressions using backticks ``` ` ```.

**Example:**
```
const name = "John";
const greeting = `Hello, ${name}!`;
console.log(greeting); // Hello, John!

```

#### =============

**What is the difference between == and === in JavaScript?**

== checks for value equality (type coercion).

=== checks for both value and type equality (strict).

**Example:**
```
console.log(5 == '5');  // true
console.log(5 === '5'); // false
``` 

#### =============

**What is the spread operator (...) and rest parameter?**

**Spread operator** expands elements.

**Rest parameter** collects remaining elements.

#### =============

**What is a Promise in ES6?**

A Promise represents the eventual result of an asynchronous operation.

#### =============

**What are default parameters in ES6?**

Default parameters allow you to set default values for function parameters.


#### =============

**What are ```Map``` and ```Set``` in ES6?**

- Map is a key-value collection where keys can be any type.

- Set stores unique values of any type.

**Example:**
```
// Map
const map = new Map();
map.set("name", "Alice");
console.log(map.get("name")); // Alice

// Set
const set = new Set([1, 2, 2, 3]);
console.log(set); // Set { 1, 2, 3 }
``` 

#### =============

**What is object shorthand and method shorthand syntax in ES6?**

ES6 allows shorthand for object properties and methods.

**Example:**
```
const name = "Bob";
const user = {
  name, // same as name: name
  greet() { // same as greet: function() {...}
    return `Hi, I'm ${this.name}`;
  }
};
console.log(user.greet()); // Hi, I'm Bob
``` 

#### =============

**What is the difference between for...of and for...in in ES6?**

- ```for...of``` iterates over iterable objects like arrays.

- ```for...in``` iterates over enumerable properties of an object.

**Example:**
```
const arr = ["a", "b"];
for (let val of arr) console.log(val); // a b

const obj = { x: 1, y: 2 };
for (let key in obj) console.log(key); // x y
``` 

#### =============

**What is the difference between shallow copy and deep copy in ES6?**

- A **shallow copy** copies only the first level of properties.

- A **deep copy** recursively copies all nested levels.

#### =============

**What is the purpose of ```Object.entries()```, ```Object.values()```, and ```Object.keys()```?**

These methods return:

- ``Object.entries()`` → array of key-value pairs.
- ```Object.values()``` → array of values.
- ```Object.keys()``` → array of keys.

#### =============

**What is the difference between Array.from() and Array.of()?**

- ```Array.from()``` converts iterable or array-like objects to arrays.

- ```Array.of()``` creates a new array with arguments.

**Example:**
```
console.log(Array.from("foo")); // ['f', 'o', 'o']
console.log(Array.of(1, 2, 3)); // [1, 2, 3]
```


#### =============

**What is the purpose of Object.freeze() in ES6?**

Object.freeze() prevents objects from being modified (no addition, deletion, or change)

**Example:**
```
const obj = Object.freeze({ a: 1 });
obj.a = 2; // Fails silently in non-strict mode
console.log(obj.a); // 1
```
