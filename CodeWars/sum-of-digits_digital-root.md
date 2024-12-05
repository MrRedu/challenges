# Sum of Digits (Digital root)

Digital root is the recursive sum of all the digits in a number.

Given `n`, take the sum of the digits of `n`. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.

Examples

```
    16  -->  1 + 6 = 7
   942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6
132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6
493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2
```

<hr>

<details>
  <summary>
    <h3>Result</h3>
  </summary>

```js
const convertNumberInArrayOfNumbers = (number) => {
  const numbersArray = [...number.toString()]; // -> 789 => ['7', '8', '9']
  const realNumbersArray = numbersArray.map((n) => Number(n)); // -> ['7', '8', '9'] => [7, 8, 9]
  return realNumbersArray;
};

const sumNumbersArray = (numbersArray) => {
  // numbersArray = [1, 2, 3]
  let total = 0;
  for (let number of numbersArray) {
    total += number;
  }
  // total = 0 + 1 === 1
  // total = 1 + 2 === 3
  // total = 3 + 3 === 6
  return total; //  6
};

const reCall = (total) => {
  if (total.toString().length > 1) {
    return reCall(sumNumbersArray(convertNumberInArrayOfNumbers(total)));
  } else {
    return total;
  }
};

function digitalRoot(n) {
  let total = 0;
  total = sumNumbersArray(convertNumberInArrayOfNumbers(n));
  return reCall(total);
}
```

</details>
