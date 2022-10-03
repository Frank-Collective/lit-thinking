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
      <ul class="routes">
        <li>
          <Link
            :classes="''"
            :link="{ url: '#our-vision', title: 'Our vision', target: '' }"
          />
        </li>
        <li>
          <Link
            :classes="''"
            :link="{ url: '#our-mission', title: 'Our mission', target: '' }"
          />
        </li>
        <li>
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
    return { currentRoute: null };
  },

  mounted() {
    this.currentRoute = this.$route.name;
  },
  methods: {},
  watch: {
    $route(to, from) {
      this.currentRoute = to.name;
    },
  },
};
</script>

<style lang="scss" scoped>
nav {
  .color-bar {
    width: 100%;
    height: 20px;
    background: linear-gradient(
      90deg,
      rgba(156, 225, 255, 1) 0%,
      rgba(189, 65, 248, 1) 100%
    );
  }

  .inner {
    @include content-max-width;
    @include gutter(padding-left);
    @include gutter(padding-right);
    padding-top: 40px;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;

    .logo {
      width: 80px;
      cursor: pointer;

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }

    .routes {
      display: flex;

      li {
        font-size: 19px;
        margin-left: 3em;

        &:first-of-type {
          margin-left: 0;
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
