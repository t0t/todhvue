<template>
  <div>


    <img :src="'/img/' + currentProduct" :alt="currentDescription" />
      <!-- <div v-for="product of products" :key="product.id">
      </div>
 -->


    <span @click="prevProduct" class="prev">
      &#10094;
    </span>
    <span @click="nextProduct" class="next">
      &#10095;
    </span>

    <div class="thumbnails">
      <div
        v-for="(product, index) of products"
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
</template>

<script>
import axios from "axios";
// import Product from "@/components/organos/Product";

export default {
  data: () => {
    return {
      activeProduct: 1,
      products: [],
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
      return this.products[this.activeProduct].name;
    },
    currentProduct() {
      return this.products[this.activeProduct].img_src;
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
  created() {
    axios
      .get("db.json")
      .then(res => {
        this.products = res.data[1].productos;
        console.log(this.products);
      })
      .catch(err => {
        console.log(err);
      });
  },
//   components: {
//     Product,
//   },
};
</script>
