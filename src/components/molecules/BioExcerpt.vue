<template>
  <aside class="Bio grid">
    <div class="col-desk-1 col-desk-shift-1 col-tab-12 col-mob-2">
      <img class="BioAvatar" :src="imagen" />
      </div>
    <h5 class="BioHeader col-desk-2 col-desk-shift-1 col-tab-12 col-mob-2">{{ header }}</h5>
    <p class="BioExcerpt col-desk-6 col-desk-shift-1 col-tab-12 col-mob-4">{{ txt }}</p>
  </aside>
</template>

<script>
export default {
  name: "BioExcerpt",
  props: {
    header: String,
    txt: String,
    imagen: String,
  },
  // computed: {
  //   imgurl() {
  //     return require("@/assets/" + this.bgimg);
  //   }
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "@/styles/main.scss";

.Bio {
  border: 1px solid $light_grey;
  padding-top: $h2;

  @include media(s1) {
  }
  @include media(s2) {
    color: $grey;
  }
  @include media(s5) {
  }
  &Avatar {
    display: block;
    width: $h4;
    height: $h4;
    border-radius: $h3;
    background-color: pink;
    @include media(s2) {
    }
  }
  &Header {
  }
  &Excerpt {
  }
}
</style>
