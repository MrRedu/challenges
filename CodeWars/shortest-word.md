# Shortest Word

Simple, given a string of words, return the length of the shortest word(s).

String will never be empty and you do not need to account for different data types.

<hr>

<details>
  <summary>
    <h3>Result</h3>
  </summary>

```js
function findShort(s) {
  const stringSplitted = s.split(" ");
  return stringSplitted.reduce((a, b) => (a.length <= b.length ? a : b)).length;
}
```

</details>
