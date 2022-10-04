<template>
  <nav id="top">
    <div class="color-bar"></div>
    <div class="inner">
      <div class="logo">
        <a v-if="currentRoute == 'index'" v-scroll-to="'#top'">
          <img src="/images/logo-black.svg" alt="" />
        </a>
        <nuxt-link v-if="currentRoute != 'index'" to="/">
          <img src="/images/logo-black.svg" alt="" />
        </nuxt-link>
      </div>
      <div
        class="burger"
        v-on:click="toggleMenu"
        v-bind:class="{ mobile_menu_open: mobileMenuOpen }"
      >
        <div></div>
        <div></div>
        <div></div>
      </div>
      <div
        class="mobile-menu-backdrop"
        v-bind:class="{ mobile_menu_open: mobileMenuOpen }"
        v-on:click="closeMenu"
      ></div>
      <ul class="routes" v-bind:class="{ mobile_menu_open: mobileMenuOpen }">
        <li class="mobile-logo"><img src="/images/logo-black.svg" alt="" /></li>
        <li v-on:click="closeMenu">
          <Link
            :classes="''"
            :link="{ url: '#our-vision', title: 'Our vision', target: '' }"
          />
        </li>
        <li v-on:click="closeMenu">
          <Link
            :classes="''"
            :link="{ url: '#our-mission', title: 'Our mission', target: '' }"
          />
        </li>
        <li v-on:click="closeMenu">
          <Link
            :classes="''"
            :link="{ url: '#contact-us', title: 'Contact us', target: '' }"
          />
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      currentRoute: null,
      mobileMenuOpen: false,
    };
  },

  mounted() {
    this.currentRoute = this.$route.name;
  },
  methods: {
    toggleMenu: function () {
      this.mobileMenuOpen = !this.mobileMenuOpen;
    },
    closeMenu: function () {
      this.mobileMenuOpen = false;
    },
  },
  watch: {
    $route(to, from) {
      this.currentRoute = to.name;
    },
  },
};
</script>

<style lang="scss" scoped>
nav {
  width: 100%;

  @include breakpoint(small) {
    position: fixed;
  }

  .color-bar {
    width: 100%;
    height: 20px;
    background: linear-gradient(
      90deg,
      rgba(156, 225, 255, 1) 0%,
      rgba(189, 65, 248, 1) 100%
    );

    @include breakpoint(small) {
      height: 5px;
    }
  }

  .inner {
    position: relative;
    @include content-max-width;
    @include gutter(padding-left);
    @include gutter(padding-right);
    padding-top: 40px;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;

    @include breakpoint(small) {
      padding-top: 10px;
      background-color: $white;
      padding-bottom: 10px;
    }

    .logo {
      width: 80px;
      cursor: pointer;

      @include breakpoint(small) {
        width: 25px;
      }

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }

    .burger {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 0;
      right: 0;
      width: 50px;
      height: 100%;
      cursor: pointer;

      &.mobile_menu_open {
        @include breakpoint(small) {
          div:first-of-type {
            opacity: 0;
          }
          div:last-of-type {
            opacity: 0;
          }
        }
      }

      @include breakpoint(small) {
        display: flex;
      }

      div {
        width: 25px;
        height: 2px;
        background-color: $black;
        margin: 2px 0;
        transition: 0.25s opacity;
      }
    }

    .mobile-menu-backdrop {
      display: none;
      position: absolute;
      top: 58px;
      left: 0;
      width: 100%;
      height: 100vh;
      height: calc(100vh - 58px);
      background-color: $black;
      opacity: 0;
      pointer-events: none;
      transition: 0.5s opacity;

      @include breakpoint(small) {
        display: block;
      }

      &.mobile_menu_open {
        @include breakpoint(small) {
          opacity: 0.85;
          pointer-events: all;
        }
      }
    }

    .routes {
      display: flex;

      @include breakpoint(small) {
        position: absolute;
        width: auto;
        height: calc(100vh - 5px);
        top: 5px;
        left: 0;
        transform: translateX(-100%);
        background-color: $white;
        flex-direction: column;
        padding: 0 50px;
        box-shadow: 24px -24px 24px -20px rgba(0, 0, 0, 0);
        transition: 0.5s transform, 0.5s box-shadow;
      }

      &.mobile_menu_open {
        @include breakpoint(small) {
          transform: translateX(0px);
          box-shadow: 0px 0px 30px -5px rgba(0, 0, 0, 0.21);
        }
      }

      li {
        font-size: 19px;
        margin-left: 3em;

        &:first-of-type {
          margin-left: 0;
        }

        &.mobile-logo {
          display: none;
          width: 60px;
          margin: 20px auto 20px;

          @include breakpoint(small) {
            display: block;
          }

          img {
            display: block;
            width: 100%;
            height: auto;
          }
        }

        @include breakpoint(small) {
          margin: 0;
          text-align: center;
          margin: 0.25em;
        }

        a {
          font-size: 19px;
          font-weight: bold;
          color: $black;
          text-transform: uppercase;
          text-decoration: none;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
