## Formularios

```html
<form>
  <fieldset>
    <legend>Formulario de Contacto</legend>
    <!-- Todos los imputs van los imputs por ejemplo-->
    <label>
      Nombre:
      <input
        type="text"
        id="nombre"
        name="nombre"
        placeholder="Escribe tu nombre"
        autofocus
        spellcheck="true"
        required
        tabindex="1s"
      />
    </label>
  </fieldset>
</form>
```

### Tipos de inputs (text, email, tel, password, color, date, datetime-local)

```html
<input
  type="tel"
  name="telefono"
  id="tel"
  placeholder="123-456-7890"
  tabindex="2"
  pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
/>
```

#### Tipo list

```html
<label for="">País:</label>
<input
  type="text"
  name="pais"
  id="country"
  placeholder="Selecciona tu país"
  tabindex="4"
  list="latam"
/>
<datalist id="latam">
  <option value="México"></option>
  <option value="Colombia"></option>
  <option value="Ecuador"></option>
  <option value="Perú"></option>
  <option value="Argentina"></option>
  <option value="Costa Rica"></option>
  <option value="Venezuela"></option>
  <option value="Chile"></option>
  <option value="Uruguay"></option>
  <option value="Bolivia"></option>
  <option value="Brásil"></option>
  <option value="Honduras"></option>
  <option value="Paraguay"></option>
  <option value="Guatemala"></option>
</datalist>
```

#### Tipo radio

```html
<label for="yes">Sí</label>
<input type="radio" name="asesoria" id="yes" />
<label for="no">No</label>
<input type="radio" name="asesoria" id="no" />
```

#### Tipo select

```html
<label for="select">Selecciona el tema</label>
<select name="tema" id="select">
  <optgroup label="Desarrollo Web">
    <option value="front">Frontend</option>
    <option value="back">Bsckend</option>
    <option value="full">FullStack</option>
  </optgroup>
  <optgroup label="Desarrollo Móvil">
    <option value="android" selected>Android</option>
    <option value="ios">IOS</option>
  </optgroup>
</select>
```

#### Tipo checkbox

```html
<label for="html">HTML5</label>
<input type="checkbox" name="estrutura" id="html" />
<label for="css">CSS</label>
<input type="checkbox" name="estilado" id="css" />
<label for="js">JS</label>
<input type="checkbox" name="dinamismo" id="js" />
```

#### Tipo textarea

```html
<label for="msj">Cuéntame Más</label>
<br />
<textarea
  name="message"
  id="msj"
  cols="50"
  rows="10"
  placeholder="¿Qué debo saber para ayudarte mejor?"
></textarea>
```

#### Tipo file

```html
<label for="file">Cargar archivo</label>
<input
  type="file"
  name="archivos"
  id="file"
  accept=".jpg, .jpeg, .png"
  multiple
/>

<label for="img">Sube tu foto</label>
<input type="file" name="image" accept="image/*" id="img" capture="user" />
<br />
<label for="video">Sube tu video</label>
<input
  type="file"
  name="film"
  id="video"
  accept="video/*"
  capture="environment"
/>
```

#### Submit

```html
<button type="submit">Enviar</button> <button type="reset">Limpiar</button>
```
