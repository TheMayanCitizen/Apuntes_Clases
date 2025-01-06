# COMANDOS BASICOS EN GIT

- `git init`: Se usa para iniciar un repositorio de git en el directorio de trabajo actual.
- `rm -rf .git`: Se usa para remover completamente tu repositorio local sin afectar los demas archivos dentro del directorio de trabajo.

- `git add .`: Agrega todos los cambios que se hayan hecho al area de stagging.

- `git commit -m " "`: Pasa los cambios del area de staggin al repositorio. Siempre va con un mensaje.
- `git commit -am " "`: Combina git add y commit en uno solo, pero al archivo ya se le debio haber aplicado un add anteriormente.

  - Si enviamos un commit sin mensaje, nos lleva a vim, donde tenemos que escribir el mensaje. Es una mala practica enviar commits sin mensaje.
  - `esc + shift + z z`: para salir de vim.
  - `esc + i`: Para empezar a escribir texto.

- `git checkout .`: `git checkout "dot"` discards the changes made in order to not add changes to stage and avoid commit.

- `git status`: Analiza si ha habido cambios en el working directory.

- `git log <nombre de archivo>`: Muestra todo el historial de cambios hechos al archivo, si no ponemos el nombre
  del archivo sale el historial de todos los archivos.

  - `git log --stat`: Muestra los cambios detallados de los commits hechos al archivo.
  - `git log --all --graph --decorate --oneline`: Muestra todos los commits de una forma legible
  - `git log --oneline --graph --all`: Usar este en vez del comando de arriba ya que el decorate no funciona.

- `git config`: Muestra configuraciones de git también podemos usar `--list` para mostrar la configuración por defecto de nuestro git
  y si añadimos `--show-origin` inhales nos muestra las configuraciones guardadas y su ubicación.

  - `git config --global user.name "nombre de usuario"`: Cambia de manera global el nombre del usuario, seguidamente ponemos entre comillas nuestro nombre.
  - `git config --global user.email "email"`: Cambia de manera global el email del usuario, seguidamente ponemos entre comillas nuestro nombre.
  - `git config --global -e`: Permite editar las configuraciones globales, si no tenemos el vscode establecido como predeterminado nos abrira el vim.
  - `git config --global core.editor "code --wait"`: Usa vscode como favorito y al usar el comando anterior podemos editar las configuraciones globales directamente en el editor.

Diferentes sistemas operativos usan diferentes caracteres para representar el final de una línea. (También son conocidas como newlines o line breaks.) Como Git usa éstos caracteres para comparar archivos, esto puede causar problemas inesperados cuando se edita un archivo en máquinas diferentes.

Se recomiendan las siguientes configuraciones:

- linux o MacOs

  - `git config --global core.autocrlf input`

- windows

  - `git config --global core.autocrlf true`

---

- `git shortlog`: Indica que commits ha realizado un usuario, mostrando el usuario y el titulo de sus commits.
- `git log --author="Name Author"`: Commits realizados por autor que cumplan exactamente con el nombre.

- `git show`: Muestra los ultimos cambios entre la version mas reciente y la anterior.

- `git reflog`: Muestra todo el historial de cambios hechos en el repositorio, con index, como si fuera un array.

- `git diff tag1 tag2`: Muestra las diferencias entre los commits que seleccionamos, es recomendable poner el commit mas antiguo en el tag1 y el mas reciente en el tag2.

- `git checkout <id del commit> <nombre del archivo>`: Sirve para analizar una version anterior del archivo, si hacemos un `git status`, nos mostrara que ha habido un cambio, si hacemos el `git commit`, corremos el riesgo de perder nuestra ultima version, para resolver este asunto, debemos hacer un checkout del archivo master y despues hacer el commit.

- `git commit --amend -m " "`: Si nos equivocamos en el mensaje del archivo, con este comando lo podemos arreglar.

- `git mv <nombre del archivo> <nuevo nombre del archivo>`: Sirve para cambiar de nombre un archivo y que git registre el cambio.

- `git rm <nombre del archivo>`: Sirve para remover un archivo del disco duro, despues de remover hay que hacer un commit para guardar el cambio.

