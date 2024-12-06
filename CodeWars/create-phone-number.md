# Create phone number

Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

**Example**

```
  createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]) // => returns "(123) 456-7890"
```

The returned format must be correct in order to complete this challenge.
Don't forget the space after the closing parentheses!

<hr>

<details>
  <summary>
    <h3>Solution</h3>
  </summary>

```js
function createPhoneNumber(numbers) {
  const newNumbers = [...numbers].map((number) => number.toString());
  newNumbers.splice(0, 0, "(");
  newNumbers.splice(4, 0, ")");
  newNumbers.splice(5, 0, " ");
  newNumbers.splice(9, 0, "-");
  return newNumbers.join("");

  // Real solution xd
  // return numbers.join('').replace(/(\d{3})(\d{3})(\d{4})/, '($1) $2-$3');
}
```

</details>
