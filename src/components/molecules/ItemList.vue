<template>
  <li class="col-desk-3 col-tab-5 col-mob-4">
    <slot>
      <navigation-link url="#laurl"> </navigation-link>
    </slot>
  </li>
</template>

<script>
import NavigationLink from "@/components/atoms/NavigationLink.vue";

export default {
  name: "item-list",
  props: {},
  components: {
    NavigationLink
  }
};
</script>