- `git reset --soft <id del commit>`: Regresa al punto que indicas pero no recupera el archivo si es que lo eliminaste, solo puedes ver las modificaciones que hayas hecho. Sirve mas para modificar el histórico de cambios sin alterar los archivos, p.j. si a partir de un punto en especifico quisieras cambiar los commits posteriores. (Un nuevo historial).

- `git reset --hard <id del commit>`: Regresa al punto que indicas y recupera el archivo en el working directory si es que lo eliminaste.

- `git reset --mixed <id del commit>`: Regresa al commit que indiquemos, borra los commits posteriores a ese pero guarda los cambios de los commits borrados. Cuando hacemos un nuevo commit, se guardan los cambios de los commits borrados (pero no los commits) y los ultimos cambios realizados.

# COMANDOS CON RAMAS: Cuando creamos una rama, esta hace una copia de donde esta ubicado el apuntador "HEAD" ya sea en la rama main o en alguna otra.

- `git switch -c <branch-name>`:create a new branch named `<branch-name>` and switch to it immediately.

- `git branch <nombreDeLaRama>`: Sirve para crear una rama de trabajo. IMPORTANTE, SIEMPRE POSICIONARNOS EN LA RAMA "MASTER" ANTES DE CREAR UNA NUEVA RAMA.
  Para movernos entre ramas solo hay que hacer un `git checkout nombreDeLaRama`.
- `git checkout <nombre de la rama>`: Nos movemos a la rama y el apuntador "HEAD" a la rama que indicamos. IMPORTANTE GUARDAR LOS CAMBIOS HECHOS ANTES DE MOVERNOS A OTRA RAMA, O PODRIAMOS PERDER NUESTROS CAMBIOS.
- `git branch`: Sirve para saber cuantas ramas tenemos y para ver en cual estamos.
- `git branch --delete <nombreRama>`: Elimina la rama que se indique.
- `git branch -v`: Muestra el ultimo commit de cada rama.
- `git branch -r`: Muestra las ramas en nuestro repositorio remoto.
- `git branch -a`: Muestra todas las ramas locales y remotas.
- `git merge <nombreDeRama con la que voy a fusionar>` : Sirve para fusionar la rama "master" con otra rama. IMPORTANTE SITUARNOS PRIMERO EN LA RAMA "MASTER" ANTES DE HACER UN MERGE.
  Cuando hay conficltos al hacer un merge de ramas, y ya sea que mantengamos los cambios actuales o aceptemos los cambios que vienen, siempre hay que hacer un `git commit`, porque realizamos cambios en el archivo.
- `git push origin --all`: Envía todas las ramas de nuestro repo local al remoto.
- `git push origin <nombre de la rama que quiero enviar al repo remoto>`: Por ejemplo, si es una que no es main o la rama principal.
- `git branch -d <nombre de la rama>`: Para borrar una rama, si no funciona -D (mayúscula).

**CUANDO QUEREMOS COPIAR UNA RAMA DEL REPO REMOTO QUE NO EXISTE EN NUESTRO REPO LOCAL HACEMOS ESTO....**

`git reset --hard origin/<remote_branch_name>`

Example: if your branch name is master:

`git reset --hard origin/master`

This command will discard any of your local branch changes and make your local branch exactly same as your remote brach. In another word, it makes your local branch a carbon copy of your remote branch.

# COMANDOS CON UN REPOSITORIO REMOTO AJENO AL NUESTRO.

- `git clone`: Clona el repositorio remoto a nuestra carpeta (directorio de trabajo) y al repositorio local. En el área de staging no hay nada.
- `git fetch`: Trae los cambios hechos en el repositorio remoto pero solo los agrega al repositorio local sin afectar el directorio de trabajo.
  Para combinar los cambios hechos en el repo remoto con lo que tenemos en el directorio de trabajo, hay que hacer un merge.
- `git pull`: Hace lo mismo que fetch y merge pero en un solo comando, en otras palabras, actualiza tanto en el repo local como en el directorio de trabajo.

# ENLAZAR GIT CON EL REPOSITORIO REMOTO EN GITHUB

1. Asegurarnos que en la terminal, estamos posicionados en el directorio donde estamos trabajando y en la rama main.
2. Agregar el origen remoto de nuestros archivos
   `git remote add origin < url o ssh> `
3. Comprobamos que se han enlazado con git remote, nos debe devolver la palabra origin `git remote -v: v(verbal)`, nos retorna algo similar a esto:

