<template>
  <div class="Gallery">
    <figure class="grid" v-for="i in [currentIndex]" :key="i">
      <img
        class="col-desk-12 col-tab-8"
        v-bind:src="require('@/assets/' + currentImg)"
      />
      <!-- <figcaption>
          <span class="title">Title</span>
          <span class="description">Description</span>
        </figcaption> -->
    </figure>
    <a class="prev" @click.self.prevent="prev" href="#">&#10094; </a>
    <a class="next" @click.self.prevent="next" href="#">&#10095; </a>
  </div>
</template>

<script>
import todh_data from "@/data";
// console.log(todh_data.main_personal_areas[0].arte.gallery);

export default {
  name: "Gallery",
  // 1. Array of image URLs from JSON file
  data: () => {
    return {
      // images: todh_data.products[0],
      images: todh_data.main_personal_areas[0].arte.gallery,
      timer: null,
      currentIndex: 0,
      // 2. Set timer to null and set currentIndex to 0 for showing the first image.
    };
  },
  mounted: function() {
    this.stopSlide();
  },
  methods: {
    stopSlide: function() {
      return this.next;
    },
    startSlide: function() {
      this.timer = setInterval(this.next, 8000);
      // 3. Created startSlide function for sliding images every 4 seconds.
    },
    // Created next and prev functions for sliding to the previous or the next image. According to the last currentImg function it detects which image must show at that time based on the index.
    next: function() {
      this.currentIndex += 1;
    },
    prev: function() {
      this.currentIndex -= 1;
    },
  },
  computed: {
    currentImg: function() {
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    },
  },
};
/* eslint-disable */
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Gallery {
  width: 100%;
  height: $h9;
  display: flex;
  justify-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: opacity 2s ease;
  @include margin-bottom(3);

  @include media(s0) {
    max-height: 25vh;
    // background-color: green;
  }
  @include media(s1) {
    max-height: 30vh;
    // background-color: red;
  }
  @include media(s3) {
    max-height: 50vh;
    // background-color: red;
  }
  @include media(s3) {
    max-height: 100vh;
    // background-color: red;
  }

  figure {
    position: relative;
    display: flex;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
  }
  // figcaption {
  //   display: flex;
  //   flex-wrap: wrap;
  //   // flex-direction: column;
  //   align-items: center;
  //   color: $white;
  // }
}

img {
  max-width: 75%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s ease;
  overflow: hidden;
  visibility: visible;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  opacity: 0;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  display: block;
  z-index: 2000;
  width: $h4;
  padding: $h0;
  color: $alpha_black;
  font-weight: bold;
  font-size: $h4;
  transition: 0.2s ease;
  text-decoration: none;
  user-select: none;
  @include media(s0) {
    top: 33%;
    // background-color: green;
  }
  @include media(s1) {
    top: 33%;
    // background-color: red;
  }
  @include media(s3) {
    top: 42%;
  }
}

.next {
  right: 0;
}

.prev {
  left: 0;
}

.prev:hover,
.next:hover {
  color: $black;
}
</style>
