<template>
  <div id="app">
    <div class="BrandToggle" role="logo" v-on:click="show = !show">
      <IcoLogo />
      <div class="closemenu" v-if="show">Close X</div>
    </div>
    <nav id="MainNav" role="navigation">
      <transition name="fade">
        <ul v-if="show">
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
import IcoLogo from "@/components/atoms/icons/IcoLogo.vue";

export default {
  data: () => {
    return {
      show: false,
    };
  },
  components: {
    IcoLogo,
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

.BrandToggle {
  position: fixed;
  top: $h2;
  right: 40%;
  left: 40%;
  z-index: 2;
  &:hover {
    cursor: pointer;
  }
  & path.sentir {
    fill: $white;
    stroke: none;
  }
  & path.hacer {
    stroke: $dark_grey;
    stroke-width: 0.5px;
  }
  & circle {
    fill: $secondary;
  }
  svg {
    width: $h4;
    height: $h4;
  }
  .closemenu {
    color: $white;
  }
  @include media(s4) {
    width: $h5;
    top: 0;
    height: $h4;
    right: 0;
    left: auto;
    padding-top: $h1;
  }
}
#MainNav {
  ul {
    position: fixed;
    top: 0;
    height: $h6;
    width: 100%;
    right: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    z-index: 1;
    background-color: $alpha_black;
    @include media(s1) {
      transform: translateY(0);
    }
    @include media(s2) {
      right: 0;
      padding: 0;
      height: $h6;
    }
    @include media(s4) {
      height: $h4;
    }
  }
  a {
    color: $white;
    padding: $h0;
    @include media(s1) {
      padding: $h0;
      background-color: $secondary;
      font-size: $h1;
    }
    @include media(s2) {
      display: block;
      padding: $h1;
      background-color: transparent;
      font-size: $h1;
      &:hover {
        background-color: $secondary;
      }
    }
    @include media(s4) {
      font-size: $h2;
    }
    &.router-link-exact-active {
      color: $tertiary;
      border-bottom: $h-1 solid $black_light;

      &:hover {
        cursor: pointer;
      }
    }
  }
  .fade-enter-active {
     animation: menu .1s 1;
  }
  .fade-leave-active {
     animation: menu .1s 1;
     animation-direction: alternate-reverse;
  }
  
}
</style>
