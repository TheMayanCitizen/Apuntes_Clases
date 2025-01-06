### Consultas de contenedor

La diferencia entre este query y el media, es que el `@media` trabaja en base al tamano de la pantalla, `@container`, trabaja en base al tamano del contenedor. Esta funcion es nueva dentro de css y puede que no sea soportada por todos los navegadores.

```html
<div><span>Contenido</span></div>
```

```css
div {
  container: container-1 / inline-size;
  /* el primer valor es el nombre del contenedor, puede ser cualquiera, el segundo valor es como se va a comportar el contenedor */
}

span {
  background-color: green;
}

/* Lo que decimos aqui es: cuando el ancho del contenedor-1 sea menor o igual a 200px, el color de fondo del span va a cambiar a rojo*/
@container container-1 (width <=200px) {
  span {
    background-color: red;
  }
}
```
