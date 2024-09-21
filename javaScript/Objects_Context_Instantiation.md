# JavaScript Objects, Context, and Instantiation

In this guide, we'll explore some fundamental concepts in JavaScript: reference types, context vs. scope, and object instantiation using classes. We'll use code examples to illustrate how these concepts work.

```javascript
// Reference Type Example
var object1 = { value: 10 };
var object2 = object1;
var object3 = { value: 10 };

// Objects are created by the programmer.
// object1 and object2 reference the same object in memory.
// object3 is a separate object with the same value.
```

**Explanation:**

- `object1` is an object with a property `value` set to `10`.
- `object2` is assigned to `object1`, so both variables reference the **same** object in memory.
- Changing `object2.value` would also change `object1.value` because they point to the same object.
- `object3` is a new object with its own `value`. It's separate from `object1` and `object2`.

---

```javascript
// Context vs. Scope Example
const object4 = {
  a: function() {
    console.log(this);
  }
};

// Context tells you where you are within the object.
// When object4.a() is called, 'this' refers to object4.
```

**Explanation:**

- The `a` function logs `this` to the console.
- When you call `object4.a()`, `this` refers to `object4`, so it will log the `object4` object.
- **Context** refers to the value of `this` within a function, depending on how the function is invoked.
- **Scope** refers to the visibility of variables within your code.

---

```javascript
// Instantiation Example (Making Instances of an Object)
class Player {
  constructor(name, type) {
    console.log('player', this);
    this.name = name;
    this.type = type;
  }

  introduce() {
    console.log(`Hi, I am ${this.name}, I'm a ${this.type}`);
  }
}

class Wizard extends Player {
  constructor(name, type) {
    super(name, type);
    console.log('wizard', this);
  }

  play() {
    console.log(`WEEEEE! I'm a ${this.type}`);
  }
}

const wizard1 = new Wizard('Shelly', 'Healer');
const wizard2 = new Wizard('Sean', 'Dark Magician');

// Usage:
wizard1.introduce(); // Outputs: Hi, I am Shelly, I'm a Healer
wizard1.play();      // Outputs: WEEEEE! I'm a Healer

wizard2.introduce(); // Outputs: Hi, I am Sean, I'm a Dark Magician
wizard2.play();      // Outputs: WEEEEE! I'm a Dark Magician
```

**Explanation:**

- **Player Class**:
  - Defines a constructor that initializes `name` and `type`.
  - `introduce()` method allows the instance to introduce itself.
  - `console.log('player', this);` logs the instance when a new `Player` is created.

- **Wizard Class**:
  - Inherits from `Player` using the `extends` keyword.
  - Calls `super(name, type);` to invoke the parent class constructor.
  - Adds a `play()` method unique to `Wizard` instances.
  - `console.log('wizard', this);` logs the instance when a new `Wizard` is created.

- **Instantiation**:
  - `wizard1` and `wizard2` are new instances of `Wizard`.
  - They inherit properties and methods from `Player`.
  - They can use both `introduce()` and `play()` methods.

**Key Concepts:**

- **Classes and Inheritance**:
  - Classes in JavaScript are templates for creating objects with shared properties and methods.
  - The `extends` keyword allows one class to inherit from another.
  - The `super()` function calls the parent class's constructor.

- **Instantiation**:
  - The `new` keyword creates a new instance of a class.
  - Each instance has its own set of properties but shares methods defined in the class.

- **Context (`this` keyword)**:
  - Inside methods, `this` refers to the instance of the class.
  - The value of `this` depends on how a function is called.

By understanding these concepts, you can create complex and organized code structures, making your JavaScript applications more efficient and easier to maintain.


### License and Usage Terms

© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
