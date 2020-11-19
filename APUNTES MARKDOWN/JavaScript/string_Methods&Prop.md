[@@@Link a Web](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String#)

# Métodos estáticos

- `String.fromCharCode(num1 [, ...[, numN]])`

  Devuelve una cadena creada utilizando la secuencia de valores Unicode especificada.

- `String.fromCodePoint(num1 [, ...[, numN]])`

  Devuelve una cadena creada utilizando la secuencia de puntos de código especificada.

- `String.raw()`

  Devuelve una cadena creada a partir de una plantilla literal sin formato.

# Propiedades de la instancia

- `x.length`

  Refleja la length de la cadena. Solo lectura.

# Métodos de instancia

- `x.charAt(index)`

  Devuelve el caracter (exactamente una unidad de código UTF-16) en el index especificado.

- `x.charCodeAt(index)`

  Devuelve un número que es el valor de la unidad de código UTF-16 en el index dado.

- `x.codePointAt(pos)`

  Devuelve un número entero no negativo que es el valor del punto de código del punto de código codificado en UTF-16 que comienza en la pos especificada.

- `x.concat(str[, ...strN])`

  Combina el texto de dos (o más) cadenas y devuelve una nueva cadena.

- `x.includes(searchString [, position])`

  Determina si la cadena de la llamada contiene searchString.

- `x.endsWith(searchString[, length])`

  Determina si una cadena termina con los caracteres de la cadena searchString.

- `x.indexOf(searchValue[, fromIndex])`

  Devuelve el índice dentro del objeto String llamador de la primera aparición de searchValue, o -1 si no lo encontró.

- `x.lastIndexOf(searchValue[, fromIndex])`

  Devuelve el índice dentro del objeto String llamador de la última aparición de searchValue, o -1 si no lo encontró.

- `x.localeCompare(compareString[, locales[, options]])`

  Devuelve un número que indica si la cadena de referencia compareString viene antes, después o es equivalente a la cadena dada en el orden de clasificación.

- `x.match(regexp)`

  Se utiliza para hacer coincidir la expresión regular regexp con una cadena.

- `x.matchAll(regexp)`

  Devuelve un iterador de todas las coincidencias de regexp.

- `x.normalize([form])`

  Devuelve la forma de normalización Unicode del valor de la cadena llamada.

- `x.padEnd(targetLength[, padString])`

  Rellena la cadena actual desde el final con una cadena dada y devuelve una nueva cadena de longitud targetLength.

- `x.padStart(targetLength[, padString])`

  Rellena la cadena actual desde el principio con una determinada cadena y devuelve una nueva cadena de longitud targetLength.

- `x.repeat(count)`

  Devuelve una cadena que consta de los elementos del objeto repetidos count veces.

- `x.replace(searchFor, replaceWith)`

  Se usa para reemplazar ocurrencias de searchFor usando replaceWith. searchFor puede ser una cadena o expresión regular, y replaceWith puede ser una cadena o función.

- `x.replaceAll(searchFor, replaceWith)`

  Se utiliza para reemplazar todas las apariciones de searchFor usando replaceWith. searchFor puede ser una cadena o expresión regular, y replaceWith puede ser una cadena o función.

- `x.search(regexp)`

  Busca una coincidencia entre una expresión regular regexp y la cadena llamadora.

- `x.slice(beginIndex[, endIndex])`

  Extrae una sección de una cadena y devuelve una nueva cadena.

  Coje la cadena desde el primer numero hasta el segundo indicado "NO incluido".

  Si no ponemos el segundo numero, cogera hasta el

  - Segun ayuda-->The index to the end of the specified portion of stringObj. The substring includes the characters up to, but not including, the character indicated by end. If this value is not specified, the substring continues to the end of stringObj.

Returns a section of a string.

- `x.split([sep[, limit] ])`

  Devuelve un arreglo de cadenas pobladas al dividir la cadena llamadora en las ocurrencias de la subcadena sep.

- `x.startsWith(searchString[, length])`

  Determina si la cadena llamadora comienza con los caracteres de la cadena searchString.

- `x.substr()`

  Devuelve los caracteres en una cadena que comienza en la ubicación especificada hasta el número especificado de caracteres.

- `x.substring(indexStart[, indexEnd])`

  Devuelve una nueva cadena que contiene caracteres de la cadena llamadora de (o entre) el índice (o indeces) especificados.

- `x.toLocaleLowerCase( [locale, ...locales])`

  Los caracteres dentro de una cadena se convierten a minúsculas respetando la configuración regional actual.

  Para la mayoría de los idiomas, devolverá lo mismo que toLowerCase().

- `x.toLocaleUpperCase( [locale, ...locales])`

  Los caracteres dentro de una cadena se convierten a mayúsculas respetando la configuración regional actual.

  Para la mayoría de los idiomas, devolverá lo mismo que toUpperCase().

- `x.toLowerCase()`

  Devuelve el valor de la cadena llamadora convertido a minúsculas.

- `x.toString()`

  Devuelve una cadena que representa el objeto especificado. Redefine el método x.toString().

- `x.toUpperCase()`

  Devuelve el valor de la cadena llamadora convertido a mayúsculas.

- `x.trim()`

  Recorta los espacios en blanco desde el principio y el final de la cadena. Parte del estándar ECMAScript 5.

- `x.trimStart()`

  Recorta los espacios en blanco desde el principio de la cadena.

- `x.trimEnd()`

  Recorta los espacios en blanco del final de la cadena.

- `x.valueOf()`

  Devuelve el valor primitivo del objeto especificado. Redefine el método x.valueOf().

- `x.@@iterator()`

  Devuelve un nuevo objeto Iterator que itera sobre los puntos de código de un valor de cadena, devolviendo cada punto de código como un valor de cadena.
