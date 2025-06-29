# **🔥 JavaScript Number Methods & Properties**  

JavaScript provides **built-in methods and properties** to manipulate and format numbers efficiently. Let’s explore the most important ones with examples. 🚀  

---

## **1️⃣ JavaScript Number Properties**
JavaScript has several useful **number properties**.

| Property | Description | Example |
|----------|------------|---------|
| `Number.MAX_VALUE` | Largest possible number in JavaScript | `1.7976931348623157e+308` |
| `Number.MIN_VALUE` | Smallest positive number | `5e-324` |
| `Number.POSITIVE_INFINITY` | Represents Infinity | `Infinity` |
| `Number.NEGATIVE_INFINITY` | Represents -Infinity | `-Infinity` |
| `Number.NaN` | Represents "Not a Number" | `NaN` |

### **Example:**
```javascript
console.log(Number.MAX_VALUE);  // ✅ 1.7976931348623157e+308
console.log(Number.MIN_VALUE);  // ✅ 5e-324
console.log(Number.POSITIVE_INFINITY); // ✅ Infinity
console.log(Number.NEGATIVE_INFINITY); // ✅ -Infinity
console.log(Number.NaN); // ✅ NaN
```

✔ **Infinity results from dividing by `0`**:  
```javascript
console.log(10 / 0); // ✅ Infinity
console.log(-10 / 0); // ✅ -Infinity
```

---

## **2️⃣ Converting Strings to Numbers**
| Method | Description | Example |
|--------|------------|---------|
| **`Number(value)`** | Converts a string to a number | `Number("123") // 123` |
| **`parseInt(value)`** | Converts a string to an integer | `parseInt("100.99") // 100` |
| **`parseFloat(value)`** | Converts a string to a float | `parseFloat("100.99") // 100.99` |

### **Example:**
```javascript
console.log(Number("123"));  // ✅ 123
console.log(Number("123abc")); // ✅ NaN (invalid number)
console.log(parseInt("100.99")); // ✅ 100 (integer only)
console.log(parseFloat("100.99")); // ✅ 100.99
```

✔ **Use `Number()` for strict conversions and `parseInt()/parseFloat()` for flexible parsing.**

---

## **3️⃣ Checking If a Value is a Number**
| Method | Description | Example |
|--------|------------|---------|
| **`isNaN(value)`** | Checks if value is **NaN** | `isNaN("hello") // true` |
| **`isFinite(value)`** | Checks if value is a **finite number** | `isFinite(100) // true` |
| **`Number.isInteger(value)`** | Checks if value is an **integer** | `Number.isInteger(10.5) // false` |

### **Example:**
```javascript
console.log(isNaN("hello")); // ✅ true (Not a number)
console.log(isNaN(100)); // ✅ false (Valid number)

console.log(isFinite(100)); // ✅ true
console.log(isFinite(Infinity)); // ✅ false

console.log(Number.isInteger(10)); // ✅ true
console.log(Number.isInteger(10.5)); // ✅ false
```

✔ **Use `isFinite()` to validate if a value is a proper number.**  

---

## **4️⃣ Formatting Numbers**
| Method | Description | Example |
|--------|------------|---------|
| **`toFixed(digits)`** | Rounds a number to `digits` decimal places | `(123.456).toFixed(2) // "123.46"` |
| **`toPrecision(digits)`** | Formats a number to `digits` significant figures | `(123.456).toPrecision(4) // "123.5"` |
| **`toExponential(digits)`** | Converts to scientific notation | `(123.456).toExponential(2) // "1.23e+2"` |
| **`toString(radix)`** | Converts number to a string in `radix` (base) | `(255).toString(16) // "ff"` |

### **Example:**
```javascript
let num = 123.456;

console.log(num.toFixed(2)); // ✅ "123.46" (Rounded to 2 decimal places)
console.log(num.toPrecision(4)); // ✅ "123.5" (4 significant figures)
console.log(num.toExponential(2)); // ✅ "1.23e+2" (Scientific notation)
console.log((255).toString(16)); // ✅ "ff" (Hexadecimal)
console.log((10).toString(2)); // ✅ "1010" (Binary)
```

