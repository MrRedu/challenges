# Persistent Bugger

Write a function, `persistence`, that takes in a positive parameter `num` and returns its multiplicative persistence, which is the number of times you must multiply the digits in `num` until you reach a single digit.

For example **(Input --> Output)**:

```
  39 --> 3 (because 3*9 = 27, 2*7 = 14, 1*4 = 4 and 4 has only one digit, there are 3 multiplications)
  999 --> 4 (because 9*9*9 = 729, 7*2*9 = 126, 1*2*6 = 12, and finally 1*2 = 2, there are 4 multiplications)
  4 --> 0 (because 4 is already a one-digit number, there is no multiplication)
```

<hr>

<details>
  <summary>
    <h3>Result</h3>
  </summary>

```js
const product = (numbers) => {
  return numbers.reduce((a, v) => a * v, 1);
};

const numberSplitted = (num) => {
  return [...num.toString()].map((n) => Number(n));
};

function persistence(num) {
  let times = 0;

  const sumTimes = () => {
    times++;
  };

  if (num.toString().length === 1) return times;

  const reCall = (total) => {
    sumTimes();
    if (total.toString().length > 1) {
      return reCall(product(numberSplitted(total)));
    } else {
      return times;
    }
  };

  let total = product(numberSplitted(num));
  return reCall(total);
}
```

</details>
