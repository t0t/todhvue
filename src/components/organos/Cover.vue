<template>
  <hgroup
    class="Cover"
    :style="{ backgroundImage: `url(${imgurl})` }"
    role="banner"
  >
    <h1 class="CoverTitle">{{ title }}</h1>
    <h2 class="CoverSubtitle">{{ subtitle }}</h2>
  </hgroup>
</template>

<script>
export default {
  name: "Cover",
  props: {
    title: String,
    subtitle: String,
    bgimg: String
  },
  computed: {
    imgurl() {
      return require("@/assets/" + this.bgimg);
    }
  }
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Cover {
  // height: 30vh;
  color: $white;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: top;
  background-color: $primary;
  height: 25vh;

  @include margin-bottom(2);
  @include media(s1) {
    height: 30vh;
  }
  @include media(s2) {
    height: 35vh;
  }
  @include media(s3) {
    height: 50vh;
  }
}

.CoverSubtitle {
  margin-right: 0;
}
</style>
