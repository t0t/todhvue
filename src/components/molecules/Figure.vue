<template>
  <figure>
    <img
      v-on:click="
        showDescription();
        show = !show;
      "
      v-bind:class="{ active: show }"
      :src="imagen"
      :alt="caption"
    />
    <figcaption v-if="show">
      {{ caption }}
    </figcaption>
  </figure>
</template>

<script>
export default {
  name: "Figure",
  props: {
    imagen: String,
    caption: String,
  },
  data: () => {
    return {
      show: false,
    };
  },
  methods: {
    showDescription() {
      console.log(this.caption);
    },
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

figure {
  // background-color: red;
  img {
    @include margin-bottom(-2);
    transition: all 0.1s ease-in-out;
      opacity: 0.5;
    &.active {
      opacity: 1;
      transform: scale(1.05);
    }
  }
  figcaption {
    color: $grey;
    font-style: italic;
    @include margin-bottom(1);
  }
}
</style>
