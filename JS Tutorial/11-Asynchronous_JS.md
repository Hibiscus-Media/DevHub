# Asynchronous JavaScript

## 7.1 Introduction to Asynchronous JavaScript

JavaScript is **single-threaded**, meaning it can only perform one task at a time. To handle operations that take time, like fetching data from a server or reading a file, JavaScript uses **asynchronous programming**. This allows long-running tasks to execute in the background without freezing the entire program.

There are three main ways to handle asynchronous code:
1. **Callbacks**
2. **Promises**
3. **Async/Await**

---

## 7.2 Callbacks

A **callback** is a function that is passed as an argument to another function and is executed once the operation is completed.

#### Example: Using Callbacks
```javascript
function fetchData(callback) {
  setTimeout(() => {
    console.log("Data fetched");
    callback(); // Callback executed after data is fetched
  }, 2000);
}

function processData() {
  console.log("Processing data...");
}

fetchData(processData);
// Output:
// Data fetched
// Processing data...
```

### Callback Hell

If you have multiple asynchronous operations that depend on each other, you might end up with nested callbacks, commonly known as **callback hell**. This can make code difficult to read and maintain.

#### Example:
```javascript
setTimeout(() => {
  console.log("Step 1 complete");
  setTimeout(() => {
    console.log("Step 2 complete");
    setTimeout(() => {
      console.log("Step 3 complete");
    }, 1000);
  }, 1000);
}, 1000);

// Output:
// Step 1 complete
// Step 2 complete
// Step 3 complete
```

---

## 7.3 Promises

A **promise** is an object that represents the eventual completion (or failure) of an asynchronous operation. Promises can be in one of three states:
- **Pending**: The operation is ongoing.
- **Fulfilled**: The operation completed successfully.
- **Rejected**: The operation failed.

You can use `.then()` for fulfilled promises and `.catch()` for rejected promises.

#### Example: Creating a Promise
```javascript
const fetchData = new Promise((resolve, reject) => {
  setTimeout(() => {
    const success = true;
    if (success) {
      resolve("Data fetched successfully");
    } else {
      reject("Error fetching data");
    }
  }, 2000);
});

fetchData
  .then(response => {
    console.log(response);
  })
  .catch(error => {
    console.log(error);
  });

// Output: Data fetched successfully (if success is true)
```

### Chaining Promises

Promises can be **chained** to handle multiple asynchronous operations in sequence.

#### Example:
```javascript
const fetchData = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Data fetched"), 1000);
});

fetchData
  .then(response => {
    console.log(response); // Output: Data fetched
    return "Processing data";
  })
  .then(process => {
    console.log(process); // Output: Processing data
  })
  .catch(error => {
    console.error("Error:", error);
  });
```

### `Promise.all()` and `Promise.race()`

- **`Promise.all()`**: Waits for all promises to be resolved before proceeding.
- **`Promise.race()`**: Resolves as soon as one of the promises is resolved.

#### Example: `Promise.all()`
```javascript
const promise1 = new Promise(resolve => setTimeout(resolve, 1000, "First"));
const promise2 = new Promise(resolve => setTimeout(resolve, 2000, "Second"));
const promise3 = new Promise(resolve => setTimeout(resolve, 3000, "Third"));

Promise.all([promise1, promise2, promise3]).then(results => {
  console.log(results); // Output: ["First", "Second", "Third"]
});
```

---

## 7.4 Async/Await (ES8)

**`async`/`await`** is built on top of promises and provides a cleaner, more readable way to write asynchronous code. It allows you to write asynchronous code that looks like synchronous code.

### `async` Functions

An `async` function always returns a promise. It allows the use of `await` inside it to pause the function execution until the promise is resolved.

### `await`

`await` can only be used inside an `async` function. It pauses the execution of the function until the promise is resolved.

#### Example: Using `async`/`await`
```javascript
const fetchData = () => {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("Data fetched");
    }, 2000);
  });
};

const process = async () => {
  const data = await fetchData();
  console.log(data); // Output: Data fetched
};

process();
```

### Error Handling in `async/await`

You can handle errors in `async/await` using **try/catch** blocks.

#### Example:
```javascript
const fetchData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      reject("Error fetching data");
    }, 2000);
  });
};

const process = async () => {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (error) {
    console.error("Error:", error); // Output: Error: Error fetching data
  }
};

process();
```

---

### Summary of Asynchronous JavaScript

- **Callbacks**: A function that is passed to another function and executed once the task is completed. Can lead to callback hell with nested operations.
- **Promises**: Represents the eventual completion or failure of an async task. `.then()` and `.catch()` are used for chaining.
- **async/await**: A cleaner, more readable way to handle promises. Allows you to write asynchronous code in a synchronous style.
- **Error Handling**: Use `try/catch` blocks to handle errors in `async/await`.

---

### Copyright Notice
© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
