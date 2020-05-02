<template>
  <div id="app">
    <MainNav />
    <router-view />
  </div>
</template>

<script>
import MainNav from "@/components/molecules/MainNav.vue";
export default {
  components: {
    MainNav
  }
}
</script>
