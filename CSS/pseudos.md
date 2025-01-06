## Pseudoclases

Nos permiten manipular los estados de los elementos html.

```html
<div class="oculto">
  Pasar por encima
  <p>Se muestra el parrafo</p>
</div>
```

```css
div.oculto p {
  display: none;
}

div.oculto:hover p {
  display: block;
}

div.oculto p:first-child {
  /* Solo al primer parrafo se le aplican los estilos con esta pseudoclase */
  font-variant: small-caps;
}
```

```html
<style>
  button:active {
    color: red;
  }

  input:focus {
    /* Cuando el cursor esta en el input el color de la linea de afuera cambia*/
    outline: 2px solid green;
  }

  a:visited {
    /* Modifica las propiedades del enlace cuando ya ha sido visitado por ejemplo */
    color: red;
    /* Cuando el usuario ya haya hecho click en este enlace su color de texto cambiara a rojo */
  }

  p:first-child {
    /* De un grupo de elementos iguales contenidos dentro de un elemento padre en html solo al primero se le va a aplicar el estilo que se ve a continuacion */
    font-weight: bold;

    /* pseudoclases similares
    last-child | nth-child(2)
    */

    p:not(.excluido) {
      /* A todos los elementos p se le aplican los estilos de abajo a excepcion del que esta dentro del :not(.excluido) con la clase excluido */
      text-decoration: underline;
    }
  }

  /* Aplica el estilo solo a los elementos impares(odd) o pares(even) */
  p:nth-of-type(odd) {
    background-color: brown;
  }

  /* Cuando los inputs de tipo checkbox estan "chequeados" se les agrega una linea azul como borde */
  input:checked {
    outline: 2px solid blue;
  }

  /* Si el elemeto p tiene un span dentro se le aplica el estilo que declaramos */
  p:has(span) {
    color: red;
  }
</style>

<button>Al hacer click el color del texto del boton se vuelve rojo</button>

<input type"text" placeholder="Haz clic aqui">
```

## Pseudoelementos

Nos permite seleccionar y crear elementos de html desde css e incluso se comportan como elementos de html aunque el elemento no este ahi.

```html
<div class="container">
  <p>Selecciona el texto</p>
  <p>Lorem blabla blabla blablablabla bla blablalalablalalblab</p>
</div>
```

```css
div.container p::selection {
  /* Al momento de seleccionar el txto se cambia el color y el background */
  color: red;
  background-color: yellow;
}

div.container P::first-line {
  /* Solo a la primer linea de cada parrafo se le aplica la propiedad font-variant */
  font-variant: small-caps;
}
div.cotainer P::first-letter {
  /* solo cambia la primera letra de cada parrafo */
}
div.container p::before {
  /* Antes de que se muestre el parrafo se muestra el guion medio */
  content: "- ";
}

div.container p::after {
  /* Despues de que se muestre el parrafo se muestra el guion medio, se puede agregar cualquier caracter */
  content: " -";

  /* Asi podemos agregar una imagen */
  content: url();
}

/* Este pseudoelemento nos permite modificar el placeholder de un input */
input::placeholder {
  color: red;
  font-style: italic;
  background-color: blue;
}
```
