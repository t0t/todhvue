<template>
  <aside class="Bio grid">
    <div class="col-desk-2 col-desk-shift-1 col-tab-12 col-mob-2">
      <img class="BioAvatar" :src="imagen" />
    </div>
    <h6 class="BioHeader col-desk-2 col-tab-12 col-mob-2">
      {{ header }}
    </h6>
    <small
      class="BioExcerpt col-desk-5 col-desk-shift-1 col-tab-12 col-mob-4"
      >{{ txt }}</small
    >
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
  color: $grey;
  @include media(s1) {
    @include padding-top(1);
  }

  &Avatar {
    display: block;
    // width: $h4;
    height: $h4;
    // border-radius: $h3;
    background-color: pink;
    // @include margin-top(1);
  }
  &Header {
  }
  &Excerpt {
  }
}
</style>
