# Comandos para GIT
Es un software de control de versiones, o Sistema de Control de Versiones Distribuido  
**Primero** de todo tendremos que descargarnos el software en la pagina de GIT.  
Creacion de repositorios tanto en local como en remoto.  

---
- Abrir terminal en MAC--> command+space-->abre Spootlight y marcamos terminal
- Interfaces para usar Git en tu equipo son GitKraken o Sourcetree
- Repositorios en la Nube son Github o Bitbucket

## Comandos

- `$ git init`: con este comando crearemos el repositorio en local en la carpeta que le indiquemos en la terminal con `cd "ruta de archivos"`

- `$ git config --global user.email alejandro.ortiz.ortega@gmail.com`

- `& git config --global user.name "AlexOrtiz92"`

- `$ git add "nombre archivo"`: añadimos los archivos de nuestra Working Area a la Stage Area.  
    - `$ git add . `: sube todo a la Stage Area menos lo ya trackeado (ya subido)
    - `$ git add -A`: sube todo a la Stage Area

- `$ git commit -m "mensaje del commit"`: Hacemos un commit y pasamos los archivos de la Stage Area al Repositorio Local

- `$ git status`: te indica como esta la situacion, si hay archivos sin commitear, si se ha actualizado algun archivo d ela working file etc.

- `$ git log`: te indica los commits que has hecho y mas informacion.

- `$ git log --oneline --graph --all`: e sun log mas bonito

- `$ gir --version`: te indica la version de GIT con la que trabajas y tienes instalada.

- `$ git rm "nombre archivo" --cache`: elimina archivos de la stage area.

- Los archivos *.gitignore son archivos que sirven para hacer que git ignore los archivos que no quieras que añada y commitee. 
    - se escribe directamente el nombre del archivo.
    - si ponemos *.jpg ignorara todos los archivos jpg.
    - si ponemos nombre.* ignorara todos los archivos que se llamen asi.
    - Si tengo una carpeta y pongo /imagenes ignorara toda la carpeta


- `$ git remote add origin "ruta del repo"`: enlazamos el repositorio local con un repositorio en la nube, ya sea en [Github](https://github.com/AlexOrtiz92)  o [Bitbucket](https://bitbucket.org/dashboard/overview).

- `$ git push origin master`: este comando sube los archivos del repositorio Local al repositorio en la nube (origin) en GitHub. Despues de indicarle origin, tendremos que poner el "nombre" de la rama al que queramos subirlo, en este ejemplo se sube a master. **CUIDADO: Trabajaremos siempre con Pull-request**

- `$ git pull origin master`: hace lo mismo solo que ahora te traes el repo de la nube al Local.

- `$ git checkout master`: cambiamos de rama en la que nos encontramos indicandole el nombre de la misma. En este ejemplo es master.

- `$ git branch "nombre de rama"`: crea una rama con el nombre que se le indique.

- `$ git clone "ruta de repo en nube"`: crea un clon del repositorio en la nube en tu Local.

- Hacer **MERGE** (INTO)
    1. Hacemos `$ git checkout master` a la rama que que vas a mergear otra
    2. `$ git merge develop`para mergear la rama develop en master.
    via--> [git-scm.com](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

- `$ git branch -d develop`: eliminar una rama, en este ejemplo se elimino develop.

- Hacer **REBASE** (ONTO)
    1. Hacemos `$ git checkout master` a la rama que que vas a rebasar otra.
    2. `$ git rebase develop` para rebasar la rama develop en master.
    via--> [git-scm.com](https://git-scm.com/docs/git-rebase)

- **PULL-REQUEST**: es la m,anera de trabajar mejor, en vez de hacer merge y rebases. Es una manera controlada y se hace a traves de GitHub.

---
1. Indicamos Carpeta donde vamos a crear el reopsitorio con `cd`
2. git init--> crear el repositorio
3. git status--> ver como esta la cosa, el estado del repositorio.
4. git config--> para indicar el correo y el usuario con el que se registraran los cmabios
5. git add--> añadir los archivos a la stage area
6. git commit-->añadir los archivos al repositorio local
7. enlazamos el repositorio local con el repositorio en remoto creado en GitHub o BitBucket

---
## Trabajando con GIT

La mejor manera de trabajar es con Git Flows. Aqui indico uno de los mas famosos, el modelo de Vincet Driessen via --> [enlace](https://nvie.com/posts/a-successful-git-branching-model/)
   
![Vincet Driessen gitflowVincet Driessen](Vincent_Driessen-GitFlow.png "Vincet Driessen gitflowVincet Driessen")


























---
[@@@@@ AYUDA con Markdown](https://markdown.es/sintaxis-markdown/)