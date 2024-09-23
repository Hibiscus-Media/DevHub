# Super in JavaScript Classes

## 5.9 Understanding `super()` in JavaScript

The `super()` function is used in classes that inherit from other classes. It provides a way to call methods or the constructor of the parent class. This is crucial when extending the functionality of an existing class without having to duplicate code.

### 1. Using `super()` in the Constructor

When a class inherits from a parent class using the `extends` keyword, the constructor of the child class must call the `super()` function if it wants to access properties or methods defined in the parent class. This is done by invoking `super()` inside the child class’s constructor.

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
    super(name); // Calls the parent class constructor with the name argument
    this.breed = breed; // Adds a breed property specific to Dog
  }
}

const dog = new Dog("Max", "Labrador");
console.log(dog.name); // Output: Max
console.log(dog.breed); // Output: Labrador
```

### Explanation:
- **`super(name)`**: Calls the constructor of the parent class `Animal` and passes `name` as an argument. This ensures that the `name` property is set for both `Animal` and `Dog` objects.
- The **child class constructor** can add additional properties (`breed` in this example) while still inheriting from the parent.

---

### 2. Using `super()` to Call Parent Class Methods

In addition to calling the parent class constructor, you can use `super.methodName()` to call methods from the parent class.

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
    super(name);
    this.breed = breed;
  }

  speak() {
    super.speak(); // Calls the speak() method from the Animal class
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Max", "Labrador");
dog.speak();
// Output:
// Max makes a sound.
// Max barks.
```

### Explanation:
- **`super.speak()`**: Calls the `speak()` method from the parent class `Animal`, ensuring the base functionality (`makes a sound`) is retained. The `Dog` class then extends this functionality by adding `barks`.

---

### 3. When to Use `super()`

- **In Constructor**: You should always use `super()` in the constructor of a subclass to call the parent class's constructor, especially if the parent class has properties that need to be initialized.
  
  - Example:
    ```javascript
    class Vehicle {
      constructor(type) {
        this.type = type;
      }
    }

    class Car extends Vehicle {
      constructor(type, model) {
        super(type); // Calls the Vehicle constructor with the 'type' argument
        this.model = model;
      }
    }
    ```

- **In Methods**: Use `super.method()` when you want to extend or reuse the functionality of the parent class’s method.

  - Example:
    ```javascript
    class Parent {
      greet() {
        console.log("Hello from parent");
      }
    }

    class Child extends Parent {
      greet() {
        super.greet(); // Calls the parent's greet method
        console.log("Hello from child");
      }
    }
    ```

---

### Important Notes About `super()`:
1. **Must be the First Statement**: In a subclass constructor, `super()` must be called before accessing `this`. Failing to do so will result in a runtime error.
   
   ```javascript
   class Animal {
     constructor(name) {
       this.name = name;
     }
   }

   class Dog extends Animal {
     constructor(name, breed) {
       // super() must be called first
       this.breed = breed; // This will cause an error
       super(name);
     }
   }
   ```

   The above code will throw an error because `this.breed` is being accessed before `super()` is called. The correct way is to call `super()` first:
   
   ```javascript
   class Dog extends Animal {
     constructor(name, breed) {
       super(name); // Must call super() before accessing 'this'
       this.breed = breed;
     }
   }
   ```

2. **`super()` in Static Methods**: You can also use `super()` in static methods to call static methods of the parent class.

   ```javascript
   class Animal {
     static info() {
       return "This is an animal";
     }
   }

   class Dog extends Animal {
     static info() {
       return super.info() + " and a dog.";
     }
   }

   console.log(Dog.info()); // Output: This is an animal and a dog.
   ```

---

### Summary of `super()`

- **`super()` in Constructor**: Calls the parent class's constructor and allows you to initialize inherited properties.
- **`super.method()`**: Calls methods from the parent class, allowing you to reuse or extend functionality.
- **Must be First**: Always call `super()` before accessing `this` in the constructor.
- **Static Methods**: `super()` can also be used in static methods to call static methods from the parent class.

---

### Copyright Notice
© 2024 Andrew Bamford. All rights reserved.
