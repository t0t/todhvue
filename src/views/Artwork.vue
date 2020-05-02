<template>
  <base-layout>
    <template slot="header">
      <PageHeader
        v-bind:title="titulo_arte"
        v-bind:subtitle="slogan_arte"
        bgimg="img9.jpg"
      />
    </template>

    <article class="grid">
      <div class="col-desk-12 col-tab-6 col-mob-4">
        <img src="/img/detalle3.jpg" />
      </div>
      <h3 class="col-desk-10 col-tab-3 col-mob-4">
        Incursión en la Creación misma
      </h3>
      <p
        class="col-desk-10 col-desk-shift-1 col-tab-10 col-tab-shift-0 col-mob-4"
      >
        Así, orbitando varios mundos como son la tecnología, el arte y la
        sabiduría antigua, Sergio afianza con los años un corpus discursivo y
        práctico que llama TODH en torno al proceso mismo de la Creación y su
        dimensión estructural holística. En este sentido su proyecto aboga por
        una reconexión incursiva con la verdad que nos habita. Podríamos decir
        que su mirada se centra en las experiencias antes que en los objetos o
        los productos, defendiendo el desarrollo de la mente abstracta frente al
        de la mente concreta.
      </p>
      <p class="col-desk-7 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/detalle1.jpg" />
      </div>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/detalle2.jpg" />
      </div>
      <p class="col-desk-7 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
    </article>

    <Features
      title=""
      feature1="Materiales"
      feature1b="PLA, Epoxi&Damar resins, Wax, Sand..."
      feature2="Idea"
      feature2b="Arte consciente"
      feature3="Proceso"
      feature3b="Sin fin"
    />
    <template slot="footer">
      <Footer />
    </template>
  </base-layout>
</template>

<script>
import todh_data from "@/data";
import BaseLayout from "@/components/layout/BaseLayout.vue";
import PageHeader from "@/components/organos/PageHeader.vue";
import Features from "@/components/molecules/Features.vue";
import Footer from "@/components/molecules/Footer.vue";

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
    BaseLayout,
    PageHeader,
    Features,
    Footer,
  },
};
</script>
