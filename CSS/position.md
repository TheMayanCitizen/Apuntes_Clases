## Propiedad Display

```css
h1 {
  display: inline | block | none | inline-block;
}

/* esta propiedad oculta el elemento pero respeta su posicion dentro de la pagina */
p {
  visibility: hidden;
}
```

**inline**: No permite modificar los valores de margin, padding, top, bottom o height.

**inline-block**: Si nos permite modificar los valores de margin, padding, top, bottom o height, por ejemplo los elementos de tipo span.

## Centrar elementos de tipo div

```css
/* Podemos usar tanto max-width como width con un valor en porcentaje para 
que el elemento de ajuste al tamano de la pantalla */
div {
  max-width: 400px | 50%;
  width: 50%;
  margin: auto; /* Centramos el div con esta propiedad*/
}
```

## Posicionamiento

### position: static

Es la posicion que viene por defecto en css, este tipo de posicionamiento mantiene
al elemento en el lugar donde estaba dentro del flujo de html. top, bottom, left y right, no afectan el posicionamiento del elemento.

### position: relative

El elemento se mueve en relacion a la posicion donde esta ubicada dentro del html.
Los valores top, left, right y bottom, si tienen efecto. Los demas elementos html no toman la posicion de nuestro elemento con posicion relativa.

```css
div {
  position: relative;
  top: 100px;
  left: 50px;
}
```

### position: fixed

El elemento se posiciona de acuerdo al tamano del viewport, los otros elementos html toman el lugar que le correspondia al elemento con position: fixed. Si hay un scroll, el elemento fixed se mueve a la par con el scroll. Se usa con barras de navegacion. Los valores top, bottom, left y right si tienen efecto.

```css
div {
  position: fixed;
  top: 0;
}
```

### position: absolute

Normalmente se usa cuando estamos trabajando dentro de un elemento div, el elemento se posiciona de manera absoluta a su elemento padre. No nos acompana si es que hay un scroll. El elemento padre debe tener una **_position: relative;_** para que absolute funcione, si el padre tiene **_position: static_** no va a funcionar.

```css
div .padre {
  width: 500px;
  height: 300px;
  position: relative;
}
div .hijo {
  position: absolute;
  /* Se posiciona en la parte superior derecha del contenedor padre. */
  top: 0;
  right: 0;
}
```

### position: sticky;

Al momento de hace scroll y que el espacio entre el elemento y su top sea 0, el elemento se queda "pegado" a la pantalla y sigue el scroll. Mientras su top sea mayor a 0, no seguira al scroll. Es una combinacion entre relative & fixed.

```css
div {
  position: sticky;
  top: 0;
}

/* Esta combinacion se usa para que el ***position: sticky;*** funcione en el navegador safari */
div {
  position: sticky;
  position: -webkit-sticky;
}
```

### Z-index

Esta propiedad determina el orden de el elemento en el eje z del contexto de apilamiento. Los valores pueden ir de negativo a positivo.

```css
div.relative {
  position: relative;
  top: -20px;
  left: 10px;
  z-index: -1 | 1;
}
```

## Propiedad Overflow

Cuando el contenido dentro de elemento padre es mas grande, se desborda. Solo funciona si especificamos el height o el width de nuestro contenedor padre

```css
div {
  /* Por Default tenermos el overflow: visible */
  overflow: visible | hidden | scroll | auto;
  overflow-x: visible | hidden | scroll | auto;
  overflow-y: visible | hidden | scroll | auto;
}
```

## Propiedad Float & clear

Permite que los elementos los podamos apliar hacia el lado que queramos a pesar de que sea un elemento de tipo bloque, al poner la propiedad float, todos los elementos se apilan uno seguido de otro sobre la misma linea.

```css
/* El valor de none es el valor por default */
div {
  float: left | right | none;
}
```

Para limpiar la propiedad float y poder seguir trabajando de manera "normal" sin que los otros elementos div se apilen a la izquierda o derecha usamos la propiedad
**_clear_**.

```css
div {
  clear: right | left | both;
}
```
