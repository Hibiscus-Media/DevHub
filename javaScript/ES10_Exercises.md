# ES10 Exercises

Solve the below questions:

### #1 Turn this array into a new array: `[1,2,3,[4],[5]]`. Bonus if you can do it on one line.
```javascript
const array = [[1],[2],[3],[[[4]]],[[[5]]]];
// Solution:
console.log(array.flat(2)); // Output: [1, 2, 3, [4], [5]]
```

---

### #2 Turn this array into a new array: `[ 'Hello young grasshopper!', 'you are', 'learning fast!' ]`
```javascript
const greeting = [["Hello", "young", "grasshopper!"], ["you", "are"], ["learning", "fast!"]];
// Solution:
console.log(greeting.flatMap(x => x.join(' '))); 
// Output: ['Hello young grasshopper!', 'you are', 'learning fast!']
```

---

### #3 Turn the greeting array above into a string: `'Hello young grasshopper you are learning fast!'`
```javascript
// Solution:
console.log(greeting.flatMap(x => x.join(' ')).join(' '));
// Output: Hello young grasshopper you are learning fast!
```

---

### #4 Turn the trapped 3 number into: `[3]`
```javascript
const trapped = [[[[[[[[[[[[[[[[[[[[[[[[[[3]]]]]]]]]]]]]]]]]]]]]]]]]];
// Solution:
console.log(trapped.flat(Infinity)); // Output: [3]
```
Infinity is actually a LARGE number in JavaScript. It represents the maximum amount of memory that we can hold for a number! Learn more [here](https://riptutorial.com/javascript/example/2337/infinity-and--infinity).

---

### #5 Clean up this email to have no whitespaces. Make the answer be in a single line (return a new string):
```javascript
const userEmail3 = '     cannotfillemailformcorrectly@gmail.com   ';
// Solution:
console.log(userEmail3.trimEnd().trimStart()); 
// Output: 'cannotfillemailformcorrectly@gmail.com'
```

---

### #6 Turn the below users (value is their ID number) into an array: `[ [ 'user1', 18273 ], [ 'user2', 92833 ], [ 'user3', 90315 ] ]`
```javascript
const users = { user1: 18273, user2: 92833, user3: 90315 };
// Solution:
const usersArray = Object.entries(users);
console.log(usersArray); 
// Output: [['user1', 18273], ['user2', 92833], ['user3', 90315]]
```

---

### #7 Change the output array of the above to have the user's IDs multiplied by 2 — Should output: `[ [ 'user1', 36546 ], [ 'user2', 185666 ], [ 'user3', 180630 ] ]`
```javascript
// Solution:
const updatedUsersArray = usersArray.map(user => [user[0], user[1] * 2]);
console.log(updatedUsersArray); 
// Output: [['user1', 36546], ['user2', 185666], ['user3', 180630]]
```

---

### #8 Change the output array of question #7 back into an object with all the users' IDs updated to their new version. Should output: `{ user1: 36546, user2: 185666, user3: 180630 }`
```javascript
// Solution:
const updatedUsers = Object.fromEntries(updatedUsersArray);
console.log(updatedUsers); 
// Output: { user1: 36546, user2: 185666, user3: 180630 }
```

---

### Additional Exercises:

### #9 Use `flatMap()` to create a new array where each element is doubled and flattened: `[1, 2, 3, 4, 5]` => `[2, 4, 6, 8, 10]`
```javascript
const numbers = [1, [2], 3, [4], 5];
// Solution:
console.log(numbers.flatMap(num => [num * 2]));
// Output: [2, 4, 6, 8, 10]
```

---

### #10 Remove all nullish values (`null`, `undefined`) from this array: `[1, 2, null, 4, undefined, 6]`
```javascript
const values = [1, 2, null, 4, undefined, 6];
// Solution:
const cleanValues = values.filter(value => value !== null && value !== undefined);
console.log(cleanValues); 
// Output: [1, 2, 4, 6]
```

---

### #11 Use `Object.fromEntries()` to convert a map of user information into an object:
```javascript
const userEntries = new Map([
  ['name', 'Alice'],
  ['age', 30],
  ['job', 'Engineer']
]);
// Solution:
const userObject = Object.fromEntries(userEntries);
console.log(userObject);
// Output: { name: 'Alice', age: 30, job: 'Engineer' }
```

---

### #12 Use `Array.prototype.flat()` to flatten an array of arrays of arrays to a depth of 1.
```javascript
const nestedArr = [[1, 2], [3, [4, 5]], [[6, 7]]];
// Solution:
const flattenedArr = nestedArr.flat(1);
console.log(flattenedArr);
// Output: [1, 2, 3, [4, 5], [6, 7]]
```

---

### Summary of Key ES10 Features Covered:
1. **Array Methods**: `flat()`, `flatMap()`
2. **String Methods**: `trimStart()`, `trimEnd()`
3. **Object Methods**: `Object.entries()`, `Object.fromEntries()`
4. **Deep Array Flattening**: Using `Infinity` with `flat()`.

---

### Copyright Notice
© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