```
origin	git@github.com:TheMayanCitizen/Practica-Git-Github.git (fetch)
origin	git@github.com:TheMayanCitizen/Practica-Git-Github.git (push)
```

4. Estamos enlazados.

5. Enviamos nuestros archivos del repositorio local a Github;

- Lo primero que debemos hacer es traernos los archivos del repo en Github.
  `git pull origin main(o master)`: Si solo ponemos solo git pull(sin origin main) nos pedira algo como `git pull <remote> <branch>`, por eso hay que poner origin main

  - Si nos da el warning: "refusing to merge unrelated histories, usamos el comando:

    `git pull origin main(o master) --allow-unrelated-histories`

    Esto se hace para forzar el merge de los archivos en el repo remoto y el local.

    `git push origin main(o master)`: Ahora revisa el repo en github deben estar ahi todos los archivos del repo local.

`git remote set-url origin tu_repo_url`: cambiar el url de un repositorio de git

# TAGS Y ALIAS EN GIT: Los alias sirven solo mientras la consola esta abierta, una vez que se cierra se borran.

`alias`: muestra una lista de los alias predeterminados que existen en git.

## Para crear un alias en git:

- `alias <nombreDelAlias>=<parametros del alias>`
- `alias arbolito = "git log --all --graph --decorate --oneline"`

## Para crear un tag:

- `git tag -a <v0.1 o la version que sea> -m "Comentario" <ID del commit al que se le hará el tag>`

- `git show-ref --tags`: Muestra los tags y a que commit esta asignado.
- `git push origin --tags`: Envia el tag a Github.
- `git tag -d <nombre del tag a borrar>`: Borrar un tag desde git.
- `git push origin :refs/tags/dormido`: Borrar un tag en Github
- `git tag -a v1.0.0 -m "RestServer quick start"` <--- esta forma es como se muestra en el curso de Fernando Herrera

- `git push --tags`

## Para crear un release tag en github:

- Vamos a los tags creados, damos click en el tag y damos en "create a release tag" boton, se encuentra a un lado del boton de "delete tag".
- Llenamos el nombre del tag y la descripcion y damo en el "release tag" al final de la pagina.

# GITIGNORE

Git ignore: Sirve para que git deje de trackear ciertos archivos que no queremos, se hace creando un archivo llamado .gitignore en la carpeta raiz. Dentro del archivo escribimos los archivos a ignorar(nombres, tipos de archivos etc.)

En Mac vas a encontrar un archivo llamado .DS_Store, para que git no traquee este archivo, vamos a escribir dentro del .gitignore la siguiente linea:
`.*` y guardamos. Esta linea(.\*) le dice a git, todos los archivos ocultos los vas a ignorar.

# CONTENT DELIVERY MANAGERS (IMGUR)

## Paso a paso para utilizar imgur

1. entra en la pagina
2. sube la imagen (no es necesario estar registrado)
3. copia la direccion url que se le asigna a la imagen
4. en tu archivo html dentro la etiqueta para un nuevo parrafo escribre la etiqueta para crear una nueva ancla `<a></a>`
5. dentro de los signo de la primera a escribe el vinculo `href=tu_url`
6. dentro de la etiqueta para el ancla escribe la etiqueta de la imagen espesificando la direccion, la cual sera igual a la direccion del hipervinculo pero con una i al principio y terminando con .jpg
7. cierras la etiqueta de ancla y cierras la etiqueta del parrafo ejemplo

- `<p><a href="https://imgur.com/P0uCD21"><img src="https://i.imgur.P0uCD2l.jpg" width="100%" title="descripcion de la imagen" /></a></p>`

# GIT REBASE

`Git rebase <nombre de la rama>`:

Es otra forma de hacer un merge de dos ramas, pero en este caso no queda registros de que haya existido otra rama.

Pj, si tenemos la rama main y la rama experimento, hacemos un git rebase, no quedaría registro de que existio la rama experimento.
Para hacer esto primero nos posicionamos en la rama experimento, segundo hacemos un `git rebase main` y con eso estamos "actualizando" la rama experimento con lo que tiene master, por ultimo, nos movemos a la rama main hacemos un `git rebase experimento` y de esta forma nos traemos todo lo que haya existido en la rama experimento a la rama main y de paso borramos el historial de la rama. Es como si todos los cambios se hubiesen hecho en main.

