<template>
  <div id="app">
    <div class="togglemenu" 
    v-on:click="show = !show; isActive = true"
    v-bind:class="{ active : isActive }"
    >
      <div class="open-menu" v-if="!show">|||</div>
      <div class="close-menu" v-if="show">X</div>
    </div>
    <BrandLogo />
    <nav id="nav-container" role="navigation">
      <transition name="fade">
        <ul v-if="show" v-on:click="show = !show; isActive = false">
          <router-link to="/artwork">Artwork</router-link>
          <router-link to="/design">Prototyping</router-link>
          <router-link to="/info">TODH</router-link>
        </ul>
      </transition>
    </nav>
    <router-view />
  </div>
</template>

<script>
import BrandLogo from "@/components/molecules/BrandLogo.vue";

export default {
  data: () => {
    return {
      show: false,
      isActive: false
    };
  },
  components: {
    BrandLogo,
  },
};
</script>

<style lang="scss">
@import "@/styles/main.scss";

#app {
  font-family: $primary_font;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.togglemenu {
  width: 60px;
  height: 60px;
  position: fixed;
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
  align-items: center;
  top: 0;
  right: 0;
  z-index: 9;
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
  .close-menu, .open-menu {
    padding: $h1;
  }
}

#nav-container {
  ul {
    position: fixed;
    top: 0;
    @include padding-top(3);
    height: 100vh;
    width: 100%;
    right: 0;
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
    align-items: center;
    background-color: $alpha_black;
    @include media(s1) {
      transform: translateY(0);
    }
  }
  a {
    color: $white;
    padding: $h0;
    font-size: $h2;
    &:hover {
    background-color: $alpha_black;
    }
    @include margin-top(1);
    @include media(s2) {
      padding: $h1;
    }
    @include media(s4) {
      font-size: $h2;
    }
    &.router-link-exact-active {
      color: $tertiary;
      border: 1px solid $white;

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
