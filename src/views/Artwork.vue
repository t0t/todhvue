<template>
  <section class="artwork">

    <PageHeader
      v-bind:title="titulo_arte"
      v-bind:subtitle="slogan_arte"
      bgimg="img9.jpg"
    />

    <Gallery />

    <article class="grid">
      <h3 class="col-desk-10 col-desk-shift-1 col-tab-8 col-mob-4">
        Incursión en la Creación misma
        </h3>
      <p 
      class="col-desk-10 col-desk-shift-1 col-tab-7 col-mob-4">
        Así, orbitando varios mundos como son la tecnología, el arte y la
        sabiduría antigua, Sergio afianza con los años un corpus discursivo y
        práctico que llama TODH en torno al proceso mismo de la Creación y su
        dimensión estructural holística. En este sentido su proyecto aboga por
        una reconexión incursiva con la verdad que nos habita. Podríamos decir
        que su mirada se centra en las experiencias antes que en los objetos o
        los productos, defendiendo el desarrollo de la mente abstracta frente al
        de la mente concreta.
      </p>
    </article>

    <BioExcerpt
      v-bind:header="bio.author"
      v-bind:txt="bio.bio"
      v-bind:imagen="require('@/assets/' + bio.avatar)"
    />

    <Features
      title=""
      feature1="Materiales"
      feature1b="PLA, Epoxi&Damar resins, Wax, Sand..."
      feature2="Idea"
      feature2b="Arte consciente"
      feature3="Proceso"
      feature3b="Sin fin"
    />
    <Footer />
  </section>
</template>

<script>
/* eslint-disable */
import Gallery from "@/components/molecules/Gallery.vue";
import PageHeader from "@/components/organos/PageHeader.vue";
import BioExcerpt from "@/components/molecules/BioExcerpt.vue";
import Features from "@/components/molecules/Features.vue";
import Footer from "@/components/molecules/Footer.vue";
import todh_data from "@/data";
// console.log(slogans);

export default {
  name: "Artwork",
  data: () => {
    return {
      titulo_arte: todh_data.main_personal_areas[0].arte.title,
      slogan_arte: todh_data.main_personal_areas[0].arte.slogans[0].web,
      bio: todh_data,
    };
  },
  components: {
    PageHeader,
    Gallery,
    BioExcerpt,
    Features,
    Footer,
  },
};
</script>
