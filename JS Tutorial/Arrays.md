# JavaScript Data Structures

## 4.1 Arrays

An **array** is a list-like object used to store multiple values in a single variable. Arrays are zero-indexed, meaning the first element is at index 0.

### Creating an Array

You can create an array using square brackets `[]`.

```javascript
const fruits = ["apple", "banana", "cherry"];
console.log(fruits); // Output: ["apple", "banana", "cherry"]
```

### Accessing Elements in an Array

You can access array elements using their index.

```javascript
const firstFruit = fruits[0];
console.log(firstFruit); // Output: apple
```

### Modifying Elements in an Array

You can modify elements by directly referencing their index.

```javascript
fruits[1] = "blueberry";
console.log(fruits); // Output: ["apple", "blueberry", "cherry"]
```

---

### Common Array Methods

JavaScript provides several powerful methods for working with arrays. Below are some key methods:

#### `push()` and `pop()`
- `push()`: Adds an element to the end of an array.
- `pop()`: Removes the last element of an array.

```javascript
fruits.push("grape");
console.log(fruits); // Output: ["apple", "blueberry", "cherry", "grape"]

fruits.pop();
console.log(fruits); // Output: ["apple", "blueberry", "cherry"]
```

#### `shift()` and `unshift()`
- `shift()`: Removes the first element from an array.
- `unshift()`: Adds an element to the beginning of an array.

```javascript
fruits.shift();
console.log(fruits); // Output: ["blueberry", "cherry"]

fruits.unshift("pear");
console.log(fruits); // Output: ["pear", "blueberry", "cherry"]
```

#### `length`
The `length` property returns the number of elements in the array.

```javascript
console.log(fruits.length); // Output: 3
```

---

### Advanced Array Methods

#### `map()`
The `map()` method creates a new array by applying a function to each element in the array.

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```

#### `filter()`
The `filter()` method creates a new array with all elements that pass a test provided by a function.

```javascript
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

#### `reduce()`
The `reduce()` method reduces an array to a single value by executing a function for each element in the array.

```javascript
const sum = numbers.reduce((total, num) => total + num, 0);
console.log(sum); // Output: 10
```

#### `forEach()`
The `forEach()` method executes a function once for each element in the array.

```javascript
numbers.forEach(num => console.log(num * 2));
// Output: 2 4 6 8
```

#### `find()` and `findIndex()`
- `find()` returns the first element that satisfies a condition.
- `findIndex()` returns the index of the first element that satisfies a condition.

```javascript
const found = numbers.find(num => num > 2);
console.log(found); // Output: 3

const foundIndex = numbers.findIndex(num => num > 2);
console.log(foundIndex); // Output: 2
```

#### `concat()`
The `concat()` method is used to merge two or more arrays.

```javascript
const moreFruits = ["mango", "pineapple"];
const allFruits = fruits.concat(moreFruits);
console.log(allFruits); // Output: ["pear", "blueberry", "cherry", "mango", "pineapple"]
```

#### `slice()` and `splice()`
- `slice()` returns a shallow copy of a portion of an array.
- `splice()` adds/removes elements from an array.

```javascript
const sliced = fruits.slice(1, 3);
console.log(sliced); // Output: ["blueberry", "cherry"]

fruits.splice(1, 1, "kiwi");
console.log(fruits); // Output: ["pear", "kiwi", "cherry"]
```

---

### Looping Through Arrays

#### Using `for` Loop:
```javascript
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
// Output: pear kiwi cherry
```

#### Using `forEach()`:
```javascript
fruits.forEach(fruit => {
  console.log(fruit);
});
// Output: pear kiwi cherry
```

#### Using `for...of`:
```javascript
for (let fruit of fruits) {
  console.log(fruit);
}
// Output: pear kiwi cherry
```

---

### Destructuring Arrays

**Array destructuring** is a concise way to extract values from an array and assign them to variables.

```javascript
const [first, second] = fruits;
console.log(first); // Output: pear
console.log(second); // Output: kiwi
```

---

### Spread Operator in Arrays

The **spread operator** (`...`) allows you to expand elements from an array into individual elements.

#### Example:
```javascript
const moreNumbers = [5, 6, 7];
const combined = [...numbers, ...moreNumbers];
console.log(combined); // Output: [1, 2, 3, 4, 5, 6, 7]
```

---

### Summary of Arrays

- **Basic Methods**: `push()`, `pop()`, `shift()`, `unshift()`, `length`
- **Advanced Methods**: `map()`, `filter()`, `reduce()`, `forEach()`, `find()`, `findIndex()`
- **Looping**: Using `for` loops, `forEach()`, and `for...of`
- **Destructuring**: Easily extract values from arrays into variables.
- **Spread Operator**: Expand elements of an array into individual elements.

---

This concludes the **Arrays** section of JavaScript data structures. Next, we'll cover **Objects** and explore how to store and manipulate key-value pairs.
