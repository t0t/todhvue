<template>
  <div class="CardItem" v-cloak>
    <h5>{{ product.name }}</h5>
    <figure>
      <img :src="'/img/' + product.img_src">
      <figcaption>{{ product.description }}</figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  props: ["product"]
};
</script>

<style>
[v-cloak] > * {
  display: none;
}
[v-cloak]::before {
  content: "8888888";
  display: block;
  width: 100%;
  height: 600px;
  background-color: black;
}
</style>