✔ **Use `toFixed()` for currency formatting and `toString()` for number system conversions.**  

---

## **5️⃣ Generating Random Numbers (`Math.random()`)**
| Method | Description | Example |
|--------|------------|---------|
| **`Math.random()`** | Generates a random number between `0` and `1` | `Math.random()` |
| **`Math.floor(Math.random() * max)`** | Generates a random number between `0` and `max-1` | `Math.floor(Math.random() * 10)` |

### **Example:**
```javascript
console.log(Math.random()); // ✅ Random number between 0 and 1
console.log(Math.floor(Math.random() * 10)); // ✅ Random number between 0 and 9
console.log(Math.floor(Math.random() * 100) + 1); // ✅ Random number between 1 and 100
```

✔ **Use `Math.random()` with `Math.floor()` to get a range of random numbers.**  

---

## **6️⃣ Rounding Numbers (`Math` Methods)**
| Method | Description | Example |
|--------|------------|---------|
| **`Math.round(value)`** | Rounds to nearest integer | `Math.round(4.5) // 5` |
| **`Math.floor(value)`** | Rounds **down** | `Math.floor(4.9) // 4` |
| **`Math.ceil(value)`** | Rounds **up** | `Math.ceil(4.1) // 5` |
| **`Math.trunc(value)`** | Removes decimal part | `Math.trunc(4.9) // 4` |

### **Example:**
```javascript
console.log(Math.round(4.5)); // ✅ 5
console.log(Math.floor(4.9)); // ✅ 4
console.log(Math.ceil(4.1)); // ✅ 5
console.log(Math.trunc(4.9)); // ✅ 4
```

✔ **Use `Math.floor()` for flooring, `Math.ceil()` for ceiling, and `Math.round()` for normal rounding.**  

---

## **7️⃣ Math Constants & More Math Methods**
| Constant | Description | Example |
|----------|------------|---------|
| **`Math.PI`** | Returns `π` | `Math.PI // 3.141592653589793` |
| **`Math.E`** | Euler’s number | `Math.E // 2.718` |

| Method | Description | Example |
|--------|------------|---------|
| **`Math.abs(x)`** | Absolute value | `Math.abs(-10) // 10` |
| **`Math.pow(x, y)`** | Exponentiation (`x^y`) | `Math.pow(2, 3) // 8` |
| **`Math.sqrt(x)`** | Square root | `Math.sqrt(25) // 5` |
| **`Math.cbrt(x)`** | Cube root | `Math.cbrt(27) // 3` |

```javascript
console.log(Math.PI); // ✅ 3.141592653589793
console.log(Math.sqrt(16)); // ✅ 4
console.log(Math.pow(2, 3)); // ✅ 8
console.log(Math.abs(-10)); // ✅ 10
console.log(Math.cbrt(27)); // ✅ 3
```

✔ **Use `Math.pow()` or `**` for exponentiation:**
```javascript
console.log(2 ** 3); // ✅ 8 (ES6 Exponentiation Operator)
```

---

## **🚀 Summary of JavaScript Number Methods**
| Method | Purpose |
|--------|---------|
| `Number()`, `parseInt()`, `parseFloat()` | Convert strings to numbers |
| `isNaN()`, `isFinite()`, `Number.isInteger()` | Check number types |
| `toFixed()`, `toPrecision()`, `toExponential()` | Format numbers |
| `Math.random()` | Generate random numbers |
| `Math.round()`, `Math.floor()`, `Math.ceil()` | Round numbers |
| `Math.pow()`, `Math.sqrt()`, `Math.abs()` | Perform calculations |

---

## **🚀 What’s Next?**
Would you like **hands-on exercises**, real-world **examples**, or a deep dive into a specific topic? Let me know! 😊🔥