# GIT STASH:

Hemos hecho unos cambios a un archivo en la rama main, si damos git status nos saldra que hay que hacer un commit, pero si yo no quiero hacer ese commit por que aun no estoy listo,y necesito cambiar de rama, uso git stash, que sirve para guardar cambios hechos al código sin tener que hacer un git add, guarda los cambios en una "reserva" y nos regresa al ultimo commit de la rama main, ahora si podemos cambiar de rama sin peligro.

- `Git stash list`: Lista todos los stash hechos.

Una vez que regresamos a la rama donde hicimos el git stash usamos `git stash pop`.

- `Git stash pop`: trae los cambios guardados en la reserva pero aun hay que hacer un git add, si es que queremos que se guarden esos cambios.

- `Git stash branch <nombre de la rama nueva>`: Crea una nueva rama con el nombre que indiquemos, y lo que haya en stash lo "transfiere" a esta nueva rama que creamos.Si regresamos a la rama main, y hacemos un git stash list, no nos retorna nada.

- `Git stash drop`: Sirve para eliminar cambios guardados en stash.

# GIT CLEAN:

Mientras estamos trabajando en un repositorio podemos añadir archivos a él, que realmente no forma parte de nuestro directorio de trabajo, archivos que no se deberían de agregar al repositorio remoto. El comando clean actúa en archivos sin seguimiento(untracked), este tipo de archivos son aquellos que se encuentran en el directorio de trabajo, pero que aún no se han añadido al índice de seguimiento de repositorio con el comando add.

- `Git clean --dry-run`: Al ejecutar el comando, se muestra una lista de lo que va a borrar.

- `Git clean -f`: Borra los archivos. No borra carpetas, esas hay que borrarlas a mano. Tampoco borra los archivos en gitignore.

# GIT CHERRY-PICK:

Sirve para traer un commit viejo de otra rama a mi rama main.

Digamos que a nuestra rama main queremos agregarle unos cambios que hicimos en la rama "mejoras", pero el ultimo commit de la rama mejoras ya tiene muchos cambios hechos adelante del cambio que queremos extraer. Lo que hacemos es, en la rama "mejoras" copiar el id del commit que queremos extraer a la rama main, nos movemos a la rama main, usamos el comando `git cherry-pick <id del commit>` y presionamos enter. Listo el commit viejo de la rama "mejoras" ya esta en la rama main.

# GIT REFLOG:

Nos muestra un historial de toditos los movimientos que hemos hecho, desde los commits hasta cuando nos movemos entre ramas.

Se debe usar solo en caso de emergencias junto con `git reset --hard`,

1. Usamos el comando `git reflog`.
2. Copiamos el id del commit al que quiero regresar,
3. Escribimos el comando `git reset --hard <id del commit al que vamos a regresar>`
4. Salvaste el semestre haha.

# GIT AMEND

- `git commit --amend -m " " `: Si nos equivocamos en el mensaje del archivo, con este comando lo podemos arreglar.

# GIT GREP

- `git grep color` -->use la palabra color
- `git grep la` --> donde use la palabra la
- `git grep -n color`–> en que lineas use la palabra color
- `git grep -n platzi` --> en que lineas use la palabra platzi
- `git grep -c la` --> cuantas veces use la palabra la
- `git grep -c paltzi` --> cuantas veces use la palabra platzi
- `git grep -c “<p>”`–> cuantas veces use la etiqueta `<p>`
- `git log -S “cabecera”` --> cuantas veces use la palabra cabecera en
  todos los commits.
- `grep`–> para los archivos
- `log` --> para los commits.

# COMANDOS COLABORATIVOS EN GIT.

- `git shortlog -sn` = muestra cuantos commit han hecho cada miembros del equipo.
- `git shortlog -sn --all `= muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
- `git shortlog -sn --all --no-merge `= muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
- `git blame ARCHIVO `= muestra quien hizo cada cosa linea por linea
- `git COMANDO --help `= muestra como funciona el comando.
- `git blame ARCHIVO -Llinea_inicial,linea_final`= muestra quien hizo cada cosa linea por linea indicándole desde que linea ver ejemplo -L35,50

# Configuracion de llaves ssh guia

https://platzi.com/tutoriales/1557-git-github/4067-configurar-llaves-ssh-en-git-y-github/
