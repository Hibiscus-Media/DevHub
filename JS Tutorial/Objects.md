# JavaScript Objects

## 4.2 Objects

In JavaScript, an **object** is a collection of key-value pairs. Each key is a string (or symbol), and the value can be any data type, such as numbers, strings, arrays, or even other objects. Objects are used to represent real-world entities like people, places, and things.

### Creating an Object

You can create an object using curly braces `{}` and define key-value pairs inside.

#### Example:
```javascript
const person = {
  name: "Alice",
  age: 30,
  isEmployed: true
};
console.log(person);
// Output: { name: "Alice", age: 30, isEmployed: true }
```

---

### Accessing Object Properties

You can access the properties of an object using either **dot notation** or **bracket notation**.

#### Dot Notation:
```javascript
console.log(person.name); // Output: Alice
```

#### Bracket Notation:
```javascript
console.log(person["age"]); // Output: 30
```

Bracket notation is useful when the property name is dynamic or includes spaces.

---

### Modifying Object Properties

You can modify the value of an object's property using dot or bracket notation.

#### Example:
```javascript
person.age = 31;
console.log(person.age); // Output: 31
```

---

### Adding New Properties

You can add new properties to an object at any time.

#### Example:
```javascript
person.job = "Developer";
console.log(person.job); // Output: Developer
```

---

### Deleting Properties

You can remove a property from an object using the `delete` keyword.

#### Example:
```javascript
delete person.isEmployed;
console.log(person.isEmployed); // Output: undefined
```

---

### Checking if a Property Exists

You can check if a property exists in an object using the `in` operator.

#### Example:
```javascript
console.log("name" in person); // Output: true
console.log("salary" in person); // Output: false
```

---

### Looping Through Object Properties

You can loop through the keys or values of an object using the `for...in` loop.

#### Example:
```javascript
for (let key in person) {
  console.log(key + ": " + person[key]);
}
// Output:
// name: Alice
// age: 31
// job: Developer
```

---

### Object Methods

Objects can also have methods, which are functions stored as object properties.

#### Example:
```javascript
const car = {
  brand: "Toyota",
  model: "Camry",
  year: 2020,
  start: function() {
    console.log("The car has started.");
  }
};

car.start(); // Output: The car has started.
```

In this example, `start` is a method of the `car` object.

---

### Destructuring Objects

**Destructuring** allows you to extract properties from an object and assign them to variables in a concise manner.

#### Example:
```javascript
const { name, age } = person;
console.log(name); // Output: Alice
console.log(age);  // Output: 31
```

---

### Object Shorthand

If the variable name matches the object key, you can use **shorthand property names** when creating objects.

#### Example:
```javascript
const brand = "Honda";
const model = "Civic";
const year = 2021;

const car = { brand, model, year };
console.log(car);
// Output: { brand: "Honda", model: "Civic", year: 2021 }
```

---

### Object Methods: `Object.keys()`, `Object.values()`, `Object.entries()`

JavaScript provides built-in methods to work with objects:

- **`Object.keys()`**: Returns an array of the object's keys.
- **`Object.values()`**: Returns an array of the object's values.
- **`Object.entries()`**: Returns an array of the object's key-value pairs.

#### Example:
```javascript
const keys = Object.keys(person);
console.log(keys); // Output: ["name", "age", "job"]

const values = Object.values(person);
console.log(values); // Output: ["Alice", 31, "Developer"]

const entries = Object.entries(person);
console.log(entries); // Output: [["name", "Alice"], ["age", 31], ["job", "Developer"]]
```

---

### Merging Objects

You can merge two or more objects using the **spread operator** (`...`) or the `Object.assign()` method.

#### Example: Using Spread Operator
```javascript
const newInfo = { nationality: "Canadian", city: "Toronto" };
const updatedPerson = { ...person, ...newInfo };
console.log(updatedPerson);
// Output: { name: "Alice", age: 31, job: "Developer", nationality: "Canadian", city: "Toronto" }
```

#### Example: Using `Object.assign()`
```javascript
const updatedPerson2 = Object.assign({}, person, newInfo);
console.log(updatedPerson2);
// Output: { name: "Alice", age: 31, job: "Developer", nationality: "Canadian", city: "Toronto" }
```

---

### Freezing Objects

You can freeze an object to prevent any modifications using `Object.freeze()`.

#### Example:
```javascript
const frozenPerson = Object.freeze(person);
frozenPerson.age = 40; // This will not change the value
console.log(frozenPerson.age); // Output: 31
```

---

### Summary of Objects

- **Creating Objects**: Use `{}` to define key-value pairs.
- **Accessing/Modifying**: Use dot or bracket notation to access and modify properties.
- **Object Methods**: Store functions inside objects.
- **Destructuring**: Simplify extracting object properties into variables.
- **Built-in Methods**: Use `Object.keys()`, `Object.values()`, and `Object.entries()` to work with objects.
- **Merging Objects**: Use the spread operator or `Object.assign()` to merge objects.
- **Freezing Objects**: Prevent modifications with `Object.freeze()`.

---

This concludes the **Objects** section of JavaScript data structures. With arrays and objects covered, you're well-equipped to manage and manipulate data in JavaScript. Next, we can dive into more advanced topics like **Classes** or explore specific methods in more detail.
