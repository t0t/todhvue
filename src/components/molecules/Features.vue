<template>
  <aside class="Features">
    <h3>{{ title }}</h3>
    <div class="FeaturesList grid">
      <dl col-desk-4 col-tab-5 col-mob-4>
        <dt>{{ feature1 }}</dt>
        <dd>{{ feature1b }}</dd>
      </dl>
      <dl col-desk-4 col-tab-5 col-mob-4>
        <dt>{{ feature2 }}</dt>
        <dd>{{ feature2b }}</dd>
      </dl>
      <dl col-desk-4 col-tab-5 col-mob-4>
        <dt>{{ feature3 }}</dt>
        <dd>{{ feature3b }}</dd>
      </dl>
    </div>
  </aside>
</template>

<script>
export default {
  name: "Features",
  props: {
    title: String,
    feature1: String,
    feature1b: String,
    feature2: String,
    feature2b: String,
    feature3: String,
    feature3b: String,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Features {
  background-color: $white;
  // padding: $h2;
  @include media(s1) {
    padding-bottom: $h3;
  }
  @include media(s5) {
    padding: $h4;
  }
  h3 {
    text-align: center;
  }
  &Title {
    width: 100%;
  }
  &List {
    @include media(s2) {
      display: flex;
      justify-content: space-between;
    }
    dl {
      margin-bottom: $h-2;
      @include media(s0) {
      }
      @include media(s1) {
        padding: $h1;
        text-align: center;
      }
      @include media(s2) {
        flex-grow: 1;
        max-width: $h7;
        // background-color: $tertiary;
      }
      @include media(s4) {
        padding: $h3;
      }
      @include media(s5) {
        padding: $h3;
      }
    }
  }
}
</style>
