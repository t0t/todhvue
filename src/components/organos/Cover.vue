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
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  align-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: top;
  background-color: $primary;
  height: 50vh;
  color: #00dcff;
  font-weight: normal;
  @include media(s2) {
    height: 100vh;
  }
}

.CoverSubtitle {
  margin-right: 0;
}
</style>
