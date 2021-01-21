# Funciones Guays

- Esta funcion sirve para generar un numero aleatorio y entero entre un minimo y un maximo:

```js
function randomInt(min, max) {
  return min + Math.floor(Math.random() * (max - min + 1)); //es +1 porque sino nunca llegaria al maximo, al redondear hacia abajo y al no llegar nunca Math.random a 1.
}
console.log(randomInt(1, 10));
```

- Operador ternario encadenado:

```js
const isNil = (x) => (x === null ? true : x === undefined ? true : false);
//si x es estok dame esto, si x es otra cosa dame esto y si es todo lo demas dame false
```

- Para saber si un valor es distinto de `null` o `undefined`

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

- Calcular el factorial de un numero (Es Recursiva):

```js
function factorial(num) {
  if (num === 0) {
    return 1;
  } else {
    return num * factorial(num - 1);
  }
}
```

- Devuelve un numero aleatorio entre 5 y 10 incluidos:

```js
function random() {
  let result = 0;
  while (result < 5 || result > 10) {
    result = Math.floor(Math.random() * 100);
  }
  return result;
}

//ó

Math.floor(Math.random() * 6) + 1)//entre 1 y 6 este ejemplo
```

- Generacion de un ID:

```js
  genId() {
    return Math.random().toString(36).substring(7);
  }
```

- Crear una funcion que te crea un array con N indices, vacios:

```js
const arrayOfN = (n) => Array.from(new Array(n));
```

- Igual que arriba, solo que ahora una funcion para que hagas lo que quieras antes de insertar cada valor.

  Funcion de un array que se aceptan y se aplican por cada elemento del array:

```js
const mapN = (n, f) => Array.from(new Array(n), f);
//undefined
mapN(3);
//(3) [undefined, undefined, undefined]
mapN(3, (x, index) => index);
//(3) [0, 1, 2]
mapN(3, (_, index) => index);
//(3) [0, 1, 2]
```

- Formato d efecha muy utilizado:

```js
new Date().toISOString();
//"2021-01-16T12:56:21.035Z"
```
