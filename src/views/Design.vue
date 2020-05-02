<template>
  <base-layout>
    <template slot="header">
      <PageHeader
        v-bind:title="titulo_diseno"
        v-bind:subtitle="slogan_web"
        bgimg="img10.jpg"
      />
    </template>

    <Card
      bgimg="img4.jpg"
      v-bind:title="cita_todh.frase"
      v-bind:subtitle="cita_todh.autor"
      v-bind:text="cita_todh.bloque"
    />

    <!-- <img v-bind:src="require('@/assets/' + bio.titulo_diseno)"> -->
    <div class="grid">
      <h3 class="col-desk-6">Commodi labore cupiditate possimus reiciendis</h3>
      <p class="col-desk-6">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi labore
        cupiditate possimus reiciendis deserunt ullam fugiat nisi corporis
        necessitatibus, ipsam id consequuntur repellendus illum eum unde dolorem
        cumque! Dolores, magnam.
      </p>
      <div class="col-desk-6 col-mob-4">
        <img src="../assets/img2.jpg" />
      </div>
      <div class="col-desk-6 col-mob-4">
        <img src="../assets/img1.jpg" />
      </div>
      <p class="col-desk-8 col-mob-4">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi labore
        cupiditate possimus reiciendis deserunt ullam fugiat nisi corporis
        necessitatibus, ipsam id consequuntur repellendus illum eum unde dolorem
        cumque! Dolores, magnam.
      </p>
      <div class="col-desk-10 col-tab-10">
        <img src="../assets/img3.jpg" />
      </div>
      <small class="col-desk-2">Pie de fotografía</small>
    </div>

    <Features
      title=":)"
      feature1="Tech Stack"
      feature1b="CSS/Html, Vuejs, Github Pages, Sass, NPM, Nucleo Icons"
      feature2="Prototipado holístico de UI"
      feature2b="Componentización, Atomic Design"
      feature3="Static site deployed in seconds"
      feature3b="Testing on real devices"
    />
    <template slot="footer">
      <Footer />
    </template>
  </base-layout>
</template>

<script>
import todh_data from "@/data";
import BaseLayout from "@/components/layout/BaseLayout.vue";
import Card from "@/components/molecules/Card.vue";
import Features from "@/components/molecules/Features.vue";
import PageHeader from "@/components/organos/PageHeader.vue";
import Footer from "@/components/molecules/Footer.vue";

export default {
  name: "Design",
  data: () => {
    return {
      titulo_diseno: todh_data.main_personal_areas[0].diseno.title,
      slogan_web: todh_data.main_personal_areas[0].diseno.slogans[0].web,
      cita_todh: todh_data.main_personal_areas[0].diseno.citas[0],
    };
  },
  components: {
    BaseLayout,
    Card,
    PageHeader,
    Features,
    Footer
  }
};
</script>
