<template>
  <a :href="url">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "navigation-link",
  props: {
    url: String
  }
};
</script>
