```js
/**
 * @param {string} val
 * @return {Object}
 */
var expect = function (val) {
  return {
    // toBe: (x) => x === val ? true : "Not Equal",
    toBe: (x) => {
      if (x !== val) {
        throw new Error("Not Equal");
      } else {
        return true;
      }
    },
    // notToBe: (x) => x !== val ? true : 'Equal'
    notToBe: (x) => {
      if (x === val) {
        throw new Error("Equal");
      } else {
        return true;
      }
    },
  };
};

/**
 * expect(5).toBe(5); // true
 * expect(5).notToBe(5); // throws "Equal"
 */
```
