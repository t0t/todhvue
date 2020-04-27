<template>
  <section>
    <ul class="Gallery" :style="listLength">
      <li v-for="(obra, index) in obras" :key="index" :style="listPosition">
        <GalleryItem :item="obra" :active="index == currentIndex" />
      </li>
    </ul>
  </section>
</template>

<script>
import GalleryItem from "@/components/molecules/GalleryItem";

export default {
  name: "Gallery",
  components: {
    GalleryItem,
  }
};
/* eslint-disable */
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Gallery {
  margin-right: 0;
  margin-left: 0;
  padding-left: 0;
  padding-right: 0;
  position: relative;
  height: 500px;
  background-color: $black;
  overflow: hidden;
  transition: all 0.5s ease;
  &.open {
    height: 600px;
    transform: translateY(-100px);
  }
  .img {
    width: 50%;
    height: 500px;
    background-position: center;
    background-size: cover;
  }
  .title {
    position: absolute;
    top: 50px;
    padding: $h0 $h1;
    height: 40px;
    background-color: rgba($color: $light_grey, $alpha: 0.2);
    color: $white;
  }
  .description {
    padding: 20px;
    color: $white;
  }
}
</style>
