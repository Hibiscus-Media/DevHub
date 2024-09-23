# JavaScript Essentials: Types, Comparisons, and Core Concepts

## JAVASCRIPT TYPES
-----------------
1. Number
   - Example: `const num = 42;`
   
2. String
   - Example: `const str = "Hello World";`

3. Boolean
   - Example: `const isTrue = true;`

4. Undefined
   - Example: `let x; // undefined`

5. Null
   - Example: `const y = null;`

<!-- 6. Symbol (new in ECMAScript 6) -->

7. Object
   - Example:
   ```javascript
   const person = {
     name: "Alice",
     age: 30
   };
   ```

## JAVASCRIPT COMPARISONS
-----------------
- `!==`
   - Example: `5 !== 3; // true`
   
- `===`
   - Example: `5 === 5; // true`

- `>=`
   - Example: `5 >= 3; // true`

- `<=`
   - Example: `2 <= 3; // true`

- `>`
   - Example: `4 > 2; // true`

- `<`
   - Example: `3 < 5; // true`

## JAVASCRIPT VARIABLES
-----------------
- `var`
   - Example: 
   ```javascript
   var name = "John";
   console.log(name); // Output: John
   ```

<!-- let (new in ECMAScript 6)-->  
<!-- const (new in ECMAScript 6)-->

## JAVASCRIPT CONDITIONALS
-----------------
- `if`
   - Example:
   ```javascript
   if (age > 18) {
     console.log("Adult");
   }
   ```

- `else`
   - Example:
   ```javascript
   if (age > 18) {
     console.log("Adult");
   } else {
     console.log("Minor");
   }
   ```

- `else if`
   - Example:
   ```javascript
   if (age > 18) {
     console.log("Adult");
   } else if (age > 12) {
     console.log("Teenager");
   } else {
     console.log("Child");
   }
   ```

<!-- ternary operator -->
<!-- switch -->

## JAVASCRIPT LOGICAL OPERATORS
-----------------
- `&&`
   - Example: 
   ```javascript
   if (isLoggedIn && isAdmin) {
     console.log("Welcome Admin!");
   }
   ```

- `||`
   - Example:
   ```javascript
   if (isLoggedIn || isGuest) {
     console.log("Welcome Guest or User!");
   }
   ```

- `!`
   - Example:
   ```javascript
   if (!isLoggedIn) {
     console.log("Please log in.");
   }
   ```

## JAVASCRIPT FUNCTIONS
-----------------
- `var a = function name() {}`
   - Example:
   ```javascript
   var greet = function(name) {
     return "Hello, " + name;
   };
   console.log(greet("Alice")); // Output: Hello, Alice
   ```

- `function name() {}`
   - Example:
   ```javascript
   function greet(name) {
     return "Hello, " + name;
   }
   console.log(greet("Bob")); // Output: Hello, Bob
   ```

- `return`
   - Example:
   ```javascript
   function add(a, b) {
     return a + b;
   }
   console.log(add(2, 3)); // Output: 5
   ```

<!-- () => (new in ECMAScript 6) -->

## JAVASCRIPT DATA STRUCTURES
-----------------
- Array
   - Example:
   ```javascript
   const fruits = ["apple", "banana", "cherry"];
   console.log(fruits[0]); // Output: apple
   ```

- Object
   - Example:
   ```javascript
   const car = { brand: "Toyota", model: "Camry" };
   console.log(car.brand); // Output: Toyota
   ```

## JAVASCRIPT LOOPING
-----------------
- `for`
   - Example:
   ```javascript
   for (let i = 0; i < 5; i++) {
     console.log(i);
   }
   ```

- `while`
   - Example:
   ```javascript
   let i = 0;
   while (i < 5) {
     console.log(i);
     i++;
   }
   ```

- `do`
   - Example:
   ```javascript
   let i = 0;
   do {
     console.log(i);
     i++;
   } while (i < 5);
   ```

- `forEach` (new in ECMAScript 5)
   - Example:
   ```javascript
   const fruits = ["apple", "banana", "cherry"];
   fruits.forEach(fruit => console.log(fruit));
   // Output: apple, banana, cherry
   ```

## JAVASCRIPT KEYWORDS
-----------------
- `break`
   - Example:
   ```javascript
   for (let i = 0; i < 5; i++) {
     if (i === 3) break;
     console.log(i);
   }
   // Output: 0, 1, 2
   ```

