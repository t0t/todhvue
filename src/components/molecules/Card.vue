<template>
  <aside class="Card">
    <div class="CardContent grid">
      <aside
        class="CardImage col-desk-3 col-tab-2 col-mob-1"
        :style="{ backgroundImage: `url(${imgurl})` }"
      ></aside>
      <hgroup class="CardHeader col-desk-4 col-tab-3 col-mob-3">
        <h4>{{ title }}</h4>
        <small>{{ subtitle }}</small>
      </hgroup>
      <main class="CardBody col-desk-5 col-desk-shift-0 col-tab-5 col-mob-4">
        <p>{{ text }}</p>
      </main>
    </div>
  </aside>
</template>

<script>
// @ is an alias to /src
export default {
  name: "Card",
  props: {
    bgimg: String,
    title: String,
    subtitle: String,
    text: String,
  },
  computed: {
    imgurl() {
      return require("@/assets/" + this.bgimg);
    },
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.Card {
  @include media(s1) {
    // @include padding-top(3);
    // @include padding-bottom(-1);
    @include margin-bottom(2);
  }

  p {
    @include media(s2) {
      @include type-setting(0);
    }
  }
  small {
    font-style: italic;
  }
}
.CardContent {
  background-color: $light_grey;
  text-align: left;
  // @include media(s2) {
  //   display: flex;
  //   flex-direction: row;
  //   flex-wrap: nowrap;
  // }
}
.CardHeader {
  @include padding-top(1);
  @include media(s5) {
    background-color: $light_grey;
  }
}
.CardBody {
  padding-top: $h2;
  @include media(s5) {
  }
}
.CardImage {
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  @include media(s4) {
  }
}
</style>
