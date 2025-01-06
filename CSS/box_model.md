## Box model

content: texto, imagenes

padding: envuelve al contenido, separa el contenido del borde, es transparente.
`padding: 10px 5px 15px;`: indicamos que 10px top, 5px left & right y 15px bottom.

border: envuelve al padding, solo a este se le puede agregar color.

margin: envuelve al elemento completo y separa al elemento html de los demas elementos, es transparente.

width: Para saber el ancho completo de nuestro elemento html tenemos que sumar el width que indiquemos + padding + border + margin.

outline:Es un concepto que se ubica entre el margen y el borde, no se toma en cuenta para sumar un ancho o alto de una caja. Si se le puede agragar color. Se sobrepone al margen.

```css
/* Usa los mismo parametros para los bordes */
div {
  outline: 10px solid #34c394;

  /* Separacion entre el borde y el outline, se aplica el mismo valor para todos los lados, no se puede personalizar cada lado del outline */
  outline-offset: 10px;
}
```

### Quitar el outline en inputs

Se usa para temas de accesibilidad. Cuando una persona que usar los "aria" sepa que esta haciendo focus en ese input

```css
input:focus-visible {
  outline: none;
}

/* No recomendable hacer esto, porque las "aria" no detectan cuando se hace focus en el input, visualmente si se aplica el estilo pero no es reconocido para el "aria" */
input:focus {
  outline: none;
}
```

### box-sizing:border-box

Se usa para establecer un ancho fijo de nuesto elemento, pj si indicamos que el elemento debe tener 300px de ancho, la suma del content + padding + border debe ser 300px. No incluye el margin.

### max-width & max-height

Se usa para que sea un elemento mas flexible y que el elemento se reajuste automaticamente a nuestra pantalla y que no salga la barra de scroll.

```css
div {
  max-width: 30%;
  max-height: 40%;
}
```

<h3>A tomar en cuenta...</h3>
<p>Un punto clave a la hora de entender los márgenes es el concepto de colapso del margen. Si tienes dos elementos cuyos márgenes se tocan, esos márgenes se combinan para convertirse en un solo margen, cuyo tamaño es el del margen más grande. Sucede con el margin-botom del elemento superior y el margin-top del elemento inferior</p>

```html
<div class="caja-margen">contenido</div>
<div class="caja-margen-dos">contenido</div>
```
