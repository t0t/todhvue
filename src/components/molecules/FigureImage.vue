<template>
  <figure>
    <img :src="imagen" :alt="caption">
    <figcaption>
      {{ caption }}
    </figcaption>
  </figure>
</template>

<script>
export default {
  name: "FigureImage",
  props: {
    imagen: String,
    caption: String,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

figure {
    // @include padding-bottom(8);
}
figcaption {
    color: $grey;
    font-style: italic;
}
</style>
