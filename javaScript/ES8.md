# ES8 Features and Using `Object.values()`, `Object.entries()`, and `String padding`

## Introduction to ES8 (ECMAScript 2017)

ES8 (ECMAScript 2017) introduced several new features that make JavaScript programming more flexible and readable. The key features introduced in ES8 are:

- **Object.values()**
- **Object.entries()**
- **String padding (`padStart()` and `padEnd()`)**
- **Async functions**

In this document, we will cover each of these features with examples.

## 1. `Object.values()`

`Object.values()` is a new method that returns an array of a given object's own enumerable property values, in the same order as a `for...in` loop would.

### Example of `Object.values()`

```javascript
const user = {
  name: 'Alice',
  age: 25,
  role: 'admin'
};

console.log(Object.values(user)); 
// Output: ['Alice', 25, 'admin']
```

This method is useful when you only need the values of an object and not the keys.

## 2. `Object.entries()`

`Object.entries()` returns an array of a given object's own enumerable string-keyed property `[key, value]` pairs. This method is particularly useful when you need both keys and values in a structured format.

### Example of `Object.entries()`

```javascript
const user = {
  name: 'Alice',
  age: 25,
  role: 'admin'
};

console.log(Object.entries(user)); 
// Output: [['name', 'Alice'], ['age', 25], ['role', 'admin']]
```

With `Object.entries()`, you can easily convert an object into an array of key-value pairs.

## 3. String Padding (`padStart()` and `padEnd()`)

The `padStart()` and `padEnd()` methods allow you to add padding to the beginning or end of a string, respectively. These methods are especially useful for formatting output.

### Example of `padStart()` and `padEnd()`

```javascript
const str = '5';

console.log(str.padStart(3, '0')); // Output: '005'
console.log(str.padEnd(3, '0'));   // Output: '500'
```

In this example, `padStart()` adds padding to the left of the string, while `padEnd()` adds padding to the right.

## 4. Async Functions

Async functions are a major addition in ES8, allowing you to write asynchronous code that looks more like synchronous code. They are built on top of Promises and use the `async` and `await` keywords.

### Example of Async Functions

```javascript
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('Data fetched');
    }, 1000);
  });
}

async function getData() {
  const data = await fetchData();
  console.log(data); // Output: 'Data fetched'
}

getData();
```

In this example, `getData()` is an async function that waits for the `fetchData()` promise to resolve before continuing.

## Conclusion

ES8 introduced several helpful features like `Object.values()`, `Object.entries()`, string padding with `padStart()` and `padEnd()`, and async functions. These features make JavaScript more versatile, improve readability, and streamline working with objects and asynchronous operations.

© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
