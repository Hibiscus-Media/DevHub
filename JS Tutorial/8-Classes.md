# JavaScript Classes

## 5.1 Introduction to Classes

A **class** in JavaScript is a blueprint for creating objects with shared properties and methods. It was introduced in ES6 and provides a more structured way to implement **object-oriented programming**.

### Defining a Class

A class is defined using the `class` keyword. You can then create objects (or instances) of the class using the `new` keyword.

#### Example:
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const alice = new Person("Alice", 30);
alice.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

### Explanation:
- **`constructor()`**: A special method for creating and initializing an object when a class is instantiated. It sets the initial values for `name` and `age`.
- **`this`**: Refers to the current instance of the class.
- **`greet()`**: A method defined inside the class that can be called on instances.

---

### 5.2 Creating Multiple Instances

You can create multiple instances of a class, each with its own properties.

#### Example:
```javascript
const bob = new Person("Bob", 25);
bob.greet(); // Output: Hello, my name is Bob and I am 25 years old.

const charlie = new Person("Charlie", 35);
charlie.greet(); // Output: Hello, my name is Charlie and I am 35 years old.
```

---

### 5.3 Class Methods

Classes can have multiple methods. These methods can perform actions on the properties of the object.

#### Example:
```javascript
class Calculator {
  add(a, b) {
    return a + b;
  }

  subtract(a, b) {
    return a - b;
  }
}

const calc = new Calculator();
console.log(calc.add(5, 3)); // Output: 8
console.log(calc.subtract(5, 3)); // Output: 2
```

---

### 5.4 Getters and Setters

**Getters** and **setters** allow you to control how properties are accessed or modified. They are used to define custom behavior for retrieving and setting values.

#### Example:
```javascript
class Person {
  constructor(name) {
    this._name = name; // Underscore convention for private variables
  }

  get name() {
    return this._name.toUpperCase(); // Getter returns name in uppercase
  }

  set name(newName) {
    this._name = newName;
  }
}

const person = new Person("Alice");
console.log(person.name); // Output: ALICE

person.name = "Bob";
console.log(person.name); // Output: BOB
```

---

### 5.5 Inheritance

**Inheritance** allows you to create a class that inherits properties and methods from another class. This is useful for creating subclasses that share some characteristics with a parent class but also have their own unique behavior.

#### Example:
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Calls the constructor of the parent class (Animal)
    this.breed = breed;
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Max", "Labrador");
dog.speak(); // Output: Max barks.
```

### Explanation:
- **`extends`**: This keyword is used to create a class that is a subclass of another class.
- **`super()`**: Used to call the constructor of the parent class.

---

### 5.6 Static Methods

**Static methods** are defined on the class itself and not on instances of the class. These methods can be called directly on the class.

#### Example:
```javascript
class MathUtils {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathUtils.add(10, 5)); // Output: 15
```

In this example, `add()` is a static method that can be called directly on the `MathUtils` class.

---

### 5.7 Private Fields (ES2022)

In ES2022, private fields were introduced. Private fields are variables that can only be accessed inside the class and are declared with a `#` prefix.

#### Example:
```javascript
class BankAccount {
  #balance = 0; // Private field

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount();
account.deposit(100);
console.log(account.getBalance()); // Output: 100
console.log(account.#balance); // Error: Private field '#balance' must be declared in an enclosing class
```

In this example, the `#balance` field is private and cannot be accessed outside the class.

---

### 5.8 Class Fields

Class fields allow you to define properties directly within the class body without needing to use a constructor.

#### Example:
```javascript
class Car {
  brand = "Toyota"; // Class field

  getBrand() {
    return this.brand;
  }
}

const car = new Car();
console.log(car.getBrand()); // Output: Toyota
```

---

### Summary of Classes

- **Classes**: Use the `class` keyword to define a class.
- **Constructors**: Initialize an object's properties using the `constructor()` method.
- **Methods**: Functions defined inside a class.
- **Getters/Setters**: Control how properties are accessed or set.
- **Inheritance**: Use `extends` to create subclasses.
- **Static Methods**: Define methods on the class itself, not on instances.
- **Private Fields**: Use `#` to define private properties that can't be accessed outside the class.
- **Class Fields**: Directly define properties within the class body.

---

### Copyright Notice
© 2024 Andrew Bamford. All rights reserved.

---

This concludes the **Classes** section. We've covered how to create classes, inheritance, static methods, getters, setters, and private fields. Next, we can move into more advanced topics like **Asynchronous JavaScript**, where we will explore **callbacks**, **promises**, and **async/await**.
