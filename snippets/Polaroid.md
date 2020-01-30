---
title: Polaroid
tags: beginner, molecule
---

This snippet creates a Polaroid-style picture. It uses `props` to obtain the url and a Slot to obtain the caption, then renders a `<figure>` element with a caption encapsulated within `<figcaption>`.

```html
<template>
  <figure class="polaroid">
    <div class="box-shadow">
      <img :src="url" :alt="caption" class="photo" />
    </div>
    <figcaption class="caption">
      <Slot>An example Polaroid made as a Vue SFC</Slot>
    </figcaption>
  </figure>
</template>

<script>
  export default {
    name: "Polaroid",
    props: {
    url: {
        type: String,
        required: false,
        default() {
          return "https://picsum.photos/500";
        },
      },
    }
  };
</script>

<style scoped>
.polaroid {
  border: 1px solid #eee;
  box-shadow: 2px 2px 11px 0 rgba(50,50,50,0.08);
  font-family: sans-serif;
  margin: .5em 0;
  max-width: 400px;
  padding: 2em 2em 0;
  position: relative;
}

.box-shadow {
  box-shadow: inset 2px 2px 2px 1px rgba(50,50,50,0.11);
}

.photo {
  display: block;
  height: auto;
  position: relative;
  width: 100%;
  z-index: -1;
}

.caption {
  margin: 1.33em 0 1.5em;
  text-align: center;
}
</style>
```

```html
<Polaroid url="https://picsum.photos/500">
    A nice caption goes here
</Polaroid>
```

