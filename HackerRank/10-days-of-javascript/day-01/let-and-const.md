```js
function main() {
  // Write your code here. Read input using 'readLine()' and print output using 'console.log()'.
  const PI = Math.PI;
  const radio = readLine();
  // Print the area of the circle:
  const area = PI * Math.pow(radio, 2);
  // Print the perimeter of the circle:
  const perimetro = 2 * PI * radio;

  // console.log(radio)
  console.log(area);
  console.log(perimetro);

  try {
    // Attempt to redefine the value of constant variable PI
    PI = 0;
    // Attempt to print the value of PI
    console.log(PI);
  } catch (error) {
    console.error("You correctly declared 'PI' as a constant.");
  }
}
```
