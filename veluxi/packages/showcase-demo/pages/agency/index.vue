<template>
  <theme-wrapper theme="oceanBlue">
    <div class="main-wrap">
      <main-header />
      <div class="container-wrap">
        <square-parallax />
        <section id="home">
          <video-banner />
        </section>
        <section
          id="about"
          :class="[isTablet ? 'space-top-short' : 'space-top']"
        >
          <about />
        </section>
        <dots-parallax />      
        <section
          id="services"
          class="space-top"
        >
          <services />
        </section>
        <section
          id="our-expertise"
          :class="[isTablet ? 'space-top-short' : 'space-top']"
        >
          <expertise />
        </section>
        <section
          id="testimonials"
          :class="[isMobile ? 'space-top-short' : 'space-top']"
        >
          <testimonials />
        </section>
        <section id="case-studies">
          <case-studies />
        </section>
        <section class="space-top-short" id="call-to-action">
          <call-action />
        </section>
        <section class="space-top-short" id="address">
          <map-address />
        </section>
      </div>
      <hidden point="mdDown">
        <page-nav />
      </hidden>
      <main-footer />
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
.space-top {
  margin-top: section-margin($spacing1);
  @include breakpoints-down(md) {
    margin-top: section-margin(6px);
  }
  @include breakpoints-down(xs) {
    margin-top: section-margin($spacing1 * 0.5);
  }
}
.space-bottom-short {
  margin-bottom: section-margin($spacing1 * 0.5);
}
.space-top-short {
  margin-top: section-margin($spacing1 * 0.5);
}
.container-wrap {
  @include breakpoints-up(md) {
    margin-top: $spacing6;
  }
  section {
    position: relative;
  }
}
</style>

<script>
import Header from '~/components/agency/Header'
import SquareParallax from '~/components/agency/Parallax/Square'
import VideoBanner from '~/components/agency/VideoBanner'
import About from '~/components/agency/About'
import Services from '~/components/agency/Services'
import Expertise from '~/components/agency/Expertise'
import Testimonials from '~/components/agency/Testimonials'
import CaseStudies from '~/components/agency/CaseStudies'
import CallAction from '~/components/agency/CallAction'
import MapAddress from '~/components/agency/MapAddress'
import Footer from '~/components/agency/Footer'
import Hidden from '~/components/agency/Hidden'
import PageNav from '~/components/agency/PageNav'
import Notification from '~/components/agency/Notification'
import DotsParallax from '~/components/agency/Parallax/Dots'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    'main-header': Header,
    SquareParallax,
    DotsParallax,
    VideoBanner,
    About,
    Services,
    Expertise,
    Testimonials,
    CaseStudies,
    CallAction,
    MapAddress,
    PageNav,
    Hidden,
    Notification,
    ThemeWrapper,
    'main-footer': Footer
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
      title: brand.agency.name + ' - Home Page'
    }
  }
}
</script>
