<template>
  <hgroup
    class="PageHeader"
    :style="{ backgroundImage: `url(${imgurl})` }"
    role="banner"
  >
    <h1 class="PageHeaderTitle col-desk-12">{{ title }}</h1>
    <h2 class="PageHeaderSubtitle col-desk-12">
      {{ subtitle }}
    </h2>
  </hgroup>
</template>

<script>
export default {
  name: "PageHeader",
  props: {
    title: String,
    subtitle: String,
    bgimg: String,
  },
  computed: {
    imgurl() {
      return require("@/assets/" + this.bgimg);
    },
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.PageHeader {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  background-color: $primary;
    @include padding-top(4);
    @include padding-bottom(3);
}

.PageHeaderTitle {}

</style>
