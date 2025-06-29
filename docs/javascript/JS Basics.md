## **🔥 JavaScript Basics: A Beginner’s Guide**  

JavaScript is a powerful, **dynamic** programming language that is widely used for web development. Let’s cover the **fundamentals** step by step with **examples**.

---

## **1️⃣ JavaScript Variables (`var`, `let`, `const`)**  
Variables store data values and can be declared using **`var`**, **`let`**, or **`const`**.

### **Example:**
```javascript
var name = "Alice"; // Old way (avoid using var)
let age = 25;       // Preferred for changing values
const PI = 3.1416;  // Constant (cannot be changed)

age = 26;  // ✅ Allowed (let allows reassignment)
PI = 3.14; // ❌ Error (const cannot be changed)
```
✔ **Use `let` for variable values that change**  
✔ **Use `const` for values that should not change**  

---

## **2️⃣ Data Types in JavaScript**
JavaScript has **two types** of data:  
🔹 **Primitive Types** (Immutable): `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`  
🔹 **Non-Primitive (Reference) Types**: `object`, `array`, `function`  

### **Example:**
```javascript
let str = "Hello";      // String
let num = 42;           // Number
let isCool = true;      // Boolean
let empty = null;       // Null
let notDefined;         // Undefined
let bigNumber = 12345678901234567890n; // BigInt
let id = Symbol("id");  // Symbol (unique)

let person = { name: "John", age: 30 }; // Object
let colors = ["red", "blue", "green"];  // Array
let greet = function() { return "Hi!"; }; // Function
```

---

## **3️⃣ Operators in JavaScript**
Operators perform operations on variables.

### **Example:**
```javascript
// Arithmetic Operators
let a = 10, b = 5;
console.log(a + b);  // ✅ 15 (Addition)
console.log(a - b);  // ✅ 5  (Subtraction)
console.log(a * b);  // ✅ 50 (Multiplication)
console.log(a / b);  // ✅ 2  (Division)
console.log(a % b);  // ✅ 0  (Modulus)

// Comparison Operators
console.log(a > b);   // ✅ true
console.log(a < b);   // ❌ false
console.log(a == 10); // ✅ true (loose equality)
console.log(a === "10"); // ❌ false (strict equality)
console.log(a !== b); // ✅ true

// Logical Operators
console.log(true && false); // ❌ false (AND)
console.log(true || false); // ✅ true (OR)
console.log(!true);         // ❌ false (NOT)
```
✔ **Use `===` instead of `==` to avoid type coercion.**  

---

## **4️⃣ Conditional Statements (`if`, `else`, `switch`)**
Used to make decisions.

### **Example (`if-else`):**
```javascript
let age = 18;
if (age >= 18) {
    console.log("You are an adult!");
} else {
    console.log("You are a minor.");
}
```

### **Example (`switch-case`):**
```javascript
let day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of the week!");
        break;
    case "Friday":
        console.log("Weekend is near!");
        break;
    default:
        console.log("It's a regular day.");
}
```

---

## **5️⃣ Loops (`for`, `while`, `do-while`)**
Loops help in **repeating** tasks.

### **Example (`for` loop):**
```javascript
for (let i = 1; i <= 5; i++) {
    console.log("Iteration:", i);
}
```

### **Example (`while` loop):**
```javascript
let i = 1;
while (i <= 5) {
    console.log("While Loop:", i);
    i++;
}
```

### **Example (`do-while` loop):**
```javascript
let j = 1;
do {
    console.log("Do-While Loop:", j);
    j++;
} while (j <= 5);
```

---

## **6️⃣ Functions in JavaScript**
Functions are **reusable** blocks of code.

### **Example (Regular Function):**
```javascript
function greet(name) {
    return "Hello, " + name + "!";
}

console.log(greet("Alice")); // ✅ "Hello, Alice!"
```

### **Example (Arrow Function - ES6)**
```javascript
const add = (a, b) => a + b;
console.log(add(5, 3)); // ✅ 8
```

✔ **Arrow functions are shorter and don’t have their own `this` context.**

---

## **7️⃣ Arrays in JavaScript**
Arrays store multiple values.

### **Example:**
```javascript
let fruits = ["Apple", "Banana", "Cherry"];

console.log(fruits[0]); // ✅ "Apple" (Accessing first element)
fruits.push("Mango");   // ✅ Add new item
console.log(fruits.length); // ✅ 4 (Array size)
```

✔ **Common Array Methods:**  
```javascript
fruits.pop();      // Remove last item
fruits.shift();    // Remove first item
fruits.unshift("Grapes"); // Add to beginning
fruits.splice(1, 1); // Remove specific index
console.log(fruits);
```

---

## **8️⃣ Objects in JavaScript**
Objects store data in **key-value pairs**.

### **Example:**
```javascript
let person = {
    name: "Alice",
    age: 25,
    greet: function() {
        return "Hello, " + this.name;
    }
};

console.log(person.name); // ✅ "Alice"
console.log(person.greet()); // ✅ "Hello, Alice"
```

✔ **Accessing Object Properties:**  
```javascript
console.log(person["age"]); // ✅ 25
person.city = "New York"; // ✅ Add new property
delete person.age; // ✅ Remove property
```

---

## **9️⃣ Asynchronous JavaScript (`setTimeout`, `setInterval`)**
JavaScript is **single-threaded**, but we can handle tasks asynchronously.

### **Example (`setTimeout` - Delays execution):**
```javascript
setTimeout(() => {
    console.log("Executed after 2 seconds!");
}, 2000);
```

### **Example (`setInterval` - Repeats execution):**
```javascript
let count = 0;
let interval = setInterval(() => {
    count++;
    console.log("Count:", count);
    if (count === 5) clearInterval(interval); // Stop after 5 times
}, 1000);
```

---

## **🔟 JavaScript `DOM` (Document Object Model)**
JavaScript can **interact with web pages** using the DOM.

### **Example (Changing HTML Content & Style)**
```javascript
document.getElementById("demo").innerHTML = "Hello, JavaScript!";
document.getElementById("demo").style.color = "red";
```

### **Example (Handling Events)**
```javascript
document.getElementById("btn").addEventListener("click", function() {
    alert("Button Clicked!");
});
```

---

## **🚀 Summary of JavaScript Basics**
| Concept | Description |
|---------|------------|
| **Variables (`let`, `const`)** | Store data values |
| **Data Types** | `string`, `number`, `boolean`, `object`, etc. |
| **Operators** | Arithmetic, comparison, logical |
| **Conditional Statements** | `if-else`, `switch` |
| **Loops** | `for`, `while`, `do-while` |
| **Functions** | `function`, arrow functions |
| **Arrays** | Collection of elements (`push()`, `pop()`, etc.) |
| **Objects** | Key-value pairs, methods |
| **Async (`setTimeout`, `setInterval`)** | Delayed and repeated execution |
| **DOM Manipulation** | Interact with HTML & CSS |

---

## **✨ What’s Next?**
Would you like **real-world examples** or **hands-on exercises**? Let me know what you want to explore next! 🚀😊