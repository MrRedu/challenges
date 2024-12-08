# Day 7: Regular Expressions I

### **Objective**

In this challenge, we use a Regular Expression to evaluate a string. Check out the attached tutorial for more details.

### **Task**

Complete the function in the editor below by returning a RegExp object, _re_, that matches any string _s_ that begins and ends with the same vowel. Recall that the English vowels are `a`, `e`, `i`, `o`, and `u`.

### **Constraints**

- The length of string _s_ is >= 3.
- String _s_ consists of lowercase letters only (i.e., `[a-z]`).

### **Output Format**

The function must return a RegExp object that matches any string _s_ beginning with and ending in the same vowel.

#### Sample Input 0 (input -> output)

```
bcd --> false
```

#### Explanation 0

This string starts with (and ends in) a consonant, so it cannot start and end with the same vowel.

#### Sample Input 1 (input -> output)

```
abcd --> false
```

#### Explanation 1

This string ends in a consonant, so it cannot start and end with the same vowel.

#### Sample Input 2 (input -> output)

```
abcda --> true
```

#### Explanation 2

This string starts and ends with the same vowel `(a)`.

#### Sample Input 3 (input -> output)

```
abcdo --> false
```

#### Explanation 3

This string starts with the vowel `a` but ends in the vowel `o`.

<hr>

<details>
  <summary>
    <h3>Solution</h3>
  </summary>

```js
function regexVar() {
  /*
   * Declare a RegExp object variable named 're'
   * It must match a string that starts and ends with the same vowel (i.e., {a, e, i, o, u})
   */

  const re = /^(.).*\1$/;
  /*
   * Do not remove the return statement
   */
  return re;
}
```

</details>
