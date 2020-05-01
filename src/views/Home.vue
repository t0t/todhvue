<template>
  <div class="home">
    <Cover
      v-bind:title="titulo_web"
      v-bind:subtitle="slogan_web"
      bgimg="detalle6.jpg"
    />

    <section class="ProductGallery grid">
      <div class="col-desk-7 col-tab-5 col-mob-4">
        <div class="ProductCard">
          <div class="ProductImage">
            <img :src="'/img/' + currentProduct" :alt="currentDescription" />
          </div>
        </div>
      </div>

      <div class="col-desk-5 col-tab-5 col-mob-4">
        <div class="actions">
          <span @click="prevProduct" class="prev">
            &#10094;
          </span>
          <span @click="nextProduct" class="next">
            &#10095;
          </span>
        </div>
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
        <div class="ProductCaption">
          <h6>{{ currentTitle }}</h6>
          <small>{{ currentDescription }}</small>
          <button class="ButtonDefault">
            <router-link :to="currentLink">Más info</router-link>
          </button>
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
// console.log(todh_data);

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
      return this.products[this.activeProduct].description;
    },
    currentLink() {
      return this.products[this.activeProduct].url;
    },
    currentTitle() {
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

.ProductGallery {
  @include margin-bottom(2);
}
.ProductImage {
  background-color: $alpha_white;
}
.ProductCaption {
  padding: $h2;
  // background-color: $secondary;
  h6 {
    @include padding-bottom(-1)
  }
}

.thumbnails {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: center;
  padding: 0;
  img {
    max-width: 100%;
    margin-bottom: 0;
  }
}
.actions {
  display: flex;
  justify-content: flex-end;

  .next,
  .prev {
    display: block;
    width: 50px;
    height: 50px;
    @include type-setting(1);
    &:hover {
      cursor: pointer;
      color: $secondary;
    }
  }
  .next {
    right: 0;
  }
  .prev {
    left: 0;
  }
}
.thumbnail-image {
  width: 50px;
  &:hover {
    cursor: pointer;
  }
}
.thumbnail-image.active {
  background-color: $secondary;
}

footer {
  margin-top: 0;
}
</style>
