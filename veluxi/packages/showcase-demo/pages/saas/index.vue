<template>
  <theme-wrapper theme="violeta">
    <div class="main-wrap">
      <main-header />
      <div class="container-wrap">
        <section id="home">
          <banner />
        </section>
        <section>
          <company-logo />
        </section>
        <section class="space-top-short">
          <counter />
        </section>
        <section id="feature" class="space-top">
          <feature />
        </section>
        <section id="testimonials" class="space-bottom-testi">
          <testimonials />
        </section>
        <section id="pricing" class="space-top">
          <pricing-plan />
        </section>
        <section id="faq" class="space-top-short">
          <faq />
        </section>
        <section class="space-top-short space-bottom-short">
          <news-event />
        </section>
      </div>
      <section id="footer">
        <footer-with-deco />
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
.space-bottom-testi {
  @include breakpoints-up(md) {
    margin-bottom: section-margin($spacing1);
  }
}
.space-bottom-short {
  margin-bottom: section-margin($spacing1 * 0.5);
}
.space-top {
  margin-top: section-margin($spacing1);
  @include breakpoints-down(sm) {
    margin-top: section-margin(6px);
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
import Header from '~/components/saas/Header'
import Hidden from '~/components/saas/Hidden'
import PageNav from '~/components/saas/PageNav'
import Banner from '~/components/saas/Banner'
import CompanyLogo from '~/components/saas/CompanyLogo'
import Counter from '~/components/saas/Counter'
import Feature from '~/components/saas/Feature'
import Testimonials from '~/components/saas/Testimonials'
import PricingPlan from '~/components/saas/PricingPlan'
import Faq from '~/components/saas/Faq'
import NewsEvent from '~/components/saas/NewsEvent'
import FooterWithDeco from '~/components/saas/Footer/FooterWithDeco'
import Notification from '~/components/saas/Notification'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    ThemeWrapper,
    'main-header': Header,
    Banner,
    CompanyLogo,
    Counter,
    Feature,
    Testimonials,
    PricingPlan,
    Faq,
    NewsEvent,
    FooterWithDeco,
    PageNav,
    Hidden,
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
      title: brand.saas.name + ' - Home Page'
    }
  }
}
</script>
