# ES7 Features and Using `filter()` with `includes()`

## Introduction

This document provides an in-depth exploration of **ES7 features** and demonstrates how to effectively use the `filter()` method in conjunction with `includes()` in JavaScript to manipulate arrays efficiently.

## Main Content

- **ES7 Features**
  - **Array `includes()` Method**
    - Introduced in ES7 to check if an array contains a specific value.
    - Returns a boolean (`true` or `false`).
    - *Example:*
      ```javascript
      const numbers = [1, 2, 3, 4, 5];
      console.log(numbers.includes(3)); // Output: true
      ```
  - **Exponentiation Operator `**`**
    - Provides a shorthand for exponentiation operations.
    - Replaces the `Math.pow()` function.
    - *Example:*
      ```javascript
      console.log(2 ** 3); // Output: 8
      ```
- **Using `filter()` with `includes()`**
  - **Understanding the `filter()` Method**
    - Creates a new array with all elements that pass the test implemented by the provided function.
    - *Syntax:*
      ```javascript
      array.filter(callback(element[, index[, array]])[, thisArg])
      ```
  - **Combining `filter()` and `includes()`**
    - **Subpoint A: Filtering Based on Inclusion Criteria**
      - Keep elements that are present in another array.
      - *Example:*
        ```javascript
        const availableColors = ['red', 'green', 'blue', 'yellow'];
        const colorsToDisplay = ['red', 'blue'];
        
        const displayedColors = availableColors.filter(color => colorsToDisplay.includes(color));
        console.log(displayedColors); // Output: ['red', 'blue']
        ```
    - **Subpoint B: Filtering Based on Exclusion Criteria**
      - Exclude elements that are present in another array.
      - *Example:*
        ```javascript
        const allUsers = ['Alice', 'Bob', 'Charlie', 'Dave'];
        const usersToExclude = ['Bob', 'Dave'];
        
        const activeUsers = allUsers.filter(user => !usersToExclude.includes(user));
        console.log(activeUsers); // Output: ['Alice', 'Charlie']
        ```

## Conclusion

In summary, ES7 introduced significant enhancements like the `includes()` method for arrays and the exponentiation operator `**`, simplifying common operations in JavaScript. Utilizing `filter()` in combination with `includes()` allows developers to write more concise and readable code for array manipulation, whether filtering based on inclusion or exclusion criteria.


### License and Usage Terms

© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
