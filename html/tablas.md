## Tablas

### Basicas

```html
<table border align="center" cellpadding="10" cellspacing="15" bgcolor="808080">
  <!-- elemento que representa a alas tablas  -->
  <tr>
    <!-- elemento que representa a las filas -->
    <td>Fila 1 Columna 1 Celda 1</td>
    <!-- elemento que representa una celda de la tabla  -->
    <td>Fila 1 Columna 2 Celda 2</td>
    <td>Fila 1 Columna 3 Celda 3</td>
  </tr>
  <tr>
    <!-- elemento que representa a las filas -->
    <td>Fila 2 Columna 1 Celda 1</td>
    <!-- elemento que representa una celda de la tabla  -->
    <td>Fila 2 Columna 2 Celda 2</td>
    <td>Fila 2 Columna 3 Celda 3</td>
  </tr>
</table>
```

### Agrgegando titulo y cabeceras

```html
<table border>
  <caption>
    <!-- elemento que le da un titulo a mi tabla  -->
    Mi tabla de Ejemplo
  </caption>
  <tr>
    <th>Columna 1</th>
    <!-- elemento que representa una columna de la tabla -->
    <th>Columna 2</th>
    <th>Columna 3</th>
  </tr>
  <tr>
    <!-- elemento que representa a las filas -->
    <td>Fila 1 Columna 1 Celda 1</td>
    <!-- elemento que representa una celda de la tabla  -->
    <td>Fila 1 Columna 2 Celda 2</td>
    <td>Fila 1 Columna 3 Celda 3</td>
  </tr>
  <tr>
    <!-- elemento que representa a las filas -->
    <td>Fila 2 Columna 1 Celda 1</td>
    <!-- elemento que representa una celda de la tabla  -->
    <td>Fila 2 Columna 2 Celda 2</td>
    <td>Fila 2 Columna 3 Celda 3</td>
  </tr>
</table>
```

### Agrupando Celdas

```html
<table border>
  <tr>
    <td colspan="5" align="center">Mis Horarios</td>
  </tr>
  <tr>
    <td colspan="2">Programación</td>
    <td colspan="2">Algoritmos</td>
    <td>Total Horas</td>
  </tr>
  <tr>
    <td>Clases</td>
    <td>Horas</td>
    <td>Clases</td>
    <td>Horas</td>
    <td rowspan="2">15 hrss</td>
  </tr>
  <tr>
    <td>3 clases</td>
    <td>9 horas</td>
    <td>2 clases</td>
    <td>6 horas</td>
  </tr>
</table>
```

### Grupos de filas

```html
<table border>
  <thead>
    <tr>
      <td>Mes</td>
      <td>Enero</td>
      <td>Febrero</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Electricidad</td>
      <td>10</td>
      <td>15</td>
    </tr>
    <tr>
      <td>Internet</td>
      <td>5</td>
      <td>10</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>15</td>
      <td>25</td>
    </tr>
  </tfoot>
</table>
```
