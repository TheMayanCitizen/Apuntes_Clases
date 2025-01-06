## Contenido embebido

### Imagenes

```html
<img
  src="assets/img/bg.png"
  alt="Esta será la descripción detallada de mi imagen"
  width="100%"
  title="Esta es una breve descripción de mi imagen"
/>

<figure>
  <img src="assets/img/bg.png" alt="Descripción" width="100%" loading="lazy" />
  <figcaption>Descripción o crédito de la imagen</figcaption>
</figure>

<picture>
  <source media="(min-width: 768px)" srcset="assets/img/cover.jpg" />
  <source media="(max-width: 767px)" srcset="assets/img/bg.png" />
  <img src="assets/img/favicon.pn" alt="Descripción" />
</picture>
```

### Videos

```html
<video
  src="assets/video/video.mp4"
  width="100%"
  muted
  loop
  controls
  poster="assets/img/cover.jpg"
></video>

<video constrols width="250" height="200" muted>
  <source src="assets/video/video.mp4" type="video/mp4" />
  <source src="assets/video/video.webm" type="video/webm" />
  <p>Su navegador no soporta videos HTML5</p>
</video>
```

### Audios

```html
<audio controls autoplay muted loop>
  <source src="assets/audio/audio.mp3" type="audio/mp3" />
  <source src="assets/audio/audio.ogg" type="audio/ogg" />
  <p>Tu navegador no soporta el tag audio</p>
</audio>
```

### Iframes

```html
<iframe src="https://www.academlo.com/" width="600" height="400"></iframe>

<iframe
  src="assets/html/documento.html"
  frameborder="0"
  width="600"
  height="400"
></iframe>

<iframe
  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d125759.38928838276!2d-84.11334505!3d9.935545650000009!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8fa0e342c50d15c5%3A0xe6746a6a9f11b882!2zU2FuIEpvc8Op!5e0!3m2!1ses!2scr!4v1705631995041!5m2!1ses!2scr"
  width="400"
  height="300"
  style="border: 0"
  allowfullscreen=""
  loading="lazy"
  referrerpolicy="no-referrer-when-downgrade"
></iframe>

<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/16Aw-xz3obw?si=qp8Yqu5-qzJy0sdW"
  title="YouTube video player"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  allowfullscreen
></iframe>
```
