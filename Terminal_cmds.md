# Comandos de la Terminal

- La ruta principal en Windows es C:\, en UNIX es solo /.
- Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.
  Recuerda que GitBash usa la ruta /c para dirigirse a C:\ (o /d para dirigirse a D:\) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es /c/Users/Nombre de tu usuario

## Comandos básicos en la terminal:

- pwd: Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
- rm: Nos permite borrar un archivo o carpeta (por ejemplo, rm archivo.txt). Mucho cuidado con este comando, puedes borrar todo tu disco duro. `rm -fr <nombre del directorio>`
- cat: Ver el contenido de un archivo (por ejemplo, `cat nombre-archivo.txt`).
- ls: Nos permite ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser -- + el nombre del argumento o - + una sola letra o shortcut por cada argumento).
  - -ls -a: Mostrar todos los archivos, incluso los ocultos.
  - -ls -l: Ver todos los archivos como una lista.
- cd: Nos permite navegar entre carpetas.
  - cd /: Ir a la ruta principal:
  - cd o cd ~: Ir a la ruta de tu usuario
  - cd carpeta/subcarpeta: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.
  - cd.. (cd + dos puntos): Regresar una carpeta hacia atrás. Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar cd . (cd + un punto).
- history: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
- ! + número: Ejecutar algún comando con el número que nos muestra el comando history (por ejemplo, !72).
- clear: Para limpiar la terminal. También podemos usar los atajos de teclado `Ctrl + L o Command + L.`
- Para “resetear” la pantalla `cmd + k`

- `mkdir <nombre_directorio>`: crea un directorio también puedes añadir la ruta
- `touch`: crea un archivo, si no indicas la extension por defecto sera .txt
- `cp <archivo> <ruta>`: nos permite duplicar archivos, para duplicar directorios con su contenido añadir el modificador -r que indica recursividad
- `mv <archivo> <ruta>` : mover un archivo hacia un directorio. También se usa para renombrar archivos `mv <archivo> <nuevo nombre>` no olvidar la extension del archivo Para mover directorios añadir el modificador -r
- `rm`: elimina archivos, con -i indica un mensaje de confirmación en consola para tener mas control sobre la elección de que archivos queremos eliminar. Para eliminar un directorio añadir -r y -ri para usar el mensaje de confirmación
-
- `rm -r dir2 dir3 mi_directorio`, para borrar múltiples archivos de manera rápida.
- `head archivo`, para mostrar las primeras 10 líneas del archivo.
  - `head archivo -n 15`, para modificar el número de líneas a mostrar.
- `tail archivo`, para mostrar las últimas 10 líneas del archivo.
  - `tail archivo -n 15`, para modificar el número de las últimas líneas a mostrar.
- `less archivo`, muestra una interfaz con todo el archivo, se puede hacer scroll, moverse con las flechas o con la barra espaciadora. Con el “/” seguido de una palabra que se quiere buscar. Para salir solo se presiona “q”.
- `code archivo/wslview archivo`, para abrir el archivo con VS desde la terminal.
- `Ctrl + c`, para matar procesos que se estén ejecutando en la terminal.
- `Open <nombredirectorio>` abre la carpeta en el finder

## OPERADORES DE CONTROL

Símbolos reservados por la terminal que permiten ejecutar más de un comando o ejecutarlos. Es posible ejecutarlos de forma síncrona, asíncrona o con condicionales.

- Forma síncrona: Se ejecutan uno detras de otro. Se colocan los comandos separados por un punto y coma ;.
- Forma asíncrona: Ejecuta comandos de forma paralela. Se colocan los comandos separados por un ampersand &.
- Forma condicional:
  - AND (&&) Solo se ejecuta si el comando anterior se ejecutó.
  - OR (||) Solo ejecutá el primer comando que sea ejecutable, los demas son ignorados.
  -

Cómo se manejan los permisos.

- Cuando listamos con ls -l se muestran varias cosas. Los tipos de archivos:
  - \- archivo normal.
  - d directorio.
  - l link simbólico.
  - b archivo de bloque especial.
- Tipos de modos: rwx corresponde con read, write y execute. Se representan con 3 bits, y los podemos manejar a través de un modo octal, esto es, pasar de binario a número.
  - rwx (1,1,1) dueño. En modo octal es 7.
  - r-x (1,1,1) grupo. En modo octal es 5.
  - r-x (1,0,1) world. Octal 5.
- Modo simbólico: Esto es para asignar los permisos a los diferentes posibles usuarios.
  - u Solo para el usuario.
  - g Solo para el grupo.
  - o Solo para otros (world).
  - a Aplica para todos.
