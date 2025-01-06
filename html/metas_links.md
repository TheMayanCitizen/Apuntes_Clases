## meta & link

```html
<meta name="author" content="Alejandra Olazagasti" />
<!-- El atributo author te permite nombrar al autor, el desarrollador de la página-->
<meta name="description" content="No más de 165 caracteres" />
<!-- El atributo description especifica una descripción del documento - no más de 165 caracteres -->
<meta
  name="keywords"
  content="palabra1, palabra2, palabra3, palabra4, palabra5"
/>
<!-- El atributo keywords te permite colocar las palabras clave que describen el contenido de una página web y que son relevantes para los motores de búsqueda - no hay un límite estricto de caracteres para las palabras clave, pero se recomienda usarlas con moderación y enfocarse en la calidad y relevancia del contenido.-->

<link rel="icon" href="assets/img/favicon.png" type="image/png" />
<!-- El atributo icon especifica el icono del documento. -->
<!-- href significa Hypertext Reference -->
<!-- type es buena práctica colocarlo para que el SEO(motores de búsqueda) detecte qué tipo de imagen es la que va a renderizar -->

<!-- Etiqueta meta para prevenir que utilicen tu sitio web en un iframe  -->
<meta name="robots" content="noindex nofollow" />

<!-- De esta manera indicamos que nuestra pagina web va a tener diferentes idiomas -->
<link rel="alternate" hreflang="en" href="http://ejemplo.com/en/index.html" />
<link rel="alternate" hreflang="fr" href="http://ejemplo.com/en/index.html" />
```
