## Formato a _TEXTOS_

```html
<h1>Formato de Textos en CSS</h1>
<div class="caja">
  <p class="texto">
    Este es un parrafo random a lo mas random que jamas ha existido amigos
  </p>
</div>
```

```css
h1 {
  color: #ef476f;
  background-color: beige;
  text-align: center | justify | left | right | inherit;
  text-transform: uppercase | capitalize | lowercase;
  text-shadow: * eje-x * * eje-y * * difuminacion * * color *;
  text-shadow: 2px 2px 2px #ced4da;

  letter-spacing: 3px | -3px; /*Separacion por letras*/
  word-spacing: 10px; /*Separacion por palabras*/
  text-decoration: overline underline;
}

.caja {
  padding: 15px;
  margin: auto; //Centra la caja
  width: 70%; //El 70% de la pantalla
  background-color: blue;
  border-radius: 5px;
  color: white;
  float: left; /* para que las cajas se vayan acomodando a la izquierda*/
}

.texto {
  text-align: justify;
  direction: ltr | rtl; /*left to right | right to left*/
  text-decoration: underline | line-through | overline;
  text-indent: 30px; /*indentacion*/
  line-height: 1.5 | 3 | 0.8; /*espacio entre lineas*/
  white-space: nowrap | normal;
  /* 
    nowrap: el texto no se envuelve dentro del elemento contenedor, no hay ningun enter
  */
}
```

## Manejo de _fuentes_

```css
p {
  font-family: "Times New Roman";
  font-style: italic | normal | oblique;
  font-weight: 100 - 900 | bold | bolder | lighter; /*ancho de fuente*/
  font-variant: small-caps; /*Todo mayusculas pero las primeras letras mas grandes */
  font-size: 16px | 1em | 2vw; /*tamano de fuente*/

  /* Simplicacion del font */
  font: * style * * variant * * weight * * size/line-height * * family *;
}
```
