# JavaScript Control Flow

## 2. JavaScript Control Flow

Control flow refers to how the program moves from one section of code to another, based on conditions or repetition. In this section, we will cover the most common control flow structures like **conditionals** and **loops**.

---

### 2.1 JavaScript Conditionals

Conditionals allow us to execute specific blocks of code depending on whether a condition is true or false.

#### `if` Statement
The `if` statement executes a block of code if the condition inside the parentheses is `true`.

```javascript
let age = 20;
if (age >= 18) {
  console.log("You are an adult.");
}
// Output: You are an adult.
```

#### `else` Statement
The `else` statement runs when the `if` condition is false.

```javascript
let age = 16;
if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
// Output: You are a minor.
```

#### `else if` Statement
You can chain multiple conditions using `else if`.

```javascript
let score = 85;
if (score >= 90) {
  console.log("Excellent");
} else if (score >= 70) {
  console.log("Good");
} else {
  console.log("Needs Improvement");
}
// Output: Good
```

#### Ternary Operator
The ternary operator is a shorthand way to write `if...else` statements. It’s structured as:  
`condition ? expressionIfTrue : expressionIfFalse`.

```javascript
let age = 20;
let message = age >= 18 ? "You are an adult." : "You are a minor.";
console.log(message);
// Output: You are an adult.
```

---

### 2.2 Switch Statement

The `switch` statement is another way to handle multiple conditions. It's useful when you have several possible values for a single variable.

#### Example:
```javascript
let fruit = 'apple';
switch (fruit) {
  case 'banana':
    console.log('You chose banana.');
    break;
  case 'apple':
    console.log('You chose apple.');
    break;
  default:
    console.log('Unknown fruit.');
}
// Output: You chose apple.
```

In this example:
- The program checks the value of `fruit`.
- If it's `'apple'`, it runs the code for that case.
- The `break` statement prevents the program from continuing to other cases.
- The `default` case runs if none of the other cases match.

---

### 2.3 JavaScript Loops

Loops allow you to repeat a block of code multiple times until a condition is met.

#### `for` Loop
The `for` loop is commonly used to iterate over arrays or perform a task a specific number of times.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Output: 0 1 2 3 4
```

**Explanation**:
- The loop starts at `i = 0`.
- It runs as long as `i < 5`.
- After each iteration, `i` increases by 1.

#### `while` Loop
The `while` loop repeats a block of code as long as the specified condition is `true`.

```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
// Output: 0 1 2 3 4
```

**Explanation**:
- The loop continues running as long as `i` is less than `5`.
- In each iteration, `i` increases by 1.

#### `do...while` Loop
The `do...while` loop is similar to the `while` loop, but it runs the block of code **at least once**, even if the condition is false.

```javascript
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
// Output: 0 1 2 3 4
```

---

### 2.4 Loop Control: `break` and `continue`

#### `break` Statement
The `break` statement is used to exit the loop before it has run all its iterations.

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    break;
  }
  console.log(i);
}
// Output: 0 1 2
```

#### `continue` Statement
The `continue` statement skips the current iteration of the loop and proceeds to the next one.

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
// Output: 0 1 2 4
```

---

### 2.5 Looping through Arrays

When dealing with arrays, it's common to loop through all the elements. You can use a regular `for` loop or the `forEach()` method.

#### `forEach()` Method
The `forEach()` method calls a function for each element in the array.

```javascript
const fruits = ["apple", "banana", "cherry"];
fruits.forEach(fruit => {
  console.log(fruit);
});
// Output: apple banana cherry
```

---

### Summary of Control Flow

- **Conditionals**: Use `if`, `else if`, and `else` to control the flow based on conditions.
- **Ternary Operator**: A shorthand for `if...else` statements.
- **Switch Statements**: Efficient when checking multiple potential values for a variable.
- **Loops**: Use `for`, `while`, and `do...while` to repeat code until a condition is met.
- **Loop Control**: Use `break` to exit a loop early and `continue` to skip an iteration.

---

This concludes the **Control Flow** section. We’ve covered how to use conditional statements and loops to manage the flow of your JavaScript programs. Next, we’ll dive into **JavaScript functions**, from the basics to advanced topics.
