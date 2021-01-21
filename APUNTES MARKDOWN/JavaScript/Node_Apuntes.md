# Node.js

Se puede escribir Node en varios lenguajes, pero el mas comun es Node.

Es una plataforma de desarrollo de aplicaciones, es de codigo abierto.

Es JavaScript en el servidor lo describirian algunos. Lo vamos a utilizar para realizar aplicaciones de servidor. Aunq ue se puede hacer de todo. Nos vamps a centrar en APIs y app de servidor.

Desde node se pueden acceder a ciertas funcionalidades de tu ordenador, desde terminal de node.

### **Instalar Node**

Descargamos Node, la version LTS que es la que mejor soporte tiene. Se suele actualizar la version segun tu proyecto.

- https://nodejs.org/es/

- Se abre la consola y se escribe `node`
- control+c y control+c

## **Apuntes**

- El ejercicio `server1.js` esta el primer ejercicio de levantar un servidor. Nuestra primera aplicacion en node.

  - Se arranca un servidor en consola con `$ node server1.js` y se para con control + c.
    - (INVESTIGAR pasos levantar server)

- `server2.js`: En este ejercicio en vez de escribir nosotros el html, lo hemos referenciado con `fs.readFile()`

  - Hay veces que dara error, en los redFile() tenemos que indicar que sucede cuando da un error, ya sea o un mensaje como en nuestra app, o redirijirnos a otra pagina usando otra vez el readFile().

- `server3.js`: En este archivo hemos usado una ruta dinamica para cambiar sobre la marcha. MUY INTERESANTE e importante

- Los servidores requieren de recarga siempre para volver a reflejar los cambios, igual que las paginas web.

- Las aplicaciones tienen que ser robustas. Siempre tenemos que dar una respuesta a cada situacion posible, errores o cualquier cosa. Se cae un servidor, por ejemplo, debemos dar una respuesta a ese posible error.

- Los LOG de errores son super UTILES. PERDERLES EL MIEDO :)

## Debuggear en el servidor con NODE

Usaremos de momento la de VSCode. damos a `Run and Debug` y elegiremos el entorno en el que vamos a correr. Node.js (legacy).

Podemos dar puntos de ruptura (break points), que son esos puntos rojos en el codigo que se marcan en la parte de la izquierda al lado del numero de las filas

Una vez se ejecuta el Debugger, con esos puntos de rutura, se para y se congela y se puede ver los valores que tiene cada cosa en ese momento y punto especifico.

IMPORTANTE: Donde este el break point, esa linea no esta ejecutada,esta congelada, se espera a pasar a la siguiente.

El orden que seguira el Debugger con cada linea sera uno especifico de JS, es decirme si se encuentra una funcion asincrona, la pasara y la ejecutara cuando la termine.

Se utiliza el debug para pararnos en nuestro codigo y ver que valen las cosas en cada momento. Ver que datos reales estan usando y poder usarlos.

![Imagen de Debugger VSCode](../imagenes_md/VSCode_Debugger.png)

## Eventos Metodos etc (INVESTIGAR)

- `require()`:Importar un modulo ya preestablecido. El modulo "http" da muchas opciones, como crear un "Web Service".

  Otro modulo por ejemplo es "fs"(file system).

  ```js
  const http = require("http");
  const fs = require("fs");
  ```

- `.createServer((request, response) => {})`: creamos nuestro servidor, con dos parametros como argumentos. Todas las APIS tienen estos parametros. Lo que pedimos al servidor `(request)` y lo que enviamos segun la peticion `(response)`.

  Por ejemplo en la realidad seria una peticion de un formulario, una busqueda etc.

  - Una manera en la response es embeber todo nuestro html
  -

  ```js
  const server = http.createServer((request, response) => {
    }
  ```

- `fs.readFile(path, (error, data) => {})`:Es un metodo de fs, para leer un documento.

  El path es una ruta real del servidor y comienza a nivel de el workspace y viene un callback, que se ejecuta cuando se termine de leer todo el fichero.

  Esta con 2 parametros, si todo va bien la info contenida del fichero estará en `data` y `error` sera null. Por otro lado si algo ha ido mal, `data` sera undefined y `error` hara lo que le indiquemos.

  ```js
  fs.readFile(path, (error, data) => {

  }
  ```

- `server.listen()`:Es un metodo del modulo "http"

  ```js
  //aqui creara un puerto en la IP localhost como defined(127.0.0.1:1111)
  server.listen(3333);

  //ó dando un puerto y una IP
  server.listen(port, host, () => {
    console.log(`Servidor corriendo en http://${host}:${port}`);
  });
  ```

- La manera de hacer que nuestra pagina sea dinamica y nos cargue cualquier tipo de recurso(.js, .html, .css, .jpg etc), cambiando el `"Content-Type"`

  [Tipos de "Content-Type"](https://developer.mozilla.org/es/docs/Web/HTTP/Basics_of_HTTP/MIME_types)

  Se saca la extension y segun esta, le aplicamos un content type distinto ademas de indicarle la ruta donde tenemos guardados ese tipo de archivos:

  ```js
  //se mete dentro del const server

  let contentType;
  let path;

  let extension = request.url.split(".")[1];

  switch (extension) {
    case "html":
      contentType = "text/html";
      path = `./public/html${request.url}`;
      break;
    case "css":
      contentType = "text/css";
      path = `./public/css${request.url}`;
      break;
    case "js":
      contentType = "text/javascript";
      path = `./public/js${request.url}`;
      break;
    default:
      path = "";
      contentType = "";
  }
  ```
