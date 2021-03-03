# MongoDB

MongoDB es una base de datos NO Relacional. Da solucion para cargas masivas de datos y grandes cantidades de informacion

- Composicion:

  - crearemos nuestra `BBDD`.

  - Esta BBDD contiene `Colecciones`.

  - Estas colecciones contienen `Documentos`.

  - Estos documentos contienen `Campos`

- Mongo creara siempre un \_id unico.

- Los Documentos y sus parametros pueden contener:

  - Numericos

    - Double
    - Decimal
    - Int
    - Long

  - Texto

    - String
    - Regex

  - Formato Fecha

    - Date
    - Timestamp

  - Especiales

    - Array
    - ObjectId
    - Javascript
    - Null
    - Boolean

## Documentacion (metodos)

https://docs.mongodb.com/manual/reference/method/

## Instalar Homebrew

Hemos usado Homebrew: es un gestor de paquetes para MACOS.

Homebrew instala todo aquello que necesitas que Apple no instala de serie.

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Intalar MongoDB

Pagina donde viene explicado (Tambien en el curso de UDEMY):
https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/

## Trabajando con MongoDB

- `$ mongod --version`: nos dice si esta instalado y la version ademas de otros datos

- `$ mongo`: inicializamos

- `$ db`: nos dice la bbdd en la que estamos

- `$ show dbs`: nos dice las bbdd que tengo

- `$ show collections`: saber las colecciones en la bbdd

- `$ use BBDD`: nos crea una base de datos con ese nombre y si ya esta creada, nos cambia de bbdd

- `$ db.createCollection("users")`: crear una coleccion.

- `$ db.users.insert({name: "alex", surname: "ortiz"})`: crear un documento, clave/valor, siempre entre corchetes

- `$ db.users.insert({name: "alex", surname: "ortiz"})`:
- `$ db.users.find()`: sb."coleccion".find() es para saber los documentos que tenemos en la coleccion.

  Si le indicamos argumentos actuara de las siguientes maneras:

  Utilizaremos **Query and Projection Operators**, que sirven para encontrar de determinadas formas:

  https://docs.mongodb.com/manual/reference/operator/query/

  - `$ db.personajes.find({raza: "humano"})`: encuentra todo lo que sea humano y lo devuelve entero.

  - `$ db.personajes.find({raza: {$eq: "humano"}})`: encuentra todo lo que sea humano y lo devuelve entero.

  - `$ db.personajes.find({raza: {$not: {$eq: "humano"}}})`: encuentra todo lo que no sea humano.

  - `db.personajes.find({"stats.fue": 5})`: devuelve personajes con fuerza 5. Aqui hemos usado una condicion que busca en la pripiedad dentro de una propiedad.

  - `$ db.personajes.find({$and: [{raza: "humano"},{"stats.des": 5}]})`

  - `$ db.personajes.find({$and: [{raza: {$not: {$eq : "orco"}}},{"stats.fue": 5}]})`: distinto de orco y fuerza 5

  **Usando el 2º argumento:**

  - `$ db.personajes.find(null, {nombre:1})`: con el null indicamos que busque en todos los objetos y con el seguno argumento le decimos que datos de esos objetos que encuentre queremos que nos devuelva.

    Si usamos 1: queremos que devuelva.

    Si usamos 0: no queremos que devuelva.

    En este caso, buscara en toda la bbdd y nos traera de esos documentos solo los nombres.

  - `$ db.personajes.find(null, {_id: 0, nombre:1, raza: 1})`

- `$ db.users.find().limit(2)`: usando limit() limita lo que devuelve al numero especificadonos devuelve los dos primeros

- `$ db.users.find().skip(2)`: por el contrario, skip() se salta 2.

- `$ db.personajes.find().sort({"stats.int": 1})`: ordena de manera numerica de menor a mayor. Si es `-1` ordena de mayor a menor.
  Tambien ordena por orden alfabetico

- `$ db.stats()`: info d ela bbDD

- `$ db.users.renameCollection("usuarios")`: renombrar una coleccion.

- `$ db.users.insert({name:"patri", surname: "ramos"})`: insertar un documento en la coleccion. CUIDADO, si la coleccion no existe, te la crea y lo inserta en esa.

- `$ db.users.insertMany([])`: inserta un array de documentos:

- `$ db.users.deleteOne({_id: ObjectId("603928c39843a2c7d58954b6")})`: eliminar un documento (en este caso por id) .deleteOne() borra el primero que encuentre
- `$ db.users.drop()`: borrar una coleccion
  11
- `$ db.dropDatabase()`: elimina una base de datos en la que te encuentres

- Actualizar un valor de un documento:
  `db.personajes.update({_id: ObjectId("60392bf09843a2c7d58954b8")}, {$set: {raza: "humana"}})`

  Utiliza dos argumentos, el primero es el elemento a modificar y el segundo (usando $set) le decimos el valor de la pripiedad nuevo.

  Si usamos un tercer argumento, nos cambiara todos los que encuentre:

  `db.personajes.update({raza: "enano"}, {$set: {raza: "humano"}}, {multi: true})`

