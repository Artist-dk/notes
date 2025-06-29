# **🔥 JavaScript Date & Time Methods**
JavaScript provides powerful built-in methods for working with **dates** and **time** using the `Date` object. Let's explore them with **examples**. 🚀  

---

## **1️⃣ Creating a Date Object**  
You can create a `Date` object using the `new Date()` constructor.

### **📌 Creating a Date Object**
```javascript
let currentDate = new Date();
console.log(currentDate); // ✅ Current date & time
```
✔ By default, it gives the **current date & time** in your system's timezone.

---

## **2️⃣ Creating Specific Dates**
### **📌 Different Ways to Create Dates**
| Method | Example | Output |
|--------|--------|--------|
| `new Date()` | `new Date()` | Current date & time |
| `new Date(year, month, day, hours, minutes, seconds, ms)` | `new Date(2025, 1, 16, 14, 30, 0)` | Feb 16, 2025, 14:30:00 |
| `new Date("YYYY-MM-DD")` | `new Date("2025-02-16")` | Feb 16, 2025 |
| `new Date(milliseconds)` | `new Date(0)` | Jan 1, 1970 (Unix Epoch) |

### **📌 Example**
```javascript
let specificDate1 = new Date(2025, 1, 16); // Year, Month (0-based), Day
console.log(specificDate1); // ✅ Sun Feb 16 2025

let specificDate2 = new Date("2025-02-16");
console.log(specificDate2); // ✅ Sun Feb 16 2025

let unixDate = new Date(0);
console.log(unixDate); // ✅ Thu Jan 01 1970 (Unix Epoch)
```
✔ **Months in JavaScript are 0-based** (January = `0`, February = `1`, etc.).

---

## **3️⃣ Getting Date & Time Components**
The `Date` object provides several **getter methods** to extract date/time values.

| Method | Description | Example |
|--------|------------|---------|
| `getFullYear()` | Returns the year | `date.getFullYear()` → `2025` |
| `getMonth()` | Returns the month (0-11) | `date.getMonth()` → `1` (Feb) |
| `getDate()` | Returns the day (1-31) | `date.getDate()` → `16` |
| `getDay()` | Returns the weekday (0-6) | `date.getDay()` → `0` (Sunday) |
| `getHours()` | Returns hours (0-23) | `date.getHours()` → `14` |
| `getMinutes()` | Returns minutes (0-59) | `date.getMinutes()` → `30` |
| `getSeconds()` | Returns seconds (0-59) | `date.getSeconds()` → `45` |
| `getMilliseconds()` | Returns milliseconds (0-999) | `date.getMilliseconds()` → `250` |
| `getTime()` | Returns Unix timestamp (ms since 1970) | `date.getTime()` → `1708118400000` |

### **📌 Example**
```javascript
let date = new Date(2025, 1, 16, 14, 30, 45);

console.log(date.getFullYear());  // ✅ 2025
console.log(date.getMonth());     // ✅ 1 (February)
console.log(date.getDate());      // ✅ 16
console.log(date.getDay());       // ✅ 0 (Sunday)
console.log(date.getHours());     // ✅ 14
console.log(date.getMinutes());   // ✅ 30
console.log(date.getSeconds());   // ✅ 45
console.log(date.getMilliseconds()); // ✅ 0
console.log(date.getTime()); // ✅ 1734385800000 (milliseconds since 1970)
```
✔ **Use `getTime()` for time comparisons.**

---

## **4️⃣ Setting Date & Time**
| Method | Description | Example |
|--------|------------|---------|
| `setFullYear(year)` | Sets the year | `date.setFullYear(2030)` |
| `setMonth(month)` | Sets the month (0-11) | `date.setMonth(5)` (June) |
| `setDate(day)` | Sets the day (1-31) | `date.setDate(25)` |
| `setHours(hours)` | Sets hours (0-23) | `date.setHours(18)` |
| `setMinutes(minutes)` | Sets minutes (0-59) | `date.setMinutes(45)` |
| `setSeconds(seconds)` | Sets seconds (0-59) | `date.setSeconds(30)` |
| `setMilliseconds(ms)` | Sets milliseconds (0-999) | `date.setMilliseconds(500)` |

