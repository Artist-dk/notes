
# Variables in JavaScript

This document covers all essential aspects of variables in JavaScript, providing a comprehensive guide for understanding their behavior, usage, and best practices.

---

## **1. What Are Variables?**
Variables are containers for storing data values. They are named identifiers that can hold various types of data and allow the manipulation of that data.

---

## **2. Declaring Variables**
### Keywords:
- `var`: Function-scoped (old way of declaring variables).
- `let`: Block-scoped (preferred for mutable variables).
- `const`: Block-scoped and read-only (immutable after initialization).

#### Syntax:
```javascript
var variableName = value;
let variableName = value;
const variableName = value;
```

---

## **3. Naming Rules for Variables**
- Can include letters, numbers, `$`, and `_`.
- Cannot start with a number.
- Case-sensitive (`myVar` and `MyVar` are different).
- Reserved keywords (e.g., `class`, `let`) cannot be used as variable names.

#### Examples:
```javascript
let _myVariable = "valid";
let $dollarSign = 100;
// let 123abc = "invalid"; // Error: Cannot start with a number
```

---

## **4. Variable Initialization**
### With a Value:
```javascript
let initialized = 42; // A variable is declared and assigned a value.
```

### Without a Value:
Variables declared without initialization have the value `undefined`:
```javascript
let uninitialized;
console.log(uninitialized); // Output: undefined
```

---

## **5. Scope of Variables**
### Function Scope (`var`):
Variables declared with `var` are function-scoped:
```javascript
function example() {
    var x = 10;
    console.log(x); // Output: 10
}
// console.log(x); // Error: x is not defined
```

### Block Scope (`let` and `const`):
Variables declared with `let` or `const` are block-scoped:
```javascript
if (true) {
    let y = 20;
    const z = 30;
    console.log(y, z); // Output: 20 30
}
// console.log(y, z); // Error: y and z are not defined
```

---

## **6. Hoisting**
- **`var`** variables are hoisted (declared but not initialized) to the top of their scope.
- **`let` and `const`** are hoisted but placed in a "temporal dead zone" (TDZ) until their declaration.

#### Example:
```javascript
console.log(a); // Output: undefined (hoisted, not initialized)
var a = 5;

// console.log(b); // Error: Cannot access 'b' before initialization
let b = 10;
```

---

## **7. Mutable and Immutable Variables**
- Variables declared with `var` and `let` can be reassigned.
- `const` variables cannot be reassigned.

#### Example:
```javascript
let x = 5;
x = 10; // Reassignment is allowed

const y = 15;
// y = 20; // Error: Assignment to constant variable
```

---

## **8. Dynamic Typing**
JavaScript is dynamically typed, meaning variables can hold values of different types at different times:
```javascript
let data = "hello"; // String
data = 42;          // Number
data = true;        // Boolean
```

---

## **9. Variable Types**
### Primitive Data Types:
- `String`
- `Number`
- `Boolean`
- `null`
- `undefined`
- `Symbol` (ES6)
- `BigInt` (ES2020)

### Reference Types:
- `Object`
- `Array`
- `Function`

#### Examples:
```javascript
let str = "Hello";      // String
let num = 42;           // Number
let flag = true;        // Boolean
let nothing = null;     // Null
let notDefined;         // Undefined
let id = Symbol("id");  // Symbol
let largeNumber = 123n; // BigInt

let obj = { key: "value" }; // Object
let arr = [1, 2, 3];        // Array
function greet() {          // Function
    return "Hi!";
}
```

---

## **10. Constant Variables with Objects and Arrays**
While `const` prevents reassignment, it doesn’t make objects or arrays immutable. Their properties or elements can still be changed.

#### Example:
```javascript
const person = { name: "Alice" };
person.age = 30; // Allowed
console.log(person); // Output: { name: "Alice", age: 30 }
```

---

## **11. Template Literals**
Variables can be interpolated into strings using backticks `` ` ``:
```javascript
let firstName = "John";
let greeting = `Hello, ${firstName}!`;
console.log(greeting); // Output: Hello, John!
```

---

## **12. Default Values**
Variables can have default values using logical operators:
```javascript
let user;
console.log(user || "Guest"); // Output: Guest
```

---

## **13. Global Variables**
Variables declared without `var`, `let`, or `const` become global:
```javascript
function example() {
    globalVar = 100; // Automatically global (bad practice)
}
example();
console.log(globalVar); // Output: 100
```

---

## **14. Best Practices**
1. Use `const` by default; use `let` when reassignment is needed.
2. Avoid using `var`.
3. Use meaningful variable names.
4. Declare variables at the top of their scope.
5. Avoid polluting the global scope.

---

