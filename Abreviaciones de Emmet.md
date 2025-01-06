# Abreviaciones de Emmet

## > Etiqueta hijo

### nav>ul>li

```html
<nav>
  <ul>
    <li>|</li>
  </ul>
</nav>
```

## + Etiqueta hermana

### div+p+img

```html
<div>|</div>
<p>|</p>
<imm>|</imm>
```

## ^ simbolo carret, nos permite salir de etiquetas anidadas de forma abreviada, se puede usar cuantas veces sea necesario.

### div+div>p>span+em^bq

```html
<div>|</div>
<div>
  <p><span>|</span><em>|</em></p>
  <blockquote>|</blockquote>
</div>
```

### div+div>p>span+em^^bq

```html
<div>|</div>
<div>
  <p><span>|</span><em>|</em></p>
</div>
<blockquote>|</blockquote>
```

## () Agrupaciones

### div>(header>ul>li\*2>a)+footer>p

```html
<div>
  <header>
    <ul>
      <li><a href="|">|</a></li>
      <li><a href="|">|</a></li>
    </ul>
  </header>
  <footer>
    <p>|</p>
  </footer>
</div>
```

### (div>dl>(dt+dd)\*3)+footer>p

```html
<div>
  <dl>
    <dt>|</dt>
    <dd>|</dd>
    <dt>|</dt>
    <dd>|</dd>
    <dt>|</dt>
    <dd>|</dd>
  </dl>
</div>
<footer>
  <p>|</p>
</footer>
```

## Crear identificaciones(#) y clases(.)

### div#header

```html
<div id="header">|</div>
```

### div.title

```html
<div class="title">|</div>
```

### form#search.wide

**_combinando class y id_**

```html
<form action="|" id="search" class="wide">|</form>
```

### p.class1.class2.class3

**_multiples clases_**

```html
<p class="class1 class2 class3">|</p>
```

## Etiquetas con otros atributos y su contenido usando [ ]

### p[title="hello world"]

```html
<p title="hello world">|</p>
```

### meta[name="keywords" content="palabra1,palabra2,palabra3,palabra4, palabra5"]

```html
<meta name="keywords" content="palabra1,palabra2,palabra3,palabra4, palabra5" />
```

**No es necesario escribir el contenido del atributo si no se necesita o no se conoce.**

## Agregando texto a nuetras etiquetas usando { }

### a{instagram}

```html
<a href="|">instagram</a>
```

### p>{Follow us on}+a{facebook}+{and like our fanpage}

```html
<p>Follow us on<a href="|">facebook</a>and like our fanpage</p>
```

## Etiquetas implicitas

### .clase1

**_nos crea un div sin nosotros indicarlo explicitamente_**

```html
<div class="clase1">|</div>
```

### em>.clase2

_Nos crea un span porque es mas comun que una etiqueta_ **em** _tenga un_ **span** _por dentro_

```html
<em><span class="clase2">|</span></em>
```

### ul>.elemento1

```html
<ul>
  <li class="elemento1">|</li>
</ul>
```

### table>.fila.columna

```html
<table>
  <tr class="fila">
    <td class="columna">|</td>
  </tr>
</table>
```

## Creando numeracion usando $

### ul>li.item$\*5

```html
<ul>
  <li class="item1">|</li>
  <li class="item2">|</li>
  <li class="item3">|</li>
  <li class="item4">|</li>
  <li class="item5">|</li>
</ul>
```

### h$[title=item$]{Ecabezado $}\*3

```html
<h1 title="item1">Ecabezado 1</h1>
<h2 title="item2">Ecabezado 2</h2>
<h3 title="item3">Ecabezado 3</h3>
```

### ul>.item$$\*10

```html
<ul>
  <li class="item01">|</li>
  <li class="item02">|</li>
  <li class="item03">|</li>
  <li class="item04">|</li>
  <li class="item05">|</li>
  <li class="item06">|</li>
  <li class="item07">|</li>
  <li class="item08">|</li>
  <li class="item09">|</li>
  <li class="item10">|</li>
</ul>
```

### ul>.item$@-\*5

**_El simbolo @- indica que queremos los numeros de manera descendiente._**

```html
<ul>
  <li class="item5">|</li>
  <li class="item4">|</li>
  <li class="item3">|</li>
  <li class="item2">|</li>
  <li class="item1">|</li>
</ul>
```

### ul>.item$@3\*5

**_De esta manera indicamos que queremos empezar a contar desde el numero 3_**

```html
<ul>
  <li class="item3">|</li>
  <li class="item4">|</li>
  <li class="item5">|</li>
  <li class="item6">|</li>
  <li class="item7">|</li>
</ul>
```
