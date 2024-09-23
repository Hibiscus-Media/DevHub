# JavaScript Tutorial: From Basics to Advanced

## 1. JavaScript Basics

### 1.1 JavaScript Variables
Variables are used to store data values. In JavaScript, we can declare variables using three keywords: `var`, `let`, and `const`.

#### `var`
- `var` is function-scoped and can be re-declared. It is hoisted but can lead to unintended behavior in large programs due to its scoping.

```javascript
var name = "John";
console.log(name); // Output: John
```

#### `let`
- `let` is block-scoped and cannot be re-declared within the same block. It is not hoisted like `var`.

```javascript
let age = 25;
console.log(age); // Output: 25
```

#### `const`
- `const` is also block-scoped but must be initialized when declared and cannot be reassigned.

```javascript
const PI = 3.14;
console.log(PI); // Output: 3.14
```

---

### 1.2 JavaScript Data Types
JavaScript provides several different data types to store various kinds of values. The most common ones are:

1. **Number**
   - Example: `const num = 42;`
2. **String**
   - Example: `const str = "Hello World";`
3. **Boolean**
   - Example: `const isTrue = true;`
4. **Undefined**
   - Example: `let x; // undefined`
5. **Null**
   - Example: `const y = null;`
6. **Object**
   - Example:
   ```javascript
   const person = {
     name: "Alice",
     age: 30
   };
   ```

---

### 1.3 JavaScript Comparisons
JavaScript has several comparison operators to compare values.

#### Strict Equality (`===`)
- Compares both value and type.

```javascript
console.log(5 === 5);   // Output: true
console.log(5 === '5'); // Output: false
```

#### Loose Equality (`==`)
- Compares only the value, ignoring type.

```javascript
console.log(5 == '5'); // Output: true
```

#### Other Comparison Operators
- **Greater than (`>`)**
   ```javascript
   console.log(10 > 5); // Output: true
   ```
- **Less than (`<`)**
   ```javascript
   console.log(5 < 10); // Output: true
   ```
- **Greater than or equal to (`>=`)**
   ```javascript
   console.log(10 >= 10); // Output: true
   ```
- **Less than or equal to (`<=`)**
   ```javascript
   console.log(5 <= 5); // Output: true
   ```

---

### 1.4 JavaScript Logical Operators
Logical operators are used to combine multiple conditions.

#### AND (`&&`)
- Returns true if both operands are true.
```javascript
const isLoggedIn = true;
const isAdmin = true;
if (isLoggedIn && isAdmin) {
  console.log("Welcome Admin!"); // Output: Welcome Admin!
}
```

#### OR (`||`)
- Returns true if at least one operand is true.
```javascript
const isLoggedIn = false;
const isGuest = true;
if (isLoggedIn || isGuest) {
  console.log("Welcome Guest!"); // Output: Welcome Guest!
}
```

#### NOT (`!`)
- Reverses the truthiness of a value.
```javascript
const isLoggedIn = false;
if (!isLoggedIn) {
  console.log("Please log in."); // Output: Please log in.
}
```

---

### 1.5 JavaScript Type Conversion
JavaScript automatically converts between types when necessary, a behavior called **type coercion**.

#### Example: Number to String
```javascript
const num = 10;
const str = "The number is " + num; 
console.log(str); // Output: The number is 10
```

#### Example: String to Number
```javascript
const strNum = "100";
const convertedNum = Number(strNum);
console.log(convertedNum); // Output: 100
```

---

### 1.6 Falsy and Truthy Values
In JavaScript, certain values are considered **falsy**, meaning they evaluate to `false` in a boolean context, while everything else is considered **truthy**.

#### Falsy Values
- `false`
- `0`
- `""` (empty string)
- `null`
- `undefined`
- `NaN` (Not a Number)

#### Truthy Values
- Everything else (non-zero numbers, non-empty strings, objects, arrays, etc.)

#### Example:
```javascript
const value = "";
if (!value) {
  console.log("Falsy!"); // Output: Falsy!
}
```

---

This concludes the **JavaScript Basics** section. Now that we’ve covered variables, data types, comparisons, and logical operators, we’ll build up to **control flow** (like conditionals and loops) in the next section!
