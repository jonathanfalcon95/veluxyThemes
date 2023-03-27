<template>
  <div class="banner-wrap">
    <div class="parallax">
      <v-parallax
        :src="imgAPI.showcase[0]"
        :height="1200"
        alt="banner"
      >
        <div class="parallax-props" />
      </v-parallax>
    </div>
    <div class="properties">
      <div class="title-banner">
        <img :src="logo" alt="logo" />
        <h1 variant="display-4">Veluxi</h1>
      </div>
      <h4 class="display-1">Vue.js Landing Page Collection</h4>
      <img src="/images/showcase/tech.png" alt="text" class="tech" />
      <div class="btn-area">
        <v-btn
          large
          class="prime"
          href="https://themeforest.net/item/veluxi-vue-js-landing-page-collection/26016174"
        >
          Buy Now
        </v-btn>
        <scrollactive v-if="loaded" tag="div" :offset="100">
          <v-btn
            href="#explore"
            class="white anchor-link scrollactive-item"
            large
          >
            Explore Demo
          </v-btn>
        </scrollactive>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.banner-wrap {
  position: relative;
  top: 0;
  left: 0;
  width: 100%;
  height: 960px;
  color: #ffffff;
  @include breakpoints-down(md) {
    background: url($imgAPI-showcase0) no-repeat top left;
    background-size: 1440px auto;
    height: 1000px;
  }
  @include breakpoints-down(xs) {
    height: 900px;
    background-position: -160px -160px;
  }
}
.parallax {
  top: 700px;
  left: 0;
  width: 100%;
  height: 100%;
  @include breakpoints-down(md) {
    display: none;
  }
  > div {
    height: 100%;
  }
  ::v-deep img {
    top: -200px;
    width: 100%;
    min-height: auto;
  }
}
.properties {
  position: absolute;
  top: 0;
  z-index: 10;
  padding: spacing(24, 8);
  width: 60%;
  h4 {
    font-family: 'Open Sans', sans-serif !important;
  }
  @include breakpoints-down(sm) {
    width: 100%;
    text-align: center;
  }
  @include breakpoints-down(xs) {
    padding: spacing(20, 2);
    h4 {
      font-size: 22px !important;
      line-height: 34px;
    }
  }
}
.title-banner {
  display: flex;
  align-items: flex-end;
  @include breakpoints-down(sm) {
    justify-content: center;
  }
  @include breakpoints-down(xs) {
    flex-direction: column;
    align-items: center;
  }
  h1 {
    font-family: 'Open Sans', sans-serif !important;
    margin-left: $spacing2;
    font-weight: 700;
    font-size: 4rem !important;
    @include breakpoints-down(xs) {
      font-size: 3rem !important;
    }
  }
  img {
    width: 60px;
    top: -28px;
    position: relative;
  }
}
.tech {
  height: 80px;
  margin-top: $spacing6;
  margin-bottm: $spacing4;
  @include breakpoints-down(xs) {
    width: 100%;
    height: auto;
  }
}
.btn-area {
  display: flex;
  margin-top: $spacing3;
  @include breakpoints-down(md) {
    justify-content: center;
  }
  @include breakpoints-down(xs) {
    flex-direction: column;
    align-items: center;
  }
  .v-btn {
    border-radius: 48px;
    font-weight: 500;
    font-size: 20px;
    width: 250px;
    padding: spacing(1, 2);
    @include breakpoints-up(sm) {
      margin-right: $spacing4;
    }
    @include breakpoints-down(xs) {
      margin-bottom: $spacing4;
    }
    &.prime {
      background: #fb5277 !important;
      color: #ffffff;
      @include shadow2;
      &:hover {
        background: #fd7c71;
      }
    }
    &.white {
      background: #ffffff;
      color: #fb5277;
      @include shadow2;
    }
  }
}
</style>

<script>
import imgAPI from '~/static/images/imgAPI'
import logo from '~/static/images/showcase/logo.png'

export default {
  data: () => ({
    imgAPI: imgAPI,
    logo: logo,
    loaded: false,
  }),
  mounted() {
    this.loaded = true
  }
}
</script>
