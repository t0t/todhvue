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
      <h3 class="col-desk-12">Sentir la creación que ya eres</h3>
      <h4 class="col-desk-12 col-tab-9 col-tab-shift-0">
        De la mente concreta a la mente abstracta
      </h4>
      <div class="col-desk-12">
        <img src="img/grafico-5.svg" />
      </div>
      <p class="col-desk-4 col-tab-5 col-mob-4">
        Estos últimos años se ha ido consolidando una manera de ver la realidad.
      </p>
      <div class="col-desk-8 col-tab-5 col-mob-4">
        <img src="/img/grafico-8.svg" />
      </div>
      <p class="col-desk-4 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <div class="col-desk-5">
        <img src="/img/grafico-1.svg" />
      </div>
      <p class="col-desk-12 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <div class="col-desk-8">
        <img src="/img/grafico-2.svg" />
      </div>
      <p class="col-desk-4 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <p class="col-desk-7 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/grafico-3.svg" />
      </div>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/grafico-4.svg" />
      </div>
      <p class="col-desk-7 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>

      <div class="col-desk-12">
        <h5>A dotted list component:</h5>
      </div>
      <List>
        <item-list v-for="intereses in lista_intereses" v-bind:key="intereses">
          <navigation-item>{{ intereses }}</navigation-item>
        </item-list>
      </List>

      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/grafico-6.svg" />
      </div>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <img src="/img/grafico-7.svg" />
      </div>
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
import PageHeader from "@/components/organos/PageHeader.vue";
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
      lista_intereses: todh_data.intereses,
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
    Footer,
  },
};
</script>
