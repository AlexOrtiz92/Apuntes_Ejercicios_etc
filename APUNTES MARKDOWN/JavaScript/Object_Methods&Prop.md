# **Object**

La clase Object representa uno de los tipos de datos de Javascript. Es es usado para guardar una colección de datos definidos y entidades más complejas. Los objetos pueden ser creados utilzando el constructor `Object()` o la sintaxis literal de objeto.

## Description

El constructor Object crea una envoltura de objeto al valor dado. Si el valor es `null` o `undefined`, creará y retornará un objeto vacío, de otra forma, retornará un objeto de un tipo que corresponda al valor dado. Si el valor ya es un objeto devolverá el valor.

Cuando es llamano en un contexto non-constructor, Object se comportará indenticamente a `new Object()`.

## Propiedades del constructor Object

- `Object.length`:

  Tiene un valor de 1.

- `Object.prototype`:

  Permite añadir propiedades a todos los objetos del tipo Object.

## Métodos del constructor Object

- `Object.assign()`:

  Copia los valores de todas sus propiedades enumerables desde uno o más objetos fuente a un objeto destino.

- `Object.create()`:

  Crea un nuevo objeto con el prototipo objeto y propiedades específicadas.

- `Object.defineProperty()`:

  Añade la propiedad nombrada descrita por un descriptor dado a un objeto.

- `Object.defineProperties()`:

  Agrega las propiedades nombradas descritas por los descriptores dados a un objeto.

- `Object.entries()`:

  Returns an array containing all of the [key, value] pairs of a given object's own enumerable string properties.

- `Object.freeze()`:

  Freezes an object: other code can't delete or change any properties.

- `Object.fromEntries()`:

  Returns a new object from an iterable of key-value pairs (reverses Object.entries).

- `Object.getOwnPropertyDescriptor()`:

  Returns a property descriptor for a named property on an object.

- `Object.getOwnPropertyDescriptors()`:

  Returns an object containing all own property descriptors for an object.

- `Object.getOwnPropertyNames()`:

  Returns an array containing the names of all of the given object's own enumerable and non-enumerable properties.

- `Object.getOwnPropertySymbols()`:

  Returns an array of all symbol properties found directly upon a given object.

- `Object.getPrototypeOf()`:

  Returns the prototype of the specified object.

- `Object.is()`:

  Compares if two values are the same value. Equates all NaN values (which differs from both Abstract Equality Comparison and Strict Equality Comparison).

- `Object.isExtensible()`:

  Determines if extending of an object is allowed.

- `Object.isFrozen()`:

  Determines if an object was frozen.

- `Object.isSealed()`:

  Determines if an object is sealed.

- `Object.keys()`:

  Returns an array containing the names of all of the given object's own enumerable string properties.

- `Object.preventExtensions()`:

  Prevents any extensions of an object.

- `Object.seal()`:

  Prevents other code from deleting properties of an object.

- `Object.setPrototypeOf()`:

  Sets the prototype (i.e., the internal [[Prototype]] property).

- `Object.values()`:

  Returns an array containing the values that correspond to all of a given object's own enumerable string properties.
