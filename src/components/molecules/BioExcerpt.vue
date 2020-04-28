<template>
  <aside class="Bio">
    <h5 class="BioHeader">{{ header }}</h5>
    <img class="BioAvatar" :src="imagen" />
    <p class="BioExcerpt">{{ txt }}</p>
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
  border: 1px solid $black;
  padding: $h1;
  margin-right: $h0;
  margin-left: $h0;
  text-align: center;
  @include media(s1) {
  }
  @include media(s2) {
    max-width: $s2;
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: space-between;
    margin-right: auto;
    margin-left: auto;
    margin-top: $h3;
  }
  @include media(s5) {
    max-width: $s3;
  }
  &Avatar {
    width: $h4;
    height: $h4;
    border-radius: $h4;
    @include media(s2) {
      padding: $h1;
    }
  }
  &Header {
    @include media(s1) {
      padding-bottom: $h1;
    }
    @include media(s2) {
      padding-bottom: 0;
    }
  }
  &Excerpt {
    padding: $h0;
    margin-left: 0;
  }
}
</style>
