<template>
  <theme-wrapper theme="cloud">
    <div class="main-wrap">
      <main-header />
      <div class="container-wrap">
        <section id="home">
          <banner />
        </section>
        <div id="promotion">
          <promotion />
        </div>
        <section id="feature">
          <feature />
        </section>
        <section id="benefit">
          <benefit />
        </section>
        <particles-canvas />
        <section id="pricing" class="space-top-short">
          <pricing-plan />
        </section>
        <section id="testimonials" class="space-top-short">
          <testimonials />
        </section>
      </div>
      <section id="footer" class="space-top">
        <footer-with-counter />
      </section>
      <hidden point="mdDown">
        <page-nav />
      </hidden>
      <hidden point="mdDown">
        <notification />
      </hidden>
    </div>
  </theme-wrapper>
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
  @include breakpoints-down(sm) {
    margin-bottom: section-margin(6px);
  }
}
.space-bottom-short {
  margin-bottom: section-margin($spacing1 * 0.5);
}
.space-top {
  margin-top: section-margin($spacing1);
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
import Header from '~/components/hosting/Header'
import Banner from '~/components/hosting/Banner'
import Promotion from '~/components/hosting/Promotion'
import Feature from '~/components/hosting/Feature'
import Benefit from '~/components/hosting/Benefit'
import PricingPlan from '~/components/hosting/PricingPlan'
import ParticlesCanvas from '~/components/hosting/ParticlesCanvas'
import Testimonials from '~/components/hosting/Testimonials'
import Hidden from '~/components/hosting/Hidden'
import PageNav from '~/components/hosting/PageNav'
import FooterWithCounter from '~/components/hosting/Footer/FooterWithCounter'
import Notification from '~/components/hosting/Notification'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    'main-header': Header,
    Banner,
    Promotion,
    Feature,
    Benefit,
    ParticlesCanvas,
    PricingPlan,
    Testimonials,
    FooterWithCounter,
    PageNav,
    Hidden,
    ThemeWrapper,
    Notification
  },
  computed: {
    isTablet() {
      return this.$mq === 'mdDown' || this.$mq === 'smDown' || this.$mq === 'xsDown' // eslint-disable-line
    },
    isMobile() {
      return this.$mq === 'smDown' || this.$mq === 'xsDown'
    }
  },
  head() {
    return {
      title: brand.hosting.name + ' - Home Page',
      script: [
        { src: '/scripts/vanta/three.r92.min.js' },
        { src: '/scripts/vanta/vanta.net.min.js' }
      ]
    }
  }
}
</script>
