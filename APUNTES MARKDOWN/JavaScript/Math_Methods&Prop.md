# NUMBER

Algunos metodos y constantes que implementa JS en los valores asociados al tipo `Number` son:

```js
Number.parseInt("1"); // Convierte un string numerico a tipo Number
Number.parseFloat("2.0"); // Convierte un string numerico a tipo Number
Number.isNaN(x); // Es x un valor NaN?
Number.isFinite(x); // Es x un numero finito?
Number.isFinite(x); // Es x un numero finito?
Number.isInteger(x); // Es x un numero entero?
Number.isSafeInteger(x); // Es x un numero entero entre los valores maximos y minimos a representar?
Number.MIN_SAFE_INTEGER; // => -(2**53-1)
Number.MAX_SAFE_INTEGER; // => 2**53-1
```

El valor `NaN` ademas no puede ser comparado con otro valor, nisiquiera consigo mismo. Lo siguiente no funcionaría:

```js
x === NaN;
```

Es mejor siempre usar:

```js
Number.isNaN(x);
```

---

# Math

**Math** es un objeto incorporado que tiene propiedades y métodos para constantes y funciones matemáticas. No es un objeto de función.

**Math** funciona con el tipo `Number`. No funciona con `BigInt`.

# Descripción

A diferencia de los demás objetos globales, el objeto `Math` no se puede editar. Todas las propiedades y métodos de `Math` son estáticos. Usted se puede referir a la constante pi como `Math.PI` y puede llamar a la función seno como `Math.sin(x)`, donde `x` es el argumento del método. Las constantes se definen con la precisión completa de los números reales en JavaScript.

```js
Math.pow(2, 53); // => 9007199254740992: 2 exponenciado a 53
Math.round(0.6); // => 1.0: redondeo al mas cercano
Math.ceil(0.6); // => 1.0: redondeo hacia arriba
Math.floor(0.6); // => 0.0: redondeo hacia abajo
Math.abs(5); // => 5: valor absoluto
Math.max(x, y, z); // Retorna el argumento mas largo
Math.min(x, y, z); // Retorna el argumento mas pequeño
Math.random(); // Devuelve un numero pseudorandomizado x donde 0 <= x < 1.0
Math.PI; // π: Circunferencia de un circulo / diametro
Math.E; // e: La base de logaritmo natural
Math.sqrt(3); // Raiz cuadrada de 3
Math.pow(3, 1 / 3); // Raiz cubica de 3
Math.sin(0); // Trigonometria: Tambien tenemos disponibles el Math.cos, Math.atan, etc.
Math.log(10); // Logaritmo de 10
// [... etc]
```

# Propiedades

- `Math.E`

  Constante de Euler, la base de los logaritmos naturales, aproximadamente 2.718.

- `Math.LN2`

  Logaritmo natural de 2, aproximadamente 0.693.

- `Math.LN10`

  Logaritmo natural de 10, aproximadamente 2.303.

- `Math.LOG2E`

  Logaritmo de E con base 2, aproximadamente 1.443.

- `Math.LOG10E`

  Logaritmo de E con base 10, aproximadamente 0.434.

- `Math.PI`

  Ratio de la circunferencia de un circulo respecto a su diámetro, aproximadamente 3.14159.

- `Math.SQRT1_2`

  Raíz cuadrada de 1/2; Equivalentemente, 1 sobre la raíz cuadrada de 2, aproximadamente 0.707.

- `Math.SQRT2`

  Raíz cuadrada de 2, aproximadamente 1.414.

# Métodos

Tenga en cuenta que las funciones trigonométricas `(sin(), cos(), tan(), asin(), acos(), atan(), atan2())` devuelven ángulos en radianes. Para convertir radianes a grados, divida por `(Math.PI / 180)`, y multiplique por esto para convertir a la inversa.

```
Tenga en cuenta que muchas de las funciones matemáticas tienen una precisión que es dependiente de la implementación. Esto significa que los diferentes navegadores pueden dar un resultado diferente, e incluso el mismo motor de JS en un sistema operativo o arquitectura diferente puede dar resultados diferentes.
```

- `Math.abs(x)`

  Devuelve el valor absoluto de un número.

- `Math.acos(x)`

  Devuelve el arco coseno de un número.

- `Math.acosh(x)`

  Devuelve el arco coseno hiperbólico de un número.

- `Math.asin(x)`

  Devuelve el arco seno de un número.

- `Math.asinh(x)`

  Devuelve el arco seno hiperbólico de un número.

- `Math.atan(x)`

  Devuelve el arco tangente de un número.

- `Math.atanh(x)`

  Devuelve el arco tangente hiperbólico de un número.

- `Math.atan2(y, x)`

  Devuelve el arco tangente del cuociente de sus argumentos.

- `Math.cbrt(x)`

  Devuelve la raíz cúbica de un número.

- `Math.ceil(x)`

  Devuelve el entero más pequeño mayor o igual que un número.

- `Math.clz32(x)`

  Devuelve el número de ceros iniciales de un entero de 32 bits.

- `Math.cos(x)`

  Devuelve el coseno de un número.

- `Math.cosh(x)`

  Devuelve el coseno hiperbólico de un número.

- `Math.exp(x)`

  Devuelve Ex, donde x es el argumento, y E es la constante de Euler (2.718...), la base de los logaritmos naturales.

- `Math.expm1(x)`

  Devuelve ex - 1.

- `Math.floor(x)`

  Devuelve el mayor entero menor que o igual a un número.

- `Math.fround(x)`

  Devuelve la representación flotante de precisión simple más cercana de un número.

- `Math.hypot([x[, y[, …]]])`

  Devuelve la raíz cuadrada de la suma de los cuadrados de sus argumentos.

- `Math.imul(x, y)`

  Devuelve el resultado de una multiplicación de enteros de 32 bits.

- `Math.log(x)`

  Devuelve el logaritmo natural (log, también ln) de un número.

- `Math.log1p(x)`

  Devuelve el logaritmo natural de x + 1 (loge, también ln) de un número.

- `Math.log10(x)`

  Devuelve el logaritmo en base 10 de x.

- `Math.log2(x)`

  Devuelve el logaritmo en base 2 de x.

- `Math.max([x[, y[, …]]])`

  Devuelve el mayor de cero o más números.

- `Math.min([x[, y[, …]]])`

  Devuelve el más pequeño de cero o más números.

- `Math.pow(x, y)`

  Las devoluciones de base a la potencia de exponente, que es, baseexponent.

- `Math.random()`

  Devuelve un número pseudo-aleatorio entre 0 y 1.

- `Math.round(x)`

  Devuelve el valor de un número redondeado al número entero más cercano.

- `Math.sign(x)`

  Devuelve el signo de la x, que indica si x es positivo, negativo o cero.

- `Math.sin(x)`

  Devuelve el seno de un número.

- `Math.sinh(x)`

  Devuelve el seno hiperbólico de un número.

- `Math.sqrt(x)`

  Devuelve la raíz cuadrada positiva de un número.

- `Math.tan(x)`

  Devuelve la tangente de un número.

- `Math.tanh(x)`

  Devuelve la tangente hiperbólica de un número.

- `Math.toSource()` (This API has not been standarized)

  Devuelve la cadena "Math".

- `Math.trunc(x)`

  Devuelve la parte entera del número x, la eliminación de los dígitos fraccionarios.
