<template>
  <div class="home">
    <!-- <div 
    v-for="cita in citas" v-bind:key="cita" 
    >
    <p>{{cita}} lorem </p>
    </div> -->

    <Cover
      v-bind:title="data.author"
      v-bind:subtitle="data.slogans[0].web"
      bgimg="img4.jpg"
    />
    <Footer />
  </div>
  <!-- <div v-else>Loading...</div> -->
</template>

<script>
import Cover from "@/components/organos/Cover.vue";
import Footer from "@/components/molecules/Footer.vue";
import todh_data from '@/data';
console.log(todh_data)

export default {
  name: "Home",
  components: {
    Cover,
    Footer
  },
  data: () => {
    return {
      data: todh_data
    }
  },
  // created () {
  //   this.fetchAllCategories()
  //     .then(categories => Promise.all(categories.map(category => this.fetchForums({ids: Object.keys(category.forums)}))))
  //     .then(() => {
  //       this.ready = true
  //     })
  // }
};
</script>

<style lang="scss">

.home .Cover {
  height: 100vh;
  // flex-wrap: nowrap;
}
</style>
