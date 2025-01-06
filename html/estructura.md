## EStructura basica de un documento de html

```html
<header>
  <nav>
    <!-- Navegación: Menu de navegación -->
    <div>
      <a href="">Logo</a>
    </div>
    <div>
      <ul>
        <li><a href="">Home</a></li>
        <li><a href="">About Me</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </div>
  </nav>
</header>

<main>
  <!-- Importante: Main contiene todo el contenido importante de la página y solo se puede colocar un elemento por página y no puede ser descendiente de otro elemento -->
  <h1>Mi primer página web</h1>
  <section>
    <article>
      <h2></h2>
    </article>
  </section>
  <aside>
    <!-- Aside: Contiene elementos que no son necesarios en la mayoría de las páginas pero que pueden ser útiles, suelen dejarse para espacios publicitarios -->
  </aside>
</main>

<footer>
  <nav>Se puede colocar también un nav</nav>
</footer>
```

```html
<body>
  <header>
    <!-- Barra de navegacion principalmente -->
    <nav>
      <!-- lista no ordenada <ul>, con elementos <li> y anclas <a> -->
      <ul>
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Nosotros</a></li>
        <li><a href="#">Servicios</a></li>
        <li><a href="#">Portfolio</a></li>
        <li><a href="#">Contacto</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <!-- contenido principal -->
    <section>
      <!-- Agrupar temas diferentes de una pagina web pj. Informacion de la empresa, una galeria de imagenes, testimonios de clientes  -->
      <article>
        <!-- Encerrar el contenido de un articulo, por ejemplo, de un blog, o articulos de un ecommerce -->
        <h3>Nombre del producto</h3>
        <img src="#" alt="" />
        <p>Descripcion del articulo</p>
      </article>
      <article>
        <h3>Producto 2</h3>
        <img src="#" alt="" />
        <p>Descripcion <span>del</span> producto</p>
      </article>
    </section>

    <aside>
      <!-- Informacion complementaria pero que no forma parte de la seccion principal, por ejemplo, informacion relacionada al blog o articulo -->
      <nav>
        <h5>Productos relacionados</h5>
        <ul>
          <li><a href="#">Producto 1</a></li>
        </ul>
        <ul>
          <li><a href="#">Producto 2</a></li>
        </ul>
        <ul>
          <li><a href="#">Producto 3</a></li>
        </ul>
      </nav>
    </aside>
    <div>
      <!-- Divicion en bloque. -->
    </div>
    <span>
      <!-- Divicion en linea -->
    </span>
  </main>
  <footer>
    <!-- enlaces de refuerzo, copyright etc -->
  </footer>
</body>
```

## Cabeceras

```html
<h1>H1 - heading 1</h1>
<!-- Importante: H1 es el encabezado principal y solo puede haber uno en la página -->
<h2>H2 - heading 2</h2>
<!-- h2 suele usarse para subtítulos, normalmente después de un h1. O también para las cabeceras de los temas que se verán en la página.  -->
<h3>H3 - heading 3</h3>
<!-- h3 suele utilizarse para cabecera de los subtemas dentro de cada sección  -->
<h4>H4 - heading 4</h4>
<h5>H5 - heading 5</h5>
<h6>H6 - heading 6</h6>
<!-- Importante: Las etiquetas h4, h5 y h6, no se recomienda utilizarlas porque afectan el SEO del navegador, ya que se interpretan como niveles profundos del documento  -->
```

## Caracteres especiales

1. #169; Copyright
2. #174; Marca registrada
3. #8482; Trade Mark
4. \&#189; Fracción medio
5. \&nbsp; Espacio
