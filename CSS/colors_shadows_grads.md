## Transparencia

```css
img {
  /* El valor por default es 1(100%) y no tenemos ningun tipo de opacidad  */
  opacity: 0.5; /* Opacidad al 50%*/
}

img:hover {
  opacity: 1;
}
```

## Fondos con gradientes(lienales y radiales)

```css
/* Para que no se repita todo le gradiente si no que ocupe todo el ancho de la pantalla usamos estas propiedades dentro del elemento html */
html {
  height: auto; /*Para que en el eje vertical se centre cualquier elemento que tengamos*/
  min-height: 100%; /*para que el valor minimo del alto sea del 100% y se expanda nuestro fondo de gradiente*/
}

body {
  /* Este es el gradiente por defaul de arriba hacia abajo */
  background: linear-gradient(#f72585, #3a0ca3);

  /* Para generar el difuminado se hace de izquierda a derecha */
  background: linear-gradient(to right, #f72585, #3a0ca3);

  /* Tambien podemos usar (to bottom right) */
  background: linear-gradient(to bottom right, #f72585, #3a0ca3);

  /* Usando un angulo */
  background: linear-gradient(145deg, #f72585, #3a0ca3);

  /* Aplicando 3 colores */
  background: linear-gradient(#24404d, #6dbff1, black);

  /* Gradientes radiales */
  background: radial-gradient(circle, #24404d, #6dbff1);
}
```

## Sombras

Solo los valores de _**eje X**_, _**eje y**_ y _**color**_ son obligatorios, los demas son opcionales.

### text-shadow

```css
h1 {
  /*Este es el orden que debe llevar el text-shadow  */
  text-shadow: * eje X * * eje Y * * blur * * color *;

  text-shadow: 3px 2px 5px #faf1e4;
}
```

### box-shadow

```css
section.main-section {
  box-shadow: * eje X * * eje Y * * blur * * size-sombra * * color *;
  box-shadow: 2px 2px 5px 2px #cedebd;
}
```

Sitios para generar sombras

**_text shadow css generator_**
**_cssgenerator.org_**
