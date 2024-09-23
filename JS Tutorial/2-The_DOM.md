# JavaScript and the DOM

## 9.1 Introduction to the DOM

The **Document Object Model (DOM)** is a programming interface for web documents. It represents the structure of a webpage as a tree of objects that can be manipulated with JavaScript. With the DOM, you can access and modify elements, attributes, and content on a web page.

---

### 9.2 Selecting DOM Elements

To manipulate the DOM, you need to first select elements. JavaScript provides various methods to select DOM elements.

#### Example: `getElementById()`
```javascript
const heading = document.getElementById("main-heading");
console.log(heading);
```

#### Example: `querySelector()` (CSS Selector)
```javascript
const firstParagraph = document.querySelector("p");
console.log(firstParagraph);
```

#### Example: `querySelectorAll()` (Multiple Elements)
```javascript
const allParagraphs = document.querySelectorAll("p");
console.log(allParagraphs); // NodeList of all <p> elements
```

### Common Methods for Selecting Elements:
- `getElementById()`
- `getElementsByClassName()`
- `getElementsByTagName()`
- `querySelector()` (selects the first matching element)
- `querySelectorAll()` (selects all matching elements)

---

### 9.3 Modifying DOM Elements

Once you’ve selected an element, you can change its content, style, or attributes.

#### Example: Changing Text Content
```javascript
const heading = document.getElementById("main-heading");
heading.textContent = "Welcome to My Website!";
```

#### Example: Changing HTML Content
```javascript
const container = document.getElementById("content");
container.innerHTML = "<h2>New Subheading</h2>";
```

#### Example: Modifying Styles
```javascript
const heading = document.getElementById("main-heading");
heading.style.color = "blue";
heading.style.fontSize = "2rem";
```

#### Example: Changing Attributes
```javascript
const link = document.querySelector("a");
link.setAttribute("href", "https://www.example.com");
```

---

### 9.4 Creating and Removing Elements

You can also create new elements and remove existing ones using JavaScript.

#### Example: Creating a New Element
```javascript
const newDiv = document.createElement("div");
newDiv.textContent = "This is a new div element.";
document.body.appendChild(newDiv);
```

#### Example: Removing an Element
```javascript
const oldElement = document.getElementById("old-element");
oldElement.remove();
```

---

### 9.5 Event Handling

You can add **event listeners** to elements to respond to user actions like clicks, keypresses, or form submissions.

#### Example: Click Event
```javascript
const button = document.querySelector("button");
button.addEventListener("click", () => {
  alert("Button was clicked!");
});
```

#### Example: Keypress Event
```javascript
document.addEventListener("keydown", (event) => {
  console.log(`Key pressed: ${event.key}`);
});
```

### Common Event Types:
- `click`
- `mouseover`
- `keydown`
- `submit`
- `input`

---

### 9.6 DOM Traversal

You can navigate between DOM elements using **parent**, **child**, and **sibling** relationships.

#### Example: Accessing Parent Element
```javascript
const childElement = document.querySelector(".child");
const parentElement = childElement.parentElement;
console.log(parentElement);
```

#### Example: Accessing Child Elements
```javascript
const parent = document.getElementById("parent");
const children = parent.children;
console.log(children); // HTMLCollection of child elements
```

#### Example: Accessing Sibling Elements
```javascript
const sibling = document.querySelector(".first-sibling");
const nextSibling = sibling.nextElementSibling;
console.log(nextSibling); // Logs the next sibling element
```

---

### 9.7 Forms and User Input

You can interact with forms and user input by getting values from form elements and validating data.

#### Example: Getting Input Value
```javascript
const inputField = document.querySelector("#name-input");
const submitButton = document.querySelector("#submit-btn");

submitButton.addEventListener("click", () => {
  const inputValue = inputField.value;
  console.log("User input:", inputValue);
});
```

---

### Summary of DOM

- **Selecting Elements**: Use `getElementById()`, `querySelector()`, and `querySelectorAll()` to select DOM elements.
- **Modifying Elements**: Change text, HTML content, styles, or attributes.
- **Creating/Removing Elements**: Dynamically create and remove elements in the DOM.
- **Event Handling**: Add event listeners to handle user interactions like clicks, keypresses, and more.
- **DOM Traversal**: Navigate between parent, child, and sibling elements.
- **Forms**: Interact with forms and process user input.

---

### Copyright Notice
© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.

