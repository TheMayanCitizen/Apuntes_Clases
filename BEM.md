# BEM (Block, Element, MOdifier)

Nos ayuda a crear componentes reutilizables, codigo claro y mantener la especificidad al minimo.

## Block en BEM

Es una entidad independiente, no necesita a otra etiqueta mas para existir. Por ejemplo:

- header
- nav
- form
- footer
- contenedor

A los bloques se les nombra con la funcionalidad del bloque.

```html
<!-- La funcionalidad del nav es ser un menu de navegacion "nav" -->
<nav class="nav"></nav>

<!-- La funcionalidad es ser un header -->
<header class="header"></header>

<!-- La funcionalidad del section es ser un "container" -->
<section class="container"></section>
<section class="gallery"></section>

<form action="" class="form"></form>
<sidebar class="sidebar"></sidebar>
```

## Element en BEM

Un elemento en BEM, esta ligado a un bloque depende directamente de el, por lo que este debe estar dentro de un bloque para existir.

A los elementos se les nombra con el nombre de su bloque contenedor, 2 guiones bajos(\_\_) y la descripcion del elemento.

```html
<form action="" class="form">
  <input type="text" class="form__input" />
  <input type="text" class="form__send" />
</form>
```

```html
<nav class="nav">
  <a href="" class="nav__link">Inicio</a>
  <a href="" class="nav__link">Contacto</a>
</nav>
```

## Modifier en BEM

Puede ser un Bloque o un Elemento, el modifier indica, como su nombre lo dice, una modificacion a dicho elemento o bloque.

A los modificadores se les nombra con el nombre que tenian anteriormente(bloque o elemento), se le agrega 2 guiones medios(--) y la descripcion de la modificacion.

```html
<nav class="nav">
  <a href="" class="nav__link">Inicio</a>
  <a href="" class="nav__link nav__link--disabled">Contacto</a>
  <!-- Un modificador se agrega al nombre de la clase, no se reemplaza como en el ejemplo de arriba -->
</nav>
```

```html
<header class="header header--blue"></header>
```

```html
<input type="text" class="form__input form__input--color-grey" />
```

```html
<button class="btn ">Press here</button>
<button class="btn ">Press here</button>
<button class="btn btn--active">Press here</button>
```

## Curiosidades en BEM

P: Que pasa si tengo un hijo dentro de un elemento, en este caso "block\_\_elem2"?

R: Se le nombra como si fuera un elemento mas dentro de "block". Como si estuviera al mismo nivel que el elemento "block**elem1" y "block**elem3"

```html
<header class="block">
  <section class="block__elem1">
    <div class="block__elem2"></div>
  </section>
  <div class="block__elem3"></div>
</header>
```

---

P: Una etiqueta puede tener 2 clases de un bloque?

R: Si, se le llama "mix" en BEM.

```html
<div class="block1 block2"></div>
```

---

P: Puedo usar modificadores globales?

R: No, porque puede generar especificidad extra y lo que buscamos con BEM es tener especificidad al minimo.

```html
<button class="button disabled hidden visible"></button>
```

---

P: Puedo anidar bloques?

R: Si, por ejemplo un nav dentro de un header

```html
<header class="header">
  <nav class="nav"></nav>
</header>
```

# Ejemplo práctico

## Codigo html con metodologia BEM

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BEM</title>
  </head>

  <body>
    <header class="header">
      <nav class="nav">
        <div class="nav__logo">
          <img src="#" alt="logo de la empresa" class="nav__img" />
        </div>

        <div class="nav__links">
          <a class="nav__link nav__link--color">Inicio</a>
          <a class="nav__link">Contacto</a>
          <a class="nav__link">Nosotros</a>
        </div>
      </nav>
    </header>
  </body>
</html>
```

## Codigo en CSS

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.nav {
  background: slateblue;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.nav__logo {
  height: 100%;
  background: #fff;
}

.nav__img {
  height: 100%;
}

.nav__link {
  color: #ffff;
  text-decoration: none;
}

/* Los modificadores siempre van despues de que se declara el elemento, en este caso ".nav__link */

.nav__link--color {
  color: tomato;
}
```
