<template>
  <div>
    <nav
      class="toggleButton"
      v-on:click="menu = !menu"
      v-bind:class="{ active: menu }"
    >
      <div class="open-menu" v-if="!menu"
      v-on:click="addBodyClass()">
        <IconMenu />
      </div>
      <div class="close-menu" v-if="menu"
      v-on:click="removeBodyClass()">
        X
      </div>
    </nav>

    <BrandLogo />

    <nav id="nav-container" role="navigation">
      <transition name="fade">
        <ul v-if="menu" v-on:click="menu = !menu; removeBodyClass()">
          <router-link to="/artwork">Artwork</router-link>
          <router-link to="/design">Prototyping</router-link>
          <router-link to="/info">TODH</router-link>
        </ul>
      </transition>
    </nav>
  </div>
</template>

<script>
import BrandLogo from "@/components/molecules/BrandLogo.vue";
import IconMenu from "@/components/atoms/icons/IconMenu.vue";

export default {
  data: () => {
    return {
      menu: false
    };
  },
  methods: {
    addBodyClass: function() {
        document.body.classList.add("overflowHidden");
    },
    removeBodyClass: function() {
        document.body.classList.remove("overflowHidden");
    },
  },
  components: {
    BrandLogo,
    IconMenu,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

.toggleButton {
  width: 60px;
  height: 60px;
  position: fixed;
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
  align-items: center;
  top: 0;
  right: 0;
  z-index: 11;
  @include media(s4) {
    width: $h5;
    top: 0;
    height: $h4;
    right: 0;
    left: auto;
  }
  &:hover {
    cursor: pointer;
  }
  .close-menu {
    color: $white;
  }
  .close-menu,
  .open-menu {
    padding: $h1;
    rect {
      fill: $white;
      stroke: $black;
      &:hover {
        stroke: $white;
        fill: $black;
      }
    }
  }
}
#nav-container {
  position: relative;
  ul {
    z-index: 10; //overwrite all content
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    background-color: $alpha_black;
    @include media(s1) {
      transform: translateY(0);
    }
  }
  a {
    padding: $h0 $h3;
    font-size: $h2;
    &:hover {
      transform: skewY(2deg);
      background-color: $alpha_black;
    }
    @include media(s2) {
      font-size: $h4;
      @include type-setting(2);
    }
    @include media(s4) {
    }
    &.router-link-exact-active {
      color: $tertiary;
      &:hover {
        cursor: pointer;
      }
    }
  }
  .fade-enter-active {
    animation: menu 0.1s 1;
  }
  .fade-leave-active {
    animation: menu 0.1s 1;
    animation-direction: alternate-reverse;
  }
}
</style>
