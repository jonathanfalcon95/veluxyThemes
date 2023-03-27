<template>
  <theme-wrapper theme="fresh">
    <div class="main-wrap">
      <main-header />
      <div class="container-wrap">
        <oval-top />
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
          id="facility"
          class="space-top"
        >
          <facilities />
        </section>
        <section
          id="our-expertise"
          :class="[isTablet ? 'space-top-short' : 'space-top']"
        >
          <expertise />
        </section>
        <section
          id="ask-doctors"
          :class="[isMobile ? 'space-top-short' : 'space-top']"
        >
          <ask-doctors />
        </section>
        <section
          id="testimonials"
          class="space-top-short"
        >
          <testimonials />
        </section>
        <section class="space-top-short" id="call-to-action">
          <call-action />
        </section>
        <section class="space-top-short" id="clinics">
          <clinics />
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
import Header from '~/components/medical/Header'
import VideoBanner from '~/components/medical/VideoBanner'
import About from '~/components/medical/About'
import Facilities from '~/components/medical/Facilities'
import Expertise from '~/components/medical/Expertise'
import Testimonials from '~/components/medical/Testimonials'
import AskDoctors from '~/components/medical/AskDoctors'
import CallAction from '~/components/medical/CallAction'
import Clinics from '~/components/medical/Clinics'
import Footer from '~/components/medical/Footer'
import Hidden from '~/components/medical/Hidden'
import PageNav from '~/components/medical/PageNav'
import Notification from '~/components/medical/Notification'
import DotsParallax from '~/components/medical/Parallax/Dots'
import OvalTop from '~/components/medical/Parallax/OvalTop'
import ThemeWrapper from '~/components/ThemeWrapper'  
import brand from '~/static/text/brand'

export default {
  components: {
    'main-header': Header,
    DotsParallax,
    OvalTop,
    VideoBanner,
    About,
    Facilities,
    Expertise,
    Testimonials,
    AskDoctors,
    CallAction,
    Clinics,
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
      title: brand.medical.name + ' - Home Page'
    }
  }
}
</script>
