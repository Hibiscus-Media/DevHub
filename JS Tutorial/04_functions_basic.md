# JavaScript Functions

## 3. JavaScript Functions

Functions are reusable blocks of code that perform a specific task. In JavaScript, functions allow you to write modular and reusable code.

---

### 3.1 Function Declaration

A **function declaration** defines a named function that can be invoked later. It is hoisted, which means you can call the function before it’s defined in the code.

#### Example:
```javascript
function greet(name) {
  return "Hello, " + name;
}
console.log(greet("Alice")); // Output: Hello, Alice
```

- The function `greet()` takes one parameter, `name`, and returns a greeting string.

---

### 3.2 Function Expression

A **function expression** assigns a function to a variable. Unlike function declarations, function expressions are not hoisted, so they cannot be called before they are defined.

#### Example:
```javascript
const greet = function(name) {
  return "Hello, " + name;
};
console.log(greet("Bob")); // Output: Hello, Bob
```

---

### 3.3 Arrow Functions (ES6)

**Arrow functions** are a shorter syntax for writing functions, introduced in ES6. They are anonymous (unnamed) and do not bind their own `this` value.

#### Basic Syntax:
```javascript
const greet = (name) => "Hello, " + name;
console.log(greet("Charlie")); // Output: Hello, Charlie
```

#### Multiple Parameters:
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // Output: 5
```

#### No Parameters:
```javascript
const greet = () => "Hello, world!";
console.log(greet()); // Output: Hello, world!
```

---

### 3.4 `return` Statement

Functions can return a value using the `return` statement. Once the `return` statement is executed, the function stops, and the value is returned to the caller.

#### Example:
```javascript
function add(a, b) {
  return a + b;
}
console.log(add(5, 3)); // Output: 8
```

- In this case, `return a + b;` sends the sum of `a` and `b` back to the function call.

---

### 3.5 Higher-Order Functions

A **higher-order function** is a function that takes another function as an argument, or returns a function as a result.

#### Example: Passing a function as an argument
```javascript
function greetUser(callback) {
  const name = "Alice";
  callback(name);
}

greetUser(function(name) {
  console.log("Hello, " + name);
});
// Output: Hello, Alice
```

#### Example: Returning a function
```javascript
function createMultiplier(multiplier) {
  return function(number) {
    return number * multiplier;
  };
}

const double = createMultiplier(2);
console.log(double(5)); // Output: 10
```

---

### 3.6 Anonymous Functions

**Anonymous functions** are functions without a name. They are often used as arguments to other functions, such as in `forEach()` or `setTimeout()`.

#### Example:
```javascript
setTimeout(function() {
  console.log("This runs after 2 seconds");
}, 2000);
```

---

### 3.7 Closures

A **closure** is a function that retains access to its parent function's scope, even after the parent function has returned.

#### Example:
```javascript
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log("Outer:", outerVariable);
    console.log("Inner:", innerVariable);
  };
}

const newFunction = outerFunction("outside");
newFunction("inside");
// Output: 
// Outer: outside
// Inner: inside
```

In this example, `innerFunction` has access to `outerVariable` from its parent scope even after `outerFunction` has finished executing.

---

### 3.8 Recursion

**Recursion** is when a function calls itself in order to solve a problem.

#### Example: Calculating Factorial
```javascript
function factorial(n) {
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

- In this example, `factorial()` calls itself until `n` is equal to `0`.

---

### 3.9 `this` in Functions

The value of `this` refers to the context in which a function is called. In regular functions, `this` refers to the object that called the function. In arrow functions, `this` is determined by the surrounding lexical context.

#### Example with Regular Functions:
```javascript
const person = {
  name: "Alice",
  greet: function() {
    console.log("Hello, " + this.name);
  }
};

person.greet(); // Output: Hello, Alice
```

#### Example with Arrow Functions:
```javascript
const person = {
  name: "Bob",
  greet: () => {
    console.log("Hello, " + this.name);
  }
};

person.greet(); // Output: Hello, undefined
```

In this case, `this.name` is `undefined` in the arrow function because it doesn't bind its own `this`.

---

### Summary of Functions

- **Function Declaration**: Traditional way of defining named functions.
- **Function Expression**: Defines a function and assigns it to a variable.
- **Arrow Functions**: Shorter syntax for writing functions, introduced in ES6.
- **Higher-Order Functions**: Functions that take or return other functions.
- **Closures**: Functions that retain access to their parent scope.
- **Recursion**: When a function calls itself to solve a problem.
- **`this` in Functions**: Regular functions and arrow functions handle `this` differently.

---

This concludes the **Functions** section. We've covered everything from basic function definitions to advanced topics like closures and higher-order functions. Next, we’ll dive into **data structures**, such as arrays and objects, and explore powerful array methods.
