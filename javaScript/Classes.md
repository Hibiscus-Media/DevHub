# Introduction to JavaScript Classes

In JavaScript, classes are a blueprint for creating objects with predefined properties and methods. They provide a clear and concise way to structure code, enabling better organization and reuse. This guide will introduce you to the concept of classes in JavaScript using an `Employee` class as an example. A class in JavaScript is a template for creating objects that share common properties and methods. Classes encapsulate data and functionality, making your code more modular and easier to maintain. Classes are defined using the `class` keyword followed by the class name and a set of curly braces `{}`.

```javascript
class Employee { 
    // Class body 
}
```

Class names are typically written in PascalCase (e.g., Employee, Person, Car). The constructor is a special method invoked when a new instance of the class is created. It initializes the object's properties.

```javascript
class Employee { 
    constructor(name, role, salary) { 
        this.name = name; 
        this.role = role; 
        this.salary = salary; 
    } 
}
```

In this example, `name`, `role`, and `salary` are the parameters passed when creating a new employee object. The `this` keyword is used to refer to the current instance of the object being created. A class can contain methods, which are functions that represent behaviors or actions an object can perform.

```javascript
class Employee { 
    constructor(name, role, salary) { 
        this.name = name; 
        this.role = role; 
        this.salary = salary; 
    }

    showInfo() { 
        console.log(`Employee Name: ${this.name}, Role: ${this.role}, Salary: $${this.salary}`); 
    } 
}
```

In this example, the `showInfo` method is defined inside the class and prints the employee's information. To create an instance (an object) of a class, use the `new` keyword. This invokes the constructor and creates a new object.

```javascript
const emp1 = new Employee('Alice', 'Software Developer', 85000);
```

In this example, `emp1` is a new object with the properties `name`, `role`, and `salary` initialized to `'Alice'`, `'Software Developer'`, and `85000`, respectively. You can call methods on class instances to perform actions. For example:

```javascript
emp1.showInfo();
```

This will output:

```
Employee Name: Alice, Role: Software Developer, Salary: $85000
```

The `showInfo` method prints the employee's details by accessing the object’s properties using the `this` keyword. Classes in JavaScript provide a structured way to create objects that share common properties and methods. By using constructors and defining methods within classes, you can create modular, reusable, and maintainable code. In this example, we used an `Employee` class to demonstrate the creation of objects and how to define and call methods. This approach makes it easy to work with multiple objects of the same type, ensuring your code is organized and easy to manage.
