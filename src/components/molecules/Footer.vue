<template>
  <div class="Footer">
    <div class="grid">
      <BioExcerpt
        v-bind:header="bio.author"
        v-bind:txt="bio.bio"
        v-bind:imagen="require('@/assets/' + bio.avatar)"
      />
    </div>
  </div>
</template>

<script>
import BioExcerpt from "@/components/molecules/BioExcerpt.vue";
import todh_data from "@/data";

export default {
  name: "Footer",
  props: {
    msg: String,
  },
  data: () => {
    return {
      bio: todh_data,
    };
  },
  components: {
    BioExcerpt,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "@/styles/main.scss";

.Footer {
  z-index: -1;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  align-content: center;
  background-color: $light_grey;
  @include padding-top(4);
  @include padding-bottom(4);
  // background-color: red;
}
</style>
