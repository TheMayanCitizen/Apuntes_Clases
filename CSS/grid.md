## GRID

```css
/* grid explicito: definimos el tamano y la cantidad de columnas y filas de nuetra grid */
div {
  display: grid;
  /* grid de 3x3 */
  grid-template-columns: 2rem 20vh 30%;
  grid-template-rows: 50% 100px 1fr;
  /* usando la propiedad repeat(rows/columns, tamaño) */
  grid-template-columns: repeat(5, 20%);
  grid-template-rows: repeat(4, auto);

  /* Propiedad de atajo, primero van las filas y despues las columnas. */
  grid-template: repeat(2, 50px 100px) / 100px 200px.;
}
```

### grid-auto-rows & grid-auto-columns

\*Estas propiedades hacen que cualquier nueva fila o columna que se cree tenga un tamano definido \*

![grid-auto-rows](../imgs/Screenshot%202023-10-22%20at%2010.40.39 PM.png)

```html
<div class="contenedor">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</div>
```

```css
.contenedor {
  background-color: #f6f1ee;
  display: grid;
  grid-template-columns: 100px 200px 300px;

  /* Asi indicamos que una vez llenadas las 3 columnas, se cree una nueva fila con 150px de height,  */
  grid-auto-rows: 150px;
  /* grid-auto-flow: column; */
  gap: 15px 20px;
}

.item {
  font-size: 4rem;
  border: 5px solid #5272f2;
}
```

### grid-auto-flow: columns | rows

\*el valor por defecto es rows

```css
.contenedor {
  background-color: #f6f1ee;
  display: grid;
  grid-template-columns: 100px 200px 300px;
  grid-auto-rows: 150px;
  /* Cuando indicamos column, lo que hace grid es crear nuevas columnas una vez que las que ya definimos anteriormente han ocupado su espacio, por eso 4 5 6 solo ocupan el espacio del contenido */
  grid-auto-flow: column;
  gap: 15px 20px;
}
```

![grid-auto-flow](../imgs/Screenshot%202023-10-22%20at%2010.48.52 PM.png)

```css
.contenedor {
  background-color: #f6f1ee;
  display: grid;
  grid-template-rows: 100px 200px;
  grid-auto-flow: column;
  grid-auto-columns: 150px;
  gap: 15px 20px;
}
```

En este caso estoy definiendo primero las filas y una vez que se llenan las filas que he indicado se crean nuevas columnas con grid-auto-flow:column, ademas le indico con grid-auto-columns que cualquier nueva columna que se cree sea de 150px.

![grid-auto-flow](../imgs/Screenshot%202023-10-22%20at%2010.59.38 PM.png)

### propiedades de alineacion

```css
div {
  display: grid;

  /* Estas propiedades ajustan la grilla completa en donde esta colocada */
  justify-content: start | end | center | stretch | space-around | space-between
    | space-evenly;
  align-content: start | end | center | stretch | space-around | space-between |
    space-evenly;

  /* Esta propiedad tanto el eje x como el eje y, tendran el mismo valor */
  place-content: center;

  /* Justify alineamos de manera horizontal */
  justify-items: start | end | center | stretch;
  /* Align es alineacion vertical*/
  align-items: start | end | center | stretch;
  /* Propiedad de atajo  en caso de que ambas propiedades sean iguales */
  place-items: center;
  place-items: start end.; /*asi se agrega 2 propiedades diferentes en una sola linea de codigo*/
}

.item {
  /* Estas propiedades se le dan a cada uno de los hijos del contenedor */
  justify-self: ;
  align-self: ;
  place-self: ;
}
```

### **grid area & grid-template-area**

### usando GRID-ROW, GRID-COLUM & GRID-AREA

grid-column-start & grid-column-end

**_shortcut_**: grid-colum: _valor inicial_ / _valor final_

grid-row-start & grid-row-end
**_shortcut_**: gri-row

**_shortcut para ambos(colum & area)_**: grid-area: _row-start_/_colum start_ / _row end_/_colum end_

![gridarea](../imgs/Screenshot%202023-10-22%20at%201.34.46 PM.png)

```html
<div class="container4">
  <div class="item item-1">1</div>
  <div class="item item-2">2</div>
  <div class="item item-3">3</div>
</div>
```

```css
.container4 {
  border: 5px solid #daddb1;
  background-color: white;
  display: grid;
  grid-template: repeat(3, 75px) / repeat(3, 150px);
  place-content: center;
}

.item-1 {
  border: 5px solid #d6c7ae;
  background-color: #fbecb2;
  grid-column: 1 / 4;
}

.item-2 {
  border: 5px solid #a7d397;
  background-color: #d0d4ca;
  grid-row: 2/4;
}

.item-3 {
  border: 5px solid #5272f2;
  background-color: #072541;
  grid-area: 2/2 / 4/4;
}
```

### usando GRID-TEMPLATE-AREA

```css
/* esto es una estructura especial de grid de forma visual*/
div {
  grid-template-areas:
    " head head" /* Estamos indicando que el area head va a ocupar 2 espacios */
    "menu content" /* 1fr para menu y el otro para el content */
    "foot foot"; /* Al igual que head, footer ocupara 2 espacios */
  /* IMPORTANTE: La cantidad de columnas deben ser las mismas, si ponemos un solo head o un solo foot, no se crea el grid */
}

/* grid-template-rows: 100px 500px 100px;  Si queremos podemos combinar las areas con grid-rows.*/

/* Si queremos cancelar algun area dentro de otras, lo hacemos con un punto */
div {
  grid-template-areas:
    " head head head"
    "menu . content" /*De esta forma estamos diciendo a css que en ese espacio no nos ponga nada*/
    "foot foot foot";
}
```

