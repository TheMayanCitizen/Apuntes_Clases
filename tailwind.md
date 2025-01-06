## Setting Up Tailwind

- Instalar extension Tailwindcss IntelliSense

### Instalando Tailwind CLI con HTML(en la terminal)

1. Usar el gestor de paquetes de node usando el comando `npm init -y` para crear el **package.json**.

2. Instalar Tailwind como dependencia de desarrllo usando el comando `npm i -D tailwindcss`(viene en la documentacion) y se usa solo para crear la carpeta **_"node_modules"_** y **_"package-lock.json"_**

3. `npx tailwindcss init` crea el archivo **_"tailwind.config.js"_**, en este archivo configuramos tailwind. En el objeto `content:[ ]`, vamos a escribir `content: ["./src/**/*.{html,js}"]`, lo que dice este archivo es que "dentro de la carpeta src, vamos a buscar cualquier archivo `.htm`l y `.js` que tengas clases de utilidad.

4. Creamos la carpeta `src` dentro de la carpeta de nuetro proyecto. Dentro de esta carpeta vamos a crear nuestro archivo index.html. Ademas creamos nuetro archivo `input.css` y pegamos estas directivas.

- @tailwind base;
- @tailwind components;
- @tailwind utilities;

5. (OPCIONAL), En el archivo package.json, en el apartado de `scripts` creamos un nuevo comando. Debe verse algo asi. O lo podemos correr el comando desde la consola directamente para esto solo pegamos desde "npx" hasta "--watch" en la consola.

```js
"scripts": {
"build": "npx tailwindcss -i ./src/input.css -o ./src/assets/output.css --watch"
}
```

Este comando va a tomar el archivo donde guardamos nuestras directivas de Tailwind que el es archivo con la bandera -i y va crearno el archivo `output` que es el "compilado" de todos nuestro css. La bandera `--watch` sirve para que tailwind constantemente este escaneando los cambios que se crean en los archivos que le dijimos que escanee. Para activar el script en la terminal tecleamos `npm run build`

6. Por ultimo linkeamos el archivo `output.css` en nuestro html

## Instalando Tailwind para proyectos de produccion usando vitejs.

1. Colocados en la carpeta de nuestro proyecto, donde se encuentra nuestro "index.html", abrimos la terminal y escribimos `npm init -y`

2. `npm install -D tailwindcss` para instalar tailwind.
3. Creamos un archivo `input.css`, que sera nuestro input, el nombre no importa. Y agregamos estas lineas en el archivo.

   - @tailwind base;
   - @tailwind components;
   - @tailwind utilities;

4. `npx tailwind init` para generar el archivo de configuracion de tailwind. Aparecera como "tailwind.config.js".
5. En el archivo "tailwind.config.js", en el apartado de "content:[]", vamos a escribir todos los archivos que vayan a contener clases de tailwind. Por ejemplo.
   **content:["./index\.html"]**.

6. `npm i -D vite postcss autoprefixer".

   - postcss es para mejorar la compilacion y autoprefixer es para mejorar la compatibilidad de los navegadores.

7. `npx tailwindcss init -p` para crear el archivo de configuracion de postcss. Se mostrar como "postcss.config.js"

8. En el archivo package.json, en la seccion de scripts agregamos estos 3 comandos:
   "scripts":\{

   - "dev" : "vite dev",
   - "build": "vite build",
   - "preview" : "vite preview"

\}

9. Para empezar a trabajar usamos `npm run dev` para que vite nos cree un servidor local. Recuerda agregar el link del archivo "input.css" a tu archivo "index.html"

- `npm run build` nos crea un archivo dist que es el paquete listo para produccion.
- `npm run preview` nos levanta un localhost para la previsualizacion de nuetro build de produccion.

Extensiones recomendadas

- tailwindcss instellisense.
- prettier
- prettier-plugin-tailwindcss.
  Installation

To get started, install prettier-plugin-tailwindcss as a dev-dependency:

`npm install -D prettier prettier-plugin-tailwindcss`

Then add the plugin to your Prettier config:

```js
// prettier.config.js
module.exports = {
  plugins: ["prettier-plugin-tailwindcss"],
};
```
