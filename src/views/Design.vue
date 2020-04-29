<template>
  <div class="design">
    <PageHeader
      v-bind:title="titulo_diseno"
      v-bind:subtitle="slogan_web"
      bgimg="img10.jpg"
    />

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
      <img class="col-desk-6" src="../assets/img2.jpg" />
      <img class="col-desk-6" src="../assets/img1.jpg" />
      <p class="col-desk-8">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi labore
        cupiditate possimus reiciendis deserunt ullam fugiat nisi corporis
        necessitatibus, ipsam id consequuntur repellendus illum eum unde dolorem
        cumque! Dolores, magnam.
      </p>
      <img class="col-desk-12" src="../assets/img3.jpg" />
      <small class="col-desk-3">Pie de fotografía</small>
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

    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/molecules/Card.vue";
import Features from "@/components/molecules/Features.vue";
import PageHeader from "@/components/organos/PageHeader.vue";
import Footer from "@/components/molecules/Footer.vue";
// import Cover from "@/components/organos/Cover.vue";
import todh_data from "@/data";
// console.log(slogans);

export default {
  name: "Design",
  data: () => {
    return {
      titulo_diseno: todh_data.main_personal_areas[0].diseno.title,
      slogan_web: todh_data.main_personal_areas[0].diseno.slogans[0].web,
      cita_todh: todh_data.main_personal_areas[0].diseno.citas[0],
      // cita_todh2: todh_data.main_personal_areas[0].todh.citas[1],
      // lista_intereses: todh_data.intereses
    };
  },
  components: {
    Card,
    // Cover,
    PageHeader,
    Features,
    Footer,
  },
};
</script>