- `case`
   - Example:
   ```javascript
   switch (fruit) {
     case 'apple':
       console.log("You have an apple!");
       break;
     case 'banana':
       console.log("You have a banana!");
       break;
     default:
       console.log("Unknown fruit.");
   }
   ```

- `catch`
   - Example:
   ```javascript
   try {
     throw new Error("Oops!");
   } catch (error) {
     console.log(error.message);
   }
   ```

- `class`
   - Example:
   ```javascript
   class Animal {
     constructor(name) {
       this.name = name;
     }

     speak() {
       console.log(`${this.name} makes a sound.`);
     }
   }

   const dog = new Animal('Dog');
   dog.speak(); // Output: Dog makes a sound.
   ```

- `const`
   - Example:
   ```javascript
   const PI = 3.14;
   console.log(PI); // Output: 3.14
   ```

- `continue`
   - Example:
   ```javascript
   for (let i = 0; i < 5; i++) {
     if (i === 2) continue;
     console.log(i);
   }
   // Output: 0, 1, 3, 4
   ```

- `debugger`
   - Example:
   ```javascript
   debugger; // Pauses execution for debugging
   ```

- `default`
   - Example:
   ```javascript
   switch (fruit) {
     case 'apple':
       console.log("Apple");
       break;
     default:
       console.log("Unknown fruit");
   }
   ```

- `delete`
   - Example:
   ```javascript
   const obj = { name: "Alice" };
   delete obj.name;
   console.log(obj); // Output: {}
   ```

- `do`
   - Example:
   ```javascript
   let i = 0;
   do {
     console.log(i);
     i++;
   } while (i < 3);
   ```

- `else`
   - Example:
   ```javascript
   if (x > 10) {
     console.log("Big number");
   } else {
     console.log("Small number");
   }
   ```

- `export`
   - Example:
   ```javascript
   export const PI = 3.14;
   ```

- `extends`
   - Example:
   ```javascript
   class Dog extends Animal {
     bark() {
       console.log('Woof!');
     }
   }
   ```

- `finally`
   - Example:
   ```javascript
   try {
     // Some code
   } catch {
     console.log("Error caught");
   } finally {
     console.log("This runs no matter what");
   }
   ```

- `for`
   - Example:
   ```javascript
   for (let i = 0; i < 5; i++) {
     console.log(i);
   }
   ```

- `function`
   - Example:
   ```javascript
   function greet() {
     return "Hello!";
   }
   ```

- `if`
   - Example:
   ```javascript
   if (x > 10) {
     console.log("x is greater than 10");
   }
   ```

- `import`
   - Example:
   ```javascript
   import { PI } from './math.js';
   ```

- `in`
   - Example:
   ```javascript
   const car = { brand: "Toyota" };
   console.log("brand" in car); // true
   ```

- `instanceof`
   - Example:
   ```javascript
   const date = new Date();
   console.log(date instanceof Date); // true
   ```

- `new`
   - Example:
   ```javascript
   const obj = new Object();
   ```

- `return`
   - Example:
   ```javascript
   function add(a, b) {
     return a + b;
   }
   ```

- `super`
   - Example:
   ```javascript
   class Dog extends Animal {
     constructor(name) {
       super(name); // Calls parent constructor
     }
   }
   ```

- `switch`
   - Example:
   ```javascript
   switch (day) {
     case 'Monday':
       console.log('Start of the week');
       break;
     default:
       console.log('Another day');
   }
   ```

- `this`
   - Example:
   ```javascript
   const person = {
     name: "Alice",
     getName: function() {
       return this.name;
     }
   };
   console.log(person.getName()); // Output: Alice
   ```

- `throw`
   - Example:
   ```javascript
   throw new Error("Something went wrong");
   ```

- `try`
   - Example:
   ```javascript
   try {
     console.log("Try block");
   } catch (error) {
     console.log("Caught error");
   }
   ```

- `typeof`
   - Example:
   ```javascript
   console.log(typeof 123); // Output: number
   ```

- `var`
   - Example:
   ```javascript
   var x = 10;
   ```

- `void`
   - Example:
   ```javascript
   void function() {
     console.log("Immediately invoked function");
   }();
   ```

- `while`
   - Example:
   ```javascript
   let i = 0;
   while (i < 3) {
     console.log(i);
     i++;
   }
   ```

- `with`
   - Example:
   ```javascript
   with (Math) {
     console.log(sqrt(16)); // Output: 4
   }
   ```

- `yield`
   - Example:
   ```javascript
   function* generator() {
     yield 1;
     yield 2;
   }
   const gen = generator();
   console.log(gen.next().value); // Output: 1
   ```

