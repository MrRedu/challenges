# Convert an array of strings to array of numbers

Some really funny web dev gave you a sequence of numbers from his API response as an sequence of strings!

You need to cast the whole array to the correct type.

Create the function that takes as a parameter a sequence of numbers represented as strings and outputs a sequence of numbers.

**Example:**

```
  ["1", "2", "3"] => [1, 2, 3]
```

Note that you can receive floats as well.

<hr>

<details>
  <summary>
    <h3>Solution</h3>
  </summary>

```js
function toNumberArray(stringarray) {
  return stringarray.map((stringNumber) => Number(stringNumber));
}
```

</details>
