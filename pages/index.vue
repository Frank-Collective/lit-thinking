<template>
  <div>
    <header>
      <div class="spacer"></div>
      <div class="inner">
        <h1>Get LIT for Life</h1>
        <div class="copy">
          <p>
            LIT THINKING is an industry thought leader determined to develop
            lighting solutions that deliver efficacy, affordability, security,
            sustainability, and aesthetics so we can all lead the healthy,
            fulfilling lives we want to lead.
          </p>
        </div>
      </div>
      <div class="spacer"></div>
    </header>
    <div id="our-vision" class="our-vision">
      <div class="inner">
        <h3>THE LIT THINKING BRAND VISION:</h3>
        <p>
          To re-establish and re-energize society’s desire to collaborate,
          socialize, and live their lives in the most effective, meaningful, and
          fulfilling ways possible - especially when indoors & in-person.
        </p>
      </div>
      <div class="spacer"></div>
    </div>
    <div id="our-mission" class="our-mission">
      <div class="inner">
        <h3>THE LIT THINKING BRAND MISSION:</h3>
        <p>
          To develop & deliver solutions that help guarantee interior spaces can
          be lit in a way that makes life as healthy & fulfilling as possible -
          especially in regards to safety, security, sustainability, efficacy,
          affordability, and aesthetics.
        </p>
      </div>
      <div class="spacer"></div>
    </div>
    <div id="contact-us" class="contact-us">
      <div class="inner">
        <h3>THE LIT THINKING BRAND MISSION:</h3>
        <p>
          John Rajchert<br />
          CEO<br />
          <a href="mailto:John@litthinking.com">John@litthinking.com</a><br />
          <a href="tel:555.555.1234">555.555.1234</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Home",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  .spacer {
    height: 11.5vw;
    max-height: 157px;
    min-height: 80px;
  }

  .inner {
    @include content-max-width;
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    justify-content: space-between;

    @include breakpoint(small) {
      flex-direction: column;
    }

    h1 {
      width: 55%;
      flex-shrink: 0;
      // text-align: center;
      background: linear-gradient(
        180deg,
        rgba(156, 225, 255, 1) 8%,
        rgba(186, 69, 255, 1) 74%,
        rgba(242, 5, 123, 1) 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;

      @include breakpoint(small) {
        width: auto;
      }
    }

    .copy {
      width: 38%;
      flex-shrink: 0;
      margin-top: 0.5em;

      @include breakpoint(small) {
        width: auto;
      }
    }
  }
}

.our-vision {
  @include gutter(padding-left);
  @include gutter(padding-right);

  @include breakpoint(small) {
    padding: 0;
  }

  .inner {
    max-width: 1200px;
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    p {
      @include body-copy-large;
    }
  }

  .spacer {
    height: 3.5vw;
    max-height: 48px;
  }
}

.our-mission {
  @include gutter(padding-left);
  @include gutter(padding-right);

  @include breakpoint(small) {
    padding: 0;
  }

  .inner {
    max-width: 1200px;
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    p {
      @include body-copy-large;
    }
  }

  .spacer {
    height: 3.5vw;
    max-height: 48px;
  }
}

.contact-us {
  @include gutter(padding-left);
  @include gutter(padding-right);

  @include breakpoint(small) {
    padding: 0;
  }

  .inner {
    max-width: 1200px;
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    p {
      @include body-copy-large;
    }
  }

  .spacer {
    height: 3.5vw;
    max-height: 48px;
  }
}
</style>
