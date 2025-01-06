### Anidamiento

```html
<div>
  <p>Parrafo anidado</p>
</div>
```

```css
/* Si queria modificar los estilos de p dentro del div tenia que hacer todo esto, escribir nuevamente div p.... y sobre escribia los estilos que p tenia por herencia de div */
div {
  color: brown;
}

div p {
  color: blue;
}

/* Con el anidamiento podemos ahorrarnos codigo y hacer lo siguiete*/
div {
  color: brown;

  p {
    color: blue;
  }
}
```
