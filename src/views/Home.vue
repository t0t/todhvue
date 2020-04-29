<template>
  <div class="home">
   <Cover
      v-bind:title="titulo_web"
      v-bind:subtitle="slogan_web"
      bgimg="img10.jpg"
    />
    <Footer />
  </div>
  <!-- <div v-else>Loading...</div> -->
</template>

<script>
import Cover from "@/components/organos/Cover.vue";
import Footer from "@/components/molecules/Footer.vue";
import todh_data from "@/data";
console.log(todh_data);

export default {
  name: "Home",
  components: {
    Cover,
    Footer
  },
  data: () => {
    return {
      titulo_web: todh_data.author,
      slogan_web: todh_data.slogans[0].web
    }
  },
  methods: {
    // LoadImage(filename) {
        // const image = require('@/assets/' + titulo_web)
        // const image = require('~@/assets/' + filename)
        // return image
    // }
  }
};
</script>

<style lang="scss">
.home .Cover {
  height: 100vh;
}
footer {
  margin-top: 0;
}
</style>
