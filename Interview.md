> What difference between map and forEach in javascript?

````javascript

In JavaScript, both `map` and `forEach` are array methods used for iterating over array elements. However, they serve different purposes and have different behaviors. Here are the key differences between them:

### Purpose and Return Value

**forEach**:
- **Purpose**: Executes a provided function once for each array element.
- **Return Value**: `undefined`. It does not return a new array; it simply executes the function for each array element.

```javascript
const arr = [1, 2, 3];
arr.forEach(element => {
    console.log(element * 2); // Output: 2, 4, 6 (in the console)
});
console.log(arr); // Output: [1, 2, 3]
````

**map**:

- **Purpose**: Creates a new array populated with the results of calling a provided function on every element in the calling array.
- **Return Value**: A new array with each element being the result of the callback function.

```javascript
const arr = [1, 2, 3];
const doubled = arr.map((element) => element * 2);
console.log(doubled); // Output: [2, 4, 6]
console.log(arr); // Output: [1, 2, 3]
```

### Use Cases

**forEach**:

- Best used when you need to perform side effects for each array element, such as logging, updating the DOM, or modifying external variables.

**map**:

- Best used when you need to transform each element in an array and get a new array with these transformed elements.

### Modifying the Original Array

Neither `forEach` nor `map` modifies the original array. However, if you modify the elements themselves within the callback function, the original array will be affected in both cases.

### Example Comparison

**Using `forEach`**:

```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num, index) => {
  numbers[index] = num * 2; // Modifying the original array
});
console.log(numbers); // Output: [2, 4, 6, 8, 10]
```

**Using `map`**:

```javascript
const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = numbers.map((num) => num * 2); // Creating a new array
console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]
console.log(numbers); // Output: [1, 2, 3, 4, 5]
```

### Performance

- **forEach**: Generally slightly faster because it doesn’t need to create and return a new array.
- **map**: May have a slight overhead due to the creation of a new array, but this is usually negligible.

### Summary

- **forEach**: Executes a function for each array element. Suitable for performing side effects. Does not return a new array.
- **map**: Executes a function for each array element and returns a new array of the results. Suitable for transforming data.

Choosing between `forEach` and `map` depends on whether you need the results of the iteration to be returned as a new array or not. If you need the new array, use `map`. If you just need to perform operations on each element without needing a new array, use `forEach`.

```

```
