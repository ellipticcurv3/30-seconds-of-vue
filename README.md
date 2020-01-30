![Logo](/assets/logo.png)

# 30 seconds of Vue

> Curated collection of useful snippets that you can understand in 30 seconds or less.

* Use <kbd>Ctrl</kbd> + <kbd>F</kbd> or <kbd>command</kbd> + <kbd>F</kbd> to search for a snippet.
* Contributions welcome, please read the [contribution guide](CONTRIBUTING.md).

#### Related projects

* [30 seconds of code](https://30secondsofcode.org/)
* [30 Seconds of CSS](https://30-seconds.github.io/30-seconds-of-css/)
* [30 Seconds of Interviews](https://30secondsofinterviews.org/)
* [30 Seconds of React](https://github.com/30-seconds/30-seconds-of-react)

## Contents
###  Beginner

<details>
<summary>View contents</summary>

* [`Polaroid`](#polaroid)

</details>


---

##  Beginner


### Polaroid

This snippet creates a Polaroid-style picture. It uses `props` to obtain the url and a Slot to obtain the caption, then renders a `<figure>` element with a caption encapsulated within `<figcaption>`.

```js
```vue
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
```

<details>
<summary>Examples</summary>

```js
```vue
<Polaroid url="https://picsum.photos/500">
    A nice caption goes here
</Polaroid>
```
```
</details>

<br>[⬆ Back to top](#contents)

## Credits

* Inspired by [30 seconds of code](https://github.com/30-seconds/30-seconds-of-code) and other [30 seconds](https://github.com/30-seconds) projects.
* This README is built using the [30 seconds starter template](https://github.com/30-seconds/30-seconds-starter).
