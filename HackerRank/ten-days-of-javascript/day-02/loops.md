```js
/*
 * Complete the vowelsAndConsonants function.
 * Print your output using 'console.log()'.
 */
function vowelsAndConsonants(s) {
  const elStringEnUnArray = [...s];
  let vocales = ["a", "e", "i", "o", "u"].sort();
  const consonantes = [
    "b",
    "c",
    "d",
    "f",
    "g",
    "h",
    "j",
    "k",
    "l",
    "m",
    "n",
    "p",
    "q",
    "r",
    "s",
    "t",
    "v",
    "w",
    "x",
    "y",
    "z",
  ].sort();

  const misVocales = elStringEnUnArray.filter((letra) =>
    vocales.includes(letra)
  );
  const misConsonantes = elStringEnUnArray.filter((letra) =>
    consonantes.includes(letra)
  );

  const arrayDeLetras = [...misVocales, ...misConsonantes];

  const imprimirLetras = (index) => {
    if (index < arrayDeLetras.length) {
      console.log(arrayDeLetras[index]);
      imprimirLetras(index + 1);
    }
  };

  imprimirLetras(0);
}
```
