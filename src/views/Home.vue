<template>
  <base-layout>
    <template slot="header">
      <Cover
        v-bind:title="titulo_web"
        v-bind:subtitle="slogan_web"
        bgimg="detalle6.jpg"
      />
    </template>

    <ProductGallery />

    <template slot="footer">
      <Footer />
    </template>
  </base-layout>
</template>

<script>
import todh_data from "@/data";
import BaseLayout from "@/components/layout/BaseLayout.vue";
import Cover from "@/components/organos/Cover.vue";
import ProductGallery from "@/components/organos/ProductGallery.vue";
import Footer from "@/components/molecules/Footer.vue";

export default {
  name: "Home",
  data: () => {
    return {
      titulo_web: todh_data.author,
      slogan_web: todh_data.slogans[0].web
    };
  },
  components: {
    BaseLayout,
    Cover,
    ProductGallery,
    Footer
  }
}
</script>