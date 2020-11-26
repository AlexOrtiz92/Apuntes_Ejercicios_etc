# Funciones Guays

- Esta funcion sirve para generar un numero aleatorio y entero entre un minimo y un maximo:

```js
function randomInt(min, max) {
  return min + Math.floor(Math.random() * (max - min + 1));
}
console.log(randomInt(1, 10));
```

- Operador ternario encadenado:

```js
const isNil = (x) => (x === null ? true : x === undefined ? true : false);
//si x es estok dame esto, si x es otra cosa dame esto y si es todo lo demas dame false
```

- Para saber si un valor es distinto de `null`o `undefined`

```js
const isNil = (x) => x != null;
```

- No se para que sirve pero hay que guardarla:

```js
const tester = (x, condicion) => condicion(x) && true;
```

- Saber si el tamaño de mi navegador es de un tamaño o de otro:

```js
function layout(size) {
  console.log(window.innerWidth);

  return size >= 960 ? "LARGE" : size >= 660 ? "MEDIUM" : "SMALL";
}
console.log(layout(window.innerWidth));
```
