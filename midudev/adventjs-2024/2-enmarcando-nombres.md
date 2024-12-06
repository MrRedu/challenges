**Santa Claus** 🎅 quiere enmarcar los nombres de los niños buenos para decorar su taller 🖼️, pero el marco debe cumplir unas reglas específicas. Tu tarea es ayudar a los elfos a generar este marco mágico.

Reglas:

- Dado un array de nombres, debes crear un marco rectangular que los contenga a todos.
- Cada nombre debe estar en una línea, alineado a la izquierda.
- El marco está construido con \* y tiene un borde de una línea de ancho.
- La anchura del marco se adapta automáticamente al nombre más largo más un margen de 1 espacio a cada lado.

Ejemplo de funcionamiento:

```js
createFrame(['midu', 'madeval', 'educalvolpz'])

// Resultado esperado:
***************
* midu        *
* madeval     *
* educalvolpz *
***************

createFrame(['midu'])

// Resultado esperado:
********
* midu *
********

createFrame(['a', 'bb', 'ccc'])

// Resultado esperado:
*******
* a   *
* bb  *
* ccc *
*******

createFrame(['a', 'bb', 'ccc', 'dddd'])
```

<hr>

### Solution

```js
function createFrame(names) {
  // Code here
  const maxLength = Math.max(...names.map((name) => name.length));
  const tamanoMarco = maxLength + 4;

  let result = "";
  const marcoTopButton = "*".repeat(tamanoMarco) + "\n";
  //  ****************
  result += "*".repeat(tamanoMarco) + "\n";

  for (let i = 0; i < names.length; i++) {
    const lineaConNombre = `* ${names[i]} ${" ".repeat(
      maxLength - names[i].length
    )}*\n`;
    result += lineaConNombre;
    // * <NAME>        *
  }

  result += "*".repeat(tamanoMarco);
  //  ****************

  return result;
}
```
