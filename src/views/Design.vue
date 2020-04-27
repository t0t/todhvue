<template>
  <div class="design">
 
    <Cover
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
import Footer from "@/components/molecules/Footer.vue";
import Cover from "@/components/organos/Cover.vue";
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
    Cover,
    Card,
    Features,
    Footer
  }
};
</script>
