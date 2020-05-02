<template>
  <div class="BrandLogo" role="logo">
    <router-link to="/">
      <IcoLogo />
    </router-link>
  </div>
</template>

<script>
import IcoLogo from "@/components/atoms/icons/IcoLogo.vue";
export default {
  name: "BrandLogo",
  components: {
    IcoLogo,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.toggleButton.active ~ .BrandLogo {
  // transform: scale(10);
  // position: fixed;
  // left: 0;
  // right: 0;
  // margin: auto;

  // top: $h1;
  // @include media(s0) {
  //   left: 36%;
  // }
  // @include media(s1) {
  //   left: 43.8%;
  //   // background-color: red;
  // }
  // @include media(s2) {
  //   left: 46%;
  // }
  // @include media(s3) {
  //   left: 50%;
  // }
  // & path {
  //   fill: $white;
  // }
  // & circle {
  //   fill: $white;
  // }
}
.BrandLogo {
  height: 50px;
  width: 50px;
  padding: 10px;
  position: fixed;
  &:hover {
    & path.hacer {
      fill: $black;
    }
    & path.sentir {
      fill: blue;
      stroke: none;
    }
    & path {
      fill: yellow;
    }
    & circle {
      fill: red;
    }
  }
}
</style>
