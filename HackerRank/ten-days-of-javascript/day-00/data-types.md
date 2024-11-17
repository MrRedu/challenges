```js
/**
 *   Print three lines:
 *
 *	Parameter(s):
 *   secondInteger - The string representation of an integer.
 *   secondDecimal - The string representation of a floating-point number.
 *   secondString - A string consisting of one or more space-separated words.
 **/
function performOperation(secondInteger, secondDecimal, secondString) {
  const firstInteger = 4;
  const firstDecimal = 4.0;
  const firstString = "HackerRank ";

  // Write code that uses console.log to print the sum of the 'firstInteger' and 'secondInteger' (converted to a Number        type) on a new line.
  const numberOne = Number(secondInteger);
  console.log(firstInteger + numberOne);

  // Write code that uses console.log to print the sum of 'firstDecimal' and 'secondDecimal' (converted to a Number            type) on a new line.
  const numberTwo = Number(secondDecimal);
  console.log(firstDecimal + numberTwo);

  // Write code that uses console.log to print the concatenation of 'firstString' and 'secondString' on a new line. The variable 'firstString' must be printed first.
  console.log(firstString + secondString);
}
```
