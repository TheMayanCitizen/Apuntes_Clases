## Manejo de _FONDOS_ en CSS

```css
body {
  color: white;

  background-color: blue;
  background-image: url("/img/imagen.png");
  background-repeat: repeat-x | repeat-y | no-repeat;
  background-position: right top | right | left | center;
  background-attachment: scroll | fixed;
  /* 
  scroll: sirve para que la imagen no siga cuando hacemos scroll 
  fixed: mantiene la imagen se queda fija al scroll
  */

  /* Forma simplificada de lo de arriba, attachment no se incluye */
  background: * color * * image * * repeat * * position *;
}

h1 {
  text-align: center;
  background-color: blue;
}
```
