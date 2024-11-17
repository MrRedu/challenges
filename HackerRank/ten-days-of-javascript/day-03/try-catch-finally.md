```js
/*
 * Complete the reverseString function
 * Use console.log() to print to stdout.
 */
function reverseString(s) {
  try {
    if (typeof s !== "string") throw new Error("s.split is not a function");

    console.log([...s].reverse().join(""));
  } catch (error) {
    console.log(error.message);
    console.log(s);
  }
}
```