- `$ db.personajes.find().pretty()`: pretifica la coleccion.

## Proyecto MongoDB real

https://www.npmjs.com/package/mongoose

- instalamos mongoose: `$ npm install mongoose`

- crearemos una api como venimos haciendo

- Realizamos la conexion con la BBDD. Con esta conexion ya podemos trabajar con la BBDD:

```js
mongoose.connect(
  "mongodb://localhost/BBDD",
  { useNewUrlParser: true, useUnifiedTopology: true },
  (err, response) => {
    if (err) {
      console.error(err, "error al conectar con la BBDD");
    } else {
      console.log("BBDD conectada");
    }
  }
);
```

- crearemos una carpeta "models" donde crearemos nuestros esquemas d enuestra BBDD. Creamos un nuevo archivo y creamos el schema y tendremos que "tiparlo" para ayudar, aunque acepte todo tipo de entradas. Tambien indicarle la coleccion que vamos a coger:

```js
const mongoose = require("mongoose");

//los esquemas suelen empezar en mayuscula por convencion de nombres
const Schema = mongoose.Schema;

const frutaSchema = new Schema(
  {
    name: String,
    qty: Number,
    color: [String], //array de string
    size: {
      h: Number,
      w: Number,
    },
  },
  { versionKey: false }
); //le ponemos esto para que no cree una prop __v por defecto

//lo exportamos y le diremos, coge este modelo y tenemos que indicarle la "coleccion" --> Fruta a la que va a referirse
module.exports = mongoose.model("Fruta", frutaSchema);
```

- ya en nuestro API, podremos hacer uso de todas las funciones de mongoose que estan en la libreria ya configuradas para no tener que estar haciendo queries como haciamos en la consola.

Por ejemplo este te busca por id:

```js
const Frutas = require("./models/fruta");

Frutas.findById(id, (err, data) => {});
```

# **Query and Projection Operators**

### Comparison

For comparison of different BSON type values, see the specified BSON comparison order.

- `$eq`: Matches values that are equal to a specified value.

- `$gt`: Matches values that are greater than a specified value.

- `$gte`: Matches values that are greater than or equal to a specified value.

- `$in`: Matches any of the values specified in an array.

- `$lt`: Matches values that are less than a specified value.

- `$lte`: Matches values that are less than or equal to a specified value.

- `$ne`: Matches all values that are not equal to a specified value.

- `$nin`: Matches none of the values specified in an array.

### Logical

- `$and`: Joins query clauses with a logical AND returns all documents that match the conditions of both clauses. Requiere ARRAY.

- `$not`: Inverts the effect of a query expression and returns documents that do not match the query expression.

- `$nor`: Joins query clauses with a logical NOR returns all documents that fail to match both clauses. Requiere ARRAY.

- `$or`: Joins query clauses with a logical OR returns all documents that match the conditions of either clause. Requiere ARRAY.

### Element

- `$exists`: Matches documents that have the specified field.

- `$type`: Selects documents if a field is of the specified type.

### Evaluation

- `$expr`: Allows use of aggregation expressions within the query language.

- `$jsonSchema`: Validate documents against the given JSON Schema.

- `$mod`: Performs a modulo operation on the value of a field and selects documents with a specified result.

- `$regex`: Selects documents where values match a specified regular expression.

- `$text`: Performs text search.
  $where Matches documents that satisfy a JavaScript expression.

### Geospatial

- `$geoIntersects`: Selects geometries that intersect with a GeoJSON geometry. The 2dsphere index supports $geoIntersects.

- `$geoWithin`: Selects geometries within a bounding GeoJSON geometry. The 2dsphere and 2d indexes support $geoWithin.

- `$near`: Returns geospatial objects in proximity to a point. Requires a geospatial index. The 2dsphere and 2d indexes support $near.

- `$nearSphere`: Returns geospatial objects in proximity to a point on a sphere. Requires a geospatial index. The 2dsphere and 2d indexes support $nearSphere.

### Array

- `$all`: Matches arrays that contain all elements specified in the query.

- `$elemMatch`: Selects documents if element in the array field matches all the specified $elemMatch conditions.

- `$size`: Selects documents if the array field is a specified size.

### Bitwise

- `$bitsAllClear`: Matches numeric or binary values in which a set of bit positions all have a value of 0.

- `$bitsAllSet`: Matches numeric or binary values in which a set of bit positions all have a value of 1.

- `$bitsAnyClear`: Matches numeric or binary values in which any bit from a set of bit positions has a value of 0.

- `$bitsAnySet`: Matches numeric or binary values in which any bit from a set of bit positions has a value of 1.

### Projection Operators

- `$Projects` :the first element in an array that matches the query condition.

- `$elemMatch`: Projects the first element in an array that matches the specified $elemMatch condition.

- `$meta`: Projects the document’s score assigned during $text operation.

- `$slice`: Limits the number of elements projected from an array. Supports skip and limit slices.

### Miscellaneous Operators

- `$comment`: Adds a comment to a query predicate.

- `$rand`: Generates a random float between 0 and 1.
