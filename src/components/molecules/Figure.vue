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
  img {
    margin-bottom: 0;
    transition: opacity .5s ease-in-out;
  }
  img.active ~ figcaption {
    @include padding-top(0);
    @include margin-top(-1);
    opacity: 1;
    animation-name: show;
    animation-iteration-count: 1;
    animation-duration: .3s;
    background-color: $white;
    border-top: 1px solid $light_grey;
  }
  figcaption {
    opacity: .5;
    text-align: left;
    font-style: italic;
    // @include type-setting(0);
    @include margin-bottom(1);
  }
}
</style>
