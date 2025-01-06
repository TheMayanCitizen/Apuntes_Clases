### Transformaciones

**transform**
Esta propiedad nos permite modificar el elemento html, no todos los elementos se pueden transformar.

```css
div {
  transform: translate(50px, 50px) scale(0.8) rotate(0.3turn) skew(30deg, 20deg);
}
```

translate: mueve el elemento en el eje(x, y) segun lo indiquemos
scale: cambia el tamano del elemento, mas pequeño(valores por debajo de 1) o mas grande (valores por arriba de 1)
rotate: gira el elemento, podemos usar unidades como "turn" o "deg"
skew: distorciona el elemento en el eje x y en el eje y.

Se pueden usar una o varias opciones de transform a la vez.

### Transiciones

Es una forma de hacer animaciones a nuestros elementos html usando transition.

```css
div{
  background-color: coral;
  height: 200px;
  width:200px;

  /* Con estas propiedades indicamos que queremos que la propiedad width incremente cuando el evento "hover" ocurra y que dura solo .5s */
  transition-property: width;
  transition-duration:.5s;
  /* Esta propiedad hace que la transicion sea mas suave en vez de ir a la misma velocidad como si usaramos linear. */
  transition-timing-function:ease;

  /* linear | ease-in | ease-out | ease-in-out | steps(4)*/

  /*
  Recurso para diferentes lineas de animacion para el transition-timing-function
  https://easing.webflow.io/
  */

/* Simplificando todas las transition properties en una sola y agregando mas*/
  transition: width .5s ease-in-out,
  height .5s ease-in-out,
  background-color: .5s,
  transform .5s ease-in-out;

  /* Refactorizando */
  transition-property:width,height,background-color,transform;
  transition-duration: .5s;
  transition-timing-function:ease-in-out;

  /* Refactorizando */
  transition: all .5s ease-in-out;

  /* De la siguiente forma nos ahorramos el escribir la siguiente linea de codigo
  div:hover{
    width: 300px;
    height: 250px;
    background-color: skyblue;
    transform:rotate(45deg)
  }
  */

  /* Agregando &:hover y las demas propiedades hacemos usamos las propiedades de anidamiento */
  &:hover{
  width: 300px;
  height: 250px;
  background-color: skyblue;
  transform:rotate(45deg)
  }

}

div:hover{
  width: 300px;
  height: 250px;
  background-color: skyblue;
  transform:rotate(45deg)
}

```

### Animaciones

```css
div{
  background-color: royalblue;
  height:100px;
  width:100px;
  animation-name:move;
  animation-duration:2s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;

  /* Simplificando */
  animation: move 2s ease-in-out infinite;
}

@keyframes move{
  0%{
    transform:translateX(0)
  }
  50%{
    transform: background-color: red;
  }
  100%{
    transform:translateX(200px)
  }
}
```
