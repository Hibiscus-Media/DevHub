# ECMAScript (ES) Versions: ES5 to ES10

ECMAScript (often referred to as JavaScript) is continuously evolving with new versions, each introducing features that make the language more powerful, flexible, and easier to work with. Below is a breakdown of the key features from **ES5** to **ES10**.

---

## 6.1 ECMAScript 5 (ES5) – Introduced in 2009

**Key Features**:
- **Strict Mode**: Enforces stricter parsing and error handling in your code.
- **Array Methods**: `forEach()`, `map()`, `filter()`, `reduce()`, `some()`, and `every()`.
- **JSON Support**: Native JSON parsing and stringifying with `JSON.parse()` and `JSON.stringify()`.
- **Property Getters and Setters**: Allows the definition of functions to be run when properties are read or written.

### Example: `forEach()` in ES5
```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => console.log(num)); 
// Output: 1 2 3 4 5
```

---

## 6.2 ECMAScript 6 (ES6/ES2015) – Introduced in 2015

**Key Features**:
- **`let` and `const`**: Block-scoped variables.
- **Arrow Functions**: Shorter syntax for writing functions.
- **Classes**: A cleaner syntax for creating objects and handling inheritance.
- **Template Literals**: Backticks for string interpolation.
- **Destructuring**: Unpacking values from arrays or objects into variables.
- **Modules**: `import` and `export` for modular code.
- **Promises**: For handling asynchronous code.
- **Default Parameters**: Assign default values to function parameters.

### Example: Arrow Functions and Destructuring in ES6
```javascript
const person = { name: "Alice", age: 30 };
const greet = ({ name, age }) => `Hello, ${name}, age: ${age}`;
console.log(greet(person)); 
// Output: Hello, Alice, age: 30
```

---

## 6.3 ECMAScript 7 (ES7/ES2016) – Introduced in 2016

**Key Features**:
- **Exponentiation Operator (`**`)**: A simpler way to raise numbers to a power.
- **`Array.prototype.includes()`**: Check if an array contains a value.

### Example: `includes()` in ES7
```javascript
const fruits = ["apple", "banana", "cherry"];
console.log(fruits.includes("banana")); 
// Output: true
```

---

## 6.4 ECMAScript 8 (ES8/ES2017) – Introduced in 2017

**Key Features**:
- **`async`/`await`**: Simplified syntax for handling asynchronous operations.
- **Object.entries()**: Returns an array of a given object’s own enumerable string-keyed property `[key, value]` pairs.
- **String Padding**: `padStart()` and `padEnd()` to pad strings.

### Example: `async`/`await` in ES8
```javascript
const fetchData = async () => {
  const response = await fetch("https://api.example.com/data");
  const data = await response.json();
  console.log(data);
};
fetchData();
```

---

## 6.5 ECMAScript 9 (ES9/ES2018) – Introduced in 2018

**Key Features**:
- **Rest/Spread Properties**: Allows spreading properties of objects.
- **Asynchronous Iteration**: `for await...of` loops for asynchronous data.
- **Promise Finally**: Adds a `.finally()` method to promises.
  
### Example: `Promise.finally()` in ES9
```javascript
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .finally(() => console.log("Finished fetching data."));
```

---

## 6.6 ECMAScript 10 (ES10/ES2019) – Introduced in 2019

**Key Features**:
- **`Array.prototype.flat()`**: Flattens an array up to a specified depth.
- **`Array.prototype.flatMap()`**: Maps and flattens an array in one step.
- **`Object.fromEntries()`**: Transforms a list of key-value pairs into an object.
- **Optional `catch` Binding**: Allows `catch` blocks to omit the error parameter.
- **String `trimStart()` and `trimEnd()`**: Removes whitespace from the start or end of a string.

### Example: `Array.prototype.flat()` in ES10
```javascript
const nestedArray = [1, 2, [3, 4, [5]]];
const flattenedArray = nestedArray.flat(2);
console.log(flattenedArray); 
// Output: [1, 2, 3, 4, 5]
```

### Example: `Object.fromEntries()` in ES10
```javascript
const entries = [["name", "Alice"], ["age", 30]];
const obj = Object.fromEntries(entries);
console.log(obj); 
// Output: { name: "Alice", age: 30 }
```

---

### Summary of ES Versions

- **ES5 (2009)**: Introduced strict mode, JSON support, array methods (`map()`, `forEach()`), and getters/setters.
- **ES6 (2015)**: Brought major changes like `let`, `const`, arrow functions, classes, promises, and destructuring.
- **ES7 (2016)**: Introduced `**` exponentiation operator and `Array.includes()`.
- **ES8 (2017)**: Brought `async`/`await`, `Object.entries()`, and string padding.
- **ES9 (2018)**: Introduced rest/spread properties, asynchronous iteration, and `Promise.finally()`.
- **ES10 (2019)**: Introduced `flat()`, `flatMap()`, `Object.fromEntries()`, and optional `catch` binding.

---

### Copyright Notice
© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
