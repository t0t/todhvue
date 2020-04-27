<template>
  <div id="gallery" class="Gallery">
    <transition-group name="fade" tag="div">
      <div v-for="i in [currentIndex]" :key="i">
        <img v-bind:src="require('@/assets/'+ currentImg)" />
      </div>
    </transition-group>
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
      images: todh_data.main_personal_areas[0].arte.gallery,
      timer: null,
      currentIndex: 0,
      // 2. Set timer to null and set currentIndex to 0 for showing the first image.
    };
  },
  mounted: function () {
    this.stopSlide();
  },
  methods: {
    stopSlide: function () {
      return this.next;
    },
    startSlide: function () {
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
    }
  },
};
/* eslint-disable */
</script>

<style lang="scss">
@import "@/styles/main.scss";
// @import '../node_modules/swiper/css/swiper.css';

.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width: 100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width: 100%;
  opacity: 0;
}

img {
  height: 600px;
  width: 100%;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 45%;
  // width: $h4;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: $h4;
  transition: 0.7s ease;
  border-radius: 0 4px 4px 0;
  text-decoration: none;
  user-select: none;
}

.next {
  right: 0;
}

.prev {
  left: 0;
}

.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.9);
}

.swiper-container {
  width: 600px;
  height: 300px;
}
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
