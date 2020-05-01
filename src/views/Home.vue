<template>
  <div class="home">
    <Cover
      v-bind:title="titulo_web"
      v-bind:subtitle="slogan_web"
      bgimg="grafico-2.svg"
    />

    <section class="ProductGallery grid">
      <h3 class="col-desk-12">Showroom lab</h3>
      <div class="col-desk-6 col-tab-7 col-mob-4">
        <div class="ProductCard">
          <figure class="ProductImage">
            <img :src="'/img/' + currentProduct" :alt="currentDescription" />
            <figcaption class="ProductCaption">{{ currentDescription }}</figcaption>
          </figure>
        </div>
      </div>

      <div class="actions">
        <span @click="prevProduct" class="prev">
          &#10094;
        </span>
        <span @click="nextProduct" class="next">
          &#10095;
        </span>
      </div>

      <div class="col-desk-5 col-tab-3 col-mob-4">
        <div class="thumbnails">
          <div
            v-for="(product, index) in products"
            :key="product.id"
            :class="['thumbnail-image', activeProduct == index ? 'active' : '']"
            @click="activateProduct(index)"
          >
            <img :src="'/img/' + product.thumb" />
          </div>
        </div>
      </div>
    </section>

    <Footer />
  </div>
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
    Footer,
  },
  data: () => {
    return {
      mostrar: true,
      activeProduct: 0,
      timer: null,
      titulo_web: todh_data.author,
      slogan_web: todh_data.slogans[0].web,
      products: todh_data.products,
    };
  },
  computed: {
    currentDescription() {
      return this.products[this.activeProduct].title;
    },
    currentProduct() {
      return this.products[this.activeProduct].imgsrc;
    },
  },
  methods: {
    nextProduct() {
      var active = this.activeProduct + 1;
      if (active >= this.products.length) {
        active = 0;
      }
      this.activateProduct(active);
    },
    prevProduct() {
      var active = this.activeProduct - 1;
      if (active < 0) {
        active = this.products.length - 1;
      }
      this.activateProduct(active);
    },
    activateProduct(productIndex) {
      this.activeProduct = productIndex;
    },
    startRotation: function() {
      this.timer = setInterval(this.next, 3000);
    },
    toggleMostrar: function() {
      this.mostrar = !this.mostrar;
    },
    next: function() {
      this.currentProduct += 1;
    },
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.home .Cover {
  // height: 30vh;
  color: $white;
  @include margin-bottom(2);
}

.ProductGallery {
  @include margin-bottom(2);
}
.ProductImage {
  background-color: $alpha_white;
  position: relative;
}
.ProductCaption {
  position: absolute;
  top: 0;
  left: 0;
  background-color: $alpha_white;
}
.thumbnails {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: center;
  padding: $h0;
  border: 1px solid $light_grey;
  img {
    max-width: 100%;
    height: auto;
  }
}
.actions {
  position: relative;
  // background-color: red;
  // padding: $h2;
  .next, .prev {
    position: absolute;
    top: -#{$h3};
    @include type-setting(1);
  }
  .next {
    right: $h1;
  }
  .prev {
    right: $h3;
  }
}
.thumbnail-image {
  width: 50px;
  // height: 50px;
}
.thumbnail-image.active {
  opacity: 0.5;
}

footer {
  margin-top: 0;
}
</style>
