## Selectores

### Descendientes

```html
<div class="descendiente">
  Selectores descendientes(en cualquier nivel interno)
  <p>Primer parrafo</p>
  <p>Segundo parrafo</p>
  <section>
    <p>Tercer parrafo</p>
  </section>
</div>
```

```css
div .descendiente p {
  /* A todos los parrafo que se encuentren dentro del div no importa el nivel interno */
}
```

### child - hijos directos

```html
<div class="hijo">
  Selectores hijo(child)
  <p>Primer parrafo</p>
  <p>Segundo parrafo</p>
  <section>
    <p>Tercer parrafo</p>
  </section>
</div>
```

```css
div .hijo > p {
  /* Todos los hijos directos de tipo parrafo dentro del div */
}
```

### Siblings - adyacentes

```html
<div class="adyacente">
  Selectores adyacentes
  <p>Primer parrafo</p>
</div>
<p>Segundo parrafo</p>
<!-- Este es el elemento adyacente o junto al elemento que hemos configurado en css -->
<p>Tercer parrafo</p>
```

```css
div .adyacente + p {
  /* El elemento p que este exactamente despues del div con la clase adyacente */
}

div .adyacente ~ p {
  /* todos los parrafos que encontremos al mismo nivel que el div con la clase adyacente se le aplican los estilos que definamos */
}
```
