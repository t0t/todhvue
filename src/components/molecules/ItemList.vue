<template>
  <li class="col-desk-3 col-tab-5 col-mob-4">
    <slot></slot>
  </li>
</template>

<script>
// import NavigationItem from "@/components/atoms/NavigationItem.vue";

export default {
  name: "item-list",
  props: {},
  components: {
    // NavigationItem
  }
};
</script>
