```js
/*
 * Modify and return the array so that all even elements are doubled and all odd elements are tripled.
 *
 * Parameter(s):
 * nums: An array of numbers.
 */
function modifyArray(nums) {
  return nums.map((number) => {
    if (number % 2 === 0) {
      return number * 2;
    } else {
      // number % 3 === 0 ?
      return number * 3;
    }
  });
}
```
