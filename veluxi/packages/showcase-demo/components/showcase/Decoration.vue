<template>
  <div class="parallax-wrap">
    <div v-if="loaded">
      <div class="banner-parallax-wrap">
        <parallax
          :speed-factor="0.15"
          :section-height="200"
          direction="down"
        >
          <div class="figure">
            <svg
              fill="#cccccc"
              width="845"
              height="1099"
              class="parallax-vertical parallax-dot"
            >
              <use xlink:href="/images/decoration/dot-deco.svg#dot" />
            </svg>
          </div>
        </parallax>
        <parallax
          :speed-factor="0.15"
          :section-height="400"
          direction="down"
        >
          <div class="figure">
            <div class="parallax-vertical parallax-circle">
              <img src="/images/showcase/deco-circle.svg" alt="deco" />
            </div>
          </div>
        </parallax>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import './parallax-style.scss';
</style>

<script>
import Parallax from 'vue-parallaxy'
export default {
  components: {
    Parallax
  },
  data() {
    return {
      loaded: false
    }
  },
  mounted() {
    this.loaded = true
  }
}
</script>
