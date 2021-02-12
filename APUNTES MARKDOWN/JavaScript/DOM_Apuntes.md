# Apuntes de DOM (Document Object Model)

El DOM es la estructura de objetos que genera el navegador cuando se carga un documento y se puede alterar mediante Javascript para cambiar dinámicamente los contenidos y aspecto de la página.

En el queda dispnible para los desarrolladores todo lo que contiene la pagina para que pueda ser añadido, modificado o suprimido.

El DOM está definido y administrado por el W3C (World Wide Web Consortium)

Es un a API(Application Programming Interface) para documentos `HTML` y `XML`

- `document` es el objeto que engloba a todos los demas, esta en la jerarquia mas alta del DOM.

## Enlaces de Interés

- https://www.freecodecamp.org/news/dom-manipulation-in-vanilla-js-2036a568dcd9/
- https://www.w3schools.com/jsref/dom_obj_style.asp
- https://www.w3schools.com/js/js_htmldom_css.asp
- https://www.w3schools.com/js/js_htmldom_nodelist.asp

---

## Methods y Properties

- `document.querySelector(".example")` **_Method_**: coge el **primer** elemento del document que se parezca a la clase o al ID contenido dentro de él.Normalmente se almacenan en constantes (`let` o `const`)

  La manera de hacer referencia se realizará de la misma manera que en un documento CSS, con los [selectores](https://www.w3schools.com/cssref/css_selectors.asp).

  ```js
  const elemento = document.querySelector(".example");
  const elemento = document.querySelector("#example");
  const elemento = document.querySelector(".example ul");
  ```

  - https://www.w3schools.com/jsref/met_document_queryselector.asp

- `.innerHTML` **_Property_**: Establece o Devuelve el contenido escrito dentro de un atributo HTML(ya sea un `<p>` un `<ul>` o lo que sea)

  ```js
  //Devuelve el contenido de una etiqueta HTML

  HTMLElementObject.innerHTML;

  //Establece o cambia el contenido d euna etiqueta

  HTMLElementObject.innerHTML = text;
  ```

  - https://www.w3schools.com/jsref/prop_html_innerhtml.asp

- `.innerText` **_Property_**: Funciona igual que innerHTML. Este sí funciona con las Text Box.

- `.addEventListener()` **_Method_**: Es un manejador de evento (event handler) a un elemento determinado, indicandole el tipo de evento.

  Se pueden añadir varios event handler a un mismo elemento.

  Se pueden añadir varios event handler del mismo "tipo" a un mismo elemento (p.ej 2 "click").

  ```js
  //sintaxis

  element.addEventListener(event, function, useCapture);

  ```

  - `event`: es cualquiera de los tipos de eventos relacionados con el DOM --> [DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp)
  - `function`: la funcion a la que queremos llamar cuando el evento ocurra.
  - `useCapture`(opcional):Si queremos usar event bubbling(`false`) o event capturing(`true`)

  - https://www.w3schools.com/js/js_htmldom_eventlistener.asp

- `document.getElementById("ID")`: Te devuelve el elemento con el ID especificado entre corchetes.

  Es uno d elos mas usados en el DOM.

  Solo puede haber un elemento con un UNICO ID, pero si hubiera mas, devolvera el primero que encuentre.

  ```js
  document.getElementById("id");

  //En este ejemplo se cambia el texto el elem con id="demo"
  <script>
  function myFunction() {
    document.getElementById("demo").innerHTML = "Hello World";
  }
  </script>
  ```

  - https://www.w3schools.com/jsref/met_document_getelementbyid.asp

- `.appendChild(node)`: Indexa al documento un nodo en el ultimo lugar como "child":

  ```js
  const node = document.createElement("LI"); // Crea un nodo <li>
  const textnode = document.createTextNode("Water"); //Crea un nodo texto
  node.appendChild(textnode); //adjunta el texto a <li>
  document.getElementById("myList").appendChild(node); // Adjunta <li> a <ul> con id="myList"
  ```

- `.insertBefore(newNode, ExistNode)`: Inserta un nodo, justo **antes** de otro nodo, que se especificara:

  ```js
  var newItem = document.createElement("LI"); // Crea un nodo <li>
  var textnode = document.createTextNode("Water"); //Crea un nodo texto
  newItem.appendChild(textnode); //adjunta el texto a <li>

  var list = document.getElementById("myList"); // Obtiene el elemento <ul> para insertar el elemento
  list.insertBefore(newItem, list.childNodes[0]); // Inserta <li> antes del primer child de <ul>
  ```

- `document.createElement("etiqueta")`: Sirve para crear elementos de nodo (etiquetas) en el documento. Debe escribirse como argumento entre comillas.

  - Si queremos darle texto debemos usar `innerText` o `innerHTML`.
  - Una vez lo creemos, debemos insertarselo con `element.appendChild()` o `element.insertBefore()`

  ```js
  const btn = document.createElement("BUTTON"); // Crea un elem <button>
  btn.innerHTML = "CLICK ME"; // Inserta el texto
  document.body.appendChild(btn); // Append <button> to <body>
  ```

  - https://www.w3schools.com/jsref/met_document_createelement.asp

- `document.createTextNode("texto")`: Como el anterior, pero este crea un "texto" que posteriormente s etendra que adjuntar a una etiqueta/nodo con `element.appendChild()` o `element.insertBefore()`(Tambien podemos usar innerHTML o innerText)

- document.body`.childNodes`:Devuelve una coleccion de los nodos hijos de un elemento(en este caso el body)

  - https://www.w3schools.com/jsref/prop_node_childnodes.asp

- `.textContent` **_Property_**: Es muy parecido a innerText, pero con diferencias.

  - `textContent` returns the text content of all elements, while `innerText` returns the content of all elements, except for `<script> `and `<style>` elements.
  - `innerText` will not return the text of elements that are hidden with CSS (`textContent` will).

## Eventos y Methods mas importantes

- classList
- getAttribute()
- setAttribute()
- appendChild()
- append()
- prepend()
- removeChild()
- remove()
- createElement
- innerText
- textContent
- innerHTML
- value
- parentElement
- children
- nextSibling
- previousSibling
- style

## **TIPS**

- Es posible escribir codigo en Linea igual que haciamos con los Styles de CSS

## **DOM Events**

[DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp)

Permiten a JavaScript registrar diferentes enet handlers en los elementos d eun documento HTML.

Normalmente se usas en combinaciones con funciones y esta funcion se ejecutara despues de que este evento ocurra.(por ejemplo hacer click en un botón)

### **Listado de Eventos**

- `abort`: The event occurs when the loading of a media is aborted _UiEvent_, _Event_

- `afterprint`: The event occurs when a page has started printing, or if the print dialogue box has been closed _Event_

- `animationend`: The event occurs when a CSS animation has completed _AnimationEvent_

- `animationiteration`: The event occurs when a CSS animation is repeated _AnimationEvent_

- `animationstart`: The event occurs when a CSS animation has started _AnimationEvent_

- `beforeprint`: The event occurs when a page is about to be printed _Event_

- `beforeunload`: The event occurs before the document is about to be unloaded UiEvent, _Event_

- `blur`: The event occurs when an element loses focus _FocusEvent_

- `canplay`: The event occurs when the browser can start playing the media (when it has buffered enough to begin) _Event_

- `canplaythrough`: The event occurs when the browser can play through the media without stopping for buffering _Event_

- `change`: The event occurs when the content of a form element, the selection, or the checked state have changed (for `<input>`, `<select>`, and `<textarea>`) _Event_

- `click`: The event occurs when the user clicks on an element _MouseEvent_

- `contextmenu`: The event occurs when the user right-clicks on an element to open a context menu _MouseEvent_

- `copy`: The event occurs when the user copies the content of an element _ClipboardEvent_

- `cut`: The event occurs when the user cuts the content of an element _ClipboardEvent_

- `dblclick`: The event occurs when the user double-clicks on an element _MouseEvent_

- `drag`: The event occurs when an element is being dragged _DragEvent_

- `dragend`: The event occurs when the user has finished dragging an element _DragEvent_

- `dragenter`: The event occurs when the dragged element enters the drop target _DragEvent_

- `dragleave`: The event occurs when the dragged element leaves the drop target _DragEvent_

- `dragover`: The event occurs when the dragged element is over the drop target _DragEvent_

- `dragstart`: The event occurs when the user starts to drag an element _DragEvent_

- `drop`: The event occurs when the dragged element is dropped on the drop target _DragEvent_

- `durationchange`: The event occurs when the duration of the media is changed _Event_

- `ended`: The event occurs when the media has reach the end (useful for messages like "thanks for listening") _Event_

- `error`: The event occurs when an error occurs while loading an external file _ProgressEvent_, _UiEvent_, _Event_

- `focus`: The event occurs when an element gets focus _FocusEvent_

- `focusin`: The event occurs when an element is about to get focus _FocusEvent_

- `focusout`: The event occurs when an element is about to lose focus _FocusEvent_

- `fullscreenchange`: The event occurs when an element is displayed in fullscreen mode _Event_

- `fullscreenerror`: The event occurs when an element can not be displayed in fullscreen mode _Event_

- `hashchange`: The event occurs when there has been changes to the anchor part of a URL _HashChangeEvent_

- `input`: The event occurs when an element gets user input _InputEvent_, _Event_

- `invalid`: The event occurs when an element is invalid _Event_

- `keydown`: The event occurs when the user is pressing a key _KeyboardEvent_

- `keypress`: The event occurs when the user presses a key _KeyboardEvent_

- `keyup`: The event occurs when the user releases a key _KeyboardEvent_

- `load`: The event occurs when an object has loaded UiEvent, _Event_

- `loadeddata`: The event occurs when media data is loaded _Event_

- `loadedmetadata`: The event occurs when meta data (like dimensions and duration) are loaded _Event_

- `loadstart`: The event occurs when the browser starts looking for the specified media _ProgressEvent_

- `message`: The event occurs when a message is received through the event source _Event_

- `mousedown`: The event occurs when the user presses a mouse button over an element _MouseEvent_

- `mouseenter`: The event occurs when the pointer is moved onto an element _MouseEvent_

- `mouseleave`: The event occurs when the pointer is moved out of an element _MouseEvent_

- `mousemove`: The event occurs when the pointer is moving while it is over an element _MouseEvent_

- `mouseover`: The event occurs when the pointer is moved onto an element, or onto one of its children _MouseEvent_

- `mouseout`: The event occurs when a user moves the mouse pointer out of an element, or out of one of its children _MouseEvent_

- `mouseup`: The event occurs when a user releases a mouse button over an element _MouseEvent_

- `mousewheel`: Deprecated. Use the wheel event instead _WheelEvent_

- `offline`: The event occurs when the browser starts to work offline _Event_

- `online`: The event occurs when the browser starts to work online _Event_

- `open`: The event occurs when a connection with the event source is opened _Event_

- `pagehide`: The event occurs when the user navigates away from a webpage _PageTransitionEvent_

- `pageshow`: The event occurs when the user navigates to a webpage _PageTransitionEvent_

- `paste`: The event occurs when the user pastes some content in an element _ClipboardEvent_

- `pause`: The event occurs when the media is paused either by the user or programmatically _Event_

- `play`: The event occurs when the media has been started or is no longer paused _Event_

- `playing`: The event occurs when the media is playing after having been paused or stopped for buffering _Event_

- `popstate`: The event occurs when the window's history changes _PopStateEvent_

- `progress`: The event occurs when the browser is in the process of getting the media data (downloading the media) _Event_

- `ratechange`: The event occurs when the playing speed of the media is changed _Event_

- `resize`: The event occurs when the document view is resized _UiEvent_, _Event_

- `reset`: The event occurs when a form is reset _Event_

- `scroll`: The event occurs when an element's scrollbar is being scrolled _UiEvent_, _Event_

- `search`: The event occurs when the user writes something in a search field (for `<input="search">`) _Event_

- `seeked`: The event occurs when the user is finished moving/skipping to a new position in the media _Event_

- `seeking`: The event occurs when the user starts moving/skipping to a new position in the media _Event_

- `select`: The event occurs after the user selects some text (for `<input>` and `<textarea>`) _UiEvent_, _Event_

- `show`: The event occurs when a `<menu>` element is shown as a context menu _Event_

- `stalled`: The event occurs when the browser is trying to get media data, but data is not available _Event_

- `storage`: The event occurs when a Web Storage area is updated _StorageEvent_

- `submit`: The event occurs when a form is submitted _Event_

- `suspend`: The event occurs when the browser is intentionally not getting media data _Event_

- `timeupdate`: The event occurs when the playing position has changed (like when the user fast forwards to a different point in the media) _Event_

- `toggle`: The event occurs when the user opens or closes the `<details>` element _Event_

- `touchcancel`: The event occurs when the touch is interrupted _TouchEvent_

- `touchend`: The event occurs when a finger is removed from a touch screen _TouchEvent_

- `touchmove`: The event occurs when a finger is dragged across the screen _TouchEvent_

- `touchstart`: The event occurs when a finger is placed on a touch screen _TouchEvent_

- `transitionend`: The event occurs when a CSS transition has completed _TransitionEvent_

- `unload`: The event occurs once a page has unloaded (for `<body>`) UiEvent, _Event_

- `volumechange`: The event occurs when the volume of the media has changed (includes setting the volume to "mute") _Event_

- `waiting`: The event occurs when the media has paused but is expected to resume (like when the media pauses to buffer more data) _Event_

- `wheel`: The event occurs when the mouse wheel rolls up or down over an element _WheelEvent_

# Ultima clase JS

- `Defer` y `async`

  ```js
    <script defer src="deferred.js"></script>//deja el script para el final y se ejecutan de manera sincrona
    <script async src="async.js"></script>//lo corre
    //en caso de especificar assync y defer, async tiene preferencia
    //si ejecutamos varios script defer, se ejecutaran en el orden en que aparecen.//si hay varios async, se ejecutaran segun vayan terminando.
  ```

- Una funcion para cargar un script desde nuestro propio \*.js (INVESTIGAR)

  ```js
  function importScript() {
    return new Promise((resolve, reject) => {
      const script = document.createElement("script");
      script.onload =
    });
  }
  ```

- Que es el DOM: Document Object Model. Hace referencia al html. Se le llama a traves del objeto `document`

  cada etiqueta que modela el DOM (del html) es un nodo. El DOM coge el htm y lo convierte en un arbol gigante. Tambien los textos dentro de una etiqueta es un nodo de texto.

  Hay nodos de `elemento` y nodos de `texto`

  Este arbol sigue la nomenclatura de los arboles familiares: abuelo, hijo, nieto, ancestro, descendiente.

- Existe una clase/objeto concreto para cada etiqueta diferente del html:

  ```js
  const img = new HTMLImageElement();
  const a = new HTMLLinkElement();
  const ul = new HTMLUListElement();
  //etc...
  ```

  Todos esos tags a los que se puede hacer referencia, tienen propiedades que tambien se les puede llamar, que tienen su metodo en javascript.

- El objeto window es el Objeto Global. A traves de ella podemos acceder a las demas APIs del navegador. Tambien es lo mismo que global.this:

  ```js
  window.document;
  window.navigator;
  ```

- Los script en un html, comparten espacio window. Es decir, si tenemos dos scripts, las variables que creemos dentro de ellos, se comparten entre ellos.

## Eventos

Esperar a que algo ocurra y en funcion de ello se realizan ciertas cosas.

Conceptos:

- `event type`: Es un string, como "click". "mousemove", "keydown". Es la accion que se realiza y a posteriori se ejecuta otra accion.

- `target type`:
  El 90% de los eventos ocurren en window, document y elementos(tag hatml).

- `event handler`(o event listeners): Son manejadores de eventos. Es una funcion que responde ante un tipo de evento en un target especificado.

  Basicamente es una funcion o callback que actua despues de realizar el evento.

- `event object`: es un objeto asociado a un evento en particular. es inyectado como argumento en tu event handler.

  Todos los event objet tienen dos propiedades, el type y el target.

  El target es el objeto entero que insertamos y el tipo es el nombre del evento. Con lo cual, podemos acceder a ese objeto (target) y a sus propiedades. Por ejemplo en un input, con target.value nos dara el valor de ese input. (INVESTIGAR 11:25)

  ```js
  element.addEventListener(event, () => {
    console.log(element.target.value);
  });

  //event--> event type
  //element--> target type
  //function--> funtion
  //la referencia de event(input p ej)--> event object
  ```

  - Como registramos event handlers, 2 maneras:(INVESTIGAR)

    **ADVERTENCIA: no se recomienda usar eventos en linea!!**

    1. Antigua:

    ```js
    const button2 = document.querySelector("#button2");

    button2.onclick = () => {
      console.log("Forma antigua");
    };
    ```

    2. Buena, usando `addEventListener()`:

    ```js
    const button = document.querySelector("#button");
    button.addEventListener("click", () => {
      console.log("Forma buena");
    });
    ```

    Si ponemos un evento igual dos veces, solo lo hara una vez.
    Tambioen podemos crear nuestra funcion fuera y hacer referencia en el addEventListener en la parte del call back.

  - Se puede eliminar eventos con `removeEventListener()`

- Se pueden realizar eventos personalizados(INVESTIGAR 12:30)

- `.querySelector()`: Se pueden usar los selectores de CSS de la misma manera que en css. Excepto el padre, que tampoco se puede en css.

  ```js
  const ELEM_SELECTOR = "div";
  const CSS_CLASS_SELECTOR = ".card";
  const ID_SELECTOR = "#card";

  const div0 = document.querySelector(ELEM_SELECTOR);
  const div1 = document.querySelector(CSS_CLASS_SELECTOR);
  const div2 = document.querySelector(ID_SELECTOR);
  ```

  - Se puede acceder a padres hijos y hermanos a traves de metodos ya establecidos, pero casi no se usa. Es mejor usar los slectores de css en queryselector:

    ```js
    div0.parentElement;
    div0.firstChild;
    div0.nextSibling;
    ```

  - Tambien podemos hacer referencia a atributos de los elementos, acceder a ellos y manipularlos:

    ```js
    //referenciamos y damos valor
    div0.id = caja;
    //reemplaza, algo por algo
    div0.classList.replace("red", "green");
    //añade
    div0.classList.add("bold");
    ```

- Maneras de insertar de crear e insertar elementos. Hay 3 maneras principales que cubren casi todos los casos:

  - createElement:

  - innerHTML: Insertar codigo HTML en nuestro archivo.(INVESTIGAR)

- Recordar informacion en el navegador.

  En chrome tenemos en Application un Local Storage y Session Storage(esta se limpia al cerrar el navegador)(INVESTIGAR)

  - `setItem`:
  - `getItem`:

## Modificacion de CSS (INVESTIGAR)

https://www.digitalocean.com/community/tutorials/como-modificar-atributos-clases-y-estilos-en-el-dom-es
