<template>
  <footer>
    <div class="bg-image">
      <img src="/images/footer-bg.jpg" alt="" />
    </div>
    <div class="inner">
      <div class="logo">
        <img src="/images/logo-white.svg" alt="" />
      </div>
      <div class="copyright">©2022 LIT THINKING</div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  position: relative;
  margin-top: -95px;
  pointer-events: none;

  .bg-image {
    img {
      display: block;
      width: 100%;
      height: auto;
      mix-blend-mode: darken;
    }
  }

  .inner {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 45px;
    @include content-max-width;
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    pointer-events: all;

    .logo {
      width: 80px;

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }

    .copyright {
      font-size: 19px;
      font-weight: bold;
      color: $black;
      text-transform: uppercase;
      text-decoration: none;
    }
  }
}
</style>
