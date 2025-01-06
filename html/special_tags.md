## Etiquetas especiales

### Dialog

```html
<dialog id="modal">
  Soy una ventana modal
  <button id="btn_close">Close Modal</button>
</dialog>

<button id="btn_open">Open Modal</button>

<script>
  btn_open.onclick = function () {
    modal.open = true;
  };
  btn_close.onclick = function () {
    modal.open = false;
  };
</script>
```

### Details

```html
<div>
  <details name="moreInfo" open>
    <summary>Read more</summary>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem
      molestiae omnis voluptatibus, dolorem, eveniet officia veniam totam alias
      eum nobis id quasi dolorum eos at doloremque, animi minus dignissimos
      error!
    </p>
  </details>
  <details name="moreInfo">
    <summary>Pikachu</summary>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem
      molestiae omnis voluptatibus, dolorem, eveniet officia veniam totam alias
      eum nobis id quasi dolorum eos at doloremque, animi minus dignissimos
      error!
    </p>
  </details>
  <details name="moreInfo">
    <summary>Read more</summary>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem
      molestiae omnis voluptatibus, dolorem, eveniet officia veniam totam alias
      eum nobis id quasi dolorum eos at doloremque, animi minus dignissimos
      error!
    </p>
  </details>
</div>
```

### Popover

```html
<button popovertarget="myPop">Abrir pop</button>
<div popover id="myPop">Soy un popover!!</div>
```

### Progress

```html
<progress value="50" max="100"></progress> <progress max="100"></progress>
```