### **📌 Example**
```javascript
let date = new Date();
date.setFullYear(2030);
date.setMonth(5);  // June
date.setDate(25);
date.setHours(18);
date.setMinutes(45);

console.log(date); // ✅ Tue Jun 25 2030 18:45:00
```
✔ **Use setters to modify a date object.**

---

## **5️⃣ Formatting Dates**
| Method | Description | Example |
|--------|------------|---------|
| `toDateString()` | Returns date as a readable string | `"Sun Feb 16 2025"` |
| `toTimeString()` | Returns time as a readable string | `"14:30:45 GMT+0530 (IST)"` |
| `toISOString()` | Returns ISO format | `"2025-02-16T14:30:00.000Z"` |
| `toUTCString()` | Returns UTC date string | `"Sun, 16 Feb 2025 14:30:00 GMT"` |
| `toLocaleDateString()` | Returns localized date | `"2/16/2025"` (US) |
| `toLocaleTimeString()` | Returns localized time | `"2:30:00 PM"` (US) |
| `toLocaleString()` | Returns localized date & time | `"2/16/2025, 2:30:00 PM"` (US) |

### **📌 Example**
```javascript
let date = new Date(2025, 1, 16, 14, 30, 0);

console.log(date.toDateString());  // ✅ "Sun Feb 16 2025"
console.log(date.toTimeString());  // ✅ "14:30:00 GMT+0530 (IST)"
console.log(date.toISOString());   // ✅ "2025-02-16T14:30:00.000Z"
console.log(date.toUTCString());   // ✅ "Sun, 16 Feb 2025 14:30:00 GMT"
console.log(date.toLocaleDateString());  // ✅ "2/16/2025"
console.log(date.toLocaleTimeString());  // ✅ "2:30:00 PM"
console.log(date.toLocaleString());      // ✅ "2/16/2025, 2:30:00 PM"
```
✔ **Use `toLocaleString()` for user-friendly formatting.**

---

## **6️⃣ Date Comparisons**
Dates can be **compared** using their **timestamp values** (`getTime()`).

### **📌 Example**
```javascript
let date1 = new Date("2025-02-16");
let date2 = new Date("2025-03-01");

if (date1.getTime() < date2.getTime()) {
    console.log("date1 is earlier than date2");
} else {
    console.log("date1 is later than date2");
}
// ✅ "date1 is earlier than date2"
```
✔ **Use `getTime()` for precise date comparisons.**

---

## **7️⃣ Getting Time Difference**
You can calculate the **time difference** between two dates.

### **📌 Example: Days Between Two Dates**
```javascript
let startDate = new Date("2025-02-01");
let endDate = new Date("2025-02-16");

let diffMs = endDate - startDate;
let diffDays = diffMs / (1000 * 60 * 60 * 24); // Convert ms to days

console.log(diffDays); // ✅ 15 days
```
✔ **Use `(1000 * 60 * 60 * 24)` to convert milliseconds to days.**

---

## **🚀 Summary of JavaScript Date Methods**
| Category | Methods |
|----------|---------|
| **Get Date/Time** | `getFullYear()`, `getMonth()`, `getDate()`, `getDay()`, `getHours()`, `getMinutes()` |
| **Set Date/Time** | `setFullYear()`, `setMonth()`, `setDate()`, `setHours()` |
| **Formatting** | `toISOString()`, `toLocaleString()`, `toDateString()` |
| **Comparison** | `getTime()` |
| **Math** | Subtract dates to find the difference |

---

## **🚀 What’s Next?**
Would you like **hands-on exercises**, real-world **examples**, or a **deep dive** into a specific topic? Let me know! 😊🔥