# **🔥 JavaScript String Methods & Properties**

JavaScript provides powerful **string methods** and **properties** to manipulate and process text efficiently. Let's explore **common string properties and methods** with **examples**. 🚀

---

## **1️⃣ JavaScript String Properties**
Properties provide information about a string.

| Property | Description | Example |
|-----------|------------|---------|
| **length** | Returns the length of a string | `"hello".length // 5` |

### **Example:**
```javascript
let text = "Hello, World!";
console.log(text.length); // ✅ Output: 13
```

---

## **2️⃣ Common JavaScript String Methods**
### **🔹 Changing Case (`toUpperCase()`, `toLowerCase()`)**
```javascript
let str = "Hello World";

console.log(str.toUpperCase()); // ✅ "HELLO WORLD"
console.log(str.toLowerCase()); // ✅ "hello world"
```

---

### **🔹 Extracting Parts of a String**
| Method | Description | Example |
|--------|------------|---------|
| **slice(start, end)** | Extracts part of a string | `"hello".slice(1, 4) // "ell"` |
| **substring(start, end)** | Similar to `slice`, but does not accept negative indexes | `"hello".substring(1, 4) // "ell"` |
| **substr(start, length)** | Extracts `length` characters from `start` | `"hello".substr(1, 3) // "ell"` |

```javascript
let str = "JavaScript";

console.log(str.slice(0, 4));   // ✅ "Java"
console.log(str.substring(0, 4)); // ✅ "Java"
console.log(str.substr(4, 6));  // ✅ "Script"
```

✔ **Use `slice()` for best performance.**  
✔ `substr()` is **deprecated**, so avoid using it.

---

### **🔹 Searching in Strings**
| Method | Description | Example |
|--------|------------|---------|
| **indexOf(value)** | Returns the first index of the value | `"hello".indexOf("l") // 2` |
| **lastIndexOf(value)** | Returns the last index of the value | `"hello".lastIndexOf("l") // 3` |
| **includes(value)** | Checks if a value exists in a string (`true` or `false`) | `"hello".includes("he") // true` |
| **startsWith(value)** | Checks if a string starts with the value | `"hello".startsWith("he") // true` |
| **endsWith(value)** | Checks if a string ends with the value | `"hello".endsWith("lo") // true` |

```javascript
let str = "Hello, World!";

console.log(str.indexOf("o")); // ✅ 4
console.log(str.lastIndexOf("o")); // ✅ 8
console.log(str.includes("World")); // ✅ true
console.log(str.startsWith("Hello")); // ✅ true
console.log(str.endsWith("!")); // ✅ true
```

---

### **🔹 Replacing & Modifying Strings**
| Method | Description | Example |
|--------|------------|---------|
| **replace(old, new)** | Replaces the first occurrence | `"hello world".replace("world", "JS") // "hello JS"` |
| **replaceAll(old, new)** | Replaces all occurrences | `"hello hello".replaceAll("hello", "hi") // "hi hi"` |
| **trim()** | Removes whitespace from both sides | `"  hello  ".trim() // "hello"` |
| **trimStart()** | Removes whitespace from the start | `"  hello".trimStart() // "hello"` |
| **trimEnd()** | Removes whitespace from the end | `"hello  ".trimEnd() // "hello"` |

```javascript
let text = "  JavaScript is awesome!  ";

console.log(text.replace("awesome", "cool")); // ✅ "JavaScript is cool!"
console.log(text.replaceAll(" ", "_")); // ✅ "__JavaScript_is_awesome!__"
console.log(text.trim()); // ✅ "JavaScript is awesome!"
console.log(text.trimStart()); // ✅ "JavaScript is awesome!  "
console.log(text.trimEnd()); // ✅ "  JavaScript is awesome!"
```

✔ **Use `trim()` to clean user inputs!**  

---

### **🔹 Splitting & Joining Strings**
| Method | Description | Example |
|--------|------------|---------|
| **split(separator)** | Splits a string into an array | `"hello,world".split(",") // ["hello", "world"]` |
| **join(separator)** | Joins an array into a string | `["hello", "world"].join("-") // "hello-world"` |

```javascript
let str = "apple,banana,grape";
let fruits = str.split(",");

console.log(fruits); // ✅ ["apple", "banana", "grape"]
console.log(fruits.join(" - ")); // ✅ "apple - banana - grape"
```

---

### **🔹 Repeating & Padding Strings**
| Method | Description | Example |
|--------|------------|---------|
| **repeat(n)** | Repeats the string `n` times | `"ha".repeat(3) // "hahaha"` |
| **padStart(length, char)** | Pads at the beginning | `"5".padStart(3, "0") // "005"` |
| **padEnd(length, char)** | Pads at the end | `"5".padEnd(3, "0") // "500"` |

```javascript
let str = "Hello";

console.log(str.repeat(3)); // ✅ "HelloHelloHello"
console.log("7".padStart(4, "0")); // ✅ "0007"
console.log("7".padEnd(4, "0")); // ✅ "7000"
```

---

### **🔹 Converting Strings**
| Method | Description | Example |
|--------|------------|---------|
| **charAt(index)** | Returns character at index | `"hello".charAt(1) // "e"` |
| **charCodeAt(index)** | Returns ASCII code of character | `"hello".charCodeAt(1) // 101` |
| **String.fromCharCode(code)** | Converts ASCII to character | `String.fromCharCode(65) // "A"` |

```javascript
let str = "JavaScript";

console.log(str.charAt(3)); // ✅ "a"
console.log(str.charCodeAt(3)); // ✅ 97
console.log(String.fromCharCode(97)); // ✅ "a"
```

---

### **🔹 Template Literals (ES6)**
Use **backticks (`) to create multi-line strings and insert variables.

```javascript
let name = "Alice";
let age = 25;

console.log(`Hello, my name is ${name} and I am ${age} years old.`);
```

✔ **Better than string concatenation (`+`) for readability.**

---

## **🚀 Summary of JavaScript String Methods**
| Method | Description |
|--------|------------|
| **length** | Returns string length |
| **toUpperCase(), toLowerCase()** | Changes case |
| **slice(), substring(), substr()** | Extracts part of a string |
| **indexOf(), lastIndexOf(), includes()** | Searches for a substring |
| **replace(), replaceAll()** | Replaces content |
| **trim(), trimStart(), trimEnd()** | Removes whitespace |
| **split(), join()** | Converts between string and array |
| **repeat(), padStart(), padEnd()** | Modifies string format |
| **charAt(), charCodeAt()** | Access character data |

---

## **🔥 What’s Next?**
Would you like **more exercises**, real-world **use cases**, or a **deep dive** into any method? Let me know! 😊🚀