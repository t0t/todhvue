<template>
  <div>
    <product
      v-for="product of products"
      v-bind:key="product.id"
      v-bind:product="product"
    />
  </div>
</template>

<script>
import axios from "axios";
import Product from "@/components/organos/Product";

export default {
  data: () => {
    return {
      products: [],
    };
  },
  mounted() {
    axios
      .get("db.json")
      .then((res) => {
        this.products = res.data[1].productos;
        console.log(this.products);
      })
      .catch((err) => {
        console.log(err);
      });
  },
  components: {
    Product,
  },
};
</script>
