<template>
  <div class="col-desk-12 col-tab-10 col-mob-4">
    <aside class="Bio grid">
      <div class="col-desk-2">
        <img class="BioAvatar" :src="imagen" />
      </div>
      <div class="col-desk-5">
        <small class="BioExcerpt">
          {{ txt }}
        </small>
      </div>
      <div class="col-desk-3">
        <SocialLinks />
      </div>
    </aside>
  </div>
</template>

<script>
import SocialLinks from "@/components/molecules/SocialLinks.vue";

export default {
  name: "BioExcerpt",
  props: {
    txt: String,
    imagen: String,
  },
  components: {
    SocialLinks,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Bio {
  display: flex;
  justify-content: space-around;
  align-items: center;

  &Avatar {
    width: 50px;
  }
}
</style>
