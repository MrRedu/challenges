```js
function getLetter(s) {
  let letter;
  // Write your code here
  letter = s[0];

  switch (true) {
    case ["a", "e", "i", "o", "u"].includes(letter):
      return "A";
    case ["b", "c", "d", "f", "g"].includes(letter):
      return "B";
    case ["h", "j", "k", "l", "m"].includes(letter):
      return "C";
    default:
      return "D";
  }
}
```
