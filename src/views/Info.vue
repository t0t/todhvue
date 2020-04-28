<template>
  <section class="info">
    
    <PageHeader
      v-bind:title="titulo_todh"
      v-bind:subtitle="slogan_web"
      bgimg="bg7.jpg"
    />

    <Card
      bgimg="svg_anim.svg"
      v-bind:title="cita_todh.frase"
      v-bind:subtitle="cita_todh.autor"
      v-bind:text="cita_todh.bloque"
    />

    <article class="grid">
      <h3 class="col-desk-12 col-desk-shift-1">Una visión basada en hechos reales</h3>
      <h5 class="col-desk-8 col-desk-shift-2">Desde la tecnología, el arte y la sabiduría antigua, Sergio afianza con los años un corpus discursivo y
        práctico en torno al proceso mismo de la Creación y su dimensión estructural
        holística.</h5>
      <p class="col-desk-6 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <p class="col-desk-6 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <p class="col-desk-6 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <p class="col-desk-6 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>

      <List>
        <item-list v-for="intereses in lista_intereses" 
        v-bind:key="intereses"
       >
          <navigation-item>{{ intereses }}</navigation-item>
        </item-list>
      </List>

    </article>

    <Card
      bgimg="svg_anim.svg"
      v-bind:title="cita_todh2.frase"
      v-bind:subtitle="cita_todh2.autor"
      v-bind:text="cita_todh2.bloque"
    />

    <Footer />
  </section>
</template>

<script>
// @ is an alias to /src
// import Cover from "@/components/organos/Cover.vue";
// import BioExcerpt from "@/components/molecules/BioExcerpt.vue";
import PageHeader from "@/components/organos/PageHeader.vue"
import List from "@/components/molecules/List.vue";
import ItemList from "@/components/molecules/ItemList.vue";
import NavigationItem from "@/components/atoms/NavigationItem.vue";
import Card from "@/components/molecules/Card.vue";
import Footer from "@/components/molecules/Footer.vue";
import todh_data from "@/data";
// console.log(slogans);

export default {
  name: "Info",
  data: () => {
    return {
      titulo_todh: todh_data.title,
      slogan_web: todh_data.main_personal_areas[0].todh.slogans[0].web,
      cita_todh: todh_data.main_personal_areas[0].todh.citas[0],
      cita_todh2: todh_data.main_personal_areas[0].todh.citas[1],
      lista_intereses: todh_data.intereses
    };
  },
  components: {
    // Cover,
    // BioExcerpt,
    PageHeader,
    List,
    Card,
    NavigationItem,
    ItemList,
    Footer
  }
};
</script>
