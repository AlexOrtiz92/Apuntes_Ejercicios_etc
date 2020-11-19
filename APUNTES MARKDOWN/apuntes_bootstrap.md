# BOOTSTRAP

Bootstrap es un framework para utilizar estilos de CSS ya predefinidos. [Link a Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

- Sigue la tecnica de 12 columnas. Es decir meter 12 columnas en cada fila.(MAX)

## ¿Que es npm?

npm es el Node Package Manager. Debes tener Node.js instalado.

## ¿Cómo funciona el Node Package Manager?

Esta herramienta funciona de dos formas:

- Como un repositorio ampliamente utilizado para la publicación de proyectos Node.js de código abierto. Lo que significa que es una plataforma en línea donde cualquiera puede publicar y compartir herramientas escritas en JavaScript.
- Como una herramienta de línea de comandos que ayuda a interactuar con plataformas en línea, como navegadores y servidores. Esta utilidad ayuda a instalar y desinstalar paquetes, gestión de versiones y gestión de dependencias necesarias para ejecutar un proyecto.

Ver mas [INFO](https://www.hostinger.es/tutoriales/que-es-npm/#Iniciando-un-proyecto-con-npm)

# Empezar un proyecto Javascript

1. Inicializamos la terminal
2. Creamos un proyecto npm con `$ npm init -y` (la y responde a las preguntas para crear el package.json)
3. Te crea un archivo .json que es un JavaScript Object Notation con los datos del proyecto
4. instalaremos un "bundler" con la siguiente expresion --> `$ npm install parcel-bundler -D` ó `npm i -D parcel-bundler`.
   Creara un archivo llamado "package-lock.json" y las dependencias.

5. Ahora instalaremos bootstrap a traves de aqui, ademas de Jquery. Tambien `$ npm i -S bootstrap jquery popper.js`
6. Nunca se eliminara una dependencia eliminando la linea en el archivo .json sino con `$ npm uninstall popper.js`
7. para volver a instalarlo `$ npm i -S popper.js`
8. Lo mas importante del package.json son los "scripts" y las "dependencies"
9. En el archivo package.json cambiaremos las "scripts" , donde pone `test-->"start"` y donde pone el mensaje pondremos `"parcel index.html"`
10. Crearemos un Index.html y haremos referencia mediante la etiqueta `<script>` al archivo main.js
11. despue sen nuestro archivo main.js añadiremos las propiedades `"import"` (supongo que para enlazarlo con Bootstrap anteriormente instalado mediante los comandos)
12. Crearemos un .gitignore para ignorar todas las carpetas que queramos
13. Para crear un servidor remoto usaremos el siguiente comando: `$ npm run start`. Este servidor lo
14. En el archivo index.html usaremos las CLASES para indicar y hacer referencia a los formatos predefinidos de Bootstrap. Podremos mirarlos en la documentacion oficial en su [Link a Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/)
15. Tambien podremos crear nuestros propios estilo usando el formato de archivo `.scss`que es como una especie de CSS. usaremos la propiedad `@extend` para hacer referencia a clases predefinidas de Bootstrap incluyendolas en clases creadas por nosotros mismos.
16. es posible darle las propiedades que queramos tambien y crear tantas clases como se desee.

## Bootstrap

- Las columnas de la rejilla definen su anchura especificando cuántas de las 12 columnas de la fila ocupan. Si por ejemplo quieres dividir una fila en tres columnas iguales, utilizarías la clase .col-xs-4 (el 4 indica que cada columna ocupa 4 de las 12 columnas en las que se divide cada fila).
