<template>
  <theme-wrapper theme="smart">
    <div class="main-wrap">
      <header-main />
      <div class="container-wrap">
        <section id="home">
          <banner />
        </section>
        <section id="feature" class="space-top">
          <feature />
        </section>
        <section id="popular" class="space-top-short">
          <popular-course />
        </section>
        <section id="explore">
          <explore />
        </section>
        <div id="about">
          <about />
        </div>
        <section id="testimonials" class="space-top">
          <testimonials />
        </section>
        <section id="blog" class="space-top-short">
          <blog />
        </section>
        <section id="subscribe" class="space-top-short">
          <subscribe-form />
        </section>
        <footer-main />
      </div>
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
  .theme--dark & {
    background-color: $dark-background-default;
  }
  .theme--light & {
    background-color: $light-background-paper;
  }
}
.space-bottom {
  padding-bottom: section-margin($spacing1);
  @include breakpoints-down(md) {
    padding-bottom: section-margin(6px);
  }
}
.space-bottom-short {
  padding-bottom: section-margin($spacing1 * 0.5);
}
.space-top {
  padding-top: section-margin($spacing1);
  @include breakpoints-down(md) {
    padding-top: section-margin(6px);
  }
  @include breakpoints-down(xs) {
    padding-top: section-margin(3px);
  }
}
.space-top-short {
  padding-top: section-margin($spacing1 * 0.5);
}
.container-wrap {
  > section {
    position: relative;
  }
}
</style>

<script>
import Header from '~/components/education/Header'
import Banner from '~/components/education/Banner'
import Feature from '~/components/education/Feature'
import PopularCourse from '~/components/education/PopularCourse'
import Explore from '~/components/education/Explore'
import About from '~/components/education/About'
import Testimonials from '~/components/education/Testimonials'
import Blog from '~/components/education/Blog'
import SubscribeForm from '~/components/education/SubscribeForm'
import Footer from '~/components/education/Footer'
import Hidden from '~/components/education/Hidden'
import PageNav from '~/components/education/PageNav'
import Notification from '~/components/education/Notification'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    'header-main': Header,
    Banner,
    Feature,
    PopularCourse,
    Explore,
    About,
    Testimonials,
    Blog,
    SubscribeForm,
    'footer-main': Footer,
    PageNav,
    Hidden,
    ThemeWrapper,
    Notification
  },
  head() {
    return {
      title: brand.education.name + ' - Home Page'
    }
  },
  computed: {
    isTablet() {
      const mdDown = this.$store.state.breakpoints.mdDown
      return mdDown.indexOf(this.$mq) > -1
    },
    isMobile() {
      const xsDown = this.$store.state.breakpoints.xsDown
      return xsDown.indexOf(this.$mq) > -1
    }
  }
}
</script>
