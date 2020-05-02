<template>
  <base-layout>
    <template slot="header">
      <PageHeader
        v-bind:title="titulo_todh"
        v-bind:subtitle="slogan_web"
        bgimg="bg7.jpg"
      />
    </template>

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
        <FigureImage caption="Description 2" imagen="/img/grafico-5.svg" />
      </div>
      <p class="col-desk-4 col-tab-5 col-mob-4">
        Estos últimos años se ha ido consolidando una manera de ver la realidad.
      </p>
      <div class="col-desk-8 col-tab-5 col-mob-4">
        <FigureImage caption="Description 8" imagen="/img/grafico-8.svg" />
      </div>
      <p class="col-desk-4 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>

      <BlockQuote
        cita="Todo según el número."
        author="Pitagoras de Samos - S.V a. C."
      />

      <div class="col-desk-5">
        <FigureImage caption="Description 12" imagen="/img/grafico-1.svg" />
      </div>
      <p class="col-desk-12 col-tab-5 col-mob-4">
        En este sentido su proyecto aboga por una reconexión incursiva con la
        verdad que nos habita. Podríamos decir que su mirada se centra en las
        experiencias antes que en los objetos o los productos, defendiendo el
        desarrollo de la mente abstracta frente al de la mente concreta.
      </p>
      <div id="#todh" class="col-desk-8">
        <FigureImage caption="Description 2" imagen="/img/grafico-2.svg" />
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
        <FigureImage caption="Description 2" imagen="/img/grafico-3.svg" />
      </div>
      <div class="col-desk-5 col-tab-5 col-mob-4">
        <FigureImage caption="Description 3" imagen="/img/grafico-5.svg" />
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
        <BlockQuote
          author="Guy Murchie, The Seven Mysteries of Life: An Exploration of Science and Philosophy"
          cita="The Fibonacci Sequence turns out to be the key to understanding how nature designs... and is... a part of the same ubiquitous music of the spheres that builds harmony into atoms, molecules, crystals, shells, suns and galaxies and makes the Universe sing."
        />

        <FigureImage
          caption="Description of the image"
          imagen="/img/grafico-7.svg"
        />
      </div>

      <div class="col-desk-5 col-tab-5 col-mob-4">
        <FigureImage caption="Description 2" imagen="/img/grafico-1.svg" />
      </div>
    </article>

    <Card
      bgimg="svg_anim.svg"
      v-bind:title="cita_todh2.frase"
      v-bind:subtitle="cita_todh2.autor"
      v-bind:text="cita_todh2.bloque"
    />

    <template slot="footer">
      <Footer />
    </template>
  </base-layout>
</template>

<script>
import BaseLayout from "@/components/layout/BaseLayout.vue";
import PageHeader from "@/components/organos/PageHeader.vue";
import BlockQuote from "@/components/atoms/BlockQuote.vue";
import List from "@/components/molecules/List.vue";
import FigureImage from "@/components/molecules/FigureImage.vue";
import ItemList from "@/components/molecules/ItemList.vue";
import NavigationItem from "@/components/atoms/NavigationItem.vue";
import Card from "@/components/molecules/Card.vue";
import Footer from "@/components/molecules/Footer.vue";
import todh_data from "@/data";

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
    BaseLayout,
    PageHeader,
    BlockQuote,
    List,
    FigureImage,
    Card,
    NavigationItem,
    ItemList,
    Footer,
  },
};
</script>
