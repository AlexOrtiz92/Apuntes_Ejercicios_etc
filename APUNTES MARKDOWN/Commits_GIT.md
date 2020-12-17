## Formato de los mensajes de commit

Todos los mensajes de los commits deben estar formados por una **cabecera** y un **cuerpo**.
La cabecera tiene un formato especial que incluye un **tipo**, un **ámbito**, y un **titulo/asunto**.

```
<tipo>(<ambito>): <asunto>
<BLANK LINE>
<cuerpo>
<BLANK LINE>
<pie>
```

La **cabecera** es obligatoria y el **ámbito** de la cabecera es opcional.

La longitud de todas las líneas del mensaje de commit debe ser inferior a 100 caracteres. Ésto permite que los mensajes
se puedan leer de forma agradable en la mayoria de las herramientas.

Ejemplos: (Mas en [ejemplos](https://github.com/angular/angular/commits/master))

```
docs(changelog): update change log to beta.5
```

```
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, and users need the latest of these.
```

## Deshacer un commit

Si el commit deshace un commit anterior, debe comenzar con `revert:`, seguido por la cabecera del commit que se deshace.
El el cuerpo debe decir: `This reverts commit <hash>`, donde el hash es el SHA del commit que se deshace.

## Tipo

Pude ser un de los siguientes::

- **feat**: Una nueva feature.
- **fix**: Arregla un bug.
- **style**: Cambios que no afectan al funcionamiento del código (Arreglos de: white-space, formatting, missing, semi-colons, etc).
- **refactor**: Cambios en el código que no arreglan un bug o añaden una feature.
- **build**: Cambios en los ficheros de configuración o scripts de construcción (configuracion de: npm, webpack, babel, ...).

## Ámbito

El ámbito puede ser cualquiera que indique dónde se realizó el cambio. Por ejemplo: `Buscador`, `TajetaECI`, etc.

## Asunto/Título

El asunto contiene una descripcion breve, concisa y precisa del cambio:

- Usa el imperativo y el tiempo prensente: "cambio" no "cambiado" ni "cambios".
- Sin mayúscula en la primera letra.
- Sin punto (.) al final.

## Cuerpo

Igual que el **asunto**, oraciones en imperativo y tiempo presente.
El cuerpo debe incluir la motivación del cambio y contrastarlo con el comportamiento anterior.
