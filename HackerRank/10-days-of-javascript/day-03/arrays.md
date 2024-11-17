```js
/**
 *   Return the second largest number in the array.
 *   @param {Number[]} nums - An array of numbers.
 *   @return {Number} The second largest number in the array.
 **/
function getSecondLargest(nums) {
  const numerosUnicos = [...new Set(nums)].sort((a, b) => a - b);
  const lengthDeNumerosUnicos = numerosUnicos.length;
  return numerosUnicos[lengthDeNumerosUnicos - 2];
}
```
