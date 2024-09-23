### 3.10 Currying

**Currying** is a technique where a function with multiple arguments is transformed into a series of functions, each taking a single argument. It allows you to break down a function that takes multiple arguments into a chain of functions.

#### Example:
```javascript
function multiply(a) {
  return function(b) {
    return a * b;
  };
}

const double = multiply(2);
console.log(double(5)); // Output: 10
console.log(multiply(3)(4)); // Output: 12
```

In this example, `multiply(3)(4)` first returns a function that remembers `a = 3`, and then it uses `b = 4` in the next function call.

---

### 3.11 Function Composition

**Function composition** is the process of combining two or more functions to produce a new function. In functional programming, this allows you to pass the output of one function as the input of another.

#### Example:
```javascript
const add = x => x + 1;
const multiply = x => x * 2;

const composedFunction = x => multiply(add(x));

console.log(composedFunction(5)); // Output: 12
```

Here, the `composedFunction(5)` first applies `add(5)` to return `6`, then applies `multiply(6)` to return `12`.

---

### 3.12 Partial Application

**Partial application** is when you fix a few arguments of a function and return a new function that takes the remaining arguments. It’s similar to currying but more flexible.

#### Example:
```javascript
function add(a) {
  return function(b, c) {
    return a + b + c;
  };
}

const addFive = add(5);
console.log(addFive(3, 2)); // Output: 10
```

In this example, `addFive` partially applies the first argument and returns a function that takes two more arguments.

---

### 3.13 Function Memoization

**Memoization** is an optimization technique that stores the results of expensive function calls and reuses them when the same inputs occur again.

#### Example:
```javascript
function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache[key]) {
      return cache[key];
    } else {
      const result = fn(...args);
      cache[key] = result;
      return result;
    }
  };
}

const slowFunction = num => {
  console.log("Running slow function...");
  return num * 2;
};

const memoizedFunction = memoize(slowFunction);

console.log(memoizedFunction(5)); // Output: Running slow function... 10
console.log(memoizedFunction(5)); // Output: 10 (retrieved from cache)
```

This is useful for functions that have expensive computations, as it avoids recalculating the same values.

---

### Advanced Summary of Functions

- **Currying**: Breaks down a function that takes multiple arguments into multiple functions, each taking a single argument.
- **Function Composition**: Combines two or more functions, where the output of one function becomes the input of another.
- **Partial Application**: Fixes a few arguments of a function and returns a new function that takes the remaining arguments.
- **Memoization**: Optimizes functions by caching results for future use.

---

This concludes the advanced section of **JavaScript Functions**. With currying, function composition, partial application, and memoization, you're entering more advanced functional programming techniques that are incredibly powerful in JavaScript.
