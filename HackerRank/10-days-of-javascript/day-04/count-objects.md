```js
/*
 * Return a count of the total number of objects 'o' satisfying o.x == o.y.
 *
 * Parameter(s):
 * objects: an array of objects with integer properties 'x' and 'y'
 */
function getCount(objects) {
  const result = objects.filter(({ x, y }) => x === y);
  return result.length;
}
```