```html
<div class="container4">
  <div class="item item-1">1</div>
  <div class="item item-2">2</div>
  <div class="item item-3">3</div>
</div>
```

```css
.container4 {
  border: 5px solid #daddb1;
  background-color: white;
  display: grid;
  grid-template: repeat(3, 75px) / repeat(3, 150px);
  grid-template-areas:
    "header header header"
    "side main main"
    "side main main";
  place-content: center;
}

.item-1 {
  border: 5px solid #d6c7ae;
  background-color: #fbecb2;
  grid-area: header;
}

.item-2 {
  border: 5px solid #a7d397;
  background-color: #d0d4ca;
  grid-area: side;
}

.item-3 {
  border: 5px solid #5272f2;
  background-color: #072541;
  grid-area: main;
}
```

### FUNCIONES ESPECIALES (minmax & repeat)

minmax: nos sirve para darle un tamano minimo y un maximo a una celda. Sin depender del contenido que tengamos en ella.

```css
.contenedor {
  display: grid;
  grid-template-columns: minmax(30px, 300px) 200px minmax(60px, 250px);
  grid-template-rows: repeat(3, auto);
}
```

### Ejemplo

![mixmax&repeat](../imgs/Screenshot%202023-10-22%20at%202.25.49 PM.png)

```html
<div class="container5">
  <div class="item5">Estar cachudo esta de moda</div>
  <div class="item5">2</div>
  <div class="item5">Estar miludo esta de moda</div>
  <div class="item5">4</div>
  <div class="item5">5</div>
  <div class="item5">6</div>
  <div class="item5">7</div>
  <div class="item5">8</div>
  <div class="item5">9</div>
</div>
```

```css
.container5 {
  background-color: #d2de32;
  border: 5px solid white;
  display: grid;
  grid-template: repeat(3, auto) / minmax(30px, max-content) 200px minmax(60px, 250px);
}

.item5 {
  font-size: 2rem;
  border: 5px solid blue;
}
```

### Keywords Especiales (fr, min-content, max-content, auto-fill/auto-fit)

```css
.container6 {
  border: 5px solid #f6ffde;
  background-color: #aac8a7;
  display: grid;

  /*Todas las columnas abarcan el mismo espacio dentro de nuestra grilla */
  grid-template-columns: repeat(4, 1fr);

  /* Cada elemento de la grilla abarca diferentes fracciones de la grilla */
  grid-template-columns: 1fr 3fr 2fr 1fr;
}

.container6 {
  border: 5px solid #f6ffde;
  background-color: #aac8a7;
  display: grid;

  /* EL ancho que toma es el minimo posible en base al contenido*/
  grid-template-columns: 1fr 3fr min-content 1fr;

  /* Al usar max-content la columna se extiende para que todo el contenido quepa dentro de la ella si es posible dentro de una sola linea */
  grid-template-columns: 1fr 3fr max-content 1fr;
}
```

### fit-content()

Este metodo ocupa los 2 conceptos anteriores, pasandole un valor como parametro, con esto podemos definir el valor maximo al que llega el elemento y como minimo toma el min-content.

```css
.grid-container {
  display: grid;
  grid-template-columns: 150px fit-content(400px) 150px;
}
```

### Ejemplos con auto-fit y auto-fill

auto-fit: hace que las columnas se expandan hasta llenar el espacio completo del contenedor. Nos permite generar columnas dinamicamente segun el valor que tenga repeat y el espacio del contenedor, pero si no hay suficientes elementos para cubrir todo el espacio entonces seguiran creciendo las columnas sin generarse nuevas.

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, 200px);
}
```

![auto-fit](../imgs/Captura%20de%20pantalla%202023-10-23%20a%20la(s)%209.42.17 a.m..png)

auto-fill: Nos permite generar columnas dinamicamente segun el valor que le coloquemos al repeaty el espacio del contenedor, pero cuando la cantidad de elementos no es la suficiente para cubrir todo el espacio, se generan columnas ficticias.

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, 200px);
}
```

![auto-fill](../imgs/Captura%20de%20pantalla%202023-10-23%20a%20la(s)%209.37.50 a.m..png)

Recuerda que al usar cualquiera de los 2, debes usar minmax() para que funcionen.

![autofit&autofit](../imgs/Screenshot%202023-10-22%20at%205.35.34 PM.png)

```html
<h3>auto-fit</h3>
<div class="container6">
  <div class="item6 item6-1">1</div>
  <div class="item6 item6-2">2</div>
  <div class="item6 item6-3">3</div>
  <div class="item6 item6-4">4</div>
</div>

<h3>auto-fill</h3>
<div class="container6-2">
  <div class="item6 item6-1">1</div>
  <div class="item6 item6-2">2</div>
  <div class="item6 item6-3">3</div>
  <div class="item6 item6-4">4</div>
</div>
```

```css
.container6 {
  border: 5px solid #f6ffde;
  background-color: #aac8a7;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}

.container6-2 {
  border: 5px solid #f6ffde;
  background-color: #aac8a7;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
}

.item6 {
  border: 5px solid #c9dbb2;
  font-size: 2rem;
}
```
