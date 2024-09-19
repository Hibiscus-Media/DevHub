# Understanding Instantiation in JavaScript

**Instantiation** in object-oriented programming refers to the process of creating specific instances of a class or object that contain real values instead of placeholders. This concept is fundamental in JavaScript, especially when dealing with classes and objects. Below, we'll discuss instantiation using sample code from an employee management system.

## Reference Types

```javascript
// Reference Type
var object1 = { value: 10 };
var object2 = object1;
var object3 = { value: 10 };

// Objects are created by the programmer
```

**Explanation:**

- `object1` is an object with a property `value` equal to `10`.
- `object2` is assigned to `object1`, so both reference the same object in memory.
- Modifying `object2.value` will affect `object1.value` because they point to the same object.
- `object3` is a new object with the same property but is a separate entity in memory.

## Context vs. Scope

```javascript
// Context vs. Scope
const object4 = {
  a: function() {
    console.log(this);
  }
};

// Context tells you where you are in the object
```

**Explanation:**

- The function `a` logs `this`, which refers to the context in which the function is called.
- When you call `object4.a()`, `this` refers to `object4`.
- **Context** is about the object to which a function belongs.
- **Scope** pertains to the visibility and lifetime of variables (where they can be accessed).

## Instantiation (Making Instances of an Object)

```javascript
// Instantiation
// (Making instances of an object)
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
    console.log(`WEEEEE I'm a ${this.type}`);
  }
}

const wizard1 = new Wizard('Shelly', 'Healer');
const wizard2 = new Wizard('Sean', 'Dark Magician');
```

**Explanation:**

- **Player Class:**
  - A blueprint for creating player objects with `name` and `type`.
  - The `constructor` method initializes new instances.
  - The `introduce` method allows the player to introduce themselves.
- **Wizard Class:**
  - Inherits from `Player` using `extends`.
  - Uses `super(name, type)` to call the parent class constructor.
  - Adds a `play` method specific to wizards.
- **Instantiation:**
  - `wizard1` and `wizard2` are new instances of `Wizard`.
  - Each wizard has unique properties but shares methods from `Player`.

## Using the Instances

```javascript
wizard1.introduce(); // Output: Hi, I am Shelly, I'm a Healer
wizard1.play();      // Output: WEEEEE I'm a Healer

wizard2.introduce(); // Output: Hi, I am Sean, I'm a Dark Magician
wizard2.play();      // Output: WEEEEE I'm a Dark Magician
```

## Key Concepts

- **Instantiation:**
  - The process of creating individual objects from a class.
  - Each instance has its own set of properties and can access shared methods.
- **Inheritance:**
  - Classes can inherit properties and methods from parent classes.
  - Promotes code reusability and organization.
- **The `this` Keyword:**
  - Refers to the current instance of the class.
  - Its value depends on the context in which a function is called.

## Conclusion

Instantiation is a core principle in object-oriented programming that allows you to create multiple, unique objects from a single class template. In the employee management system example, we demonstrated how to use classes to define templates (`Player` and `Wizard`) and instantiate them to create individual objects (`wizard1` and `wizard2`).

By mastering instantiation, you can:

- **Create Modular Code:** Build reusable and maintainable code structures.
- **Manage Complex Systems:** Efficiently handle multiple objects with shared characteristics.
- **Enhance Readability:** Keep your code organized and intuitive.

Understanding instantiation and related concepts like context and inheritance is essential for developing robust applications in JavaScript.
