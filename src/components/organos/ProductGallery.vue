<template>
  <section class="ProductGallery grid">
    <div class="col-desk-7 col-tab-5 col-mob-4">
      <div class="ProductCard">
        <div class="ProductImage">
          <img :src="'./img/' + currentProduct" :alt="currentDescription" />
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
          :class="['thumbnail-image', activeProduct == index ? 'active' : '']"
          v-for="(producto, index) in products"
          v-bind:key="producto.id"
        >
          <img
            v-on:click="activateProduct(index)"
            :src="'./img/' + producto.thumb"
            :title="producto.name"
          />
        </div>

        <div class="ProductCaption">
          <h6>{{ currentTitle }}</h6>
          <small>{{ currentDescription }}</small>
          <button class="ButtonDefault">
            <a :href="'/#' + currentLink">Más info</a>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "ProductGallery",
  data: () => {
    return {
      products: [{}],
      activeProduct: 0,
    };
  },
  created() {
    axios
      .get("db.json")
      .then((res) => {
        this.products = res.data.productos;
        console.log(this.products);
      })
      .catch((err) => {
        console.log(err);
      });
  },
  computed: {
    currentDescription() {
      return this.products[this.activeProduct].description;
    },
    currentLink() {
      return this.products[this.activeProduct].url;
    },
    currentTitle() {
      return this.products[this.activeProduct].name;
    },
    currentProduct() {
      return this.products[this.activeProduct].imagen;
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
    @include padding-bottom(-1);
  }
}

.thumbnails {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: center;
  padding: 0;
  img {
    // max-width: 150px;
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
</style>
