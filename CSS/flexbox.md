## Flexbox

\*: valor por defecto

```css
div {
  display: flex;
  flex-direction: row * | row-reverse | column-reverse | column;

  /* Para que los elemento se pasen a la parte inferior si la ventana se hace mas pequena */
  flex-wrap: nowrap * | wrap;

  /* Simplificando flex-direction y flex-wrap */
  flex-flow: row wrap;

  /* eje x */
  justify-content: flex-start * | center | flex-end | space-between |
    space-around | space-evenly;

  /* eje y */
  align-items: flex-start | center | stretch | flex-end |baseline;
  /* baseline toma como base el texto para alinear las cajas.  */

  /* Se usa mayormente cuando tenemos varios bloques de elementos */
  align-content: flex-start | flex-end | center | space-(around, between);
}

p {
  order: 1, 2, 3;
  flex-grow: 1, 2, 5;
  align-self: center;
}
/* La propiedad order se usa en cada uno de los elementos para organizarlos de manera individual, por defecto el valor de order es 0 */

/* flew-grow: Nos ayuda a indicar el tamano que queremos que abarque cada uno de los elementos dentro de nuestro contenedor, entre mas grande el valor que le demos, mas espacio ocupa el elemento */
```

### Centrando elementos con flexbox y margin

![align-items](../imgs/Captura%20de%20pantalla%202023-10-23%20a%20la(s)%207.07.20 p.m..png)

```css
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

@media screen and (min-width: 1200px) {
  .container {
    flex-direction: row;
    width: max-content;
    margin-left: auto;
    margin-right: auto;
  }
}
```

![margins](../Captura%20de%20pantalla%202023-10-23%20a%20la(s)%207.05.49 p.m..png)
