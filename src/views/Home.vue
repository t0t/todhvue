<template>
  <div class="home">
    <Cover
      title="sergio fores"
      subtitle="Original 3D-printed Artwork & Modern prototyping for the web"
      bgimg="img4.jpg"
    />
    <Footer />
  </div>
  <!-- <div v-else>Loading...</div> -->
</template>

<script>
import Cover from "@/components/organos/Cover.vue";
import Footer from "@/components/molecules/Footer.vue";

export default {
  name: "Home",
  components: {
    Cover,
    Footer
  }
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.home .Cover {
  height: 100vh;
  // flex-wrap: nowrap;
}
</style>
