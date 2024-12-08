# Regular Expressions II

**Task**

Complete the function in the editor below by returning a RegExp object, `re`, that matches any string `s` satisfying both of the following conditions:

- String `s` starts with the prefix `Mr.`, `Mrs.`, `Ms.`, `Dr.`, or `Er.`
- The remainder of string `s` (i.e., the rest of the string after the prefix) consists of one or more upper and/or lowercase English alphabetic letters (i.e., `[a-z]` and `[A-Z]`).

**Constraints**

- The length of string `s` is `>= 3`.

**Output Format**

The function must return a RegExp object that matches any string `s` satisfying both of the given conditions.

**Sample Input -> Output 0**

```
Mr.X -> true
```

**Explanation 0**

This string starts with `Mr.`, followed by an English alphabetic letter `(X)`.

**Sample Input -> Output 1**

```
Mrs.Y -> true
```

**Explanation 1**

This string starts with `Mrs.`, followed by an English alphabetic letter `(Y)`.

**Sample Input -> Output 2**

```
Dr#Joseph -> false
```

**Explanation 2**

This string starts with `Dr#` instead of `Dr.`, so it's invalid.

**Sample Input -> Output 3**

```
Er .Abc -> false
```

**Explanation 3**

This string starts with `Er` but there is a space before the period `(.)`, making the string invalid.

<hr>

<details>
  <summary>
    <h3>Solution</h3>
  </summary>

```js
function regexVar() {
  /*
   * Declare a RegExp object variable named 're'
   * It must match a string that starts with 'Mr.', 'Mrs.', 'Ms.', 'Dr.', or 'Er.',
   * followed by one or more letters.
   */

  const re = /^(Mr\.|Mrs\.|Ms.\|Dr\.|Er\.).*/;

  /*
   * Do not remove the return statement
   */
  return re;
}
```

</details>
