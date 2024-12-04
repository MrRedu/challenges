Given a number `n`, draw stairs using the letter `"I"`, `n` tall and `n` wide, with the tallest in the top left.

For example `n = 3` result in:

```
"I\n I\n  I"
```

or printed:

```
I
 I
  I
```

Another example, a 7-step stairs should be drawn like this:

```
I
 I
  I
   I
    I
     I
      I
```

<hr>

### Result

```js
function drawStairs(n) {
  let voidArray = new Array(n).fill(null);
  return voidArray
    .map((element, index) => `I`.padStart(index + 1, " "))
    .join("\n");
}
```
