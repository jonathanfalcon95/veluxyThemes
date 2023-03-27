<template>
  <div>
    <gradient-deco />
    <theme-wrapper theme="money">
      <div class="main-wrap">
        <main-header />
        <div class="container-wrap">
          <section id="home">
            <banner />
          </section>
          <section id="promotions">
            <promotion />
          </section>
          <section id="feature" class="space-top-short-md-down">
            <feature />
          </section>
          <section id="benefit" class="space-top-short">
            <benefit />
          </section>
          <section id="testimonials" class="space-top">
            <testimonials />
          </section>
          <section id="faq" class="space-top">
            <faq />
          </section>
        </div>
        <footer-with-counter />
        <hidden point="mdDown">
          <page-nav />
        </hidden>
        <hidden point="mdDown">
          <notification />
        </hidden>
        <script src="/scripts/particles.min.js"></script>
        <script src="/scripts/stats.min.js"></script>
      </div>
    </theme-wrapper>
  </div>
</template>

<style scoped lang="scss">
@import '~/assets/styles';

@function section-margin($margin) {
  @return $margin * 20;
}
.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  @include palette-text-primary;
  .theme--dark & {
    background-color: $dark-background-default;
  }
  .theme--light & {
    background-color: $light-background-paper;
  }
}
.space-bottom {
  margin-bottom: section-margin($spacing1);
  @include breakpoints-down(md) {
    margin-bottom: section-margin(6px);
  }
}
.space-top {
  margin-top: section-margin($spacing1);
  @include breakpoints-down(md) {
    margin-top: section-margin(6px);
  }
}
.space-bottom-short {
  margin-bottom: section-margin($spacing1 * 0.5);
}
.space-top-short-md-down {
  @include breakpoints-between(md, lg) {
    margin-top: section-margin($spacing1 * 0.5);
  }
}
.space-top-short {
  margin-top: section-margin($spacing1 * 0.5);
}
.container-wrap {
  margin-top: -40px;
  > section {
    position: relative;
  }
}
</style>

<script>
import GradientDeco from '~/components/crypto/GradientDeco'
import Header from '~/components/crypto/Header'
import Banner from '~/components/crypto/Banner'
import Promotion from '~/components/crypto/Promotion'
import Feature from '~/components/crypto/Feature'
import Benefit from '~/components/crypto/Benefit'
import Testimonials from '~/components/crypto/Testimonials'
import Faq from '~/components/crypto/Faq'
import FooterWithCounter from '~/components/crypto/Footer/FooterWithCounter'
import Hidden from '~/components/crypto/Hidden'
import PageNav from '~/components/crypto/PageNav'
import Notification from '~/components/crypto/Notification'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    GradientDeco,
    'main-header': Header,
    Banner,
    Promotion,
    Feature,
    Benefit,
    Testimonials,
    Faq,
    FooterWithCounter,
    PageNav,
    Hidden,
    Notification,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.crypto.name + ' - Home Page',
      script: [
        { src: '/scripts/particles.min.js' },
        { src: '/scripts/stats.min.js' }
      ]
    }
  }
}
</script>
